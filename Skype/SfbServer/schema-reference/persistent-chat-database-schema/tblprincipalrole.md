---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含分配给节点的显式角色。
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295235"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole 包含分配给节点的显式角色。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, not null  <br/> |角色所应用的节点 ID。  <br/> |
|prinRolePrinID  <br/> |int, not null  <br/> |主体 ID。  <br/> |
|prinRoleTypeID  <br/> |int, not null  <br/> |角色类型 ID (来自 tblRoleType)。  <br/> |
|prinRoleUpdatedBy  <br/> |int, not null  <br/> |上次更新此条目的主体的 ID。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |主键。  <br/> |
|prinRoleNodeID  <br/> |带有 tblNode 表中的 lookup 的外键。  <br/> |
|prinRolePrinID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
|prinRoleTypeID  <br/> |TblRoleType 表中的 lookup 的外键。  <br/> |
   

