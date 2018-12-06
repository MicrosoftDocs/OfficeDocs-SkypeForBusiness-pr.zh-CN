---
title: Lync Server 2013：部署持久聊天服务器
TOCTitle: 部署持久聊天服务器
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205357(v=OCS.15)
ms:contentKeyID: 49314524
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中部署持久聊天服务器

 

_**上一次修改主题：** 2014-03-31_

Lync Server 2013持久聊天服务器是 Lync Server 2013 基础结构的一部分。

部署 持久聊天服务器需要您：

  - 使用 拓扑生成器定义或导入拓扑和要部署的组件，然后发布它们。

  - 使环境做好部署 持久聊天服务器组件的环境。

  - 安装和配置要部署的 持久聊天服务器组件。

持久聊天服务器可作为单独的池（不与 企业版前端服务器并置）与 Lync Server 2013企业版 一起提供。在 企业版 池中， 持久聊天服务器需要 SQL Server后端服务器 才能存储聊天室内容和其他相关元数据。建议您在专用 SQL Server后端服务器 上安装 **PersistentChatStore**，尽管支持在相同的 SQL Server 上收集 Lync Server 2013后端服务器 和 **PersistentChatStore**。

持久聊天服务器还可以与 Lync Server 2013标准版一起部署。 在这种情况下，可在 标准版 计算机上收集 **PersistentChatService**前端服务器，并可将 **PersistentChatStore**后端服务器部署到本地 SQL Server Express 实例上。

有关支持的并置配置的详细信息，请参阅[Lync Server 2013 中支持的服务器并置](lync-server-2013-supported-server-collocation.md)。

> [!IMPORTANT]
> 我们不支持 持久聊天服务器标准版 的高可用性。性能和规模将受到限制。另外，我们仅支持新的 持久聊天服务器Standard Edition Server。不支持将 Lync Server 2010、 群聊服务器 升级到 Lync Server 2013持久聊天服务器标准版。


如果您的组织需要合规性支持，则可以在 持久聊天服务器前端服务器上安装 持久聊天服务器合规性服务。合规性需要一个单独的数据库。

每台服务器至少需要一台安装了 Lync Server 2013 的服务器和一台安装了 SQL Server 数据库软件的服务器。

使用 拓扑生成器将 持久聊天服务器添加到 Lync Server 2013 部署。可以使用 拓扑生成器选择添加一个或多个 持久聊天服务器池。按照部署任何池的相同部署说明部署多个 持久聊天服务器池，有关详细信息，请参阅部署文档中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。

有关可用拓扑以及安装 持久聊天服务器服务器的技术和软件要求的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)，规划文档、部署文档或操作文档中的 [Lync Server 2013 中的持久聊天服务器的工作原理](lync-server-2013-how-persistent-chat-server-works.md)，及支持性文档中的 [支持的适用于 Lync Server 2013 的硬件](lync-server-2013-supported-hardware.md)。

有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅部署文档中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。

单个 持久聊天服务器前端服务器可支持 20,000 个活动用户。您可以有一个 持久聊天服务器池，带有支持总数为 80,000 个并发用户的多达 4 个活动 前端服务器。

虚拟服务器也支持 持久聊天服务器。如果虚拟服务器与物理服务器的规格一致，则最多可支持 20,000 个并发用户。

> [!IMPORTANT]
> 持久聊天服务器必须安装在 Windows NT 文件系统上才能帮助强制执行文件系统安全性。FAT32 是 持久聊天服务器不支持的文件系统。


## 本节内容

  - [Lync Server 2013 中的持久聊天服务器的工作原理](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lync Server 2013 中的持久聊天服务器的部署清单](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Lync Server 2013 中持久聊天服务器的技术要求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [在 Lync Server 2013 中设置持久聊天服务器的系统和基础结构](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [在 Lync Server 2013 中将持久聊天服务器添加到部署](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [在 Lync Server 2013 中安装持久聊天服务器](lync-server-2013-installing-persistent-chat-server.md)

  - [在 Lync Server 2013 中添加持久聊天管理员](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [在 Lync Server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)

  - [使用 Windows PowerShell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [在 Lync Server 2013 中使用 Windows PowerShell Cmdlet 排查持久聊天服务器配置故障](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [在 Lync Server 2013 中为持久聊天服务器配置高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [在 Lync Server 2013 中对持久聊天服务器进行故障转移和故障回复](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

