---
title: AudioSignal 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 每个记录表示音频信号测量数据为一个端点。 通常情况下，每次调用具有两个记录、 一种用于调用方，和一种用于被调用方。
ms.openlocfilehash: 25d565538ecdf7cae15ff23f539a2e2eddf8680f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="audiosignal-table"></a>AudioSignal 表
 
每个记录表示音频信号测量数据为一个端点。 通常情况下，每次调用具有两个记录、 一种用于调用方，和一种用于被调用方。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0： 被调用方的数据  <br/> 1： 呼叫者的数据  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |表示后模拟获得控制音频信号级别。 此度量单位是 dBmo。 对于可接受的质量，它应该至少 30 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |请参阅 SendSignalLevel。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |表示后模拟获得控制音频噪声。 此度量单位是 dBmo。 对于可接受的质量，它应该是少于 35 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |请参阅 SendNoiseLevel。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |回声返回丢失增强指标。 此度量单位为 dB。 较低的值表示较少的回响。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |平均每 5 分钟的扬声器呈现的难题。 良好的质量，这应该是每五分钟不少于一次。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |平均每 5 分钟对麦克风捕获的难题。 良好的质量，这应该是每五分钟不少于一次。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |麦克风设备时钟偏移比率，相对于 CPU 时钟。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |演讲者设备时钟偏移比率，相对于 CPU 时钟。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |演讲者设备时钟偏移比率，相对于 CPU 时钟。  <br/> 平均的麦克风捕捉流时间戳错误，以毫秒为单位，在最后 20 秒的呼叫。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |平均的扬声器呈现流时间戳错误，以毫秒为单位，在最后 20 秒的呼叫。  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |语音交换机是半双工模式，减少了的中断能力。 语音交换机条目的原因如下：  <br/> ENTER_VS_BADTS 0X01  <br/> ENTER_VS_ECHO 0X02  <br/> ENTER_VS_FORCEORCONVERGENCE 0X04  <br/> ENTER_VS_DNLP 0X08  <br/> 原因可能是在这些个别原因的组合。 出于测试目的的 regkey 只可以启用 ENTER_VS_FORCEORCONVERGENCE。  <br/> 此列的数据类型已在 Microsoft Lync Server 2013。  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |回音式事件的原因：  <br/> ECHO_EVENT_BAD_TIMESTAMP 0X01  <br/> ECHO_EVENT_POSTAEC_ECHO 0X02  <br/> ECHO_EVENT_ANLP 0X04  <br/> ECHO_EVENT_DNLP 0X08  <br/> ECHO_EVENT_MIC_CLIPPING 0X10  <br/> 0X20 ECHO_EVENT_BAD_STATE  <br/> 原因可能是在这些个别原因的组合。  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |在麦克风捕获流量中检测回声时的时间百分比。通常，对于耳机或话筒，值较低，而对于扬声器电话或独立扬声器，值较高。对于支持板载声学回声消除的设备，高值表示回声泄漏。对于其他设备，不应使用此指标评估设备质量。  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||已发送的流中检测到回音的时的时间的百分比。 在高回声百分比将流发送回显泄漏的指示。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |从该网关; 收到中介服务器的信号强度这仅适用于中介服务器。 此度量单位是 dBoV。 良好的质量，对于可接受的范围应为 [-30 至-18] dBoV。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |从该网关中介服务器上接收到的信号级别。 这仅适用于中介服务器。 此度量单位是 dBoV。 良好的质量，在可接受范围应小于-50 dBoV。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |自动控制 (AGC) 的中介服务器一侧。  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |根均方 (RMS) 到第一个 30 秒的呼叫的传入信号。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||通道 1 上接收到的信号强度。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||2 信道上接收到的信号电平。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||为已接收通道 1 上的噪声级别。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||为已接收通道 2 上的噪声级别。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||为已发送通道 1 上的信号电平。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||为已发送通道 2 上的信号电平。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||为已发送通道 1 上的噪声级别。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||为已发送通道 2 上的噪声级别。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
   

