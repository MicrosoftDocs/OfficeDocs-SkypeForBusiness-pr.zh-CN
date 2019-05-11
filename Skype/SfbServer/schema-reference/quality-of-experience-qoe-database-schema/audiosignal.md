---
title: AudioSignal 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 每条记录代表一个终结点的音频信号指标。 通常，每个呼叫的两个记录、 一个为呼叫者，并且一个被叫方。
ms.openlocfilehash: 676a66cda3c87f5e16c956d23624b28af4b4357f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920248"
---
# <a name="audiosignal-table"></a>AudioSignal 表
 
每条记录代表一个终结点的音频信号指标。 通常，每个呼叫的两个记录、 一个为呼叫者，并且一个被叫方。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0： 被叫方的数据  <br/> 1： 呼叫者的数据  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |代表后模拟增益控制音频信号级别。 此度量单位是 dBmo。 对于可接受的质量，它应至少 30 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |请参阅 SendSignalLevel。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |代表后模拟增益控制音频的噪音级别。 此度量单位是 dBmo。 对于可接受的质量，它应小于 35 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |请参阅 SendNoiseLevel。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |回声返回丢失增强指标。 此度量单位是 dB。 较低值表示减少回声。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |每五分钟的扬声器呈现的平均难题。 良好质量，应小于 1 每五分钟。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |每五分钟的麦克风捕获的平均难题。 良好质量这应该是小于 1 每五分钟。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |麦克风设备时钟的偏移率，相对于 CPU 时钟。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |扬声器设备时钟的偏移率，相对于 CPU 时钟。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |扬声器设备时钟的偏移率，相对于 CPU 时钟。  <br/> 呼叫的最后 20 秒内的平均麦克风捕获流时间戳错误，以毫秒为单位。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |呼叫的最后 20 秒内，平均扬声器呈现流时间戳错误，以毫秒为单位。  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |语音切换是半双工模式，减少了的中断功能。 语音切换条目的原因：  <br/> ENTER_VS_BADTS 0X01  <br/> ENTER_VS_ECHO 0X02  <br/> ENTER_VS_FORCEORCONVERGENCE 0X04  <br/> ENTER_VS_DNLP 0X08  <br/> 原因可以是这些单个原因的组合。 只能通过注册密钥出于测试目的启用 ENTER_VS_FORCEORCONVERGENCE。  <br/> Microsoft Lync Server 2013 中已更改此列的数据类型。  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |回声事件的原因：  <br/> ECHO_EVENT_BAD_TIMESTAMP 0X01  <br/> ECHO_EVENT_POSTAEC_ECHO 0X02  <br/> ECHO_EVENT_ANLP 0X04  <br/> ECHO_EVENT_DNLP 0X08  <br/> ECHO_EVENT_MIC_CLIPPING 0X10  <br/> ECHO_EVENT_BAD_STATE 0X20  <br/> 原因可以是这些单个原因的组合。  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |在麦克风捕获流量中检测回声时的时间百分比。通常，对于耳机或话筒，值较低，而对于扬声器电话或独立扬声器，值较高。对于支持板载声学回声消除的设备，高值表示回声泄漏。对于其他设备，不应使用此指标评估设备质量。  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||在发送流中检测到回声的时的时间的百分比。 在高回声百分比发送流相对值的回声泄漏。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |收到来自网关; 中介服务器上的信号级别这仅适用于中介服务器。 此指标的单位是 dBoV。 良好质量，可接受的范围应 [-30-18 至] dBoV。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |中介服务器的网关上收到的信号级别。 这仅适用于中介服务器。 此指标的单位是 dBoV。 良好质量，可接受的范围应小于-50 dBoV。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |自动增益控制 (AGC) 在中介服务器端。  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |方根 (RMS) 的最多的呼叫的前 30 秒钟的传入信号。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||信道 1 上收到的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||信道 2 上收到的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||信道 1 上收到的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||信道 2 上收到的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||信道 1 上发送的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||信道 2 上发送的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||信道 1 上发送的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||信道 2 上发送的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||在 dBFS 发送到扬声器进行播放的信号级别。 已收到的信号所做的任何提升调整的帐户。 <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||发送到扬声器进行播放信号中的干扰内容 dBFS 中的级别 <br/> |

