---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可与节点关联的注册外接程序的列表。
ms.openlocfilehash: 3f1ad0461bc227970d4a2a0864dbc6318ef0af32d854402180321bab74aa91e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305374"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList 是可与节点关联的注册外接程序的列表。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID，不为 null  <br/> |外接程序的 GUID。  <br/> |
|siopName  <br/> |nvarchar (50)，不为 null  <br/> |外接程序的显示名称。  <br/> |
|siopUrl  <br/> |nvarchar (255)，不为 null  <br/> |外接程序的 URL。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|siopID  <br/> |主键。  <br/> |
   

