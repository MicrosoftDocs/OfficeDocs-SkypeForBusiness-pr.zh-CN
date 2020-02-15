---
title: Lync Server 2013：示例持久聊天数据库查询
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sample Persistent Chat database queries
ms:assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558649(v=OCS.15)
ms:contentKeyID: 48184133
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc1d53046b6a43da38a7a91c7e19f195e6667f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sample-persistent-chat-database-queries-for-lync-server-2013"></a>Lync Server 2013 的示例持久聊天数据库查询

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

本节包含持久聊天数据库的示例查询。

使用以下示例获取特定日期后的最活跃持久聊天室的列表。

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

使用以下示例可获得某个日期后多数活动用户的列表。

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

使用以下示例可获得曾经发送其中包含“Hello World”的消息的每位用户的列表。

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

使用以下示例可获得某个主体的组成员身份的列表。

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

使用以下示例可获得用户 Jane Dow 属于其直接成员的每个聊天室的列表。

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

使用以下示例可获得用户已接收的邀请的列表。

    SELECT prinName
          ,nodeName
          ,invID   
          ,createdOn
      FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
      where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
      ORDER BY invID DESC

</div>

<span> </span>

</div>

</div>

</div>

