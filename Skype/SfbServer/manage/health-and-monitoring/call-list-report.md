---
title: 响应组中响应组呼叫列表Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 摘要：了解应用程序中的响应组Skype for Business Server。
ms.openlocfilehash: 8f86e71606f09d5f2313578ef0ab90dfd20c654d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398936"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a>响应组中响应组呼叫列表Skype for Business Server

**摘要：** 了解应用程序中的响应组Skype for Business Server。

响应组应用程序提供了一种Skype for Business Server根据拨打的号码以及（可选）呼叫者对一系列问题的响应来应答和路由电话呼叫。 通常，响应组呼叫不路由到单个人员，而是路由到称为代理组的一组人员。 例如，如果有人呼叫技术支持的电话号码，Skype for Business Server可以将该呼叫自动路由到第一个可用的技术支持代理。 或者，Skype for Business Server在遇到硬件问题 (请按 1"时询问一系列问题。 如果您有软件问题，请按 2。 如果您有网络问题，请按 3。") ，然后根据这些问题的回答将呼叫路由至最合适的技术支持代理。

响应组呼叫列表报告代表针对指定的时间段和指定的呼叫类型所进行的呼叫集合。响应组使用报告（必需先打开该报告，才能打开响应组呼叫列表报告）可识别以下呼叫类型：

- **收到的呼叫**。响应组应用程序的所有实例收到的呼叫总数。

- **成功呼叫**。 响应组应用程序接听的呼叫总数。

- **发起的呼叫**。转接到响应组代理的呼叫总数。

- **应答的呼叫**。响应组代理实际应答的呼叫总数。

- **放弃的呼叫的百分比。** 响应组应用程序已收到但代理未应答的呼叫的百分比。 此值的计算方法是用“收到的呼叫数”减去“应答的呼叫数”，然后用所得的值除以收到的呼叫数。 例如，如果收到 10 个呼叫，但应答了 7 个，则计算方法是 10 减去 7，得出未应答的呼叫是 3 个。 然后用该值除以 10，得出放弃的呼叫的百分比为 30%。

- **转接的呼叫**。因队列超时或队列溢出而转接的响应组呼叫总数。

## <a name="accessing-the-response-group-call-list-report"></a>访问响应组呼叫列表报告

只能单击"响应组使用情况报告"中的以下指标之一来访问响应组呼叫[列表Skype for Business Server](response-group-usage-report.md)：

- 收到的呼叫

- 成功呼叫

- 发起的呼叫

- 应答的呼叫

- 转接的呼叫

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>充分利用响应组呼叫列表报告

响应组呼叫列表报告允许您将所显示的数据限制为涉及特定响应组工作流的呼叫。为执行此操作，需要在“工作流 URI”框中输入工作流 URI（工作流的 SIP 地址）。但是，您必须实际上能够看到“工作流 URI”框，才能执行此操作。要显示响应组呼叫列表报告的筛选选项，请单击报告窗口左上部分的“显示/隐藏参数”按钮。

请注意，如果将鼠标停留在其中任一指标上，响应组呼叫列表不会显示有关响应代码或诊断 ID 的信息。 如果您需要更多信息，您可以记下响应代码和/或诊断 ID，然后在 Skype for Business Server 中的"首要故障报告["中搜索这些值](top-failures-report.md)。

对于类似如下的问题：“哪个个别工作流收到的呼叫数最多？”，您可以执行以下操作：

1. 在“响应组使用报告”上，设置所需的时间段，然后单击“收到的呼叫”指标。这样即会打开“响应组呼叫列表报告”。

2. 导出“响应组呼叫列表报告”上所显示的数据。例如，可以使用 Microsoft Excel 格式导出数据，然后使用 Excel 将该数据转换为逗号分隔值文件。

3. 使用 Windows PowerShell 运行您的分析。

例如，如果已将数据保存到名为 C:\Data\Response_Group_Call_List_Report.csv 的文件，则可以使用以下命令，针对报告中所列出的每个工作流返回收到的呼叫总数：

```PowerShell
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

这将返回与以下类似的信息：

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于响应组呼叫列表报告的筛选器。

**响应组呼叫列表报告筛选器**


| **名称**               | **说明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **From** <br/>         | 时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
| **To** <br/>           | 时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/>        |
| **工作流 URI** <br/> | 允许您限制返回的数据，以便仅显示指定响应组工作流的数据。若要使用该筛选器，请输入工作流 SIP 地址。例如：  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| **通话** <br/>        | 可以选择以下呼叫类型之一： <br/>  收到的呼叫 <br/>  成功呼叫 <br/>  提供的呼叫 <br/>  应答的呼叫 <br/>  转接的呼叫 <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a>度量标准

下表列出了响应组应用程序收到的每个呼叫的响应组呼叫列表报告中提供的信息。

**响应组呼叫列表报告指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**Caller** <br/> |否  <br/> |呼叫者的 SIP 地址  <br/> |
|**工作流** <br/> |否  <br/> |响应组工作流的 SIP 地址。  <br/> |
|**开始时间** <br/> |否  <br/> |呼叫开始的日期和时间。  <br/> |
|**结束时间** <br/> |否  <br/> |呼叫结束的日期和时间。  <br/> |
|**响应代码** <br/> |否  <br/> |会话失败时发送的 SIP 响应代码。  <br/> |
|**诊断 ID** <br/> |否  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。  <br/> |


