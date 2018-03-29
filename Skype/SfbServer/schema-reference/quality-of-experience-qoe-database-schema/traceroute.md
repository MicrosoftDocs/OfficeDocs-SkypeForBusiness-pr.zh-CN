---
title: 路由追踪表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: 路由追踪表包含来自呼叫路由信息。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: e8796b164bd6a0f2809025b784ada9d12dda449b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="traceroute-table"></a>路由追踪表
 
路由追踪表包含来自呼叫路由信息。 在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主键和外  <br/> |日期和时间的呼叫开始。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主键和外  <br/> |用来区分可能在同一日期，在同一时间开始的多个调用的唯一标识符。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主键和外  <br/> |表示在调用中使用的视频线的类型。 允许的值包括：  <br/> 0-音频  <br/> 1-视频  <br/> 2-全景视频  <br/> 3/桌面应用程序共享  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |将调用的终结点。  <br/> |
|**跃点** <br/> |int  <br/> ||网络跃点 /  <br/> |
|**IPAddressKey** <br/> |int  <br/> |外  <br/> |IP 地址的唯一标识符。 [Ip 地址表](ipaddress.md)中存储 IP 地址信息。  <br/> |
|**RTT** <br/> |int  <br/> ||往返时间。 往返时间测量的语音数据包到达其目的地，然后发送回通知已被接收所花费的时间。  <br/> |
   

