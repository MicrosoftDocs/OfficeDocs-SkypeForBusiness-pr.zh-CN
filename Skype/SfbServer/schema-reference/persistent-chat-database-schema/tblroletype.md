---
title: tblRoleType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是一个静态查找表，其中包含角色类型及其关联的权限集。
ms.openlocfilehash: 2b03473b6f89e0dd2f572e2462b607bc72a2a2eb5f83aa18d2d779f9f66ee220
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318675"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType 是一个静态查找表，其中包含角色类型及其关联的权限集。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int，不为 null  <br/> |角色类型 ID。  <br/> |
|rtypeDesc  <br/> |nvarchar (256)，不为 null  <br/> | 角色类型描述。可用角色有四种： <br/>  成员：聊天室成员 <br/>  管理员：聊天室管理员 <br/>  有发布权的人：大会堂聊天室的演讲者 <br/>  创建者：可以创建聊天室 <br/> |
|rtypeAllowedPermSet  <br/> |bigint，不为 null  <br/> | 角色的权限集。使用的位为： <br/>  2：在角色可以管理节点时为 True。 <br/>  4：在角色可以创建子节点时为 True。 <br/>  7：在角色可以加入聊天室（或某类别的子聊天室）时为 True。 <br/>  8：在角色可以在聊天室中（或某类别的子聊天室中）聊天时为 True。 <br/>  10：在角色即使不加入聊天室也可读取聊天历史记录时为 True。 <br/>  11：在角色可以看到聊天室时为 True。（该值可通过作用域和可见性等因素进一步优化。） <br/>  12：在角色可以在大会堂聊天室中聊天时为 True。 <br/>  13：在角色查看节点后可以绕过可见性规则时为 True。 <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|rtypeID  <br/> |主键。  <br/> |
   

