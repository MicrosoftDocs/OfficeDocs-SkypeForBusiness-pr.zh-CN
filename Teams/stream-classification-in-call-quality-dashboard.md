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
- Adm_Skype4B_Online
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
ms.openlocfilehash: 47658f0ce2b2860ce4dc7275c90b962f4e17968f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018788"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>通话质量仪表板中的流分类

呼叫质量仪表板 (CQD) 的 Microsoft 团队和 Skype 业务 online 使您能够获得见解进行业务服务使用的 Microsoft 团队和 Skype 的呼叫的质量。 本主题提供有关媒体流质量分类的详细信息。 若要了解有关 CQD 以及如何启用它的详细信息，请参阅[打开和使用呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)。

## <a name="classifier-definitions"></a>分类器定义

基于可用关键质量度量的值，CQD 中的流被分类为“好”、“差”或“未经分类”。 下表显示了用于流分类的指标和条件。 可以使用 CQD 的 "Poor Due To" 维度来了解哪个指标导致分类为“差”。 参阅[呼叫质量仪表板中提供的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)，了解更多关于这些维度的信息。

### <a name="audio-classifier"></a>音频分类器

如果满足以下一个或多个条件，则音频流标记为“差”：

|**指标**|**异常条件**|**解释**|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1.0|关于流降级的网络平均意见得分的平均值。 表示网络损耗和抖动对所收到的音频质量的影响程度。|
|Round Trip|> 500|计算的平均网络传播往返时间，根据 RFC3550 以毫秒为单位指定。|
|Packet Loss Rate|> 0.1|流的平均丢包率。|
|Jitter|> 30|流的平均抖动值，以毫秒为单位。|
|Ratio Concealed Samples Avg|> 0.07|使用生成的数据包丢失的总数的音频帧的样本隐藏样本数的音频帧的数目的平均比率。|

### <a name="video-classifier"></a>视频分类器

视频流根据第一个可用指标的值按以下顺序标记为“好”或“差”：

|**步骤编号**|**指标**|**异常条件**|**如果条件为真的分类**|**如果条件为假的分类**|**如果指标不可用的分类**|**解释**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|继续前往步驟 2|向用户显示的视频帧丢失平均百分比。 其中包括从网络丢失恢复的帧。|
|2|Video Frame Rate Avg|< 7|Poor|Good|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|Poor|Good|Unclassified|数据包丢失率应用 FEC 后聚合跨所有视频流和编解码器。|

### <a name="vbss-classifier"></a>VBSS 分类器

VBSS 流根据第一个可用指标的值按以下顺序标记为“好”或“差”：

|**步骤编号**|**指标**|**异常条件**|**如果条件为真的分类**|**如果条件为假的分类**|**如果指标不可用的分类**|**解释**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|继续前往步驟 2|向用户显示的视频帧丢失平均百分比。 其中包括从网络丢失恢复的帧。|
|2|Video Frame Rate Avg|<2|Poor|Good|继续前往步驟 3|在会话持续期间计算到的视频流每秒接收的平均帧数。|
|3|Video Post FECPLR|> 0.15|Poor|Good|Unclassified|数据包丢失率应用 FEC 后聚合跨所有视频流和编解码器。|

### <a name="application-sharing-classifier"></a>应用程序共享分类器

如果满足以下一个或多个条件，则应用程序共享流标记为“差”：

**指标**|**异常条件**|**解释**|
|:-----|:-----|:-----|
|Spoiled Tile Percent Total|> 36|图块，而不是 （例如，从到查看器 MCU) 发送到远程对等方被丢弃的百分比。 丢弃 （或损坏） 平铺可能是由客户端和服务器之间的带宽限制导致的。|
|AppSharing RDP Tile Processing Latency Average|> 400|在会议服务器上处理 RDP 堆栈图块的平均延迟，以毫秒为单位。|
|AppSharing Relative OneWay Average|> 1.75|以秒为单位的应用程序共享流终结点之间相对单向延迟的平均时间。|

## <a name="unclassified-streams"></a>未经分类的流

在 CQD 中，当 ICE 连接失败或者没有报告计算流分类所需的所有指标时，流标记为未经分类。

要检查 ICE 连接故障，请检查 "First Connectivity Ice" 和 "Second Connection Ice" 维度是否为 "FAILED" 值。 如果任一值指示失败，则该流将被标记为未经分类。

如果未经分类的流成功执行 ICE 连接，则该流可能被视为未经分类，因为未报告关键流指标。 这些指标可能不会被报告的原因有几个：

- **没有收到 QoE 报告** - 用于分类的指标在呼叫结束时发送的 QoE 报告中予以报告。 如果未生成此报告（例如，由于某些第三方端点可能不发送 QoE）或无法发送（例如，由于网络中断），CQD 无法对流进行分类。

> [!TIP]
> "QoE Record Available" 维度可用于确定是否收到某个流的 QoE 报告。 请注意，如果从任一端点接收到 QoE 报告，则此维度的值将为 "True"。 为了最准确地报告指标，需要两个端点的 QoE 报告。

- **短时间呼叫** - 短时间呼叫可能没有足够的媒体活动来计算关键流指标。 如果没有这些指标，CQD 无法对流进行分类。

> [!TIP]
> 可以使用 "Duration (Seconds)"、"Duration (Minutes)"、"Duration 5 seconds or less" 和 "Duration 60 seconds or more" 等维度来确定流的持续时间。 "Avg Call Duration" 度量也可用于计算一组流的平均持续时间。

- **低数据包利用率** - 就像“短时间呼叫”情况那样，关键流指标的计算需要足够的数据包利用率。 如果没有这些指标，CQD 无法对流进行分类。
    - 当用户加入会议来聆听演讲者但从不说话（可能像在大多数呼叫中那样将麦克风静音）时，会出现常见的低数据包利用率。 在这种情况下，一个音频流将具有高数据包利用率（入站到客户端），而另一个音频流几乎不具有数据包利用率（从客户端出站）。 在这种情况下，流的持续时间可能为一小时或更长，但由于麦克风被静音，从客户端到服务器的流数据包利用率将非常低，从而导致未分类的流。

> [!TIP]
> "Packet Utilization" 维度和 "Avg Packet Utilization" 度量可用于确定流的数据包活动。


## <a name="related-topics"></a>相关主题
[打开和使用呼叫质量仪表板 (CQD)](turning-on-and-using-call-quality-dashboard.md)

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[使用通话分析解决通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)
