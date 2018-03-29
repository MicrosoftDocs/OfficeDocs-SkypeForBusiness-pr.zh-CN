---
title: tblRoleType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是静态查找表与角色类型及其关联的权限集。
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType 是静态查找表与角色类型及其关联的权限集。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int，不为空  <br/> |角色类型 id。  <br/> |
|rtypeDesc  <br/> |nvarchar (256) 不为空  <br/> | 角色类型说明。 有四个可用的角色： <br/>  成员： 聊天室成员 <br/>  经理： 聊天室经理 <br/>  对于大会堂聊天室浊音： 演示者 <br/>  创建者： 可以创建聊天室 <br/> |
|rtypeAllowedPermSet  <br/> |bigint，不为空  <br/> | 设置为该角色的权限。 所使用的位： <br/>  2： 如果该角色可以管理节点则为 true。 <br/>  4： 如果该角色可以创建子节点。 <br/>  7： 如果该角色可以加入聊天室 （或某一类别的儿童聊天室） 则为 true。 <br/>  8： 如果该角色可以聊天，在聊天室中 （或在某一类别的儿童聊天室） 则为 true。 <br/>  10： 如果该角色可以读取即使没有加入聊天室聊天历史则为 true。 <br/>  11： 如果该角色可以看到聊天室则为 true。 （这是进一步改进了范围和可见性等因素。） <br/>  12： 如果该角色可以在大会堂聊天室聊天。 <br/>  13： 如果该角色可以查看节点时跳过可见性规则。 <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|rtypeID  <br/> |为主键。  <br/> |
   

