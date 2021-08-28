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
ms.localizationpriority: medium
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每条记录都包含视频通话中一个终结点的客户端事件。 通常，一个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。
ms.openlocfilehash: de088fb6f4bb5cd41c4f4be69fba2445c61c3e96
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595252"
---
# <a name="videoclientevent-table"></a>VideoClientEvent 表
 
每条记录都包含视频通话中一个终结点的客户端事件。 通常，一个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |主  <br/> |0：被叫方的数据  <br/> 1：呼叫者的数据  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |针对"Bad"状态触发 LowBandwidth 事件的会话百分比。 可用带宽不足，无法提供可接受的语音体验。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |为"Bad"状态触发 ReceiveSendQuality 事件的会话百分比。  <br/> 抖动或数据包丢失的网络质量十分严重，并且会影响接收的音频质量。  <br/> |
   

