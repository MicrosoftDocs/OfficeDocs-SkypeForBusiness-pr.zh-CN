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
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会议表是支持表。 每条记录表示一个会议或对等会话。
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295011"
---
# <a name="conference-table"></a>Conference 表
 
会议表是支持表。 每条记录表示一个会议或对等会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |标识此会议记录的唯一号码。  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |唯一  <br/> |会议 URI (如果这是会议) 或 DialogID (如果这是对等会话)。  <br/> |
|**检查** <br/> |int  <br/> |食指  <br/> |会议 URI 的校验和。 此功能在内部使用。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

