---
title: AudioSignal 表
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
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 每条记录表示一个终结点的音频信号指标。 通常，每个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。
ms.openlocfilehash: 1e4f7bf92448d4f2efefe3bfad4e1ca556ad44b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761780"
---
# <a name="audiosignal-table"></a>AudioSignal 表
 
每条记录表示一个终结点的音频信号指标。 通常，每个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |主  <br/> |0：被叫方的数据  <br/> 1：呼叫者的数据  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |代表模拟后增益控制音频信号级别。 此指标的单位为 dBmo。 对于可接受的质量，它应至少为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |请参阅 SendSignalLevel。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |代表模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 对于可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |请参阅 SendNoiseLevel。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |回声返回丢失增强功能指标。 此指标的单位为 dB。 较低的值表示回声较少。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |每五分钟一次用于呈现的呈现的平均故障数。 为保证良好的质量，这应小于每五分钟一个。 A/V 会议服务器、中介服务器或 IP 电话未报告。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |麦克风捕获每五分钟的平均故障数。 为保证良好的质量，该时间应小于每五分钟一个。 A/V 会议服务器、中介服务器或 IP 电话未报告。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal (9，2)   <br/> | <br/> |麦克风设备时钟偏移量，相对于 CPU 时钟。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal (9，2)   <br/> | <br/> |扬声器设备时钟的偏移量，相对于 CPU 时钟。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal (9，2)   <br/> | <br/> |扬声器设备时钟的偏移量，相对于 CPU 时钟。  <br/> 呼叫的最后 20 秒的平均麦克风捕获流时间戳错误（以毫秒为单位）。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal (9，2)   <br/> | <br/> |呼叫的最后 20 秒的平均扬声器呈现流时间戳错误（以毫秒为单位）。  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |语音交换机是半双工模式，中断能力降低。 语音切换条目的原因：  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 原因可能是这些单个原因的组合。 ENTER_VS_FORCEORCONVERGENCE仅能由 regkey 启用用于测试目的。  <br/> 此数据类型的名称在 Microsoft Lync Server 2013 中已更改。  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |回声事件的原因：  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 原因可能是这些单个原因的组合。  <br/> |
|**EchoPercentMicIn** <br/> |decimal (5，2)   <br/> | <br/> |在麦克风捕获流中检测到回声的时间百分比。 通常，耳机或话筒的值较低，而扬声器电话或独立扬声器的值较高。 对于支持板载回声消除的设备，高值表示回声泄漏。 对于其他设备，不应使用此指标评估设备质量。  <br/> |
|**EchoPercentSend** <br/> |decimal (5，2)   <br/> ||在发送的流中检测到回声的时间百分比。 发送流的高回声百分比表示回声泄漏。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |从网关接收中介服务器的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为获得良好的质量，可接受的范围应为 [-30 至 -18] dBoV。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |从网关接收中介服务器的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为保证良好的质量，可接受的范围应小于 -50 dBoV。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |自动增益控制 (中介) AGC 服务器。  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |根平均 (RMS) 呼叫前 30 秒传入信号的平均值。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||通道 1 上接收的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||通道 2 上接收的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||通道 1 上接收到的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||通道 2 上接收到的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||通道 1 上发送的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||通道 2 上发送的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||通道 1 上发送的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||通道 2 上发送的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||发送到扬声器以播放的信号的 dBFS 级别。 对接收的信号进行的任何收益调整的帐户。 <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||发送到扬声器进行播放的信号中噪音内容的 dBFS 级别 <br/> |

