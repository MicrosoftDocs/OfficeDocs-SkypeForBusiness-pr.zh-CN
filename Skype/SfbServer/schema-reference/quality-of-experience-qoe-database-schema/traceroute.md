---
title: TraceRoute 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表包含来自呼叫的路由信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 323f8160e7543c2fa08bebe9d1805355469acfd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294626"
---
# <a name="traceroute-table"></a>TraceRoute 表
 
TraceRoute 表包含来自呼叫的路由信息。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主、外部  <br/> |通话开始的日期和时间。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主、外部  <br/> |用于区分可能在同一日期和同一时间开始的多个通话的唯一标识符。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主、外部  <br/> |表示通话中使用的视频线路类型。 允许的值包括：  <br/> 0-音频  <br/> 1-视频  <br/> 2全景视频  <br/> 3-应用程序/桌面共享  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |发出呼叫的终结点。  <br/> |
|**跳** <br/> |int  <br/> ||网络跃点/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |外表  <br/> |IP 地址的唯一标识符。 IP 地址信息存储在 "ip 地址"[表](ipaddress.md)中。  <br/> |
|**RTT** <br/> |int  <br/> ||往返时间。 往返时间测量语音数据包到达其目标所需的时间量, 然后发送发送回收到通知的时间。  <br/> |
   

