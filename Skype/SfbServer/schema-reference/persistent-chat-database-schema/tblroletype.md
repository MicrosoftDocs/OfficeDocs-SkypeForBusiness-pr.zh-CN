---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是一个具有角色类型及其关联权限集的静态查找表。
ms.openlocfilehash: 8d49e9f2c61b8672a01a9c77bcc825925a4e7b2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295214"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType 是一个具有角色类型及其关联权限集的静态查找表。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, not null  <br/> |角色类型 ID。  <br/> |
|rtypeDesc  <br/> |nvarchar (256), not null  <br/> | 角色类型说明。 有四个可用的角色: <br/>  成员: 聊天室成员 <br/>  管理器: 聊天室管理器 <br/>  浊音: 演示者使用 auditorium 聊天室 <br/>  创建者: 可以创建聊天室 <br/> |
|rtypeAllowedPermSet  <br/> |bigint, not null  <br/> | 角色的权限集。 所用位为: <br/>  2: 如果角色可以管理节点, 则为 True。 <br/>  4: 如果角色可以创建子节点, 则为 True。 <br/>  7: 如果角色可以加入聊天室 (或类别的子聊天室), 则为 True。 <br/>  8: 如果角色可以在聊天室中 (或在子类别的子聊天室中) 聊天, 则为 True。 <br/>  10: 如果角色可以读取聊天历史记录 (即使未加入聊天室), 则为 True。 <br/>  11: 如果角色可以查看聊天室, 则为 True。 (这将通过范围和可见性等因素进一步改进。) <br/>  12: 如果角色可以在 auditorium 聊天室中聊天, 则为 True。 <br/>  13: 如果角色在查看节点时可以绕过可见性规则, 则为 True。 <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|rtypeID  <br/> |主键。  <br/> |
   

