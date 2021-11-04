---
title: AudioClientEvent 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 每条记录都包含音频呼叫中一个终结点的客户端事件。 通常，一个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。
ms.openlocfilehash: a7e5e481fd9398532212f4bda767bab83815250c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767310"
---
# <a name="audioclientevent-table"></a>AudioClientEvent 表
 
每条记录都包含音频呼叫中一个终结点的客户端事件。 通常，一个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |主  <br/> |0：被叫方的数据  <br/> 1：呼叫者的数据  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 NetworkSendQuality 事件的会话百分比。  <br/> 抖动或数据包丢失的网络质量十分严重，并且会影响发送的音频质量。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 ReceiveSendQuality 事件的会话百分比。  <br/> 抖动或数据包丢失的网络质量十分严重，并且会影响接收的音频质量。  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 Delay 事件的会话百分比。 网络延迟十分严重，并且会阻止交互式通信，从而影响体验  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |针对"Bad"状态触发 LowBandwidth 事件的会话百分比。 可用带宽不足，无法提供可接受的语音体验。  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |会话因"错误"状态而触发的 CPU 事件不足的百分比。 对于当前使用中的形式和应用程序，处理 CPU 周期不足。 这会导致音频通道失真。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 DeviceHalfDuplexAEC 事件的会话百分比。 为了防止回声，系统已进入半双工。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 DeviceRenderNotFunctioning 事件的会话百分比。 当前正用于会话的呈现设备无法正常工作。 这可能会导致单向音频问题。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 DeviceCaptureNotFunctioning 事件的会话百分比。 当前用于会话的捕获设备无法正常工作。 这可能会导致单向音频问题。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 DeviceGlitches 事件的会话百分比。 音频呈现存在严重故障，从而导致失真。 这些故障可能是由驱动程序问题、DPC (延迟过程调用) 大量 (驱动程序) 高 CPU 使用率造成的。  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 DeviceLowSNR 事件的会话百分比。 捕获质量非常差，非常干扰或用户离麦克风太远了。 这可能会导致失真。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 DeviceLowSpeechLevel 事件的会话百分比。 用户的语音级别太低，系统无法进一步增加语音级别。 这可能会导致失真或被感知为单向音频。  <br/> |
|**DeviceClippingEventRatio** <br/> |十 (5，2)   <br/> | <br/> |为"Bad"状态触发 DeviceClipping 事件的会话百分比。  <br/> 当近端语音剪辑麦克风时，远端会听到由于剪裁而失真。 避免近端麦克风剪辑很重要。  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 DeviceEchoEvent 事件的会话百分比。 设备或设置导致回声超出系统进行补偿的能力。  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal (5，2)   <br/> | <br/> |为"Bad"状态触发 DeviceNearEndToEchoRatio 事件的会话百分比。 与捕获的回声相比，用户语音太低，这会影响用户体验，因为它限制了中断用户有多容易。 降低扬声器音量，将麦克风移到距离扬声器更近的位置。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||会话期间为"Bad"状态触发 DeviceMultipleEndpoints 事件的时间。 在同一会话中检测到多个音频终结点，并且系统通过减少呈现量而具有大量音频终结点。  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |会话期间为"Bad"状态触发 DeviceHowlingEvent 事件的时间。 检测到音频反馈 (多个终结点共享音频路径) 。  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal (5，2)   <br/> ||由于状态为"Bad"而触发的 DeviceRenderZeroVolume 事件的会话百分比。 呈现设备已设置为零音量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal (5，2)   <br/> ||由于状态为"Bad"而触发的 DeviceRenderMute 事件的会话百分比。 呈现设备已静音。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

