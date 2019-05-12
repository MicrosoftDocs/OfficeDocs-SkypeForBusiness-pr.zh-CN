---
title: Conference 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Conference 表是一个支持表。 每条记录代表一个会议或对等会话。
ms.openlocfilehash: 0914e98aed4aea16e5301ccae454e925663454a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920164"
---
# <a name="conference-table"></a>Conference 表
 
Conference 表是一个支持表。 每条记录代表一个会议或对等会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |标识此会议记录的唯一编号。  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |唯一  <br/> |会议 URI 如果这是 dialogid 会议，如果它是对等会话。  <br/> |
|**校验和** <br/> |int  <br/> |索引  <br/> |会议 URI 的校验和。 这是在内部使用。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

