---
title: 部署 Lync 客户端
TOCTitle: 部署 Lync 客户端
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204827(v=OCS.15)
ms:contentKeyID: 49312579
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 部署 Lync 客户端

 

_**上一次修改主题：** 2012-10-03_

Lync 2013 引入了不同的客户端部署方法。与早期版本不同，Lync 2013 不再具有自己的安装程序。相反，Lync 是 Office 2013 安装程序附带的。若要将 Lync 2013 部署到您的用户，您可以使用 Office 2013 安装方法和自定义工具。

  - **Office 2013 Windows Installer** 是一类基于 Windows Installer 的安装程序包且包含多个 MSI 文件。一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。本节中的主题介绍了如何使用和自定义 Office 2013 Windows Installer 以部署 Lync 2013。

  - **Office 2013 即点即用**是一类安装程序，它将 Office 安装文件从 Microsoft Office 365 门户流式传输到用户。通过使用针对即点即用的 Office 部署工具，管理员可以自定义安装。由于 Office 2013 即点即用主要用于 Microsoft Office 365 环境中，因此，本节将不会详细介绍此安装方法。有关使用和自定义即点即用安装的详细信息，请参阅 Office 2013 资源工具包文档。管理员还可以将 Office 2013 即点即用程序和语言源文件下载到本地位置，这在您因企业安全要求而需要最大程度地减小网络需求或阻止用户从 Internet 安装软件时很有用。

本节中的主题重点说明了如何使用基于 Office 2013 MSI 的安装程序部署客户端。您主要应参考 Office 2013 资源工具包文档，该文档详细描述了如何准备基础结构、自定义安装以及部署 Office 2013。但您应将 Office 文档与本节中的主题结合使用，这些主题指明了特定于 Lync 2013 的部署注意事项。

> [!NOTE]  
> <ul><li><p>支持在 Outlook 消息和协作客户端中进行会议管理的 Lync 2013 联机会议外接程序将自动随 Lync 2013 一起安装。</p></li>
> <li><p>Office 2013 安装程序不会卸载早期版本的 Lync 或 Office Communicator。Lync 2013 客户端可与其他 Lync 或 Office Communicator 客户端并行安装。</p></li></ul>



## 本节内容

  - [自定义客户端安装](lync-server-2013-customizing-client-installation.md)

  - [自定义 Lync 行为和用户界面](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [自定义联机会议外接程序](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [在 Lync Server 2013 中配置与会页面](lync-server-2013-configuring-the-meeting-join-page.md)

  - [配置支持的客户端版本](lync-server-2013-configuring-supported-client-versions.md)

  - [配置增强状态隐私模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

