---
title: TraceRoute 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表包含来自呼叫路由信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 741eaabbe94ee1849bd5a7d5e516714861658d7e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212072"
---
# <a name="traceroute-table"></a>TraceRoute 表
 
TraceRoute 表包含来自呼叫路由信息。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主、 外  <br/> |日期和呼叫开始的时间。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主、 外  <br/> |用来区分可能在相同日期和相同时间开始的多个呼叫的唯一标识符。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主、 外  <br/> |代表在呼叫中使用的视频线的类型。 允许的值包括：  <br/> 0-音频  <br/> 1-视频  <br/> 2-全景视频  <br/> 3-应用程序/桌面共享  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |发出呼叫的终结点。  <br/> |
|**跃点** <br/> |int  <br/> ||网络跃点 /  <br/> |
|**IPAddressKey** <br/> |int  <br/> |外  <br/> |IP 地址的唯一标识符。 [IPAddress 表](ipaddress.md)中存储的 IP 地址信息。  <br/> |
|**RTT** <br/> |int  <br/> ||往返时间。 往返时间度量语音数据包可以到达其目标，然后发送后已被接收的通知所需的时间量。  <br/> |
   

