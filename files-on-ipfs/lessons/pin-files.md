# 课程：确保你 IPFS 仓库中的文件持久化储存

## 目标

本章涵盖了在 IPFS 仓库中关于 `pinning` 和垃圾收集器删除文件的相关知识。`pinning` 是 IPFS 中一个非常重要的概念。它是一种可以让 IPFS 始终保存某份文件不被垃圾收集删除的机制

完成这节课后，你将能够：
* 告诉 IPFS 在你的本地 IPFS 仓库中保留特定文件
* 使用垃圾收集器从你的本地 IPFS 仓库中清理不需要的文件

## 步骤

### 步骤 1：创建你将要添加并固定的文件

创建一个名为 `foo.txt` 的文件，并在其中输入文本 "ipfs rocks"。这是在命令行中执行此操作的一个简单方法：

```sh
$ echo "ipfs rocks" > foo.txt
```

### 步骤 2：将文件添加到IPFS

```sh
$ ipfs add foo.txt
added QmRTV3h1jLcACW4FRfdisokkQAk4E4qDhUzGpgdrd4JAFy foo.txt
```

### 步骤 3：列出固定到本地存储的对象

```sh
$ ipfs pin ls --type=all
QmRTV3h1jLcACW4FRfdisokkQAk4E4qDhUzGpgdrd4JAFy recursive
QmY5heUM5qgRubMDD1og9fhCPA6QdkMp3QCwd4s7gJsyE7 indirect
```

上面列出的第一个对象是 `foo.txt` 文件。通过 `ipfs add` 添加的对象默认会被递归固定。

在 ipfs 中，有三种类型的固定：

a) 直接固定，只固定单个块，与之相关的其他块无关；

b) 递归固定，固定给定的块及其所有子块；

c) 间接固定，当给定块的父块被递归固定时的结果。

### 步骤 4：取消固定一个对象

如果想取消固定 `foo.txt` 请使用 `rm` 子命令：

```sh
$ ipfs pin rm QmRTV3h1jLcACW4FRfdisokkQAk4E4qDhUzGpgdrd4JAFy
unpinned QmRTV3h1jLcACW4FRfdisokkQAk4E4qDhUzGpgdrd4JAFy
```

现在验证它不再存在：

```sh
$ ipfs cat QmRTV3h1jLcACW4FRfdisokkQAk4E4qDhUzGpgdrd4JAFy
ipfs rocks
```

等等，它似乎还在那里！好吧，你必须运行垃圾回收器然后再次验证：

```sh
$ ipfs repo gc
removed QmRTV3h1jLcACW4FRfdisokkQAk4E4qDhUzGpgdrd4JAFy
$ ipfs cat QmRTV3h1jLcACW4FRfdisokkQAk4E4qDhUzGpgdrd4JAFy
Error: merkledag: not found
```

IPFS 有一个较为积极的缓存机制，即在你对某个文件执行任意操作后会短时间内保留该对象，但这些对象会被定期地垃圾回收。

不过被固定的文件对象并不会被垃圾收集器删除，你可以通过以下命令来验证：

```sh
$ ipfs add foo.txt
added QmRTV3h1jLcACW4FRfdisokkQAk4E4qDhUzGpgdrd4JAFy

foo.txt
$ ipfs repo gc
$ ipfs cat QmRTV3h1jLcACW4FRfdisokkQAk4E4qDhUzGpgdrd4JAFy
ipfs rocks
```

## 解释

IPFS 节点将它们存储的数据视为缓存，这意味着不能保证数据将继续被存储。我们通过 `pin` 一个 CID （哈希）告诉IPFS节点该数据很重要，不应该被抛弃。实际使用中应该固定任何你认为重要的内容，以确保内容长期被保存。由于对别人来说重要的数据可能对你来说并不重要，`pin` 让你可以间接的控制你的磁盘空间和希望保留的文件。

## 下一步
接下来请阅读 [上线](../../going-online/README.md) 章节。
