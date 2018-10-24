---
title: Lync Server 2013：设置系统平台
TOCTitle: 设置系统平台
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204783(v=OCS.15)
ms:contentKeyID: 49312374
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中设置系统平台

 

_**上一次修改主题：** 2013-02-21_

在开始部署 持久聊天服务器之前，您必须在服务器上满足系统要求的硬件上安装必要的操作系统：

有关支持的服务器硬件（运行 Lync Server 2013、数据库服务器和文件服务器）的详细信息，请参阅可支持性文档中的 [支持的适用于 Lync Server 2013 的硬件](lync-server-2013-supported-hardware.md)。有关支持的操作系统和数据库软件的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。有关 Windows 更新要求的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。

持久聊天服务器前端服务器**PersistentChatService** 可以部署在 Lync Server 2013企业版 池中的一个或多个独立计算机上。它们无法并置在 Lync Server企业版前端服务器上。 持久聊天服务器可以由引导程序部署，就像其他 Lync Server 角色一样。 **用于文件上载/下载的 持久聊天 Web 服务**和 **用于聊天室管理的 持久聊天 Web 服务**都是部署在 Lync Server 2013前端服务器上的 Web 组件。

单个 持久聊天服务器前端服务器可以支持 20,000 个活动用户。您的 持久聊天服务器池最多可以具有共支持 80,000 个并发用户的 4 个活动前端。 持久聊天后端服务器**PersistentChatStore** 存储聊天室和类别。建议您将 **PersistentChatStore** 安装在 企业版 池中的专用 SQL Server后端服务器上；但支持将 Lync Server 2013后端服务器和 **PersistentChatStore** 并置在同一 SQL Server 实例上。

如果您的组织需要合规性支持，则可以使用 拓扑生成器安装它。 持久聊天服务器合规性服务与 持久聊天服务器前端服务器安装在同一计算机上。合规性需要单独的数据库。有关 持久聊天服务器的合规性要求的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

每个拓扑至少需要一台安装了 Lync Server 2013 的服务器和一台安装了 SQL Server 数据库软件的服务器。 拓扑生成器支持多个 持久聊天服务器池。按照部署文档中 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 中的部署任何池的相同部署说明来部署多个 持久聊天服务器池。

您还可以使用 Lync Server 2013标准版 部署 持久聊天服务器。在这种情况下， **PersistentChatService**前端服务器并置在 Standard Edition Server 上，并且您可以将 **PersistentChatStore**后端服务器部署在本地 SQL Server Express 实例上。

> [!IMPORTANT]
> 我们不支持 持久聊天服务器标准版 以实现高可用性。性能和规模将受到限制。另外，我们只支持新的 持久聊天服务器  Standard Edition Server 部署，并且不支持将 Lync Server 2010群聊服务器升级到 Lync Server 2013持久聊天服务器标准版。


## 另请参阅

#### 概念

[Lync Server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)  

#### 其他资源

[支持的适用于 Lync Server 2013 的硬件](lync-server-2013-supported-hardware.md)  
[Lync Server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)  
[在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)  
[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)

