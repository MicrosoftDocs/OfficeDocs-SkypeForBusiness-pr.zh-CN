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
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831482"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList 是可与节点关联的注册外接程序的列表。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID，不为 null  <br/> |外接程序的 GUID。  <br/> |
|siopName  <br/> |nvarchar (50)，不为 null  <br/> |外接程序的显示名称。  <br/> |
|siopUrl  <br/> |nvarchar (255)，不为 null  <br/> |外接程序的 URL。  <br/> |
   
**注册表项**

|**列**|**说明**|
|:-----|:-----|
|siopID  <br/> |主键。  <br/> |
   

