---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含邀请所有用户设置自动邀请的所有节点上。
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites 包含邀请所有用户设置自动邀请的所有节点上。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为空  <br/> |主体标识。  <br/> |
|invID  <br/> |int，不为空  <br/> |唯一序列号 （每个主体 ID) 从 tblLastInviteId 表中生成。  <br/> |
|nodeID  <br/> |int，不为空  <br/> |节点 ID （仅适用于聊天室）。  <br/> |
|createdOn  <br/> |日期时间不为空  <br/> |创建时间。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<prinID nodeID\>  <br/> |为主键。  <br/> |
|prinID  <br/> |TblPrincipal.prinID 表中查找与外键。  <br/> |
|nodeID  <br/> |TblNode.nodeID 表中查找与外键。  <br/> |
   

