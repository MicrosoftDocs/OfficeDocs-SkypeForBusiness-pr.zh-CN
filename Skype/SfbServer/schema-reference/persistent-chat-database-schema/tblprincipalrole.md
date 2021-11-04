---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含分配给节点的显式角色。
ms.openlocfilehash: bedb7025605dc5cd3e5808ac265931d8623060b3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767320"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole 包含分配给节点的显式角色。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int，不为 null  <br/> |角色应用于的节点 ID。  <br/> |
|prinRolePrinID  <br/> |int，不为 null  <br/> |主体 ID。  <br/> |
|prinRoleTypeID  <br/> |int，不为 null  <br/> |角色类型 ID (tblRoleType) 。  <br/> |
|prinRoleUpdatedBy  <br/> |int, 不为 null  <br/> |上次更新此项的主体的 ID。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |主键。  <br/> |
|prinRoleNodeID  <br/> |其查找包含在 tblNode.nodeID 表中的外键。  <br/> |
|prinRolePrinID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
|prinRoleTypeID  <br/> |在 tblRoleType.rtypeID 表中查找的外键。  <br/> |
   

