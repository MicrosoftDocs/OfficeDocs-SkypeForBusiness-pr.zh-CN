---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含尚未由后面的 Active Directory 同步步骤处理的 Active Directory 域服务更改。
ms.openlocfilehash: 4ed1abe2d5926c8b34ddccb28133ecc34ddaa03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929859"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates 包含尚未由后面的 Active Directory 同步步骤处理的 Active Directory 域服务更改。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为 null  <br/> |更改的对象的主体 GUID。  <br/> |
|prinADPath  <br/> |nvarchar (384)，不为 null  <br/> |对象的可分辨的名称。  <br/> |
|prinAttributesChanged  <br/> |bit，不为 null  <br/> |如果对象至少一个属性更改为 true。  <br/> |
|prinMembersChanged  <br/> |bit，不为 null  <br/> |如果成员身份被更改，则为 true。  <br/> |
|prinAffiliationsChanged  <br/> |bit，不为 null  <br/> |不使用。  <br/> |
|prinDeleted  <br/> |bit，不为 null  <br/> |如果对象已删除，则为 true。  <br/> |
|lastUpdated  <br/> |datetime，不为 null  <br/> |插入行的时间戳。  <br/> |
   

