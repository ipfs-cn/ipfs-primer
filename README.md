# IPFS入门指南

本入门指南包含一系列教程，解释了IPFS、Merkle树以及去中心化网络。它以 [Gitbook](https://www.gitbook.com/about) 的形式编写和维护，因此人们可以通过多种格式阅读它。

本书的原版 GitHub 仓库位于 https://github.com/ipfs-shipyard/ipfs-primer。  
中文版翻译的 GitHub 仓库位于 https://github.com/ipfs-cn/ipfs-primer。


# 获取帮助

在这些教程中，如果你有任何问题，欢迎在[IPFS论坛](https://discuss.ipfs.io) 或 [chat.freenode.net 上的 #ipfs 频道](irc://chat.freenode.net/%23ipfs) 提问。我们拥有一个庞大、活跃的社区，这些场所是我们主要寻求支持和提供帮助的地方。

## 教程

本指南包含关于

 1. [下载和安装IPFS](install-ipfs/README.md)
 2. [IPFS上的文件](files-on-ipfs/README.md)
 3. [联网 - 加入分布式网络](going-online/README.md)
 4. [与传统 (HTTP) 网络的交互](classical-web/README.md)
 5. [访问和分发 IPFS 内容的众多方式](avenues-for-access/README.md)
 6. [在永久网络上进行更改](publishing-changes/README.md)
 7. [Merkle 树和 IPFS DAG](ipfs-dag/README.md)
 8. [IPFS 上的动态内容](dynamic-content/README.md)

 完整的教程列表，详情请查看[目录](SUMMARY.md)。

## 概念

* 加密哈希和内容寻址
* 身份验证图
* 将文件转换为树结构
* 将任何数据转换为树结构
* 在 DHT 上发布哈希
* 从对等网络 (P2P) 获取数据
* 不变性：“更改”作为树结构的 _添加_
* CRDTs
* Pubsub
* 经过身份验证的流（使用pubsub）

## 格式

每个教程是一组 *课程*，所有这些课程都使用受 [Railsbridge课程](http://curriculum.railsbridge.org/intro-to-rails/) 启发的格式。每节课都声明一组 *目标*，或 [学习目标](http://edglossary.org/learning-objectives/)，然后列出 *步骤* ，或活动，最后提供 *解释*，回顾你所做的内容，并将这些活动与课程的目标联系起来。每节课的格式如下：

![Railsbridge课程格式示例](/images/railsbridge-format.png)

## 对贡献者的说明

为了简要说明学习目标（在本书中我们称之为 _目标_ ），请阅读 UC Denver 的 [评估与教学对齐教程](http://www.ucdenver.edu/faculty_staff/faculty/center-for-faculty-development/Documents/tutorials/Assessment/module3/index.htm)。尝试使你的学习目标 [具体、可观察且可衡量](http://www.ucdenver.edu/faculty_staff/faculty/center-for-faculty-development/Documents/tutorials/Assessment/module3/good_objectives.htm)，并遵循他们使用 [认知过程级别的动词表工作表](http://www.ucdenver.edu/faculty_staff/faculty/center-for-faculty-development/Documents/tutorials/Assessment/documents/examples_verbs_cognitive_process_level.pdf) 中的动词列表来帮助你选择课程学习目标的可观察行为的建议。

要一次性构建书籍的HTML、PDF、epub和mobi版本，请运行 `./build-book.sh`

# 贡献者

本入门指南由 @flyingzumwalt 创建。这些教程的内容最初是从 IPFS 网站上的第一代文档和 IPFS 示例（现已归档）的 git 仓库中提取的。它们现在已迁移到 [docs.ipfs.io](https://docs.ipfs.io)上，特别是 ["使用思路和示例"](https://docs.ipfs.io/concepts/usage-ideas-examples/) 部分。

对这些原始文档做出贡献的人包括：

* @whyrusleeping
* @jbenet
* @lgierth
* @lynnandtonic
* @wraithgar
* @adambrault
* @donothesitate
* @djdv

以及原始示例仓库的一长串 [贡献者](https://github.com/ipfs/examples/network/members)。