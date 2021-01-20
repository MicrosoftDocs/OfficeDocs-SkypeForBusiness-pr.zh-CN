---
title: 'CQD (呼叫质量仪表板中的流) '
ms.author: serdars
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
description: 了解如何在 Microsoft Teams 和 Skype for Business Online (CQD) 流质量分类。
ms.openlocfilehash: 400dcd953805595b4457b4ca9443c31b66f7425d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909036"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>CQD 呼叫质量仪表板中的 (分类) 

借助适用于 Microsoft Teams (Skype for Business Online) CQD 仪表板，你可以深入了解使用 Microsoft Teams 和 Skype for Business 服务进行呼叫的质量。本主题提供有关媒体流的质量分类的详细信息。若要了解有关 CQD 以及如何设置 CQD，请参阅"设置呼叫[质量仪表板"。](turning-on-and-using-call-quality-dashboard.md)

## <a name="classifier-definitions"></a>分类器定义

CQD 中的流根据可用密钥质量指标的值分类为"良好"、"差"或"未分类"。 用于对流进行分类的指标和条件显示在以下表中。CQD 的"Poor Due To"维度可用于了解哪个指标 _负责较差分类_。有关这些维度详细信息，请参阅"呼叫质量仪表板"[中提供的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)。

### <a name="audio-classifier"></a>音频分类器

如果满足以下一个或多个条件，音频流将标记为 _差_：

|指标|使用场景|条件|解释|
|:-----|:-----|:-----|:-----|
|Audio Degradation Avg|有效负载说明不是 SATIN|> 1.0|关于流降级的网络平均意见得分的平均值。 网络丢失和抖动对接收音频质量的影响很大。|
|Round Trip|ALL|> 500|以毫秒为单位计算的平均往返网络传播时间。 [RFC3550 中提供了详细信息](https://tools.ietf.org/html/rfc3550)。|
|Packet Loss Rate|ALL|> 0.1|流的平均丢包率。|
|抖动|ALL|> 30|流的平均抖动值，以毫秒为单位。|
|Ratio Concealed Samples Avg|有效负载说明不是 SATIN|> 0.07|数据包丢失修复生成的隐藏样本的音频帧数与音频帧总数的平均比率。|
||||

### <a name="video-classifier-due-to-freeze"></a>由于冻结导致的视频分类器

根据生成的分类器评分值，视频流标记为"良好"或"差"，以估计最终用户遇到了冻结视频。 此分类器仅适用于 Microsoft Teams 产品。

|步骤编号|指标|使用场景|条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |服务器对是客户端：服务器|>0.246|_Poor_|_Good_|_Unclassified_|基于用户体验、冻结持续时间统计信息和总体调用体验的组合生成的介于 0 和 1 之间的分数 |
|2|Video Poor Due to Freeze Classifier |服务器对是客户端：客户端|>0.524|_Poor_|_Good_|_Unclassified_|基于用户体验、冻结持续时间统计信息和总体调用体验的组合生成的介于 0 和 1 之间的分数 |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>视频分类器
视频流根据第一个可用指标的值按以下顺序标记为"良好"或"差"：

|步骤编号|指标|条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|继续前往步驟 2|向用户显示的视频帧丢失平均百分比。 平均值包括从网络丢失中恢复的帧。|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|应用 FEC 后跨所有视频流和编解码器聚合的丢包率。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分类器

VBSS 流根据第一个可用指标的值按以下顺序标记为"良好"或"差"：

|步骤编号 |指标 |条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|继续前往步驟 2|向用户显示的视频帧丢失平均百分比。 平均值包括从网络丢失中恢复的帧。|
|2|Video Frame Rate Avg|<2|_Poor_|_Good_|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|应用 FEC 后跨所有视频流和编解码器聚合的丢包率。|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>应用程序共享分类器

如果满足以下一个或多个条件，应用程序共享流将标记为差：

| 指标     | 条件 | 解释 |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | 放弃而不是发送到远程对等节点的平铺的百分比 (例如，从 MCU 到查看器或) 。 丢弃 (或损坏) 可能是客户端和服务器之间的带宽限制导致的。 |
| AppSharing RDP Tile Processing Latency Average | > 400 | 在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。 |
| AppSharing Relative OneWay Average | > 1.75 | 应用程序共享流的终结点之间的平均单向延迟（以秒数表示）。 |
| | | |

## <a name="unclassified-streams"></a>未经分类的流

在 CQD 中，当交互式连接建立 (ICE) 连接失败或未报告计算流分类所需的所有指标时，流标记为"未分类"。

要检查 ICE 连接故障，请检查 "First Connectivity Ice" 和 "Second Connection Ice" 维度是否为 "FAILED" 值。 如果任一值指示失败，流将标记为 _"未分类"。_

如果未分类流的 ICE连接成功，则流可能被视为未分类，因为未报告密钥流指标。 这些指标可能不会被报告的原因有几个：

- **未收到 QoE 报告** - 用于分类的指标在通话结束时发送的 QoE 报告中报告。 如果未生成此报告 (例如，由于某些第三方终结点可能无法发送 QoE) 或无法发送 (例如，由于网络中断) ，CQD 无法对流进行分类。

  > [!TIP]
  > "QoE Record Available" 维度可用于确定是否收到某个流的 QoE 报告。 请注意，如果从任一端点接收到 QoE 报告，则此维度的值将为 "True"。 为了最准确地报告指标，需要两个端点的 QoE 报告。

- **短调用** - 短调用可能没有足够的媒体活动来计算密钥流指标。 如果没有这些指标，CQD 无法对流进行分类。

  > [!TIP]
  > 可以使用 "Duration (Seconds)"、"Duration (Minutes)"、"Duration 5 seconds or less" 和 "Duration 60 seconds or more" 等维度来确定流的持续时间。 "Avg Call Duration" 度量也可用于计算一组流的平均持续时间。

- **低数据包利用率** - 与"短调用"方案一样，需要有足够的数据包利用率才能计算密钥流指标。 如果没有这些指标，CQD 无法对流进行分类。
  - 当与会者加入会议以收听演示者的声音，但从不 (在大多数呼叫过程中麦克风被静音时，会出现一种常见的低数据包) 。 此处，入站到客户端的音频流具有较高的数据包利用率，而来自客户端的出站音频流几乎没有数据包利用率。 流的持续时间可能为一小时或更长时间，但从客户端到服务器的流上的数据包利用率较低，因为麦克风已静音，并且会导致未 _分类的_ 流。

  > [!TIP]
  > "Packet Utilization" 维度和 "Avg Packet Utilization" 度量可用于确定流的数据包活动。

## <a name="related-topics"></a>相关主题
[改进和监视 Teams 的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[设置呼叫质量仪表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[上传租户和建筑物数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)
