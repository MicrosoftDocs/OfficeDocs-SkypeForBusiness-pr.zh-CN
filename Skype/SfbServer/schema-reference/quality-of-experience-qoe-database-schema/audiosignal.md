---
title: AudioSignal 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 每条记录表示一个终结点的音频信号指标。 通常, 每个通话都有两条记录, 一个用于呼叫方, 另一个用于被呼叫方。
ms.openlocfilehash: f8d617e96fe3427493bcb9e4cc70008fedae72e7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295074"
---
# <a name="audiosignal-table"></a>AudioSignal 表
 
每条记录表示一个终结点的音频信号指标。 通常, 每个通话都有两条记录, 一个用于呼叫方, 另一个用于被呼叫方。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: 被调用方的数据  <br/> 1: 调用方的数据  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |表示模拟后增益控制音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |请参阅 SendSignalLevel。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |表示模拟后增益控制音频噪声级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |请参阅 SendNoiseLevel。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |回音返回损失增强指标。 此指标的单位为 dB。 较低的值表示较少的回声。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |扬声器呈现每五分钟的平均故障。 为了获得良好的质量, 这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |麦克风捕获每五分钟的平均故障。 为了获得良好的质量, 这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |十进制 (9, 2)  <br/> | <br/> |麦克风设备时钟相对于 CPU 时钟的偏移速率。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |十进制 (9, 2)  <br/> | <br/> |扬声器设备时钟相对于 CPU 时钟的偏移速率。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |十进制 (9, 2)  <br/> | <br/> |扬声器设备时钟相对于 CPU 时钟的偏移速率。  <br/> 在呼叫的最后20秒内, 麦克风捕获流时间戳的平均时间戳错误 (以毫秒为单位)。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |十进制 (9, 2)  <br/> | <br/> |在呼叫的最后20秒内, 演讲者渲染流的时间戳错误 (以毫秒为单位)。  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |语音开关是一种具有更低中断能力的半双工模式。 语音切换条目的原因:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 原因可能是这些个别原因的组合。 ENTER_VS_FORCEORCONVERGENCE 只能由 regkey for 测试用途启用。  <br/> 在 Microsoft Lync Server 2013 中, 此列的数据类型已更改。  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |回声事件的原因:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 原因可能是这些个别原因的组合。  <br/> |
|**EchoPercentMicIn** <br/> |十进制 (5, 2)  <br/> | <br/> |在麦克风捕获流量中检测回声时的时间百分比。通常，对于耳机或话筒，值较低，而对于扬声器电话或独立扬声器，值较高。对于支持板载声学回声消除的设备，高值表示回声泄漏。对于其他设备，不应使用此指标评估设备质量。  <br/> |
|**EchoPercentSend** <br/> |十进制 (5, 2)  <br/> ||在发送流中检测到回显的时间百分比。 发送流中的高回显百分比表示回声泄漏。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |从网关在中介服务器上收到信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量, 可接受的范围应为 [-30 至-18] dBoV。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |从网关在中介服务器上接收信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得优质, 可接受范围应小于-50 dBoV。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |中介服务器端的自动增益控制 (AGC)。  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |呼叫的前30秒内的传入信号的根平均值 (RMS)。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||频道1上接收的信号级别。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||频道2上接收的信号级别。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||频道1上接收的噪音级别。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||频道2上接收的噪音级别。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||频道1上发送的信号级别。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||频道2上发送的信号级别。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||频道1上发送的噪音级别。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||频道2上发送的噪音级别。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||DBFS 中发送到扬声器的信号的级别。 对收到的信号进行的任何增益调整帐户。 <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||DBFS 中发送到扬声器播放信号内容的噪音内容的级别 <br/> |

