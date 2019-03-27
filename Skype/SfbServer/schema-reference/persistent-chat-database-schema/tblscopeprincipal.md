---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含分配至节点。
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885622"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal 包含分配至节点。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int，不为 null  <br/> |作用域适用的节点 ID。  <br/> |
|scopePrinID  <br/> |int，不为 null  <br/> |主体 id。  <br/> |
|scopeIsDenied  <br/> |bit，不为 null  <br/> |作用域的类型为 Deny; 时为 true允许则为 false。  <br/> |
|scopeUpdatedBy  <br/> |int，不为 null  <br/> |上次更新此项的主体的 ID。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<scopeNodeID scopePrinID\>  <br/> |主键。  <br/> |
|scopeNodeID  <br/> |在 tblNode.nodeID 表中查找的外键。  <br/> |
|scopePrinID  <br/> |在 tblPrincipal.prinID 表中查找的外键。  <br/> |
   

