---
title: 示例持久聊天数据库查询
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: 本部分包含持久聊天数据库的示例查询。
ms.openlocfilehash: f161deb55cb9ecb0e42eb23e71cd842aa8f3d99a
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887711"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="1d279-103">示例持久聊天数据库查询</span><span class="sxs-lookup"><span data-stu-id="1d279-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="1d279-104">本部分包含持久聊天数据库的示例查询。</span><span class="sxs-lookup"><span data-stu-id="1d279-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="1d279-105">使用以下示例获取特定日期后最活跃的持久聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="1d279-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="1d279-106">使用以下示例，获取特定日期后最活跃的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="1d279-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="1d279-107">使用以下示例获取曾经使用 "Hello World" 发送邮件的所有人的列表。</span><span class="sxs-lookup"><span data-stu-id="1d279-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="1d279-108">使用以下示例获取特定主体的组成员身份列表。</span><span class="sxs-lookup"><span data-stu-id="1d279-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="1d279-109">使用以下示例获取用户（Jane 道琼斯）的每个聊天室的列表，该列表是的直接成员。</span><span class="sxs-lookup"><span data-stu-id="1d279-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="1d279-110">使用以下示例获取用户已收到的邀请列表。</span><span class="sxs-lookup"><span data-stu-id="1d279-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
