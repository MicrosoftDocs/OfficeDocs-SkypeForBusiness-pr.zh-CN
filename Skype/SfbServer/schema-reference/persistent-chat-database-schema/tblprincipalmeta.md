---
title: tblPrincipalMeta
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含需要刷新从 Active Directory 域服务的主体。
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta 包含需要刷新从 Active Directory 域服务的主体。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为空  <br/> |主体标识。  <br/> |
|prinAffiliationsDirty  <br/> |位，不为空  <br/> |如果主要附属机构需要被刷新。  <br/> |
|prinAttributesDirty  <br/> |位，不为空  <br/> |如果主体属性必须被刷新。  <br/> |
|prinDeleted  <br/> |位，不为空  <br/> |如果主体已被删除，则为 true。  <br/> |
|tryCount  <br/> |int  <br/> |若要刷新到目前为止发生的 AD ds 主体的尝试次数。  <br/> |
|lastTry  <br/> |datetime  <br/> |从最新尝试刷新主体的时间戳。 可以为 null，如果尚未已尝试了任何一次刷新。  <br/> |
|nextTry  <br/> |datetime  <br/> |下次计划更新的时间戳。 可以刷新已没有进一步安排的情况下为 null。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |为主键。  <br/> |
|prinID  <br/> |TblPrincipal.prinID 表中查找与外键。  <br/> |
   

