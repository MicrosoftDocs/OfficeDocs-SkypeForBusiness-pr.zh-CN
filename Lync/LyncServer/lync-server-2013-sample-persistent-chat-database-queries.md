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
ms.openlocfilehash: cfbe31844e0ca78a3f9b133bde96f2a6f625f759
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511029"
---
# <a name="sample-persistent-chat-database-queries-for-lync-server-2013"></a><span data-ttu-id="f796c-102">Lync Server 2013 的示例持久聊天数据库查询</span><span class="sxs-lookup"><span data-stu-id="f796c-102">Sample Persistent Chat database queries for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f796c-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f796c-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f796c-104">本节包含持久聊天数据库的示例查询。</span><span class="sxs-lookup"><span data-stu-id="f796c-104">This section contains sample queries for the Persistent Chat database.</span></span>

<span data-ttu-id="f796c-105">使用以下示例获取特定日期后的最活跃持久聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="f796c-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

<span data-ttu-id="f796c-106">使用以下示例可获得某个日期后多数活动用户的列表。</span><span class="sxs-lookup"><span data-stu-id="f796c-106">Use the following example to get a list of your most active users after a certain date.</span></span>

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

<span data-ttu-id="f796c-107">使用以下示例可获得曾经发送其中包含“Hello World”的消息的每位用户的列表。</span><span class="sxs-lookup"><span data-stu-id="f796c-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

<span data-ttu-id="f796c-108">使用以下示例可获得某个主体的组成员身份的列表。</span><span class="sxs-lookup"><span data-stu-id="f796c-108">Use the following example to get a list of group memberships for a certain principal.</span></span>

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

<span data-ttu-id="f796c-109">使用以下示例可获得用户 Jane Dow 属于其直接成员的每个聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="f796c-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

<span data-ttu-id="f796c-110">使用以下示例可获得用户已接收的邀请的列表。</span><span class="sxs-lookup"><span data-stu-id="f796c-110">Use the following example to get a list of invitations that a user has received.</span></span>

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

