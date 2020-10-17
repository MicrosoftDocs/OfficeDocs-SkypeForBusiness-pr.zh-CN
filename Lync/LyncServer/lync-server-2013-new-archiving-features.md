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
ms.openlocfilehash: 3150d56bbd4935d6139c8584fcd69d721056317e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505379"
---
# <a name="new-archiving-features-in-lync-server-2013"></a>Lync Server 2013 中的新存档功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

Lync Server 2013 中的存档可以存档以下类型的内容：

  - 对等即时消息

  - 多方即时消息的会议

  - 会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）

此外，Lync Server 2013 中的存档还提供了可提高部署和操作效率的新功能。 这些新功能包括：

  - **并置前端服务器上的存档。**    Lync Server 2013 没有单独的存档服务器角色。 存档是 Enterprise Edition 部署中的所有前端服务器或可为池或站点实施并配置的 Standard Edition 服务器上所提供的一项可选功能。

  - **Microsoft Exchange 集成。**    在部署存档时，可以将数据存储与托管在 Exchange 2013 上的所有用户的现有 Exchange 2013 存储集成在一起，并将其邮箱置于 In-Place 保留状态，因此无需部署单独的 SQL Server 数据库来存档 Lync 数据。 如果您没有 Exchange 2013 部署，或者您不希望与它集成，或者如果您有任何 Lync 2013 用户未驻留在 Exchange 2013 上，并且其邮箱置于 In-Place 保留状态，则可以通过使用 SQL Server 来存储 Lync 通信中的存档数据来部署单独的存档数据库。 如果要对部署中的某些而不是所有用户使用 Microsoft Exchange 集成，则可以使用 Microsoft Exchange 集成和 Lync Server 2013 存档数据库。 有关 In-Place 保留的详细信息，请参阅处的 "就地保留" [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) 。

  - **SQL 存储镜像。**    在部署存档时，可以为存档数据库启用 SQL Server 数据库镜像。

  - **白板和轮询的存档。**    存档的会议内容现在包含在会议期间共享的白板和投票。

不存档以下类型的内容：

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

