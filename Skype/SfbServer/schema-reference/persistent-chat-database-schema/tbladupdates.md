---
title: tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含尚未处理后续活动目录同步步骤通过 Active Directory 域服务更改。
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates 包含尚未处理后续活动目录同步步骤通过 Active Directory 域服务更改。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不为空  <br/> |主体的更改的对象的 GUID。  <br/> |
|prinADPath  <br/> |nvarchar (384) 不为空  <br/> |对象的可分辨的名称。  <br/> |
|prinAttributesChanged  <br/> |位，不为空  <br/> |如果至少一个对象的属性更改，则为 true。  <br/> |
|prinMembersChanged  <br/> |位，不为空  <br/> |如果更改的成员资格，则为 true。  <br/> |
|prinAffiliationsChanged  <br/> |位，不为空  <br/> |不使用。  <br/> |
|prinDeleted  <br/> |位，不为空  <br/> |如果对象已被删除，则为 true。  <br/> |
|上次更新  <br/> |日期时间不为空  <br/> |插入行的时间戳。  <br/> |
   

