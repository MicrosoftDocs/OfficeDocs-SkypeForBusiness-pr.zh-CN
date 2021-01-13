---
title: Skype for Business Server (每个用户) 诊断报告
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
ms.assetid: 9da13470-001e-415f-b8c5-29b1f3b531ba
description: 摘要：了解 Skype for Business Server 中使用的每用户呼叫诊断报告。
ms.openlocfilehash: bcf59c63e98bb7c701b52fd6df564da16fd3761d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817092"
---
# <a name="call-diagnostic-reports-per-user-in-skype-for-business-server"></a>Skype for Business Server (每个用户) 诊断报告
  
呼叫诊断报告提供有关失败的点对点会话和会议会话的每用户信息。 目前只有一个报告，即 **用户活动报告**。

用户活动报告提供了由用户在给定时间段内执行的点对点会话和会议会话的详细列表。与很多监控报告不同，用户活动报告会将每个呼叫与单个用户绑定。例如，点对点会话指定发起呼叫（源用户）的人员以及被呼叫（目标用户）的人员的 SIP URI。如果展开会议的信息，则会看到所有会议参与者及其在该会议中担任的角色的列表。

用户活动报告有时候称为“技术支持”报告。这是因为该报告通常由技术支持人员用于检索特定用户的会话信息。您可以筛选来自或发往单个用户的呼叫，只需在“用户 URI”前缀框中键入该用户的 SIP URI 即可。

如果这样做，用户活动报告将返回 SIP URI 以指定字符串开头的任何用户的信息。 例如，如果在 URI 框中键入 **ken，** 则用户活动报告将找到 **Ken。** Myer@litwareinc.com。 但是，它还会找到以下用户：

- **ken** azi@litwareinc.com

- **ken** burg@litwareinc.com

- **Ken**。Sanchez@litwareinc.com

- **Ken** nedy@litwareinc.com

若要确保仅返回 Ken Myer 的信息，在搜索框中键入他的完整 URI (Ken.Myer@litwareinc.com) ，或至少键入 Ken 的 URI 类型以将其与组织中其他用户进行唯一区分。 例如：

Ken.my

## <a name="to-access-the-user-activity-report"></a>访问用户活动报告

用户活动报告是从“监控报告”主页访问的。 您还可以通过单击 Skype for Business Server 中的 IP 电话清单报告上的用户 URI 指标来访问 [用户活动报告](ip-phone-inventory-report.md)。 在用户活动报告中，单击“会议 URI”（针对会议）会将您转到会议详细信息报告。 同样，单击对等呼叫的详细信息指标将进入 Skype for Business Server 中的对等会话 [详细信息报告](peer-to-peer-session-detail-report.md)。

## <a name="making-the-best-use-of-the-user-activity-report"></a>充分利用用户活动报告

尽管用户活动报告中有很多有用的信息，但这些信息有时候可能很难找到。 例如，指定期间在组织中发生的所有用户活动都包含在用户活动报告中;这意味着报告中隐藏着有关哪些用户以某种方式实际使用 Skype for Business Server 的信息。

> [!NOTE]
> 从技术上说，某些用户活动可能未记录：虽然 Skype for Business Server 努力保留有关所有电话呼叫的信息，但可能在未将有关该呼叫的信息写入数据库的情况下进行了呼叫。 Skype for Business Server 旨在提供非常准确但不一定完美地查看 Skype for Business Server 的使用方式。  (无法保证记录 100% 的呼叫，这说明为什么 Skype for Business Server 监控不应用作计费系统。) 其次，监控报告最多只能显示 1，000 条记录。 根据您具有的用户活动的数量以及您工作的时间段，这意味着您的查询可能无法返回数据库中实际存储的所有数据。 

- 哪些用户在此时间段内实际上使用了系统？

- 我的哪些用户在此时间段内最活跃？

- 发出电话呼叫最多的用户是否也是参与即时消息会话最多的用户？

如果需要回答类似这样的问题，可以将监控报告检索到的数据导出到 Excel 电子表格。 然后使用该电子表格和/或逗号分隔值文件以用户活动报告的方式分析数据。 例如，假设您已经将报表数据导出到 Excel，然后导出到逗号分隔的值文件中。 此时，可以从中导入数据。要通过使用Windows PowerShell的 CSV 文件：

```PowerShell
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

导入数据后，可以使用简单的Windows PowerShell命令来帮助回答你的问题。 例如，以下命令将返回至少在一个会话中充当“源用户”的唯一用户的列表：

```PowerShell
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

换一种形式就是：

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

```PowerShell
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

```PowerShell
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

如果将鼠标悬停在报告上显示的任何诊断 ID 上，则会出现一个描述该 ID 的工具提示。

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，用户活动报告允许您基于活动类型（即点对点会话还是会议会话）或用户的 SIP 地址（允许您查看一个用户的活动）筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。

下表列出了可用于用户活动报告的筛选器。

**用户活动报告筛选器**


| **名称**   | **说明**  |
|:-----------|:--------|
| **From** <br/>             | 时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 7/17/12015 1：00 PM  <br/> 如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 7/17/12015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/13/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/>                                                      |
| "自" <br/>               | 时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 7/17/12015 1：00 PM  <br/> 如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 7/17/12015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/13/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/>                                                             |
| **活动类型** <br/>    | 活动的类型。选择下列选项之一： <br/>  [全部] <br/>  对等 <br/>  会议 <br/>      |
| **形式** <br/>         | 可用的形式因选择活动类型而异。 如果活动类型为对等，可以选择 IM;文件传输;应用程序共享;语音;或视频形式。  <br/> 如果活动类型为会议，可以选择 IM 电话会议;Web 会议;应用程序共享;语音/视频会议;或电话会议。  <br/>         |
| **会话类别** <br/> | 指示相应活动已成功还是失败。选择下列选项之一： <br/>  [全部] <br/>  成功 <br/>  预期失败 <br/>  意外失败 <br/>  “预期失败”是指预计会出现的失败情况；例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。“意外失败”是指在本该正常运行的系统中出现的失败情况。例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。如果终止，则会被标记为意外失败。 <br/> |
| **用户 URI 前缀** <br/>  | 用户的 SIP 地址。要仅查看用户 Ken Myer 的记录，您需要输入 Ken Myer 的 SIP 地址。例如：  <br/> sip:kenmyer@litwareinc.com  <br/>

## <a name="metrics-for-peer-to-peer-sessions"></a>点对点会话的指标

下表列出了点对点会话（即，只涉及两个参与者的会话）的用户活动报告中提供的信息。

**点对点会话的指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**详细信息** <br/> |否  <br/> |单击此项时，报告将显示所选会话的点对点会话详细信息报告。  <br/> |
|**来源用户** <br/> |是  <br/> |发起点对点会话的用户的 SIP 地址。  <br/> |
|**目标用户** <br/> |是  <br/> |加入点对点会话的用户的 SIP 地址。  <br/> |
|**形式** <br/> |是  <br/> |会话中使用的通信类型。例如，IM、音频或文件传输。  <br/> |
|**邀请时间** <br/> |是  <br/> |发送加入点对点会话的初始邀请的日期和时间。  <br/> |
|**响应时间** <br/> |是  <br/> |“目标”用户接受会话邀请的日期和时间。  <br/> |
|**结束时间** <br/> |是  <br/> |点对点会话结束的日期和时间。  <br/> |
|**诊断 ID** <br/> |是  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>会议会话的指标

下表列出了会议会话（即，涉及三个或更多参与者的会话）的用户活动报告中提供的信息。

**会议会话的指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**会议 URI** <br/> |是  <br/> |唯一会议标识符。单击此项时，报告将显示所选会话的会议详细信息报告。展开此项时，报告将显示有关会议参与者的信息。有关详细信息，请参阅本主题后面的“会议参与者的指标”一节。  <br/> |
|**Organizer** <br/> |是  <br/> |组织会议的用户的 SIP 地址。  <br/> |
|**Pool** <br/> |是  <br/> |会议中使用的边缘服务器（如果有）的名称。  <br/> |
|**开始时间** <br/> |是  <br/> |会议开始的日期和时间。  <br/> |
|**结束时间** <br/> |是  <br/> |会议结束的日期和时间。  <br/> |

## <a name="metrics-for-conference-participants"></a>会议参与者的指标

下表列出了会议的每个参与者的用户活动报告中提供的信息。

**会议参与者的指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**角色** <br/> |否  <br/> |用户的会议角色（例如，演示者）。  <br/> |
|**参与者** <br/> |否  <br/> |用户的 SIP 地址。  <br/> |
|**连接** <br/> |否  <br/> |网络连接类型。例如，“来自内部”表示内部连接，“来自 PSTN”表示拨入用户。  <br/> |
|**加入时间** <br/> |否  <br/> |用户加入会议的日期和时间。  <br/> |
|**离开时间** <br/> |否  <br/> |用户离开会议的日期和时间。  <br/> |
|**诊断 ID** <br/> |否  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。  <br/> |

