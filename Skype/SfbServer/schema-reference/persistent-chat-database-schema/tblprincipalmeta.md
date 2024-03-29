---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。
ms.openlocfilehash: 77c260f56fe2f3e5b61956808b26bef1c7cf8827
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398616"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，不为 null  <br/> |主体 ID。  <br/> |
|prinAffiliationsDirty  <br/> |bit，不为 null  <br/> |如果必须刷新主体附属关系，则为 True。  <br/> |
|prinAttributesDirty  <br/> |bit，不为 null  <br/> |如果必须刷新主体属性，则为 True。  <br/> |
|prinDeleted  <br/> |bit，不为 null  <br/> |如果主体已删除，则为 True。  <br/> |
|tryCount  <br/> |int  <br/> |截止目前，已发生的尝试从 AD DS 刷新主体的次数。  <br/> |
|lastTry  <br/> |datetime  <br/> |最近尝试刷新主体的时间戳。如果尚未尝试任何刷新，可以为 null。  <br/> |
|nextTry  <br/> |datetime  <br/> |计划的下一次刷新的时间戳。如果尚未计划进一步刷新，可以为 null。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|prinID  <br/> |主键。  <br/> |
|prinID  <br/> |其查找包含在 tblPrincipal.prinID 表中的外键。  <br/> |
   

