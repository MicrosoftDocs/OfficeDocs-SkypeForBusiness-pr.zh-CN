---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含分配至节点的作用域。
ms.openlocfilehash: 4f2bcb7734badde8f734c30f074ba6dda82cc7eb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745708"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal 包含分配至节点的作用域。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int，不为 null  <br/> |作用域适用的节点 ID。  <br/> |
|scopePrinID  <br/> |int，不为 null  <br/> |主体 ID。  <br/> |
|scopeIsDenied  <br/> |bit，不为 null  <br/> |如果作用域的类型为 Deny，则为 True；如果作用域的类型为 Allow，则为 False。  <br/> |
|scopeUpdatedBy  <br/> |int, 不为 null  <br/> |上次更新此项的主体的 ID。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |主键。  <br/> |
|scopeNodeID  <br/> |其查找包含在 tblNode.nodeID 表中的外键。  <br/> |
|scopePrinID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
   

