---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含分配给节点的作用域。
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295193"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal 包含分配给节点的作用域。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, not null  <br/> |作用域所适用的节点 ID。  <br/> |
|scopePrinID  <br/> |int, not null  <br/> |主体 ID。  <br/> |
|scopeIsDenied  <br/> |位, not null  <br/> |如果范围的类型为 "拒绝", 则为 True;如果允许, 则为 False。  <br/> |
|scopeUpdatedBy  <br/> |int, not null  <br/> |上次更新此条目的主体的 ID。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |主键。  <br/> |
|scopeNodeID  <br/> |带有 tblNode 表中的 lookup 的外键。  <br/> |
|scopePrinID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
   

