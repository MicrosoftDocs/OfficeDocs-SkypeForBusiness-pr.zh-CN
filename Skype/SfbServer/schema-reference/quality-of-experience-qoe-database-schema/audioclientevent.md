---
title: AudioClientEvent 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 每个记录包含一个终结点，音频呼叫的客户端事件。 通常，一个电话有两个记录、 调用方和被调用方。
ms.openlocfilehash: dd910c9abf5cbd8d95a7448f72b49641148a2c64
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="audioclientevent-table"></a>AudioClientEvent 表
 
每个记录包含一个终结点，音频呼叫的客户端事件。 通常，一个电话有两个记录、 调用方和被调用方。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0： 被调用方的数据  <br/> 1： 呼叫者的数据  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 NetworkSendQuality 事件的百分比。  <br/> 根据抖动或数据包丢失的网络质量是严重并正在发送的音频质量的影响。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 ReceiveSendQuality 事件的百分比。  <br/> 根据抖动或数据包丢失的网络质量是严重和影响正在接收音频的质量。  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发延迟事件的百分比。 网络延迟会严重并通过防止交互通信影响的经验  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 LowBandwidth 事件的百分比。 可用的带宽不足以可接受的声音体验。  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话没有足够的 CPU 事件触发的百分比。 没有与当前的形式和使用的应用程序的处理不足的 CPU 周期。 这将导致扭曲与音频通道。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 DeviceHalfDuplexAEC 事件的百分比。 为了防止回响，系统已进入半双工。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 DeviceRenderNotFunctioning 事件的百分比。 目前正用于该会话的呈现设备不能正常工作。 这可能导致单向音频问题。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 DeviceCaptureNotFunctioning 事件的百分比。 会话当前正在使用的捕获设备不能正常工作。 这可能导致单向音频问题。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 DeviceGlitches 事件的百分比。 音频失真导致的呈现中有严重失灵。 由驱动程序问题、 延迟的过程调用 (DPC) 风暴 （驱动程序），以及 CPU 使用率过高，可能会导致这些难题。  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 DeviceLowSNR 事件的百分比。 捕获质量也是非常差，噪音很大或用户正在太远从麦克风。 这将导致失真。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 DeviceLowSpeechLevel 事件的百分比。 用户的语音级别是太低，系统不能增加任何进一步。 这也会导致扭曲或单向音频，所以我们认为。  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |错误状态的会话触发 DeviceClipping 事件的百分比。  <br/> 当附近结束语音剪辑麦克风时，另一头会听到由于剪切变形。 请务必避免附近结束麦克风剪辑。  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 DeviceEchoEvent 事件的百分比。 设备或安装程序导致系统的补偿能力之外的回响。  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态的会话触发 DeviceNearEndToEchoRatio 事件的百分比。 这将影响用户体验，因为它限制了可中断用户是多么容易捕获回音相比，用户的语音值太低。 降低扬声器音量，移动到 talker 的麦克风移近一些。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Bad 状态激发 DeviceMultipleEndpoints 的会话期间的次数。 通过减少呈现卷补偿有多个音频检测到同一会话中的终结点和系统。  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Bad 状态激发 DeviceHowlingEvent 的会话期间的次数。 检测到的音频反馈循环 （如共享音频路径的多个终结点所致）。  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||对于正处于激发 DeviceRenderZeroVolume 的会话的百分比"糟糕状态。 呈现器设备被设置为零卷。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||对于正处于激发 DeviceRenderMute 的会话的百分比"糟糕状态。 呈现器设备已静音。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
   

