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
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可与节点相关联的注册外接程序的列表。
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295172"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList 是可与节点相关联的注册外接程序的列表。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, not null  <br/> |外接程序的 GUID。  <br/> |
|siopName  <br/> |nvarchar (50), not null  <br/> |显示-外接程序的名称。  <br/> |
|siopUrl  <br/> |nvarchar (255), not null  <br/> |外接程序的 URL。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|siopID  <br/> |主键。  <br/> |
   

