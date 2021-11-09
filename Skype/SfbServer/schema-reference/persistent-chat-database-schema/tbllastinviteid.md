---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含上次为每个用户生成的并且在 tblPrincipalInvites 表中使用的邀请 ID。
ms.openlocfilehash: 56df4cf4002a67b665dfc33f1364493b07ac9ea7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855206"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId 包含上次为每个用户生成的并且在 tblPrincipalInvites 表中使用的邀请 ID。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 ID。  <br/> |
|lastInviteID  <br/> |int，不为 null  <br/> |上次使用的邀请 ID。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblPrincipalInvites](tblprincipalinvites.md)
