---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含分配至节点的显式角色。
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890767"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole 包含分配至节点的显式角色。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int，不为 null  <br/> |角色适用的节点 ID。  <br/> |
|prinRolePrinID  <br/> |int，不为 null  <br/> |主体 id。  <br/> |
|prinRoleTypeID  <br/> |int，不为 null  <br/> |角色类型 ID （来自 tblRoleType)。  <br/> |
|prinRoleUpdatedBy  <br/> |int，不为 null  <br/> |上次更新此项的主体的 ID。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<prinRoleNodeID，prinRolePrinID prinRoleTypeID\>  <br/> |主键。  <br/> |
|prinRoleNodeID  <br/> |在 tblNode.nodeID 表中查找的外键。  <br/> |
|prinRolePrinID  <br/> |在 tblPrincipal.prinID 表中查找的外键。  <br/> |
|prinRoleTypeID  <br/> |在 tblRoleType.rtypeID 表中查找的外键。  <br/> |
   

