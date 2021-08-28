---
title: PSTN 会议摘要报告Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 摘要：了解 pstN 会议摘要报告中Skype for Business Server。
ms.openlocfilehash: c1f652e6c99db1e011624ee368244795555b61f4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591146"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>PSTN 会议摘要报告Skype for Business Server
 
**摘要：** 了解 PSTN 会议摘要报告中Skype for Business Server。
  
在 Skype for Business Server 中，PSTN 会议是至少一个参与者使用 PSTN (公用电话交换网或电话拨入音频部分) 会议。  (PSTN 电话是"座机"、"移动电话"或不使用 IP 语音的其他任何电话。) 尽管监控报告中称为 PSTN 会议，但是这些会议可能更常称为电话拨入式会议。
  
PSTN 会议摘要报告提供了有关您组织中召开的所有 PSTN 会议（即，所有至少有一个电话拨入式用户的会议）的信息。此报告包括有关 PSTN 会议总数和参与这些会议的人员总数的信息，并且可能包括有关电话拨入式用户的总数（PSTN 参与者指标总计）的信息（此信息最重要）。
  
## <a name="accessing-the-pstn-conference-summary-report"></a>访问 PSTN 会议摘要报告

只能从监控报告主页访问 PSTN 会议摘要报告。此报告未链接到任何其他报告。请注意，您无法检索 PSTN 会议的详细呼叫信息，部分原因在于单个终结点负责提交此信息。PSTN 电话无法跟踪或提交呼叫详细信息。
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>最充分地利用 PSTN 会议摘要报告

若要确定包含电话拨入用户的所有会议的百分比，请将 PSTN 会议指标总计值与 Skype for Business Server 中的会议摘要报告上找到的会议总指标[进行比较](conference-summary-report.md)。
  
如果您未看到所预计数目的 PSTN 会议，请记住，组织允许电话拨入式用户的会议的能力取决于已分配给用户的会议策略：如果仅允许几个用户主持 PSTN 会议，则可以明显看到 PSTN 会议的数目极少。 如果有任何会议策略 (命令行管理程序) 运行以下命令来快速验证哪些会议策略Skype for Business Server PSTN 会议：
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

这将返回与以下内容类似的数据：
  
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

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。 例如，PSTN 会议摘要报告允许您选择数据的分组方式。 在此示例中，将按小时、日、周或月对会议进行分组。
  
下表列出了可用于 PSTN 会议摘要报告的筛选器。
  
**PSTN 会议摘要报告筛选器**

|**名称**|**说明**|
|:-----|:-----|
|**From** <br/> |时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**To** <br/> |时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**Interval** <br/> | 时间间隔。选择下列选项之一： <br/>  每小时（最多可显示 25 个小时） <br/>  每天（最多可显示 31 天） <br/>  每周（最多可显示 12 周） <br/>  每月（最多可显示 12 个月） <br/>  如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。 例如，如果您选择开始日期为 2015/7/7 和结束日期为 2015/2/28 的"每天"间隔， 显示 2015 年 8 月 7 日上午 12：00 到 2015 年 9 月 7 日上午 12：00 (即总共 31 天的数据) 。 <br/> |
   
## <a name="metrics"></a>度量标准

下表列出了 PSTN 会议摘要报告中的信息。
  
**PSTN 会议摘要报告指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**每小时** <br/> **每天** <br/> **每周** <br/> **每月** <br/> |否  <br/> |指示所选的时间间隔。 如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。 例如，如果使用"每天"间隔并单击 2015/7/7，则会看到该日期的用户注册活动的每小时细分信息。  <br/> |
|**PSTN 会议总数** <br/> |否  <br/> |允许拨入访问的会议总数。  <br/> |
|**参与者总数** <br/> |否  <br/> |参与允许拨入访问的会议的人员总数。  <br/> |
|**A/V 会议总分钟数** <br/> |否  <br/> |音频/视频会议时间的总长度。  <br/> |
|**A/V 会议参与者总分钟数** <br/> |否  <br/> |音频/视频参与者时间的总长度。例如，如果一个参与者在 A/V 会议中花费了 5 分钟，另一个参与者在相同的会议中花费了 3 分钟，则 A/V 会议参与者总时间将为 8 分钟。  <br/> |
|**PSTN 参与者总数** <br/> |否  <br/> |拨入允许拨入访问的会议的用户的总数。  <br/> |
|**PSTN 参与者总分钟数** <br/> |否  <br/> |拨入用户花费的总会议时间长度。例如，如果一个拨入参与者在会议中花费了 5 分钟，另一个参与者在相同的会议中花费了 3 分钟，则 PSTN 参与者总时间将为 8 分钟。  <br/> |
|**唯一会议组织者** <br/> |否  <br/> |至少组织过一次允许拨入访问的会议的用户总数。与仅组织过一次会议的用户一样，组织过多次会议的用户算作一个唯一组织者。  <br/> |
   

