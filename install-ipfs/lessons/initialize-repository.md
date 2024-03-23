# 课程：初始化你的IPFS仓库

## 目标

完成本课程后，你将能够：

* 初始化本地的 ipfs 仓库
* 找到 IPFS 存储库的位置
* 打开 IPFS 配置文件

## 步骤

### 步骤1：初始化仓库

使用 `ipfs init` 命令来初始化仓库。这将为当前登录的用户生成一个本地的 ipfs 仓库。它还会生成一个加密密钥对，用来对你在 ipfs 节点上创建的内容和消息进行加密签名。

```sh
$ ipfs init
initializing ipfs node at /Users/jbenet/.go-ipfs
generating 2048-bit RSA keypair...done
peer identity: Qmcpo2iLBikrdf1d6QU6vXuNb6P7hwrbNPW9kLAH8eG67z
to get started, enter:

  ipfs cat /ipfs/QmYwAPJzv5CZsnA625s3Xf2nemtYgPpHdWEz79ojWnPbdG/readme

```

<div class="alert alert-info">
<b>注意：</b>如果你的机器上已经初始化过 ipfs，你将收到类似这样的错误信息：

<pre>
initializing ipfs node at /Users/sally/.ipfs
Error: ipfs configuration file already exists!
Reinitializing would overwrite your keys.
</pre>

这是正常的。这意味着你已经完成了这一步。你可以安全地继续到步骤 2。
</div>

### 步骤2：使用IPFS探索安装后的文档

<div class="alert alert-info">
如果你安装了不同版本的ipfs，你可能得到了稍有不同的路径。这两个路径对于本教程都是有效的。在运行 `ipfs init` 命令时得到的路径即是存储你数据的地方
</div>

当运行`ipfs init`时，它会输出一个提示告诉你如何开始：
```bash
to get started, enter:

  ipfs cat /ipfs/QmYwAPJzv5CZsnA625s3Xf2nemtYgPpHdWEz79ojWnPbdG/readme

```

`ipfs cat` 命令告诉 ipfs 根据你提供的路径读取匹配的内容。如果内容在本地不可用，ipfs 将尝试在点对点（P2P）网络上寻找它。

要运行这些命令，必须首先启动 ipfs 的守护进程。请使用 `ipfs daemon &` 在后台启动 ipfs 守护进程。

```sh
$ ipfs daemon &
```

运行`ipfs cat`命令和初始化消息中得到的路径：

```sh
$ ipfs cat /ipfs/QmYwAPJzv5CZsnA625s3Xf2nemtYgPpHdWEz79ojWnPbdG/readme
```

你应该看到类似这样的内容：

```
Hello and Welcome to IPFS!

██╗██████╗ ███████╗███████╗
██║██╔══██╗██╔════╝██╔════╝
██║██████╔╝█████╗  ███████╗
██║██╔═══╝ ██╔══╝  ╚════██║
██║██║     ██║     ███████║
╚═╝╚═╝     ╚═╝     ╚══════╝

If you're seeing this, you have successfully installed
IPFS and are now interfacing with the ipfs merkledag!

 -------------------------------------------------------
| Warning:                                              |
|   This is alpha software. use at your own discretion! |
|   Much is missing or lacking polish. There are bugs.  |
|   Not yet secure. Read the security notes for more.   |
 -------------------------------------------------------

Check out some of the other files in this directory:

  ./about
  ./help
  ./quick-start     <-- usage examples
  ./readme          <-- this file
  ./security-notes

```
你可以接着探索其中的其他对象。例如，查看 `security-notes`:

```sh
ipfs cat /ipfs/QmYwAPJzv5CZsnA625s3Xf2nemtYgPpHdWEz79ojWnPbdG/security-notes
```

### 第3步：定位IPFS在你的机器上存储仓库内容的位置

`ipfs` 将其本地对象仓库存储在 `~/.ipfs`

```sh
$ ls ~/.ipfs
```

该目录的内容如下所示：

```sh
blocks		config		datastore	version
```
你本地 IPFS 仓库上的所有内容都存储在这个目录中。例如，上面的 readme 文件就存储在这里，连同它链接到的其他文件一起。你可以运行一个 grep 命令来找出确切的位置。

### 第4步：打开IPFS配置文件

你的 ipfs 仓库的配置是一个通常存储在 `~/.ipfs/config` 的json文件。要查看当前配置，运行：

```sh
$ ipfs config show
```
这个配置文件中的一个有用的细节是在 `Datastore.Path`。这告诉你 ipfs 仓库的内容被存储在哪里。正如第3步中所看到的，一般默认是`~/.ipfs`

## 下一步

接下来，继续进行 [IPFS上的文件](../../files-on-ipfs)教程。