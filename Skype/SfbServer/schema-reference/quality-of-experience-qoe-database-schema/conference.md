---
title: Conference 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Conference 表是一个支持表。 每条记录代表一个会议或对等会话。
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212261"
---
# <a name="conference-table"></a>Conference 表
 
Conference 表是一个支持表。 每条记录代表一个会议或对等会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |标识此会议记录的唯一编号。  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |唯一  <br/> |会议 URI 如果这是 dialogid 会议，如果它是对等会话。  <br/> |
|**校验和** <br/> |int  <br/> |索引  <br/> |会议 URI 的校验和。 这是在内部使用。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

