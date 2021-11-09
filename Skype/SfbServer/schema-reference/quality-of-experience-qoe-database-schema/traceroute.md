---
title: TraceRoute 表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表包含来自呼叫的路由信息。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 8a4ca952bb2b6ced61f4b1aae6745a5e1b68d417
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840914"
---
# <a name="traceroute-table"></a>TraceRoute 表
 
TraceRoute 表包含来自呼叫的路由信息。 此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主、外  <br/> |呼叫开始的日期和时间。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主、外  <br/> |用来区分可能在相同日期和相同时间开始的多个呼叫的唯一标识符。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主、外  <br/> |表示在呼叫中使用的视频行的类型。允许的值包括：  <br/> 0 - 音频  <br/> 1 - 视频  <br/> 2 - 全景视频  <br/> 3 - 应用程序/桌面共享  <br/> |
|**FromCaller** <br/> |bit  <br/> |主  <br/> |发起呼叫的终结点。  <br/> |
|**跃点** <br/> |int  <br/> ||网络跃点/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Foreign  <br/> |IP 地址的唯一标识符。 IP 地址信息存储在 [IPAddress 表中](ipaddress.md)。  <br/> |
|**RTT** <br/> |int  <br/> ||来回行程的时间。来回行程的时间会测量语音数据包到达其目标，然后将其所收到的通知发送回来所需的时间量。  <br/> |
   

