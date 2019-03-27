---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblprincipalmeta 表包含必须从 Active Directory 域服务刷新的主体。
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889605"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblprincipalmeta 表包含必须从 Active Directory 域服务刷新的主体。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 id。  <br/> |
|prinAffiliationsDirty  <br/> |bit，不为 null  <br/> |如果主体附属关系必须刷新。  <br/> |
|prinAttributesDirty  <br/> |bit，不为 null  <br/> |如果主体属性必须刷新。  <br/> |
|prinDeleted  <br/> |bit，不为 null  <br/> |如果主体已被删除，则为 true。  <br/> |
|tryCount  <br/> |int  <br/> |若要刷新的主体从 AD DS 到目前为止已发生的次数。  <br/> |
|lastTry  <br/> |datetime  <br/> |从最新尝试刷新主体的时间戳。 可以为 null，如果尚未已尝试了任何一次刷新。  <br/> |
|nextTry  <br/> |datetime  <br/> |下一计划刷新的时间戳。 可以为 null，如果没有进一步已计划刷新。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinID  <br/> |在 tblPrincipal.prinID 表中查找的外键。  <br/> |
   

