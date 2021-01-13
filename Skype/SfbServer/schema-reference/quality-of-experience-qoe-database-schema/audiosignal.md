---
title: AudioSignal 表
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
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 每条记录表示一个终结点的音频信号指标。 通常，每个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。
ms.openlocfilehash: ab918941357b85c6bcb25dcbaeb93a7be9c55f2d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809652"
---
# <a name="audiosignal-table"></a>AudioSignal 表
 
每条记录表示一个终结点的音频信号指标。 通常，每个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。 
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**FromCaller** <br/> |bit  <br/> |主  <br/> |0：被叫方的数据  <br/> 1：呼叫者的数据  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |代表模拟后增益控制音频信号级别。 此指标的单位为 dBmo。 对于可接受的质量，它应至少为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |请参阅 SendSignalLevel。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |代表模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 对于可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |请参阅 SendNoiseLevel。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |回声返回丢失增强指标。 此指标的单位为 dB。 较低的值表示较少的回声。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |每五分钟呈现一次平均故障数。 为保证良好的质量，此时间应小于每五分钟一个。 A/V 会议服务器、中介服务器或 IP 电话未报告。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |麦克风捕获每五分钟的平均故障数。 为保证良好的质量，此时间应小于每五分钟一个。 A/V 会议服务器、中介服务器或 IP 电话未报告。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal (9，2)   <br/> | <br/> |相对于 CPU 时钟的麦克风设备时钟偏移速率。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal (9，2)   <br/> | <br/> |扬声器设备时钟偏移速率，相对于 CPU 时钟。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal (9，2)   <br/> | <br/> |扬声器设备时钟偏移速率，相对于 CPU 时钟。  <br/> 呼叫的最后 20 秒的平均麦克风捕获流时间戳错误（以毫秒为单位）。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal (9，2)   <br/> | <br/> |呼叫的最后 20 秒的平均扬声器呈现流时间戳错误（以毫秒为单位）。  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |语音切换是半双工模式，中断能力降低。 语音交换机输入的原因：  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 原因可能是这些单个原因的组合。 ENTER_VS_FORCEORCONVERGENCE只能由 regkey 启用用于测试目的。  <br/> 此数据类型在 Microsoft Lync Server 2013 中已更改。  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |回声事件的原因：  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 原因可能是这些单个原因的组合。  <br/> |
|**EchoPercentMicIn** <br/> |decimal (5，2)   <br/> | <br/> |在麦克风捕获流中检测到回声的时间百分比。 通常，耳机或话筒的值较低，而扬声器电话或独立扬声器的值较高。 对于支持板载回声消除的设备，高值表示回声泄漏。 对于其他设备，此指标不应用于评估设备质量。  <br/> |
|**EchoPercentSend** <br/> |decimal (5，2)   <br/> ||在已发送流中检测到回声的时间百分比。 发送流中的高回声百分比表示回声泄漏。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |从网关接收中介服务器的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为获得良好的质量，可接受的范围应为 [-30 至 -18] dBoV。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |从网关接收中介服务器上的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了质量良好，可接受的范围应小于 -50 dBoV。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |中介服务器端 (AGC) 自动获取控制。  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |根平均值 (RMS) 呼叫前 30 秒传入信号的平均值。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||通道 1 上接收的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||通道 2 上接收的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||通道 1 上收到的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||通道 2 上收到的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||通道 1 上发送的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||通道 2 上发送的信号级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||通道 1 上发送的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||通道 2 上发送的噪音级别。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||发送到扬声器以播放的信号的 dBFS 级别。 对收到的信号进行的任何收益调整的帐户。 <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||发送到扬声器进行播放的信号中噪音内容的 dBFS 级别 <br/> |

