---
title: Skype for Business Server 2015 中的 ConferenceUris 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表是一个支持表，用于存储已参与数据库中记录的会议会话的各种会议 URI 列表。表中的每条记录代表一个会议 URI。
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816132"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ConferenceUris 表
 
ConfereneUris 表是一个支持表，用于存储已参与数据库中记录的会议会话的各种会议 URI 列表。表中的每条记录代表一个会议 URI。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |主  <br/> |内部使用的时间戳。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |主  <br/> |标识此会议 URI 的唯一编号。  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)   <br/> ||会议 URI。  <br/> |
|**校验和** <br/> |int  <br/> ||ConferenceUri 的校验和。用于增加数据库搜索的速度。  <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |URI 类型，如 conf:chat 代表 IM 会议，conf:audio-video 代表音频/视频会议。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表表。 <br/> |
   

