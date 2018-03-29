---
title: VideoClientEvent 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每个记录包含一个终结点，视频通话的客户端事件。 通常，一个电话有两个记录、 调用方和被调用方。
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="videoclientevent-table"></a>VideoClientEvent 表
 
每个记录包含一个终结点，视频通话的客户端事件。 通常，一个电话有两个记录、 调用方和被调用方。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0： 被调用方的数据  <br/> 1： 呼叫者的数据  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |错误状态的会话触发 LowBandwidth 事件的百分比。 可用的带宽不足以可接受的声音体验。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |错误状态的会话触发 ReceiveSendQuality 事件的百分比。  <br/> 根据抖动或数据包丢失的网络质量严重，而且影响所接收到的音频的质量。  <br/> |
   

