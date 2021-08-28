---
title: '呼叫质量仪表板中的流分类 (CQD) '
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 了解如何在呼叫质量仪表板中分类流质量 (CQD) Microsoft Teams Skype for Business Online。
ms.openlocfilehash: f4c4fb72d15ce79c60c2400b068898ad463f1b07
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598336"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>呼叫质量仪表板中的流分类 (CQD) 

使用适用于 (和 Skype for Business Online 的 CQD) 呼叫质量仪表板Microsoft Teams可深入了解使用 Microsoft Teams 和 Skype for Business 服务进行呼叫的质量。 本主题提供有关媒体流质量分类的详细信息。 若要详细了解 CQD 及其设置，请参阅设置 [呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)。

## <a name="classifier-definitions"></a>分类器定义

CQD 中的流 _根据可用密钥_ 质量指标的值被分类为良好、较差或未分类。 用于对流进行分类的指标和条件显示在以下表中。 CQD 的"Poor Due To"维度可用于了解哪个指标导致 _较差分类。_ 有关这些维度详细信息，请参阅呼叫质量仪表板中提供的 [维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)。

### <a name="audio-classifier"></a>音频分类器

如果满足以下一个或多个条件，音频流将标记为 _差_：

|指标|使用场景|条件|解释|
|:-----|:-----|:-----|:-----|
|Round Trip|ALL|> 500|平均往返网络传播时间，以毫秒为单位计算。 [RFC3550 中提供了详细信息](https://tools.ietf.org/html/rfc3550)。|
|Packet Loss Rate|ALL|> 0.1|流的平均丢包率。|
|抖动|ALL|> 30|流的平均抖动值，以毫秒为单位。|
||||

### <a name="video-classifier-due-to-freeze"></a>由于冻结导致的视频分类器

根据生成的分类器评分值，视频流被标记为"良好"或"差"，以估计最终用户是否遇到了冻结视频。 此分类器仅适用于Microsoft Teams产品。

|步骤编号|指标|使用场景|条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |服务器对是客户端：服务器|>0.246|_Poor_|_Good_|_Unclassified_|基于用户体验、冻结持续时间统计信息和总体呼叫体验的组合生成的介于 0 和 1 之间的分数 |
|2|Video Poor Due to Freeze Classifier |服务器对是客户端： 客户端|>0.524|_Poor_|_Good_|_Unclassified_|基于用户体验、冻结持续时间统计信息和总体呼叫体验的组合生成的介于 0 和 1 之间的分数 |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>视频分类器
视频流 _根据第一_ 个可用指标的值按以下顺序标记为"良好"或"差"：

|步骤编号|指标|条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|继续前往步驟 2|向用户显示的视频帧丢失平均百分比。 平均值包括从网络损失中恢复的帧数。|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|应用 FEC 后跨所有视频流和编解码器聚合的数据包丢失率。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分类器

VBSS 流根据第一个可用指标的值按以下顺序标记为"良好"或"差"：

|步骤编号 |指标 |条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|继续前往步驟 2|向用户显示的视频帧丢失平均百分比。 平均值包括从网络损失中恢复的帧数。|
|2|Video Frame Rate Avg|<2|_Poor_|_Good_|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|应用 FEC 后跨所有视频流和编解码器聚合的数据包丢失率。|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>应用程序共享分类器

如果满足以下一个或多个 _条件，应用程序_ 共享流将标记为"差"：

| 指标     | 条件 | 解释 |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | 丢弃而不是发送到远程对等节点的平铺的百分比 (例如，从 MCU 发送到查看器) 。 丢弃 (或损坏) 可能是客户端和服务器之间的带宽限制导致的。 |
| AppSharing RDP Tile Processing Latency Average | > 400 | 在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。 |
| AppSharing Relative OneWay Average | > 1.75 | 应用程序共享流的终结点之间的平均单向延迟，以秒数表示。 |
| | | |

## <a name="unclassified-streams"></a>未经分类的流

在 CQD 中，当交互式连接公司 (ICE) 连接失败或未报告计算流分类所需的所有指标时，流将标记为"未分类"。

要检查 ICE 连接故障，请检查 "First Connectivity Ice" 和 "Second Connection Ice" 维度是否为 "FAILED" 值。 如果任一值指示失败，流将标记为 _"未分类"。_

如果未分类流的 ICE连接成功，则流可能被视为"未分类"，因为未报告密钥流指标。 这些指标可能不会被报告的原因有几个：

- **未收到 QoE** 报告 - 用于分类的指标在通话结束时发送的 QoE 报告中报告。 例如，如果未生成此 (，因为某些第三方终结点可能无法发送 QoE) 或无法发送 (例如，由于网络中断) ，CQD 无法对流进行分类。

  > [!TIP]
  > "QoE Record Available" 维度可用于确定是否收到某个流的 QoE 报告。 请注意，如果从任一端点接收到 QoE 报告，则此维度的值将为 "True"。 为了最准确地报告指标，需要两个端点的 QoE 报告。

- **短调用** - 短调用可能没有足够的媒体活动来计算密钥流指标。 如果没有这些指标，CQD 无法对流进行分类。

  > [!TIP]
  > 可以使用 "Duration (Seconds)"、"Duration (Minutes)"、"Duration 5 seconds or less" 和 "Duration 60 seconds or more" 等维度来确定流的持续时间。 "Avg Call Duration" 度量也可用于计算一组流的平均持续时间。

- **数据包利用率** 低 - 与"短调用"方案一样，计算密钥流指标需要足够的数据包利用率。 如果没有这些指标，CQD 无法对流进行分类。
  - 当与会者加入会议以收听演示者的声音，但从不说话时 (大多数呼叫都静音时，会出现一种常见的低数据包利用率) 。 此处，入站到客户端的音频流具有较高的数据包利用率，而从客户端出站的音频流很少或没有数据包利用率。 流的持续时间可能为一小时或更长时间，但从客户端到服务器的流上的数据包利用率较低，因为麦克风已静音，并且导致未 _分类_ 的流。

  > [!TIP]
  > "Packet Utilization" 维度和 "Avg Packet Utilization" 度量可用于确定流的数据包活动。

## <a name="related-topics"></a>相关主题
[改进和监视呼叫质量Teams](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[使用 CQD (设置呼叫质量) ](turning-on-and-using-call-quality-dashboard.md)

[Upload租户和建筑物数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[使用Power BI分析 CQD 数据](CQD-Power-BI-query-templates.md)
