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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295291"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |主体 ID。  <br/> |
|invID  <br/> |int, not null  <br/> |从 tblLastInviteId 表生成的唯一序列号 (每个主体 ID)。  <br/> |
|a  <br/> |int, not null  <br/> |节点 ID (仅聊天室)。  <br/> |
|createdOn  <br/> |datetime, not null  <br/> |创建时间。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<prinID、\>  <br/> |主键。  <br/> |
|prinID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
|a  <br/> |带有 tblNode 表中的 lookup 的外键。  <br/> |
   

