---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含已生成 （和 tblPrincipalInvites 表中） 的最后一次邀请 ID 为每个用户。
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId 包含已生成 （和 tblPrincipalInvites 表中） 的最后一次邀请 ID 为每个用户。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为空  <br/> |主体标识。  <br/> |
|lastInviteID  <br/> |int，不为空  <br/> |最后用的邀请 id。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |为主键。  <br/> |
|prinID  <br/> |TblPrincipal.prinID 表中查找与外键。  <br/> |
   
## <a name="see-also"></a>另请参阅

#### 

[tblPrincipalInvites](tblprincipalinvites.md)

