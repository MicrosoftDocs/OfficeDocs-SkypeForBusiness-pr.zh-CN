---
title: tblPrincipalInvites
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。
---

# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 ID。  <br/> |
|invID  <br/> |int，不为 null  <br/> |从 tblLastInviteId 表中生成的唯一连续数字（每个主体 ID）。  <br/> |
|nodeID  <br/> |int，不为 null  <br/> |节点 ID（仅聊天室）。  <br/> |
|createdOn  <br/> |datetime，不为 null  <br/> |创建的时间。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |主键。  <br/> |
|prinID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
|nodeID  <br/> |其查找包含在 tblNode.nodeID 表中的外键。  <br/> |
   

