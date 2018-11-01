---
title: 'Lync Server 2013：示例持久聊天数据库查询 '
TOCTitle: 示例持久聊天数据库查询
ms:assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558649(v=OCS.15)
ms:contentKeyID: 49312867
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的示例持久聊天数据库查询

 

_**上一次修改主题：** 2012-10-06_

本节包含 持久聊天数据库的示例查询。

使用以下示例可获得某个日期后多数活动 持久聊天聊天室的列表。

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

