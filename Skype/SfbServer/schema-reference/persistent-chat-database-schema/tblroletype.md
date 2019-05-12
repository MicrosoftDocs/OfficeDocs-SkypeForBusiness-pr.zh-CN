---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是一个静态查找表包含角色类型及其关联的权限集。
ms.openlocfilehash: 074b65d3f701d122bbb311da3096e6727dd17264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924961"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType 是一个静态查找表包含角色类型及其关联的权限集。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int，不为 null  <br/> |角色类型 id。  <br/> |
|rtypeDesc  <br/> |nvarchar (256)，不为 null  <br/> | 角色类型说明。 有四个可用的角色： <br/>  成员： 聊天室成员 <br/>  管理员： 聊天室管理员 <br/>  有： 大会堂聊天室的演讲者 <br/>  创建者： 可以创建聊天室 <br/> |
|rtypeAllowedPermSet  <br/> |bigint，不为 null  <br/> | 权限集的角色。 使用的预留有位： <br/>  2： 在角色可以管理节点时为 true。 <br/>  4： 在角色可以创建子节点时为 true。 <br/>  7： 在角色可以加入聊天室 （或某类别的子聊天室） 时为 true。 <br/>  8： 在角色可以聊天在聊天室中 （或某类别的子聊天室） 时为 true。 <br/>  10： 在角色可以读取即使不加入聊天室的聊天历史记录时为 true。 <br/>  11： 在角色可以看到该聊天室时为 true。 （这被细化由如范围和可视性的因素。） <br/>  12： 在角色可以在大会堂聊天室中聊天时为 true。 <br/>  13： 在角色可以查看节点时绕过可见性规则时为 true。 <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|rtypeID  <br/> |主键。  <br/> |
   

