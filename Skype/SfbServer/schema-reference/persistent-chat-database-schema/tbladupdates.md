---
title: tblADUpdates
ms.reviewer: null
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含尚未由稍后的 Active Directory 同步步骤处理的 Active Directory 域服务更改。
---

# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates 包含尚未由稍后的 Active Directory 同步步骤处理的 Active Directory 域服务更改。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为 null  <br/> |被更改对象的主体 GUID。  <br/> |
|prinADPath  <br/> |nvarchar (384)，不为 null  <br/> |对象的可分辨名称。  <br/> |
|prinAttributesChanged  <br/> |bit，不为 null  <br/> |如果对象至少有一个属性被更改，则为 True。  <br/> |
|prinMembersChanged  <br/> |bit，不为 null  <br/> |如果成员身份被更改，则为 True。  <br/> |
|prinAffiliationsChanged  <br/> |bit，不为 null  <br/> |未使用。  <br/> |
|prinDeleted  <br/> |bit，不为 null  <br/> |如果对象已删除，则为 True。  <br/> |
|lastUpdated  <br/> |datetime，不为 null  <br/> |插入行时的时间戳。  <br/> |
   

