---
title: 业务服务器中 Skype 调用 Diagnostic Reports (per user)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9da13470-001e-415f-b8c5-29b1f3b531ba
description: 摘要： 了解每个用户呼叫诊断报告中 Skype 用于业务服务器。
ms.openlocfilehash: 0c8e17151ab07814db2b07d1f0dda3ead3a509f9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200307"
---
# <a name="call-diagnostic-reports-per-user-in-skype-for-business-server"></a>业务服务器中 Skype 调用 Diagnostic Reports (per user)
  
呼叫诊断报告提供有关失败的点对点会话和会议会话的每用户信息。 目前没有只有一个报告，**用户活动报告**。

用户活动报告提供了由用户在给定时间段内执行的对等会话和会议会话的详细列表。与很多监控报告不同，用户活动报告会将每个呼叫与单个用户绑定。例如，对等会话指定发起呼叫（源用户）的人员以及被呼叫（目标用户）的人员的 SIP URI。如果展开会议的信息，则会看到所有会议参与者及其在该会议中担任的角色的列表。

用户活动报告有时候称为“技术支持”报告。这是因为该报告通常由技术支持人员用于检索特定用户的会话信息。您可以筛选来自或发往单个用户的呼叫，只需在“用户 URI”前缀框中键入该用户的 SIP URI 即可。

如果这样做，用户活动报告将返回其 SIP URI 以指定字符串开头的任何用户的信息。 例如，如果您在 URI 框中键入 **ken**，则用户活动报告将查找 **Ken**.Myer@litwareinc.com。 但是，它还会查找以下用户：

- **ken** azi@litwareinc.com

- **ken** burg@litwareinc.com

- **Ken**.Sanchez@litwareinc.com

- **Ken** nedy@litwareinc.com

若要确保该信息仅为返回 Ken myer 的用户，键入其完整 URI (Ken.Myer@litwareinc.com) 在搜索框或至少足够类型的 Ken 的唯一区分他从您的组织中的其他用户的 URI。 例如：

Ken.my

## <a name="to-access-the-user-activity-report"></a>访问用户活动报告

用户活动报告是从“监控报告”主页访问的。 您还可以通过单击[IP 电话清单报告中 Skype 业务服务器](ip-phone-inventory-report.md)上的用户 URI 指标来访问用户活动报告。 在用户活动报告中，单击“会议 URI”（针对会议）会将您转到会议详细信息报告。 同样，单击对等呼叫详细信息指标可转到[Skype 业务服务器中的对等会话详细信息报告](peer-to-peer-session-detail-report.md)。

## <a name="making-the-best-use-of-the-user-activity-report"></a>充分利用用户活动报告

尽管用户活动报告中有很多有用的信息，但这些信息有时候可能很难找到。 用户活动报告; 例如，包含指定时段内组织中发生的所有用户活动是指淹没、 报告中，则有关哪些用户实际上用于 Skype 业务服务器以某种方式的信息。

> [!NOTE]
> 技术上讲，则可能某些用户活动可能转债务： 时 Skype 的业务服务器都在努力保留所有电话有关的信息可能的呼叫可能已进行了不写入到该呼叫的信息数据库。 Skype 业务服务器旨在使在 Skype 业务 server 如何使用的极准确，但不是一定是理想外观。 （这一事实存在的 100%的所有呼叫都将记录不能保证情况说明为什么业务服务器监控的 Skype 应不能用作帐单系统）。其次，监控报告可以仅显示，最 1,000 记录。 根据您具有的用户活动的数量以及您工作的时间段，这意味着您的查询可能无法返回数据库中实际存储的所有数据。 

- 哪些用户在此时间段内实际上使用了系统？

- 我的哪些用户在此时间段内最活跃？

- 发出电话呼叫最多的用户是否也是参与即时消息会话最多的用户？

如果您需要回答问题如下所示，您可以导出检索 Excel 电子表格监控报告的数据。 您然后使用该电子表格和/或逗号分隔值文件分析中的用户活动报告的方式的数据。 例如，假设已报表数据导出到 Excel 和逗号分隔值文件。 此时，您可以导入的数据。CSV 文件到 Windows PowerShell 使用类似如下的命令：

```
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

数据已导入后您然后可以使用简单的 Windows PowerShell 命令来帮助应答您的问题。 例如，以下命令将返回至少在一个会话中充当“源用户”的唯一用户的列表：

```
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

换言之：

<pre>
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
</pre>

以下命令将根据唯一用户参与的会话的总数列出这些用户：

```
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

这将返回类似于下面的数据：

<pre>
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
</pre>

以下命令会将报告的会话限制为将音频作为一种形式包含的会话：

```
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

如果将鼠标悬停在报告上显示的任何诊断 ID 上，则会出现一个描述该 ID 的工具提示。

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，用户活动报告允许您基于活动类型（即对等会话还是会议会话）或用户的 SIP 地址（允许您查看一个用户的活动）筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。

下表列出了可用于用户活动报告的筛选器。

**用户活动报告筛选器**


| **名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。   | **说明**  |
|:-----------|:--------|
| **从** <br/>             | 时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 7/17/12015 13:00  <br/> 如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 7/17/12015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 2015/7/13  <br/> 一周始终是从星期日开始至星期六结束。  <br/>                                                      |
| **到** <br/>               | 时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 7/17/12015 13:00  <br/> 如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 7/17/12015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 2015/7/13  <br/> 一周始终是从星期日开始至星期六结束。  <br/>                                                             |
| **活动类型** <br/>    | 活动的类型。选择下列选项之一： <br/>  [所有] <br/>  对等 <br/>  会议 <br/>      |
| **形式** <br/>         | 可用的形式取决于选择的“活动类型”。 如果对等活动类型，您可以选择 IM;文件传输;应用程序共享;语音;或为形式的视频。  <br/> 如果“活动类型”是“会议”，您可以选择“IM 电话会议”、“Web 会议”、“应用程序共享”、“语音/视频会议”或“电话会议”。  <br/>         |
| **会话类别** <br/> | 指示相应活动已成功还是失败。选择下列选项之一： <br/>  [所有] <br/>  成功 <br/>  预期失败 <br/>  意外失败 <br/>  “预期失败”是指预计会出现的失败情况；例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。“意外失败”是指在本该正常运行的系统中出现的失败情况。例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。如果终止，则会被标记为意外失败。 <br/> |
| **用户 URI 前缀** <br/>  | 用户的 SIP 地址。要仅查看用户 Ken Myer 的记录，您需要输入 Ken Myer 的 SIP 地址。例如：  <br/> sip:kenmyer@litwareinc.com  <br/>

## <a name="metrics-for-peer-to-peer-sessions"></a>对等会话的指标

下表列出了对等会话（即，只涉及两个参与者的会话）的用户活动报告中提供的信息。

**对等会话的指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**详情** <br/> |否  <br/> |单击此项时，报告将显示所选会话的对等会话详细信息报告。  <br/> |
|**来源用户** <br/> |是  <br/> |发起对等会话的用户的 SIP 地址。  <br/> |
|**目标用户** <br/> |是  <br/> |加入对等会话的用户的 SIP 地址。  <br/> |
|**形式** <br/> |是  <br/> |会话中使用的通信类型。例如，IM、音频或文件传输。  <br/> |
|**邀请时间** <br/> |是  <br/> |发送加入对等会话的初始邀请的日期和时间。  <br/> |
|**响应时间** <br/> |是  <br/> |“目标”用户接受会话邀请的日期和时间。  <br/> |
|**结束时间** <br/> |是  <br/> |对等会话结束的日期和时间。  <br/> |
|**诊断 ID** <br/> |是  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>会议会话的指标

下表列出了会议会话（即，涉及三个或更多参与者的会话）的用户活动报告中提供的信息。

**会议会话的指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**会议 URI** <br/> |是  <br/> |唯一会议标识符。单击此项时，报告将显示所选会话的会议详细信息报告。展开此项时，报告将显示有关会议参与者的信息。有关详细信息，请参阅本主题后面的“会议参与者的指标”一节。  <br/> |
|**组织者** <br/> |是  <br/> |组织会议的用户的 SIP 地址。  <br/> |
|**池** <br/> |是  <br/> |会议中使用的边缘服务器（如果有）的名称。  <br/> |
|**开始时间** <br/> |是  <br/> |会议开始的日期和时间。  <br/> |
|**结束时间** <br/> |是  <br/> |会议结束的日期和时间。  <br/> |

## <a name="metrics-for-conference-participants"></a>会议参与者的指标

下表列出了会议的每个参与者的用户活动报告中提供的信息。

**会议参与者的指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**角色** <br/> |否  <br/> |用户的会议角色（例如，演示者）。  <br/> |
|**参与者** <br/> |否  <br/> |用户的 SIP 地址。  <br/> |
|**连接** <br/> |否  <br/> |网络连接类型。例如，“来自内部”表示内部连接，“来自 PSTN”表示拨入用户。  <br/> |
|**加入时间** <br/> |否  <br/> |用户加入会议的日期和时间。  <br/> |
|**离开时间** <br/> |否  <br/> |用户离开会议的日期和时间。  <br/> |
|**诊断 ID** <br/> |否  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。  <br/> |

