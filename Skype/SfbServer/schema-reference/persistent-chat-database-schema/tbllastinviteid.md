---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含为每位用户生成（并在 tblPrincipalInvites 表中使用）的最后一个邀请 ID。
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814570"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId 包含为每位用户生成（并在 tblPrincipalInvites 表中使用）的最后一个邀请 ID。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，not null  <br/> |主体 ID。  <br/> |
|lastInviteID  <br/> |int，not null  <br/> |上次使用的邀请 ID。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblPrincipalInvites](tblprincipalinvites.md)
