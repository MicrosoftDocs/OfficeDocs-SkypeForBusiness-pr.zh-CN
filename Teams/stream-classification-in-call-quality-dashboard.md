---
title: 调用质量仪表板 (CQD) 中的流分类
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
description: 了解如何在用于Microsoft Teams和联机Skype for Business的呼叫质量仪表板 (CQD) 中对流质量进行分类。
ms.openlocfilehash: 5ee2575cf952eb9d7e78f14b2b8ba7693cd3f878
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059253"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>调用质量仪表板中的流分类 (CQD) 

使用用于Microsoft Teams和联机Skype for Business的呼叫质量仪表板 (CQD) ，可以深入了解使用Microsoft Teams和Skype for Business服务进行的呼叫的质量。 本主题提供有关媒体流质量分类的详细信息。 若要详细了解 CQD 以及如何设置它，请参阅 [“设置呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)”。

## <a name="classifier-definitions"></a>分类器定义

CQD 中的流根据可用的关键质量指标的值分类为 _“好_”、“ _差_”或 _“未分类_ ”。 用于对流进行分类的指标和条件显示在后面的表中。 CQD 的“差原因”维度可用于了解哪个指标应对 _分类错误_ 负责。 有关这些维度的详细信息，请参阅 [通话质量仪表板中提供的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)值。

### <a name="audio-classifier"></a>音频分类器

如果满足以下一个或多个条件，并且数据包使用率> 500 个数据包，则音频流将标记为 _“差_” ：

|指标|使用场景|条件|解释|
|:-----|:-----|:-----|:-----|
|Round Trip|所有|> 500|平均往返网络传播时间，计算为毫秒。 [RFC3550](https://tools.ietf.org/html/rfc3550) 中提供的详细信息。|
|Packet Loss Rate|所有|> 0.1|流的平均丢包率。|
|抖动|所有|> 30|流的平均抖动值，以毫秒为单位。|
||||

### <a name="video-classifier-due-to-freeze"></a>由于冻结而导致的视频分类器

根据生成的分类器分数的值将视频流标记为  _“好_ ”或 _“差_ ”，以估计最终用户经历了“冻结视频”。 此分类器仅适用于Microsoft Teams产品。

|步骤编号|指标|使用场景|条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|由于冻结分类器导致视频差 |服务器对是客户端：服务器|>0.246|_Poor_|_Good_|_Unclassified_|根据用户体验、冻结持续时间统计信息和整体调用体验的组合生成的分数介于 0 和 1 之间 |
|2|由于冻结分类器导致视频差 |服务器对是客户端：客户端|>0.524|_Poor_|_Good_|_Unclassified_|根据用户体验、冻结持续时间统计信息和整体调用体验的组合生成的分数介于 0 和 1 之间 |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>视频分类器
根据以下顺序中第一个可用指标的值，视频流标记为 _“好_ ”或 _“差_ ”：

|步骤编号|指标|条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|继续前往步驟 2|向用户显示的视频帧丢失平均百分比。 平均值包括从网络损失中恢复的帧。|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|_Poor_|_Good_|_Unclassified_|在所有视频流和编解码器中应用 FEC 后的数据包丢失率。|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>VBSS 分类器

VBSS 流根据以下顺序中第一个可用指标的值标记为 _“好_ ”或 _“差_ ”：

|步骤编号 |指标 |条件 |如果条件为真的分类 |如果条件为假的分类 |如果指标不可用的分类 |解释 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|编解码器不是 H264S</br>和</br>StreamDirection 为入站</br></br>如果 FrameLoss > 50%|_Poor_|_Good_|_Unclassified_|向用户显示的视频帧丢失平均百分比。 平均值包括从网络损失中恢复的帧。 FrameLoss 仅用于对入站非 H264S 流进行分类。|
|2|Video Frame Rate Avg|< 1|_Poor_|_Good_|_Unclassified_|在会话持续期间计算到的视频流每秒接收的平均帧数。 适用于 H264S 的所有出站流和 StreamDirection。|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>应用程序共享分类器

如果满足以下一个或多个条件，则应用程序共享流标记为 _“差_ ”：

| 指标     | 条件 | 解释 |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | 放弃而不是发送到远程对等 (的磁贴的百分比，例如，从 MCU 发送到查看器) 。 丢弃的 (或损坏的) 磁贴可能是由客户端和服务器之间的带宽限制引起的。 |
| AppSharing RDP Tile Processing Latency Average | > 400 | 在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。 |
| AppSharing Relative OneWay Average | > 1.75 | 应用程序共享流的终结点之间平均相对单向延迟（以秒为单位）。 |
| | | |

## <a name="unclassified-streams"></a>未经分类的流

在 CQD 中，当交互式连接建立 (ICE) 连接失败或未报告计算流分类所需的所有指标时，流标记为 _“未分类_ ”。

要检查 ICE 连接故障，请检查 "First Connectivity Ice" 和 "Second Connection Ice" 维度是否为 "FAILED" 值。 如果任一值指示失败，则流标记为 _“未分类_”。

如果 _未分类_ 流的 ICE 连接成功，则流可能被视为 _未分类_ ，因为未报告关键流指标。 这些指标可能不会被报告的原因有几个：

- **未收到 QoE 报告** - 用于分类的指标在呼叫结束时发送的 QoE 报表中报告。 例如，如果未生成此报告 (，因为某些第三方终结点可能无法发送 QoE) 或无法发送 (例如，由于网络中断) ，CQD 无法对流进行分类。

  > [!TIP]
  > "QoE Record Available" 维度可用于确定是否收到某个流的 QoE 报告。 请注意，如果从任一端点接收到 QoE 报告，则此维度的值将为 "True"。 为了最准确地报告指标，需要两个端点的 QoE 报告。

- **短呼叫** - 短呼叫可能没有足够的媒体活动来计算关键流指标。 如果没有这些指标，CQD 无法对流进行分类。

  > [!TIP]
  > 可以使用 "Duration (Seconds)"、"Duration (Minutes)"、"Duration 5 seconds or less" 和 "Duration 60 seconds or more" 等维度来确定流的持续时间。 "Avg Call Duration" 度量也可用于计算一组流的平均持续时间。

- **低数据包使用率** - 与“短呼叫”方案一样，计算关键流指标需要足够的数据包利用率。 如果没有这些指标，CQD 无法对流进行分类。
  - 当与会者加入会议以收听演示者，但始终不说话 (麦克风在大多数呼叫) 静音时，就会出现常见的低数据包使用率方案。 此处，入站到客户端的音频流具有较高的数据包利用率，而从客户端出站的音频流几乎没有数据包利用率。 流的持续时间可能为一小时或更长时间，但从客户端到服务器的流上的数据包利用率较低，因为麦克风处于静音状态，并且会产生 _未分类_ 的流结果。

  > [!TIP]
  > "Packet Utilization" 维度和 "Avg Packet Utilization" 度量可用于确定流的数据包活动。

## <a name="related-topics"></a>相关主题
[改进和监视Teams的呼叫质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[设置呼叫质量仪表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[Upload租户和生成数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[使用Power BI分析 CQD 数据](CQD-Power-BI-query-templates.md)
