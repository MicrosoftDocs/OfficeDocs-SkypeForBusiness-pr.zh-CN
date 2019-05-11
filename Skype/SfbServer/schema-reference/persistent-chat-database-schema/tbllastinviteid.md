---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。
ms.openlocfilehash: f57ca67a91b71b9245644a53eb3e5c5771ca6fb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929901"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId 包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 id。  <br/> |
|lastInviteID  <br/> |int，不为 null  <br/> |上次使用的邀请 id。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinID  <br/> |在 tblPrincipal.prinID 表中查找的外键。  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblPrincipalInvites](tblprincipalinvites.md)
