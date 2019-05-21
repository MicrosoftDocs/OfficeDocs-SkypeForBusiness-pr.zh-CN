---
title: AudioClientEvent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 每条记录都包含音频呼叫中一个终结点的客户端事件。 通常, 一个通话有两个记录, 一个用于呼叫方, 另一个用于被呼叫方。
ms.openlocfilehash: 1f754f9b7ef19919503988d40347fdeb218830d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295102"
---
# <a name="audioclientevent-table"></a>AudioClientEvent 表
 
每条记录都包含音频呼叫中一个终结点的客户端事件。 通常, 一个通话有两个记录, 一个用于呼叫方, 另一个用于被呼叫方。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 被调用方的数据  <br/> 1: 调用方的数据  <br/> |
|**NetworkSendQualityEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 NetworkSendQuality 事件的百分比。  <br/> "抖动" 或 "数据包丢失" 方面的网络质量非常严重, 影响音频的质量。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 ReceiveSendQuality 事件的百分比。  <br/> "抖动" 或 "数据包丢失" 方面的网络质量非常严重, 影响了接收音频的质量。  <br/> |
|**NetworkDelayEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比延迟事件针对 "错误" 状态引发。 网络延迟非常严重, 并通过阻止交互式通信影响体验  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 LowBandwidth 事件的百分比。 可用带宽不足以获得可接受的语音体验。  <br/> |
|**CPUInsufficientEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发的 CPU 事件不足。 没有足够的 CPU 周期用于处理当前形式和正在使用的应用程序。 这将导致音频通道出现扭曲。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 DeviceHalfDuplexAEC 事件的百分比。 为了防止回声, 系统已输入半双工。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 DeviceRenderNotFunctioning 事件的百分比。 当前用于会话的渲染设备不能正常工作。 这可能会导致单向音频问题。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 DeviceCaptureNotFunctioning 事件的百分比。 当前用于会话的捕获设备不能正常工作。 这可能会导致单向音频问题。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 DeviceGlitches 事件的百分比。 呈现导致扭曲的音频有严重的难题。 这些故障可能由驱动程序问题、延期过程调用 (DPC) 风暴 (驱动程序) 和高 CPU 使用率导致。  <br/> |
|**DeviceLowSNREventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 DeviceLowSNR 事件的百分比。 捕获质量非常差, 很大噪音, 或者用户距离麦克风太远。 这将导致扭曲。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 DeviceLowSpeechLevel 事件的百分比。 用户的语音级别太低, 系统无法再进一步增加。 这可能会导致扭曲或视为单向音频。  <br/> |
|**DeviceClippingEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 DeviceClipping 事件的百分比。  <br/> 近距离的语音剪辑时, 麦克风的最大声音将因剪辑而被听到。 避免接近结束的麦克风剪辑非常重要。  <br/> |
|**DeviceEchoEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 DeviceEchoEvent 事件的百分比。 设备或安装程序导致回声超出了系统进行补偿的能力。  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |十进制 (5, 2)  <br/> | <br/> |会话百分比为 "坏" 状态引发 DeviceNearEndToEchoRatio 事件的百分比。 与正在捕获的回显相比, 用户的语音太低, 这会影响用户体验, 因为它限制了中断用户的难易程度。 缩小扬声器音量, 将麦克风移近讲话者。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||会话期间的次数 DeviceMultipleEndpoints 事件针对 "错误" 状态引发。 检测到同一会话中有多个音频终结点, 并且系统通过减少呈现音量进行了补偿。  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |会话期间的次数 DeviceHowlingEvent 事件针对 "错误" 状态引发。 检测到音频反馈循环 (由多个终结点共享音频路径引起)。  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |十进制 (5, 2)  <br/> ||触发 DeviceRenderZeroVolume 事件以处于 "错误" 状态的会话百分比。 呈现设备已设置为零卷。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |十进制 (5, 2)  <br/> ||触发 DeviceRenderMute 事件以处于 "错误" 状态的会话百分比。 呈现设备已静音。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
   

