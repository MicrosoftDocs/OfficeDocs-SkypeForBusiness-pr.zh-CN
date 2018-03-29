---
title: 在业务服务器 2015年的 Skype 的 ConferenceUris 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表是一个支持的表来存储各种会议参加讲座记录在数据库中的 Uri 的列表。 每个表中的记录表示一个会议的 URI。
ms.openlocfilehash: 921bb448ffe50d62aa7680db0e8097c186eef8e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 ConferenceUris 表
 
ConfereneUris 表是一个支持的表来存储各种会议参加讲座记录在数据库中的 Uri 的列表。 每个表中的记录表示一个会议的 URI。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |内部使用的时间戳。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |标识的 URI 的这次会议的唯一编号。  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||会议的 URI。  <br/> |
|**校验和** <br/> |int  <br/> ||ConferenceUri 的校验和。 使用为增加数据库搜索的速度。  <br/> |
|**UriTypeId** <br/> |int  <br/> |外  <br/> |URI 类型，如 IM 会议或 conf:audio conf:chat-视频的音频/视频会议。 [UriTypes](uritypes.md)表的详细信息，请参阅。 <br/> |
   

