---
title: tblLastInviteId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873935"
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
