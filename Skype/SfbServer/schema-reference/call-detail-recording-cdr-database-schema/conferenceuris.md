---
title: Skype for Business Server 2015 中的 ConferenceUris 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表是一个支持表, 用于存储参与数据库中记录的会议会话的各种会议 Uri 的列表。 表中的每条记录表示一个会议 URI。
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296390"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ConferenceUris 表
 
ConfereneUris 表是一个支持表, 用于存储参与数据库中记录的会议会话的各种会议 Uri 的列表。 表中的每条记录表示一个会议 URI。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |时间戳, 内部使用。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |标识此会议 URI 的唯一号码。  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||会议 URI。  <br/> |
|**检查** <br/> |int  <br/> ||ConferenceUri 的校验和。 用于提高数据库搜索的速度。  <br/> |
|**UriTypeId** <br/> |int  <br/> |外表  <br/> |URI 类型, 例如会议: 用于即时消息会议的聊天或会议: 音频-音频/视频会议的视频。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)表。 <br/> |
   

