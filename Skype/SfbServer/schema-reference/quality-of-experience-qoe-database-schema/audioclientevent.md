---
title: AudioClientEvent 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 每个记录都包含一个终结点，音频呼叫的客户端事件。 通常，一次调用具有两个记录，一个用于呼叫者，一个用于被叫方。
ms.openlocfilehash: 307406446d71adf462cdc8a0345aa823129a8f99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895053"
---
# <a name="audioclientevent-table"></a>AudioClientEvent 表
 
每个记录都包含一个终结点，音频呼叫的客户端事件。 通常，一次调用具有两个记录，一个用于呼叫者，一个用于被叫方。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0： 被叫方的数据  <br/> 1： 呼叫者的数据  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态触发 NetworkSendQuality 事件的会话百分比。  <br/> 网络质量抖动或数据包丢失十分严重，且影响要发送的音频的质量。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态触发 ReceiveSendQuality 事件的会话百分比。  <br/> 网络质量抖动或数据包丢失十分严重，且影响要接收音频的质量。  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话延迟激发错误状态的百分比。 十分严重网络延迟并影响通过防止交互式通信的体验  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话 LowBandwidth 激发错误状态的百分比。 可用带宽不足以获得可接受语音体验。  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |错误状态触发不足 CPU 事件的会话百分比。 有足够 CPU 周期处理与当前形式和使用的应用程序。 此时会扭曲与音频信道。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话 DeviceHalfDuplexAEC 激发错误状态的百分比。 为了防止回声，系统已输入半双工。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话 DeviceRenderNotFunctioning 激发错误状态的百分比。 当前正在使用的会话的呈现设备未正常工作。 这可能会导致单向音频问题。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话 DeviceCaptureNotFunctioning 激发错误状态的百分比。 当前正在使用的会话的捕获设备未正常工作。 这可能会导致单向音频问题。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话 DeviceGlitches 激发错误状态的百分比。 在呈现的音频失真导致的有严重故障。 这些难题可能是由驱动程序问题、 延迟的过程调用 (DPC) 风暴 （驱动程序） 和 CPU 使用率过高导致的。  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话 DeviceLowSNR 激发错误状态的百分比。 或者是很差，捕获质量非常噪音或用户从麦克风太远通话。 这将导致失真。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话 DeviceLowSpeechLevel 激发错误状态的百分比。 用户的语音级别是太低，系统不能增加其任何进一步。 这也会导致失真或感知作为单向音频。  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |错误状态触发 DeviceClipping 事件的会话百分比。  <br/> 当附近端语音剪辑麦克风时，最最终会听到由于剪辑失真。 请务必避免附近端麦克风剪辑。  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话 DeviceEchoEvent 激发错误状态的百分比。 设备或安装程序导致了回声超出补偿系统的能力。  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |会话 DeviceNearEndToEchoRatio 激发错误状态的百分比。 用户的语音是太低与要捕获其影响的用户体验，因为它限制中断用户是多么容易回声。 减少扬声器音量、 麦克风接近移到 talker。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||在错误状态触发 DeviceMultipleEndpoints 事件的会话过程中次数。 检测到同一个会话中的多个音频终结点和系统已通过减少呈现卷补偿。  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |在错误状态触发 DeviceHowlingEvent 事件的会话过程中次数。 检测到的音频回馈循环 （由多个终结点共享音频路径）。  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||会话百分比 DeviceRenderZeroVolume 激发在"错误状态。 呈现设备被设置为零卷。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||会话百分比 DeviceRenderMute 激发在"错误状态。 呈现设备已处于静音状态。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

