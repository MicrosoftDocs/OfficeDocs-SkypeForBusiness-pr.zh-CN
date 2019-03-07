---
title: 通话质量仪表板中的流分类
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 了解如何在 Microsoft Teams 和 Skype for Business Online 的呼叫质量仪表板中进行流质量分类。
ms.openlocfilehash: 9a25e44393cbe8660687451fea5163f064c16240
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460305"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>通话质量仪表板中的流分类

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>分类器定义

Streams in CQD are classified as good, poor, or unclassified based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables below. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a poor classification. See [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for more information on these dimensions.

### <a name="audio-classifier"></a>音频分类器

如果满足以下一个或多个条件，则音频流标记为“差”：

|**指标**|**条件**|**解释**|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1.0|Average Network Mean Opinion Score degradation for stream. Represents how much the network loss and jitter has impacted the quality of received audio.|
|Round Trip|> 500|计算的平均网络传播往返时间，根据 RFC3550 以毫秒为单位指定。|
|Packet Loss Rate|> 0.1|流的平均丢包率。|
|Jitter|> 30|流的平均抖动值，以毫秒为单位。|
|Ratio Concealed Samples Avg|> 0.07|使用生成的数据包丢失的总数的音频帧的样本隐藏样本数的音频帧的数目的平均比率。|

### <a name="video-classifier"></a>视频分类器

视频流根据第一个可用指标的值按以下顺序标记为“好”或“差”：

|**步骤编号**|**指标**|**条件**|**如果条件为真的分类**|**如果条件为假的分类**|**如果指标不可用的分类**|**解释**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|继续前往步驟 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 7|Poor|Good|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|Poor|Good|Unclassified|数据包丢失率应用 FEC 后聚合跨所有视频流和编解码器。|

### <a name="vbss-classifier"></a>VBSS 分类器

VBSS 流根据第一个可用指标的值按以下顺序标记为“好”或“差”：

|**步骤编号**|**指标**|**条件**|**如果条件为真的分类**|**如果条件为假的分类**|**如果指标不可用的分类**|**解释**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|继续前往步驟 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|<2|Poor|Good|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|Poor|Good|Unclassified|数据包丢失率应用 FEC 后聚合跨所有视频流和编解码器。|

### <a name="application-sharing-classifier"></a>应用程序共享分类器

如果满足以下一个或多个条件，则应用程序共享流标记为“差”：


| **指标**                                     | **条件** | **解释**                                                                                                                                                                                                        |
|:-----------------------------------------------|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spoiled Tile Percent Total                     | > 36          | Percentage of tiles that are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Discarded (or spoiled) tiles may be caused by bandwidth restrictions between client and server. |
| AppSharing RDP Tile Processing Latency Average | > 400         | 在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。                                                                                                                          |
| AppSharing Relative OneWay Average             | > 1.75        | 以秒为单位的应用程序共享流终结点之间相对单向延迟的平均时间。                                                                                                                       |

## <a name="unclassified-streams"></a>未经分类的流

在 CQD 中，当 ICE 连接失败或者没有报告计算流分类所需的所有指标时，流标记为未经分类。

To check for ICE connectivity failures, examine the dimensions "First Connectivity Ice" and "Second Connectivity Ice" for a "FAILED" value. If either value indicates a failure, the stream will be marked as unclassified.

If ICE connectivity succeeded for an unclassified stream, the stream is likely considered unclassified because key stream metrics were not reported. There are a few reasons these metrics may not be reported:

- **QoE reports were not received** - The metrics used for classification are reported in a QoE report sent at the end of a call. If this report is not produced (e.g., because some third-party endpoints may not send QoE) or was not able to be sent (e.g., because of a network outage), CQD is unable to classify the stream.

> [!TIP]
> The "QoE Record Available" dimension can be used to determine whether a QoE report was received for a stream. Note that this dimension will have a value of "True" if a QoE report was received from either endpoint. A QoE report from both endpoints is required for the most accurate reporting of metrics.

- **Short calls** - Short calls may not have enough media activity to compute key stream metrics. Without these metrics, CQD is unable to classify the stream.

> [!TIP]
> The dimensions "Duration (Seconds)", "Duration (Minutes)", "Duration 5 seconds or less", and "Duration 60 seconds or more" can be used to determine the duration of a stream. The measurement "Avg Call Duration" can also be used to compute the average duration for a set of streams.

- **Low packet utilization** - Like the "short call" scenario, sufficient packet utilization is required for computation of key stream metrics. Without these metrics, CQD is unable to classify the stream.
    - A common low packet utilization scenario occurs when a user joins a meeting to listen to the presenter but never speaks (likely muting the microphone for most of the call). In such a scenario, one audio stream will have high packet utilization (inbound to the client) while the other will have little to no packet utilization (outbound from the client). In this scenario, the duration of the stream may be an hour or longer but the packet utilization on the stream from the client to the server will be extremely low due to the microphone being muted, resulting in an unclassified stream.

> [!TIP]
> "Packet Utilization" 维度和 "Avg Packet Utilization" 度量可用于确定流的数据包活动。


## <a name="related-topics"></a>相关主题
[打开和使用呼叫质量仪表板 (CQD)](turning-on-and-using-call-quality-dashboard.md)

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)
