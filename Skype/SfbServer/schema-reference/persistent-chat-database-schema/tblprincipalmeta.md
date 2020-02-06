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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813570"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，not null  <br/> |主体 ID。  <br/> |
|prinAffiliationsDirty  <br/> |位，not null  <br/> |如果必须刷新主体隶属关系，则为 True。  <br/> |
|prinAttributesDirty  <br/> |位，not null  <br/> |如果必须刷新主体属性，则为 True。  <br/> |
|prinDeleted  <br/> |位，not null  <br/> |如果主体已被删除，则为 True。  <br/> |
|tryCount  <br/> |int  <br/> |尝试从目前为止发生的 AD DS 刷新主体的次数。  <br/> |
|lastTry  <br/> |datetime  <br/> |从最新尝试刷新主体的时间戳。 如果尚未尝试刷新，则可以为 null。  <br/> |
|nextTry  <br/> |datetime  <br/> |下一次计划刷新的时间戳。 如果尚未安排进一步刷新，则可以为 null。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinID  <br/> |TblPrincipal 表中的 lookup 的外键。  <br/> |
   

