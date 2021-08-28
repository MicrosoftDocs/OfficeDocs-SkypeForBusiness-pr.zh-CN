---
title: 使用 CQD Microsoft Teams查看Power BI的使用情况
ms.author: serdars
author: SerdarSoysal
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
description: 使用Teams使用情况Power BI访问 Microsoft Teams 呼叫质量仪表板 (CQD) 数据来跟踪Microsoft Teams使用情况。
ms.openlocfilehash: e026f2b6b2b5e04d98dbf14582e5ce1ffc7f5007
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616288"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>使用 CQD Microsoft Teams查看Power BI的使用情况

我们于 2020 年 3 月新增了一个Teams使用情况报告，该报表已添加到[CQD Power BI可下载的查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)中。 

此新的 Teams 利用率报告通过访问 Teams 呼叫质量仪表板 (CQD) 数据， (用户使用 Microsoft Teams) 的用户数。 这些报告旨在成为管理员和业务领导都可以快速转到此数据的集中位置。

"Teams使用率Power BI报告包含两个主要报告："呼叫 **[计数](#call-count-summary-report)** 摘要"和"**[音频分钟数摘要"。](#audio-minutes-summary-report)** 当用户[利用下面](#daily-usage)说明中记下的向下[](#conference-details)钻取报表[](#user-list)时，"每日使用情况、区域音频详细信息、会议详细信息和用户列表"报告将发挥作用。 [](#regional-audio-details)

> [!NOTE]
> 必须填充生成和子网数据，以提供区域和网络筛选功能。

## <a name="call-count-summary-report"></a>呼叫计数摘要报告

呼叫 (摘要) 主页立即提供过去 30 天和 90 天内的音频、视频和屏幕共享会话数，如部分标题所述。 最初显示的数据适用于整个组织，可以使用页面左侧的切片器下拉选项进行筛选。

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report1.png)

1. 切片器下拉列表右侧按媒体类型细分为过去 30 天内的内部/外部视图。 通过上面的屏幕截图可以看到，从组织外部位置发生的调用越来越多，这考虑到当前的全局环境是有意义的。
  ![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report2.png)

1. 在媒体类型计数框的右侧，我们按媒体类型显示过去 90 天的每月呼叫计数。 可以将每个列和媒体类型悬停在上方以显示上个月或当前月份到目前为止的计数，从而提供使用趋势信息。
  ![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report3.png)
 

1. 中间图的作用与 90 天图一样，但它提供过去 30 天的每日使用情况视图，允许用户右键单击并向下钻取特定日期的详细信息。
  ![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report4.png)

在页面左下角，可找到一个表，其中提供了过去一年每种媒体类型的总计值。 
    ![屏幕截图：Teams利用率报告 ](media/CQD-teams-utilization-report5.png) ![ 屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report6.png)   

在表格右侧，条形图显示过去 30 天内 (通话/流) 的客户端。
   ![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report7.png)

此页面的最后一组图表分别显示每种媒体类型，其中显示了会议的细目和 P2P 使用情况。 下面的图表显示，与 P2P 相比，会议使用量要高得多。
  ![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>音频分钟数摘要报告

在"音频分钟数使用情况"报表上，通过几个不同的视图提供总分钟数使用情况。 

切片器旁边显示的 30 天使用情况摘要易于使用文本框。 顶部数字显示 30 天总计，内部和外部细目低于该数字。

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report9.png)

右上方的条形图提供会议音频使用情况的一年视图。 将鼠标悬停在一个月内以显示会议音频分钟数。

为了显示 P2P 和会议音频的差异，左下角的图表采用过去一年的所有音频，并在这两种类型之间进行分解。

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report10.png)

"音频分钟数"页的最后一个图表显示全局地图覆盖层上的音频分钟数使用情况。 只有在将生成和子网数据上传到租户时，此图表才工作。 可以钻取地图上的饼图覆盖层，随后提供区域音频使用情况。

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>钻取功能

如前所述，用户可以深入了解每日和区域使用情况报告。

### <a name="daily-usage"></a>每日使用情况

"每日使用情况"报表允许管理员确定一天中的高峰使用时段。 除了使用情况，我们还能够捕获当天的总体用户情绪和反馈。

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report12.png)

"每日使用情况"报表显示所选天的音频、视频和屏幕共享数，并添加了区分内部和外部连接的能力。 "会议"和"对等"细分位于"形式总计"框的右下角。 报表的右上方提供了一个会议列表，其中列出了当天的关联 ID 和参与者。 会议列表还提供对"会议详细信息"报告的其他向下钻取。 替换图形

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report13.png)

中心区域中的条形图允许用户确定一天中的高峰使用时段。 用户可以向下钻取图表上表示的小时，该小时将显示"用户列表"报告。

在条形图右侧，以可视格式显示用户反馈。 虽然用户情绪可能是主观的，但它确实提供可用于识别潜在问题的见解。

底部表提供当天的指标范围。 较差的百分比和失败率可为管理员提供潜在的改进方面。 也可以单独选择每小时，如下所示。

此数据可用于识别在高峰使用时段出现问题的区域。


单击该天的列以显示该小时的指标。
![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report14.png)
  
  1.  图表下方的表格将显示该小时的指标。 这可以通过任何列标题进行排序;但是，我们希望找到有问题的领域。  
    ![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report15.png)
    
  2.  在此时间帧内，我们看到 IND 区域在会议中遇到较差的视频性能。 随后，CQD QER Microsoft 报告可用于缩小问题位置范围，因为已识别到该区域和时间范围。

### <a name="conference-details"></a>会议详细信息

"会议详细信息"报告提供会议的其他见解，从与会者列表到会话期间使用的媒体类型。

右键单击"每日使用状况"页面上会议 ID 图表中的参与者栏，向下钻取会议详细信息。

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report24.png)

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report25.png)
  

我们可以看到会议参与者以及数据包丢失和抖动的所有相关信息，以帮助在底部表格中进行潜在的故障排除工作。

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>区域音频详细信息

"区域音频详细信息"向下钻取专门显示所选区域的音频分钟数使用情况。 有权访问 CQD 的用户可以在所选区域查看 P2P 和会议音频的使用趋势。

1.  在"呼叫计数摘要"页上，通过表钻取到作为特定区域。
  ![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report16.png)

2.  选择包含区域的其他信息的行。
  ![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report17.png)

3.  数据趋势显示内部网络上使用大量分钟数，会议远超 P2P 使用。
  ![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report18.png)

区域音频趋势可用于显示用户受到世界外部影响的影响。 具体而言，我们现在预期 EMEA 和 APAC 区域的外部使用量会随着要求远程工作的人的增加而增加。


### <a name="user-list"></a>用户列表

"用户列表"向下钻取按预期提供查看报告的用户选择的特定小时的用户特定信息。 可以通过每日使用情况报表上"每小时趋势"图中的向下钻取来访问用户列表报表。 右键单击所需的小时其他信息，然后选择"钻取"和"用户列表"，如下所示。

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report19.png)

"用户列表"报表通过页面顶部中心的圆环图显示内部/外部连接。 下图显示了企业网络外部存在大量参与活动。

图的右上方显示每个用户在这一小时内进行调用的数量。

![屏幕截图：Teams利用率报告](media/CQD-teams-utilization-report20.png)

底部表提供每个用户在这一小时内参与的会话的详细信息。 "失败类型"列可用于确定导致调用删除的原因。 "捕获"和"呈现设备"列可用于识别报告通话质量差的原因。


## <a name="related-topics"></a>相关主题

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)

[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](./monitor-call-quality-qos.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
