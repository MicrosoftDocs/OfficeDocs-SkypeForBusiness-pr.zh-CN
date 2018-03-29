---
title: tblPrincipalRole
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含显式角色分配给节点。
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole 包含显式角色分配给节点。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int，不为空  <br/> |该角色适用于的节点 ID。  <br/> |
|prinRolePrinID  <br/> |int，不为空  <br/> |主体标识。  <br/> |
|prinRoleTypeID  <br/> |int，不为空  <br/> |角色类型 ID （从 tblRoleType)。  <br/> |
|prinRoleUpdatedBy  <br/> |int，不为空  <br/> |上次更新此项的主要用户的 ID。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<prinRoleNodeID，prinRolePrinID prinRoleTypeID\>  <br/> |为主键。  <br/> |
|prinRoleNodeID  <br/> |TblNode.nodeID 表中查找与外键。  <br/> |
|prinRolePrinID  <br/> |TblPrincipal.prinID 表中查找与外键。  <br/> |
|prinRoleTypeID  <br/> |TblRoleType.rtypeID 表中查找与外键。  <br/> |
   

