---
title: 使用 CQD 数据查看 Power BI 中的 Microsoft Teams 利用率
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: 使用 Teams 利用率 Power BI 报表访问 Microsoft Teams 通话质量仪表板 (CQD) 数据，以跟踪组织中的 Microsoft Teams 使用情况。
ms.openlocfilehash: 6e96f9dd06f872f2907d04aa335e2af2d7a75f2b
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790337"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>使用 CQD 数据查看 Power BI 中的 Microsoft Teams 利用率

2020 年 3 月新增功能，我们已将 Teams 利用率报告添加到 [CQD 的可下载 Power BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 

通过此新的 Teams 使用率报告，可通过访问 Teams 呼叫质量仪表板 (CQD) 数据来了解用户使用 Microsoft Teams 的 (程度和) 。 这些报表旨在成为管理员和业务主管可以快速访问此数据的集中位置。

Teams 利用率 Power BI 报表包含两个主要报表： **[通话计数摘要](#call-count-summary-report)** 和 **[音频分钟数摘要](#audio-minutes-summary-report)**。 当用户利用下拉报表时，将开始使用 [每日使用](#daily-usage)情况、 [区域音频详细信息](#regional-audio-details)、 [会议详细信息](#conference-details) 和 [用户列表](#user-list) 报告，如下所述。

> [!NOTE]
> 必须填充生成数据和子网数据，以提供区域和网络筛选功能。

## <a name="call-count-summary-report"></a>呼叫计数摘要报表

主页 (呼叫计数摘要) 立即提供过去 30 天和 90 天内的音频、视频和屏幕共享会话数，如节标题中所述。 最初显示的数据面向整个组织，可以使用页面左侧的切片器下拉列表选项进行筛选。

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report1.png)

1. 在切片器下拉列表的右侧，过去 30 天按媒体类型进行的调用数将细分为内部/外部视图。 我们可以通过上面的屏幕截图看出，从组织外部发生更多呼叫，考虑到当前的全局环境，这很有意义。
  ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report2.png)

1. 在媒体类型计数框的右侧，我们拥有过去 90 天的按媒体类型的每月呼叫计数。 可以将每个列和媒体类型悬停在上面以显示上一个月或当前月份至今的计数，从而提供使用趋势信息。
  ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report3.png)
 

1. 中间图的功能与 90 天图形一样，但它提供了过去 30 天的每日使用情况视图，并允许用户右键单击并向下钻取特定日期的详细信息。
  ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report4.png)

在页面左下部分，你将找到一个表，其中提供了过去一年中每个媒体类型的总值。 
    ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report5.png)
    ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report6.png)   

在表右侧，条形图显示过去 30 天内使用 (调用/流) 最多的客户端。
   ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report7.png)

此页的最后一组图表分别显示每个媒体类型，其中显示会议和 P2P 使用情况的细目。 下图显示，与 P2P 相比，会议使用量要高得多。
  ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>音频分钟摘要报告

在音频分钟使用情况报告中，总分钟使用量通过几个不同的视图提供。 

我们已在切片器旁边显示三十天的使用情况摘要，以便轻松使用文本框。 最上面的数字显示三十天的总数，其中内部和外部细分如下。

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report9.png)

右上角的条形图提供长达一年的会议音频使用视图。 将鼠标悬停在一个月内以显示会议音频分钟数。

为了显示 P2P 和会议音频的差异，左下角图表采用过去一年的所有音频，并在两种类型之间进行分隔。

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report10.png)

“音频分钟数”页的最后一个图表显示全局地图覆盖层上的音频分钟使用情况。 仅当生成数据和子网数据上传到租户时，此图表才有效。 地图上的饼图覆盖层可以钻取到其中，随后提供区域音频使用情况。

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>钻取功能

如前所述，用户可以深入了解每日和区域使用情况报告。

### <a name="daily-usage"></a>每日使用情况

“每日使用情况”报告允许管理员在一天中标识高峰使用期。 除了使用情况，我们还能够捕获当天的总体用户情绪和反馈。

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report12.png)

每日使用情况报告显示所选日期的音频、视频和屏幕共享数，并增加了区分内部和外部连接的功能。 “会议”和“对等”细分位于模式总框的右侧。 报表右上角提供了一个会议列表，其中包含其当天的关联 ID 和参与者。 会议列表还向下钻取了会议详细信息报告。 REPLACE GRAPHIC

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report13.png)

中心区域中的条形图允许用户在一天中标识高峰使用期。 用户可以向下钻取到图形上表示的小时，该时间将显示该小时的用户列表报表。

条形图右侧以视觉格式显示用户反馈。 虽然用户情绪可能是主观的，但它确实提供了可用于识别潜在问题的见解。

下表提供当天的一系列指标。 低百分比和失败率可以为管理员提供潜在的改进领域。 还可以单独选择每小时，如下所示。

此数据可用于识别在使用高峰期出现问题的区域。


单击当天的列以显示该小时的指标。
![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report14.png)
  
  1.  图表下方的表将显示该小时的指标。 这可以按任何列标题进行排序;但是，我们有兴趣找到有问题的领域。  
    ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report15.png)
    
  2.  我们看到，在此期间，IND 区域在会议中的视频性能不佳。 随后，CQD QER Microsoft 报表可用于在确定区域和时间范围后缩小有问题的位置。

### <a name="conference-details"></a>会议详细信息

会议详细信息报告为会议提供了更多见解，从与会者列表到会话期间使用的媒体类型。

右键单击“每日使用情况”页上会议 ID 图表中的参与者栏，向下钻取会议详细信息。

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report24.png)

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report25.png)
  

我们可以看到会议的参与者，以及有关数据包丢失和抖动的所有相关信息，以帮助解决下表中的潜在故障排除工作。

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>区域音频详细信息

区域音频详细信息向下钻取专门显示所选区域的音频分钟使用情况。 有权访问 CQD 的用户可以在所选区域内查看 P2P 和会议音频的使用趋势。

1.  在“呼叫计数摘要”页上，通过表钻取到特定区域。
  ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report16.png)

2.  选择具有区域附加信息的行。
  ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report17.png)

3.  数据趋势显示，在内部网络上使用的分钟数相当多，会议远远超过了 P2P 的使用。
  ![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report18.png)

区域音频趋势可用于显示用户如何受到世界外部影响的影响。 具体而言，现在，我们预计 EMEA 和 APAC 区域的外部使用量会随着人们被要求远程工作而增加。


### <a name="user-list"></a>用户列表

用户列表向下钻取可能会提供查看报表的人员选择的特定小时的用户特定信息。 可通过每日使用情况报告中的“每小时趋势”图中的向下钻取访问用户列表报表。 右键单击所需的小时附加信息，然后选择“钻取”和“用户列表”，如下所示。

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report19.png)

用户列表报表显示通过页面顶部中心圆环图的内部/外部连接。 在下图中，可以看到来自公司网络外部的大量参与。

图右上角显示每个用户在该小时内发出的呼叫数。

![屏幕截图：Teams 利用率报告。](media/CQD-teams-utilization-report20.png)

下表提供了每个用户在该小时内参与的会话的详细信息。 故障类型列可用于确定导致调用下降的原因。 捕获和呈现设备列可用于确定为什么报告呼叫质量较差。


## <a name="related-topics"></a>相关主题

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)

[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](./monitor-call-quality-qos.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
