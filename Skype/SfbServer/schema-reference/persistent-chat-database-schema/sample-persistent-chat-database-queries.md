---
title: 示例持久聊天数据库查询
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: 此部分包含持久聊天数据库的示例查询。
ms.openlocfilehash: 9dace51aa882402cd7f4f6c58c9444c21263333c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212682"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="bb3e8-103">示例持久聊天数据库查询</span><span class="sxs-lookup"><span data-stu-id="bb3e8-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="bb3e8-104">此部分包含持久聊天数据库的示例查询。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="bb3e8-105">使用下面的示例可获得某个日期后您最活跃的持久聊天聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="bb3e8-106">使用下面的示例可获得某个日期后多数活动用户的列表。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="bb3e8-107">下面的示例用于获取用户曾经发送其中包含"Hello World"的消息的每个人的列表。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="bb3e8-108">使用以下示例可获得某个主体的组成员身份列表。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="bb3e8-109">使用下面的示例可获得用户 Jane Dow 属于其直接成员的每个聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="bb3e8-110">使用下面的示例可获得用户已接收的邀请的列表。</span><span class="sxs-lookup"><span data-stu-id="bb3e8-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
