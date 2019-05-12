---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含分配至节点。
ms.openlocfilehash: f682c8a2235ef30cda365bc5950cbfb123840595
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924925"
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
   

