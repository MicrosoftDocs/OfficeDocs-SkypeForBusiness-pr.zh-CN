---
title: Lync Server 2013：使用监控仪表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 643cbc55730d8efb1520ed88c40977c90e35f2fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a>在 Lync Server 2013 中使用监控仪表板

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

监控仪表板为管理员提供其 Microsoft Lync Server 2013 系统运行状况和系统使用情况的快速概述。 仪表板旨在显示关键系统指标的聚合视图，通过显示以下任一内容来实现此目标：

  - 当天的汇总。 请注意，当前日期显示的值表示从午夜到当前时间（基于报告服务器的本地时间）记录的数据。 这意味着您通常会查看部分日期的数据，而不是24小时的时间。 例如，如果服务器的本地时间为 8:00 AM，则会看到8小时的数据，因为午夜和当前时间为 8:00 AM 之间有八个小时。

  - 一周的总计和过去六周的趋势总计。

  - 月总数和过去六个月的趋势总计（仅适用于系统使用情况）。

请注意，您可以使用[CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet 返回用于访问 Lync Server 2013 监视报告的 URL：

    Get-CsReportingConfiguration

默认情况下，监控仪表板显示当前星期的以下指标的数据（和前六周的趋势总计）：

<div>

## <a name="system-usage-metrics"></a>系统使用指标

**注册**

  - 唯一用户登录

**对等**

  - 会话总数

  - IM 会话

  - 音频会话

  - 视频会话

  - 应用程序共享

  - 音频会话总分钟数

  - 平均音频会话分钟数

**发布会**

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

除了系统使用指标，以下指标还显示当前日期和前六天的总计（如果选择 "**每周视图**"），或者在选择 "**月视图**" 时为当前星期和过去六周。

</div>

<div>

## <a name="per-user-call-diagnostics"></a>每用户呼叫诊断

**具有呼叫失败的用户**

  - 具有呼叫故障的用户总数

  - 具有呼叫故障的会议组织者

**具有较差的呼叫质量较差的用户**

  - 使用质量较差的呼叫的用户总数

</div>

<div>

## <a name="call-diagnostics"></a>呼叫诊断

对等

  - 失败总次数

  - 整体故障率

  - IM 故障率

  - 音频故障率

  - 应用程序共享故障率

发布会

  - 失败总次数

  - 整体故障率

  - IM 故障率

  - A/V 故障率

  - 应用程序共享故障率

按失败会话排列的前5台服务器

</div>

<div>

## <a name="media-quality-diagnostics"></a>媒体质量诊断

对等

  - 质量较差的呼叫总数

  - 质量较差的呼叫百分比

  - 质量较差的 PSTN 呼叫

发布会

  - 质量较差的呼叫总数

  - 质量较差的呼叫百分比

  - 质量较差的 PSTN 呼叫

低质量呼叫百分比最差的服务器

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a>使用监控仪表板

如前所述，默认情况下显示当前周的汇总，并且趋势值显示过去六周。 如果您想要查看当前月的总和（以及过去六个月的趋势值），请单击仪表板右上角的 "**月视图**" 链接。 如果您决定查看每月总计，则链接文本将更改为**每周视图**。 您可以通过单击该链接切换回每周视图。

<div>


> [!TIP]  
> 监控仪表板限制您查看当前周（或月）的总和和过去六周（或月）的趋势值。 您不能更改这些日期和时间。 例如，不能使用仪表板查看每九个月前的时间段的报告总计。



</div>

"**本周**"、"**本月**" 或 "**今日**" 列中显示的值将链接到有关项目的更多详细信息。 请记住，列名称和列中显示的值通常会有所不同，具体取决于所选的指标，取决于您是否选择了 "每周" 视图或 "按月" 视图。 例如，如果单击显示的**唯一用户登录**指标的总计，则将在指定时间段内看到**用户注册报告**。 您可以通过单击 "**仪表板**" 随时返回到 "监控" 仪表板。

<div>


> [!TIP]  
> 您还可以通过单击仪表板右上角的 "<STRONG>报告</STRONG>" 链接来访问 "监视服务器报告" 主页。



</div>

"**趋势**" 列显示一个简单的线形图，显示过去六周的总计（或过去六天或过去六个月的时间间隔，取决于指标和时间间隔）。 这些简单的折线图为每个时间段显示一个未标记的数据点（例如，过去六周中每一个未标记的数据点）。 但是，您可以通过将鼠标指针悬停在关系图上来检索这些关系图的实际值。 在这种情况下，工具提示会向您显示图形中的最大值和最小值。

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a>从监控仪表板导出数据

监控仪表板提供了多种方法来导出当前的仪表板视图。 在仪表板工具栏上，你将看到一个图标，看起来像一个附加了绿色箭头的软盘。 如果单击此图标，将显示一个下拉列表，提供以下数据导出格式：

  - 具有报告数据的 XML 文件

  - CSV（逗号分隔）

  - PDF

  - MHTML（Web 存档）

  - Excel

  - TIFF 文件

  - Word

若要导出当前的仪表板视图（及其值），请单击所需的 "导出" 选项。 Lync Server 2013 生成指定格式的报告，然后为您提供打开该报告或保存该报告的选项。 请注意，默认情况下，Lync Server 将报告**监控仪表板**标题，并将其保存到 "下载" 文件夹中。 若要为报告指定不同的名称或将其存储在不同的文件夹中，请单击 "**保存**" 按钮旁边的箭头，然后单击 "**另存为**"。 如果您使用名称**监控仪表板**并将报告保存在 "下载" 文件夹中，只需单击 "**保存**" 按钮即可。

当您尝试导出仪表板数据时，将显示一个**安全警告**对话框，并显示 "当前设置不允许下载此文件" 消息。 如果出现这种情况，请执行以下操作：

  - 在 Internet Explorer 中，选择 " **Internet 选项**"。

  - 在 " **Internet 选项**" 对话框中的 "**安全**" 选项卡上，单击 "**受信任的网站**"，然后单击 "**网站**"。

  - 在 "**受信任的站点**" 对话框中，单击 "**添加**" 将运行 lync Server 2013 报告的 lync server 2013 添加到受信任的网站的集合。

  - 单击 "**关闭**"，然后单击 **"确定"**。

然后，您需要刷新监控仪表板，更改才会生效。 若要执行此操作，请按 F5 或单击仪表板工具栏中的 "**刷新**" 图标。 （**刷新**图标是一个圆圈，其中包含一对绿色箭头。）

您还可以创建包含实时数据源的 Excel 电子表格，其中包括指向最新监控仪表板数据的链接。 若要创建实时数据馈送文件，请单击工具栏中的 "**将导出为数据馈送**的橙色" 图标。

如果您希望打印当前仪表板，请单击工具栏中的打印机图标。

</div>

</div>

<span> </span>

</div>

</div>

</div>

