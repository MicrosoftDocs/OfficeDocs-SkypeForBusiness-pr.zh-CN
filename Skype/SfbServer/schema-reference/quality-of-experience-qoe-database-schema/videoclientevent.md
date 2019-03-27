---
title: VideoClientEvent 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每个记录包含在视频呼叫的一个端点的客户端事件。 通常，一次调用具有两个记录，一个用于呼叫者，一个用于被叫方。
ms.openlocfilehash: 314e4df9313a3d111d71b6eaa06565edcbb765d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891235"
---
# <a name="videoclientevent-table"></a>VideoClientEvent 表
 
每个记录包含在视频呼叫的一个端点的客户端事件。 通常，一次调用具有两个记录，一个用于呼叫者，一个用于被叫方。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0： 被叫方的数据  <br/> 1： 呼叫者的数据  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |会话 LowBandwidth 激发错误状态的百分比。 可用带宽不足以获得可接受语音体验。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |错误状态触发 ReceiveSendQuality 事件的会话百分比。  <br/> 网络质量抖动或数据包丢失非常严重，影响收到的音频的质量。  <br/> |
   

