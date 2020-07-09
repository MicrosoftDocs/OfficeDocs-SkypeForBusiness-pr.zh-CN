---
title: 通话质量仪表板（CQD）中的流分类
ms.author: lolajacobsen
author: lolaj
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 了解如何在 Microsoft 团队和 Skype for business Online 的通话质量仪表板（CQD）中分类流质量。
ms.openlocfilehash: 28c3857f1bf30903e9a59d45e8149f8ecbfc57be
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085888"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>通话质量仪表板（CQD）中的流分类

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to set it up, see [Set up Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>分类器定义

Streams in CQD are classified as _Good_, _Poor_, or _Unclassified_ based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables that follow. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a _Poor_ classification. For more information on these dimensions, see [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>音频分类器

如果满足以下一种或多种条件，音频流将标记为_差_：

|指标|条件|解释|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1.0|Average Network Mean Opinion Score degradation for stream. How much network loss and jitter have impacted the quality of received audio.|
|Round Trip|> 500|平均往返行程网络传播时间，以毫秒为单位计算。 [根据 rfc3550](https://tools.ietf.org/html/rfc3550)中提供的详细信息。|
|Packet Loss Rate|> 0.1|流的平均丢包率。|
|抖动|> 30|流的平均抖动值，以毫秒为单位。|
|Ratio Concealed Samples Avg|> 0.07|带有隐藏样本（由数据包丢失修复生成）到音频帧总数的音频帧数的平均比率。|
||||

### <a name="video-classifier-due-to-freeze"></a>由于冻结而导致视频分类器

视频流基于生成的分类器分数的值标记为 "_良好_" 或 "_差_"，以估计最终用户遇到了冻结的视频。 此分类器仅适用于 Microsoft 团队产品。

|步骤编号|指标|使用场景|条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|由于冻结分类器而导致视频较差 |服务器对是客户端：服务器|>0.246|_Poor_|_Good_|_Unclassified_|基于用户体验、冻结持续时间统计和整体通话体验的组合生成的0和1之间的分数 |
|2|由于冻结分类器而导致视频较差 |服务器对是客户端：客户端|>0.524|_Poor_|_Good_|_Unclassified_|基于用户体验、冻结持续时间统计和整体通话体验的组合生成的0和1之间的分数 |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>视频分类器
视频流根据第一个可用指标的值标记为 "_良好_" 或 "_差_"，顺序如下：

|步骤编号|指标|条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|继续前往步驟 2|向用户显示的视频帧丢失平均百分比。 平均值包括从网络丢失恢复的帧。|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|在所有视频流和编解码器上应用 FEC 后的数据包丢失率。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分类器

根据第一个可用跃点数的值，将 VBSS 流标记为 "_良好_" 或 "_差_"，顺序如下：

|步骤编号 |指标 |条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|继续前往步驟 2|向用户显示的视频帧丢失平均百分比。 平均值包括从网络丢失恢复的帧。|
|2|Video Frame Rate Avg|<2|_Poor_|_Good_|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|在所有视频流和编解码器上应用 FEC 后的数据包丢失率。|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>应用程序共享分类器

如果满足以下一种或多种条件，应用程序共享流将标记为_差_：

| 指标     | 条件 | 解释 |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | 被丢弃而不是发送到远程对等（例如，从 MCU 到查看器）的磁贴的百分比。 已放弃（或损坏）磁贴可能由客户端和服务器之间的带宽限制导致。 |
| AppSharing RDP Tile Processing Latency Average | > 400 | 在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。 |
| AppSharing Relative OneWay Average | > 1.75 | 应用程序共享流终结点之间的平均相对单向延迟（以秒为单位）。 |
| | | |

## <a name="unclassified-streams"></a>未经分类的流

在 CQD 中，当交互式连接建立（ICE）连接失败或未报告计算流分类所需的所有指标时，流将标记为未_分类_。

要检查 ICE 连接故障，请检查 "First Connectivity Ice" 和 "Second Connection Ice" 维度是否为 "FAILED" 值。 如果任一值指示失败，则流将标记为未_分类_。

如果未_分类_流的 ICE 连接成功，则该流可能被视为未_分类_，因为未报告密钥流度量值。 这些指标可能不会被报告的原因有几个：

- **未收到 QoE 报表**-用于分类的度量在呼叫结束时发送的 QoE 报告中报告。 如果不生成此报告（例如，由于某些第三方终结点可能无法发送 QoE）或无法发送（例如，由于网络中断），CQD 无法对流进行分类。

> [!TIP]
> "QoE Record Available" 维度可用于确定是否收到某个流的 QoE 报告。 请注意，如果从任一端点接收到 QoE 报告，则此维度的值将为 "True"。 为了最准确地报告指标，需要两个端点的 QoE 报告。

- **短通话**—短通话可能没有足够的媒体活动来计算密钥流指标。 如果没有这些指标，CQD 无法对流进行分类。

> [!TIP]
> 可以使用 "Duration (Seconds)"、"Duration (Minutes)"、"Duration 5 seconds or less" 和 "Duration 60 seconds or more" 等维度来确定流的持续时间。 "Avg Call Duration" 度量也可用于计算一组流的平均持续时间。

- **较低的数据包利用率**-如 "短通话" 方案，需要足够的数据包利用率才能计算关键流指标。 如果没有这些指标，CQD 无法对流进行分类。
  - 当与会者加入会议以收听演示者时，将会出现常见的低数据包使用情况，但永远不会讲话（在大多数通话中麦克风静音）。 在这里，音频流入站到客户端具有高数据包利用率，而从客户端的音频流出站几乎没有数据包利用率。 流的持续时间可能是一小时或更长时间，但从客户端到服务器的数据流的数据包利用率较低，因为麦克风已静音，而未_分类_的流结果。

> [!TIP]
> "Packet Utilization" 维度和 "Avg Packet Utilization" 度量可用于确定流的数据包活动。

## <a name="related-topics"></a>相关主题
[改善和监控团队的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[设置通话质量仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md)

[上载租户和生成数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报告](CQD-data-and-reports.md)

[使用 CQD 管理通话和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)
