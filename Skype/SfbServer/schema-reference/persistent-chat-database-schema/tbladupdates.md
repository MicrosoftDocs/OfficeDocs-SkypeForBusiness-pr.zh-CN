---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814680"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，not null  <br/> |已更改对象的主体 GUID。  <br/> |
|prinADPath  <br/> |nvarchar （384），not null  <br/> |对象的可分辨名称。  <br/> |
|prinAttributesChanged  <br/> |位，not null  <br/> |如果对象的至少一个属性发生更改，则为 True。  <br/> |
|prinMembersChanged  <br/> |位，not null  <br/> |如果成员身份已更改，则为 True。  <br/> |
|prinAffiliationsChanged  <br/> |位，not null  <br/> |未使用。  <br/> |
|prinDeleted  <br/> |位，not null  <br/> |如果对象已删除，则为 True。  <br/> |
|lastUpdated  <br/> |datetime，not null  <br/> |插入行的时间戳。  <br/> |
   

