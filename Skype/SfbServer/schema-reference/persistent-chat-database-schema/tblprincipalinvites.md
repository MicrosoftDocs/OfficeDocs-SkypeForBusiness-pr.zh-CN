---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814180"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，not null  <br/> |主体 ID。  <br/> |
|invID  <br/> |int，not null  <br/> |从 tblLastInviteId 表生成的唯一序列号（每个主体 ID）。  <br/> |
|a  <br/> |int，not null  <br/> |节点 ID （仅聊天室）。  <br/> |
|createdOn  <br/> |datetime，not null  <br/> |创建时间。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<prinID、\>  <br/> |主键。  <br/> |
|prinID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
|a  <br/> |带有 tblNode 表中的 lookup 的外键。  <br/> |
   

