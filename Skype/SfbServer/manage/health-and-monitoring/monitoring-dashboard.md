---
title: 在 Skype for Business Server 中使用监控仪表板
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 摘要：了解 Skype for Business Server 中的监视仪表板。
ms.openlocfilehash: 83a04a60e63deb39666ee4d042f74973b7d16d0b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118601"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a>在 Skype for Business Server 中使用监控仪表板
 
**摘要：** 了解 Skype for Business Server 中的监控仪表板。
  
监控仪表板为管理员提供了 Skype for Business Server 系统运行状况和系统使用情况的快速概述。 仪表板旨在显示关键系统指标的聚合视图，并且通过显示以下任一项来实现此目标：
  
- 当前天的总计。 请注意，当前天显示的值表示从午夜到当前时间记录的数据 (报告服务器记录的本地时间) 。 这意味着你通常会查看部分日期的数据，而不是 24 小时的数据。 例如，如果服务器的本地时间是上午 8：00，则会看到 8 个小时的数据，因为午夜和当前时间上午 8：00 之间有 8 个小时。
    
- 一周汇总，以及过去六周的趋势汇总。
    
- 当月总计和过去六个月的趋势总计 (系统使用情况) 。
    
请注意，您可以使用 [Get-CsReportingConfiguration](/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet 返回用于访问 Skype for Business Server 监控报告的 URL：
  
```PowerShell
Get-CsReportingConfiguration
```

默认情况下，监控仪表板显示本周的以下指标 (过去六周的趋势汇总) ：
  
## <a name="system-usage-metrics"></a>系统使用情况指标

 **Registration**
  
- 唯一用户登录
    
  **对等**
  
- 会话总数
    
- IM 会话
    
- 音频会话
    
- 视频会话
    
- 应用程序共享
    
- 音频会话总分钟数
    
- 平均音频会话分钟数
    
  **Conference**
  
- 会议总数
    
- IM 会议
    
- A/V 会议
    
- 应用程序共享会议
    
- Web 会议
    
- 组织者总数
    
- A/V 会议总分钟数
    
- Avg.A/V 会议分钟数
    
- PSTN 会议总数
    
- PSTN 参与者总数
    
- PSTN 参与者总分钟数
    
除了"系统使用情况"指标之外，如果选择"周视图) "，则以下指标显示当天和前六天 (如果选择了"周视图) "，或者如果选择"每月视图"，则显示当前周和过去六周的总 **时间**。
  
## <a name="per-user-call-diagnostics"></a>Per-User呼叫诊断

 **呼叫失败的用户**
  
- 呼叫失败的用户总数
    
- 呼叫失败的会议组织者
    
  **通话质量欠佳的用户**
  
- 质量欠佳呼叫的用户总数
    
## <a name="call-diagnostics"></a>呼叫诊断

对等
  
- 总失败数
    
- 总体故障率
    
- IM 故障率
    
- 音频故障率
    
- 应用程序共享失败率
    
会议
  
- 总失败数
    
- 总体故障率
    
- IM 故障率
    
- A/V 故障率
    
- 应用程序共享失败率
    
按失败会话数排名前五的服务器
  
## <a name="media-quality-diagnostics"></a>媒体质量诊断

对等
  
- 质量欠佳的呼叫总数
    
- 质量欠佳的呼叫百分比
    
- 质量较差的 PSTN 呼叫
    
会议
  
- 质量欠佳的呼叫总数
    
- 质量欠佳的呼叫百分比
    
- 质量较差的 PSTN 呼叫
    
质量欠佳的呼叫百分比表示最差的服务器
  
## <a name="working-with-the-monitoring-dashboard"></a>使用监控仪表板

如前所述，默认情况下显示本周汇总，并显示过去六周的趋势值。 如果更希望查看当月 (以及) 过去六个月的趋势值，请单击仪表板右上角的"每月视图"链接。  如果你决定查看每月总计，链接文本将更改为每周 **视图**。 可以通过单击该链接切换回每周视图。
  
> [!TIP]
> 监控仪表板限制您查看当前周 (或) 的汇总以及过去六周或)  (的趋势) 。 您不能更改这些日期和时间。 例如，不能使用仪表板查看从 9 个月之前开始的时间段的报告总计。 
  
"本周、本月"或"今天"列中显示的值将链接至有关该项目的更多详细信息。 请记住，列名称和显示在该列中的值通常因选择的指标以及选择每周视图还是按月视图而不同。 例如，如果单击"唯一用户登录数"指标显示的总计，将看到指定时间段的用户注册报告。 通过单击"仪表板"，您随时都可以返回到监控 **仪表板**。
  
> [!TIP]
> 您还可以通过单击仪表板右上角的"报告"链接访问监控服务器报告主页。
  
" **趋势** "列显示一个简单的直线图，显示过去六周或过去六 (，或者根据指标和时间间隔，显示过去六天或过去六个月的) 。 这些简单的线图针对每个时间段显示一个未标记的 (例如，过去六周内每个时间段的一个未标记) 。 但是，可以通过将鼠标指针悬停在图形上来检索这些图形的实际值。 在这种情况下，工具提示会显示图形中的最大值和最小值。
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a>从监控仪表板导出数据

监控仪表板提供了多种导出当前仪表板视图的方法。 在仪表板工具栏上，你将看到一个看起来像软盘的图标，并附带一个绿色箭头。 如果单击此图标，将显示一个下拉列表，为您提供以下数据导出格式：
  
- 具有报告数据的 XML 文件
    
- CSV（逗号分隔）
    
- PDF
    
- MHTML（Web 存档）
    
- Excel
    
- TIFF 文件
    
- Word
    
若要导出当前仪表板视图 (及其值) ，请单击所需的导出选项。 Skype for Business Server 生成指定格式的报告，然后为您提供打开或保存该报告的选项。 请注意，默认情况下，Skype for Business Server 将报告标题设置为"监控仪表板"，并保存到"下载"文件夹中。 若要为报表指定其他名称或将其存储在不同的文件夹中，请单击"保存"按钮旁边的箭头，然后单击"另 **存为"。** 如果名称监控仪表板和将报告保存在"下载"文件夹中，只需单击"保存 **"** 按钮即可。
  
当您尝试导出仪表板数据时，可能会显示"安全警报"对话框以及消息"当前设置不允许下载此文件"。 如果发生这种情况，请执行下列操作：
  
- 在Internet Explorer中，选择 **"Internet 选项"。**
    
- 在 **"Internet 选项**"对话框中的"安全"选项卡上，单击"**受信任的** 站点"，然后单击"站点 **"。**
    
- 在"**受信任的站点"** 对话框中，单击"添加"以将运行 Skype for Business Server 报表的 Skype for Business Server 添加到受信任网站的集合。
    
- 单击 **"关闭**"，然后单击"确定 **"。**
    
然后，您需要刷新监控仪表板，更改才能生效。 为此，请按 F5 或单击仪表板工具栏中的 **"** 刷新"图标。  (**刷新图标** 是一个圆形，其中有一对绿色箭头。) 
  
还可以创建包含实时数据源的 Excel 电子表格，其中包含指向最新监控仪表板数据的链接。 若要创建实时数据馈送文件，请单击工具栏中的橙色 **"导出到数据源** "图标。
  
如果希望打印当前仪表板，请单击工具栏中的打印机图标。
