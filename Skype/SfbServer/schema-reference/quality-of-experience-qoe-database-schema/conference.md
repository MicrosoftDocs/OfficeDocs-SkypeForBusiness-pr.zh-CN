---
title: Conference 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会议表是支持表。 每条记录表示一个会议或对等会话。
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810300"
---
# <a name="conference-table"></a>Conference 表
 
会议表是支持表。 每条记录表示一个会议或对等会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |标识此会议记录的唯一号码。  <br/> |
|**ConfURI** <br/> |nvarchar （450）  <br/> |唯一  <br/> |会议 URI （如果这是会议）或 DialogID （如果这是对等会话）。  <br/> |
|**检查** <br/> |int  <br/> |食指  <br/> |会议 URI 的校验和。 此功能在内部使用。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

