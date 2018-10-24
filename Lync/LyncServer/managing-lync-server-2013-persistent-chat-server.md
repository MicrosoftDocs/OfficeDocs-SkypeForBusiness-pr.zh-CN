---
title: 管理 Lync Server 2013 持久聊天服务器
TOCTitle: 管理 Lync Server 2013 持久聊天服务器
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398657(v=OCS.15)
ms:contentKeyID: 49313429
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理 Lync Server 2013 持久聊天服务器

 

_**上一次修改主题：** 2012-10-11_

使用 Lync Server 2013持久聊天服务器可使多个用户参与对话，对话过程中这些用户可针对特定的主题发布和访问内容，其中包括文本、链接和文件。尽管用户可以在会话期间实时进行通信，但每个会话的内容都可以持久保存，也就是说，在会话结束后依然可以获得这些内容。

持久聊天聊天室的内容主要包括短文本消息，但也可以包括称为 *文章* 的较长消息，以及超链接、图释和上载的文档。

> [!NOTE]  
> Lync 2013 客户端不支持文件上载和下载；但 Lync Server 2013持久聊天服务器仍支持这两个功能。旧版 群聊客户端可以发布和查看文件，但如果通过 Lync 2013 客户端访问相同的聊天室，则前者无法访问这些文件。


聊天室的访问由成员身份列表控制。完整聊天室历史记录可供任何成员按时间顺序查阅或进行全文搜索。有关使用 持久聊天客户端的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划客户端](lync-server-2013-planning-for-clients.md)和部署文档中的 [在 Lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)。

为组织设置 持久聊天服务器时，需要在部署过程中指定初始配置。但是，有时您可能想要更改实现 持久聊天服务器支持的方式。例如，您可能需要以不同的方式为组织内的特定团队或组设置 持久聊天服务器支持和控制。本节提供可帮助您自定义 持久聊天服务器部署的信息和步骤。有关您可以为 持久聊天服务器配置的功能的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中定义持久聊天服务器要求](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)以及规划文档、部署文档或操作文档中的 [Lync Server 2013 中的持久聊天服务器的工作原理](lync-server-2013-how-persistent-chat-server-works.md)。有关为 Lync Server 2013 部署 持久聊天服务器的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)。

## 本部分内容

  - [Lync Server 2013 中的持久聊天服务器的工作原理](lync-server-2013-how-persistent-chat-server-works.md)

  - [使用类别管理持久聊天服务器](using-categories-to-administer-persistent-chat-server.md)

  - [了解持久聊天成员身份](understanding-persistent-chat-membership.md)

  - [持久聊天服务器最佳做法](persistent-chat-server-best-practices.md)

  - [在 Lync Server 2013 中管理类别、聊天室和加载项](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [在 Lync Server 2013 中管理持久聊天用户访问](lync-server-2013-managing-persistent-chat-user-access.md)

  - [在 Lync Server 2013 中运行和维护持久聊天系统](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

