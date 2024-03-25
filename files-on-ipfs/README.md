# 教程：IPFS上的文件
这些课程已在以下 go-ipfs 版本测试通过：
0.5.0，
0.9.0

_请在 github 上更新此文件，以反映已经测试过的任何其他版本。_

## 先决条件

- 你应该对命令行有一定的熟悉度。
- 已经安装了 `ipfs` - [上一个教程](../install-ipfs) 中有安装说明

## 学习目标
这些课程将教你如何：
* 向你的本地 IPFS 节点添加文件
* 从你的本地 IPFS 节点读取文件
* 列出你的 IPFS 节点中的文件
* 通过 _固定（pinning）_ 功能来告诉 IPFS 保留一个文件

## 关键概念
* IPFS 与常规文件系统之间的区别
* 通过哈希值来识别文件
* IPFS 的垃圾回收
* 在 IPFS 节点上固定文件

## 课程

1. [课程：向 IPFS 中添加内容并检索](/files-on-ipfs/lessons/add-and-retrieve-file-content.md)
2. [课程：在 IPFS 通过文件夹来保存文件名信息](/files-on-ipfs/lessons/wrap-directories-around-content.md)
3. [课程：固定 - 告诉 IPFS 保留文件](/files-on-ipfs/lessons/pin-files.md)

## 下一步

当了解如何向 IPFS 添加文件并检索后，下一步就是在 P2P 网络上分享这些文件了，详情参考文章： [教程：上线 - 加入分布式网络](/going-online/README.md)

如果你想知道在分享这些文件后如何更新它们，请参见 [教程：在永久网络上发布更改](/publishing-changes/README.md)。

如果想了解如何通过传统的 HTTP 方式访问这些文件，请转到 [教程：与经典(HTTP)网络互动](/classical-web/README.md)。

如果想更多地了解 IPFS 在内部如何使用 Merkle DAGs 来存储这些内容，请前往 [教程：Merkle树和IPFS DAG](/ipfs-dag/README.md)。
