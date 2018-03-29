---
title: tblScopePrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含分配给节点的作用。
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal 包含分配给节点的作用。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int，不为空  <br/> |作用域应用到的节点 ID。  <br/> |
|scopePrinID  <br/> |int，不为空  <br/> |主体标识。  <br/> |
|scopeIsDenied  <br/> |位，不为空  <br/> |如果类型的作用域是拒绝;假如果允许。  <br/> |
|scopeUpdatedBy  <br/> |int，不为空  <br/> |上次更新此项的主要用户的 ID。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<scopeNodeID scopePrinID\>  <br/> |为主键。  <br/> |
|scopeNodeID  <br/> |TblNode.nodeID 表中查找与外键。  <br/> |
|scopePrinID  <br/> |TblPrincipal.prinID 表中查找与外键。  <br/> |
   

