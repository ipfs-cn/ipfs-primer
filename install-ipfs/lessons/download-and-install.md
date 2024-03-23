# 课程：下载并安装IPFS

## 目标

完成本课程后，你将能够：
* 下载 IPFS 并将其安装在你的操作系统上
* 显示你正在使用的 IPFS 版本
* 获取 ipfs 二进制文件支持的命令列表


## 步骤

### 步骤 1：下载预构建的 IPFS 包
访问 IPFS 安装页面 https://docs.ipfs.io/guides/guides/install/ 并根据你当前操作系统下载预构建的 ipfs 二进制文件。

**为什么安装页面会提到 "Go IPFS"？** IPFS 协议有多种实现。IPFS 核心团队维护了 Golang 和 Javascript 的实现。这些通常被称为 [go-ipfs](https://github.com/ipfs/go-ipfs) 和  [js-ipfs](https://github.com/ipfs/js-ipfs)。官方二进制文件是从 Go 实现构建的。

### 步骤 2：解压预构建包

Mac OSX 和 Linux 的二进制文件采用 gzipped tar 格式(`.tar.gz`)。Windows 的二进制文件使用 zip 压缩。更多信息请参考官方文档 https://docs.ipfs.io/guides/guides/install/ 中 _Installing from a Prebuilt Package_ 一章。

解压后将创建一个名为 go-ipfs 的目录。
```bash
LICENSE		README.md	build-log	install.sh ipfs
```

名为 `ipfs` 的文件是你的可执行ipfs二进制文件。

### 步骤 3：将 IPFS 二进制文件安装在你的可执行路径上

要安装二进制文件，你需要做的就是将 `ipfs` 二进制文件放在你环境变量 PATH 里的某个地方。

**关于权限的注意事项**：无论你使用哪种方法安装，都需要你有必要的权限。在 Mac OSX 或 Linux 上，使用 [sudo](https://www.sudo.ws/) 切换至 root 用户

如果你使用的是 Mac OSX 或 Linux，你可以通过运行提供的安装脚本来使用

```bash
cd go-ipfs
sudo ./install.sh
```

如果此命令的输出提示无法写入文件，请参考上面关于权限的注意事项

### 步骤 4：显示IPFS版本

当你遇到问题时知道你正在使用的 ipfs 版本很重要。要找出当前版本，请运行

```sh
$ ipfs version
```

### 步骤 5：显示 IPFS 帮助页面和命令列表

如果你想了解或者记住更多的 ipfs 命令，请运行：
```sh
$ ipfs help
```

得到的输出类似于：

```sh
USAGE
  ipfs  - Global p2p merkle-dag filesystem.

SUBCOMMANDS
  BASIC COMMANDS
    init          Initialize local IPFS configuration
...
```

要获取 ipfs 支持的所有命令的列表，请运行
```sh
$ ipfs commands
```

## 下一步

接下来，[初始化你的IPFS仓库](initialize-repository.md)