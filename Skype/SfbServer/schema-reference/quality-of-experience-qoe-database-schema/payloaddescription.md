---
title: PayloadDescription 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 表是支持表。 每条记录表示一个编解码器, 用于音频或视频会话。
ms.openlocfilehash: 41819c8329802b224bd3848334eddbc9de6935f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294808"
---
# <a name="payloaddescription-table"></a>PayloadDescription 表
 
PayloadDescription 表是支持表。 每条记录表示一个编解码器, 用于音频或视频会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |标识编解码器的唯一号码。  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |唯一  <br/> |编解码器名称。  <br/> |
   

