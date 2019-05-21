---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295256"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |主体 ID。  <br/> |
|prinAffiliationsDirty  <br/> |位, not null  <br/> |如果必须刷新主体隶属关系, 则为 True。  <br/> |
|prinAttributesDirty  <br/> |位, not null  <br/> |如果必须刷新主体属性, 则为 True。  <br/> |
|prinDeleted  <br/> |位, not null  <br/> |如果主体已被删除, 则为 True。  <br/> |
|tryCount  <br/> |int  <br/> |尝试从目前为止发生的 AD DS 刷新主体的次数。  <br/> |
|lastTry  <br/> |datetime  <br/> |从最新尝试刷新主体的时间戳。 如果尚未尝试刷新, 则可以为 null。  <br/> |
|nextTry  <br/> |datetime  <br/> |下一次计划刷新的时间戳。 如果尚未安排进一步刷新, 则可以为 null。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
   

