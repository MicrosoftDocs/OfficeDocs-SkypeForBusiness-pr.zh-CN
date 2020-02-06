---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可与节点相关联的注册外接程序的列表。
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812110"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList 是可与节点相关联的注册外接程序的列表。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID，not null  <br/> |外接程序的 GUID。  <br/> |
|siopName  <br/> |nvarchar （50），not null  <br/> |显示-外接程序的名称。  <br/> |
|siopUrl  <br/> |nvarchar （255），not null  <br/> |外接程序的 URL。  <br/> |
   
**Key**

|**列**|**说明**|
|:-----|:-----|
|siopID  <br/> |主键。  <br/> |
   

