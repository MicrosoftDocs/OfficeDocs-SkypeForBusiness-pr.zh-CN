---
title: ConferenceUris 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表是一个支持表，用于存储各种会议已参与记录数据库中的会议会话的 Uri 的列表。 表中的每条记录代表一个会议 URI。
ms.openlocfilehash: 70cb3ccecf1c63dd128cbffd6ac205e77c771835
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901064"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>ConferenceUris 表中的业务服务器 2015 Skype
 
ConfereneUris 表是一个支持表，用于存储各种会议已参与记录数据库中的会议会话的 Uri 的列表。 表中的每条记录代表一个会议 URI。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |内部使用的时间戳。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |标识此会议 URI 的唯一编号。  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||会议 URI。  <br/> |
|**校验和** <br/> |int  <br/> ||ConferenceUri 校验和。 使用到提高的搜索数据库的速度。  <br/> |
|**UriTypeId** <br/> |int  <br/> |外  <br/> |URI 类型，如 IM 会议，或 conf:audio conf:chat-音频/视频会议的视频。 [UriTypes 表](uritypes.md)表的详细信息，请参阅。 <br/> |
   

