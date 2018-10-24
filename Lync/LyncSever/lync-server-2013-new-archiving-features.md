---
title: Lync Server 2013：新的存档功能
TOCTitle: 新的存档功能
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205225(v=OCS.15)
ms:contentKeyID: 49314118
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中新的存档功能

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 中的存档可以存档以下类型的内容：

  - 对等即时消息

  - 多方即时消息的会议

  - 会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）

此外， Lync Server 2013 中的存档提供了一些新功能，可用于提高部署和运行效率。这些新功能包括：

  - **前端服务器上的存档并置。**    Lync Server 2013 不包含单独的存档服务器角色。存档是 Enterprise Edition 部署中的所有前端服务器或可为池或站点实施并配置的 Standard Edition 服务器上所提供的一项可选功能。

  - **Microsoft Exchange 集成。**   在部署存档时，您可以针对驻留在 Exchange 2013 上并使其邮箱处于就地保留状态的所有用户，将存档的数据存储与现有 Exchange 2013 存储集成，以便无需部署单独的 SQL Server 数据库即可存档 Lync 数据。如果您没有 Exchange 2013 部署，或不希望与其进行集成，或拥有的任何 Lync 2013 用户并非驻留在 Exchange 2013 上并使其邮箱处于就地保留状态，则可以使用 SQL Server 部署单独的存档数据库，以存储 Lync 通信中的存档数据。如果您想要针对部署中的部分但并非所有用户使用 Microsoft Exchange 集成，则可以同时使用 Microsoft Exchange 集成和 Lync Server 2013 存档数据库。有关就地保留的详细信息，请参阅“就地保留”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)。

  - **SQL 存储镜像。**  在您部署存档时，可为您的存档数据库启用 SQL Server 数据库镜像。

  - **白板和轮询存档**   存档的会议内容现包括会议期间共享的白板和轮询。

不存档以下类型的内容：

  - 对等文件传输

  - 对等即时消息和会议的音频/视频

  - 对等即时消息和会议的应用程序共享

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)

