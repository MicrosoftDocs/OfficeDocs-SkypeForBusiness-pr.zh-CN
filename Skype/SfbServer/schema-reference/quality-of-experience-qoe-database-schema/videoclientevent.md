---
title: VideoClientEvent 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每条记录都包含视频呼叫中一个终结点的客户端事件。 通常，一个呼叫有两条记录，一条用于呼叫者，另一条用于被叫方。
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821392"
---
# <a name="videoclientevent-table"></a>VideoClientEvent 表
 
每条记录都包含视频呼叫中一个终结点的客户端事件。 通常，一个呼叫有两条记录，一条用于呼叫者，另一条用于被叫方。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |主  <br/> |0：被叫方的数据  <br/> 1：呼叫者的数据  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |因"错误"状态触发 LowBandwidth 事件的会话百分比。 可用带宽不足，无法提供可接受的语音体验。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |因"错误"状态触发 ReceiveSendQuality 事件的会话百分比。  <br/> 抖动或数据包丢失方面的网络质量十分严重，并影响所接收音频的质量。  <br/> |
   

