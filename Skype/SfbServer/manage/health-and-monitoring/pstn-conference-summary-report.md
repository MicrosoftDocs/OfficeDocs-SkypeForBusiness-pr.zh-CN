---
title: Skype for Business 服务器中的 PSTN 会议摘要报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 摘要：了解 Skype for Business 服务器中的 PSTN 会议摘要报告。
ms.openlocfilehash: c0ecb9ae2a5630a8d68b9d22892890617127826a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992157"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Skype for Business 服务器中的 PSTN 会议摘要报告
 
**摘要：** 了解 Skype for Business 服务器中的 PSTN 会议摘要报告。
  
在 Skype for Business 服务器中，PSTN 会议是指至少有一位参与者通过使用 PSTN （公共交换电话网络）电话拨入音频部分的任何会议。 （PSTN 电话是一种 "座机"、一种手机或任何其他未使用通过 IP 语音的电话。）尽管在监视报告中称为 PSTN 会议，但这些会议可能更常见，也称为拨入式会议。
  
PSTN 会议摘要报告提供了有关您组织中召开的所有 PSTN 会议（即，所有至少有一个电话拨入式用户的会议）的信息。此报告包括有关 PSTN 会议总数和参与这些会议的人员总数的信息，并且可能包括有关电话拨入式用户的总数（PSTN 参与者指标总计）的信息（此信息最重要）。
  
## <a name="accessing-the-pstn-conference-summary-report"></a>访问 PSTN 会议摘要报告

只能从监控报告主页访问 PSTN 会议摘要报告。此报告未链接到任何其他报告。请注意，您无法检索 PSTN 会议的详细呼叫信息，部分原因在于单个终结点负责提交此信息。PSTN 电话无法跟踪或提交呼叫详细信息。
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>最充分地利用 PSTN 会议摘要报告

若要确定包括拨入用户的所有会议的百分比，请将 PSTN 会议总指标的值与[Skype For Business Server 中 "会议摘要" 报表](conference-summary-report.md)上的 "总会议总数" 进行比较。
  
如果您未看到所预计数目的 PSTN 会议，请记住，组织允许电话拨入式用户的会议的能力取决于已分配给用户的会议策略：如果仅允许几个用户主持 PSTN 会议，则可以明显看到 PSTN 会议的数目极少。 你可以通过从 Skype for Business Server Management Shell 中运行以下命令，快速验证你的会议策略（如果有）允许用户安排 PSTN 会议：
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

这将返回与以下类似的数据：
  
<pre>
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True
</pre>

## <a name="filters"></a>筛选器

利用筛选器，你可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，PSTN 会议摘要报告允许你选择数据的分组方式。在此示例中，将按小时、日、周或月对会议进行分组。
  
下表列出了可用于 PSTN 会议摘要报告的筛选器。
  
**PSTN 会议摘要报告筛选器**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**说明**|
|:-----|:-----|
|**从** <br/> |时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 2015/7/7 13:00  <br/> 如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 2015/7/7  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 2015/7/3  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**到** <br/> |时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 2015/7/7 13:00  <br/> 如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 2015/7/7  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 2015/7/3  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**间隔** <br/> | 时间间隔。选择下列选项之一： <br/>  每小时（最多可显示 25 个小时） <br/>  每天（最多可显示 31 天） <br/>  每周（最多可显示 12 周） <br/>  每月（最多可显示 12 个月） <br/>  如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 2015/7/7、结束日期为 2015/2/28、间隔为“每天”，则显示从 2015/8/7 12:00 AM 到 2015/9/7 12:00 AM 这些天的数据（即总共 31 天的数据）。 <br/> |
   
## <a name="metrics"></a>指标

下表列出了 PSTN 会议摘要报告中的信息。
  
**PSTN 会议摘要报告指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**每小时** <br/> **每天** <br/> **每周** <br/> **每月** <br/> |否  <br/> |指示所选的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 2015/7/7，可查看当日用户注册活动的每小时细分信息。  <br/> |
|**PSTN 会议总数** <br/> |否  <br/> |允许拨入访问的会议总数。  <br/> |
|**参与者总数** <br/> |否  <br/> |参与允许拨入访问的会议的人员总数。  <br/> |
|**A/V 会议总分钟数** <br/> |否  <br/> |音频/视频会议时间的总长度。  <br/> |
|**A/V 会议参与者总分钟数** <br/> |否  <br/> |音频/视频参与者时间的总长度。例如，如果一个参与者在 A/V 会议中花费了 5 分钟，另一个参与者在相同的会议中花费了 3 分钟，则 A/V 会议参与者总时间将为 8 分钟。  <br/> |
|**PSTN 参与者总数** <br/> |否  <br/> |拨入允许拨入访问的会议的用户的总数。  <br/> |
|**PSTN 参与者总分钟数** <br/> |否  <br/> |拨入用户花费的总会议时间长度。例如，如果一个拨入参与者在会议中花费了 5 分钟，另一个参与者在相同的会议中花费了 3 分钟，则 PSTN 参与者总时间将为 8 分钟。  <br/> |
|**唯一会议组织者** <br/> |否  <br/> |至少组织过一次允许拨入访问的会议的用户总数。与仅组织过一次会议的用户一样，组织过多次会议的用户算作一个唯一组织者。  <br/> |
   

