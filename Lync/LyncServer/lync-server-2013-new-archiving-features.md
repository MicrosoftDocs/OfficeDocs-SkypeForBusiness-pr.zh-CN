---
title: Lync Server 2013：新的存档功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1509a0857b54673ab20783f69b34b59c6d2afde8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Lync Server 2013 中新的存档功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-09_

Lync Server 2013 中的存档可存档以下类型的内容：

  - 对等即时消息

  - 多方即时消息的会议（会议）

  - 会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）

此外，Lync Server 2013 中的存档提供了可提高部署和操作效率的新功能。 这些新功能包括：

  - **Collocation 前端服务器上的存档。**   Lync Server 2013 没有单独的存档服务器角色。 存档是在企业版部署中的所有前端服务器上提供的可选功能，也可以在标准版服务器上实现，可以为池或网站进行配置。

  - **Microsoft Exchange 集成。**   部署存档时，你可以将数据存储与托管在 exchange 2013 上的所有用户的现有 exchange 2013 存储进行集成，并将其邮箱置于就地保留，因此无需部署单独的 SQL Server 数据库来存档 Lync 数据。 如果你没有 Exchange 2013 部署，或者你不希望与它集成，或者如果你拥有的任何 Lync 2013 用户未托管在 Exchange 2013 上，并且其邮箱放置在原地保留中，你可以通过使用 SQL Server 使用 SQL Server 来部署单独的存档数据库 store 已存档 Lync 通信中的数据。 如果你想要对部署中的部分而非所有用户使用 Microsoft Exchange 集成，则可以使用 Microsoft Exchange 集成和 Lync Server 2013 存档数据库。 有关就地保留的详细信息，请参阅的 "就地保留" [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)。

  - **SQL 应用商店镜像。**   部署存档时，可以为存档数据库启用 SQL Server 数据库镜像。

  - **白板和投票的存档。**   已存档的会议内容现在包括在会议期间共享的白板和投票。

以下类型的内容未存档：

  - 对等文件传输

  - 对等即时消息和会议的音频/视频

  - 对等即时消息和会议的应用程序共享

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

