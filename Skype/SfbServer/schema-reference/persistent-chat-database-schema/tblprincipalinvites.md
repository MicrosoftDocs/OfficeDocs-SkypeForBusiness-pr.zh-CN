---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212465"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 id。  <br/> |
|invID  <br/> |int，不为 null  <br/> |生成的唯一连续数字 （每个主体 ID) 从 tblLastInviteId 表。  <br/> |
|nodeID  <br/> |int，不为 null  <br/> |节点 ID （仅聊天室）。  <br/> |
|createdOn  <br/> |datetime，不为 null  <br/> |创建的时间。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<prinID nodeID\>  <br/> |主键。  <br/> |
|prinID  <br/> |在 tblPrincipal.prinID 表中查找的外键。  <br/> |
|nodeID  <br/> |在 tblNode.nodeID 表中查找的外键。  <br/> |
   

