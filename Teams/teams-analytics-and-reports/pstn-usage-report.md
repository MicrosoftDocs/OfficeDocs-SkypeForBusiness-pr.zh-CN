---
title: Microsoft 团队 PSTN 使用报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: 了解如何使用 Microsoft 团队管理中心中的 "团队 PSTN 使用情况" 报表大致了解组织中的通话和音频会议使用情况。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3372bc77a4850da0690c2076c5858812e3e80452
ms.sourcegitcommit: a4fd238de09366d6ed33d72c908faff812da11a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637189"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft 团队 PSTN 使用报告

Microsoft 团队管理中心中的 "团队 PSTN 使用情况" 报表概括介绍了您的组织中的通话和音频会议活动。 如果您使用的是电话运营商，则可以查看呼叫计划的详细呼叫活动，以及使用自己的电话运营商时的直接路由。

"**呼叫计划**" 选项卡显示信息，包括用户在入站和出站 PSTN 呼叫中花费的分钟数以及这些呼叫的开销。 **直接路由**选项卡显示您的信息，包括 SIP 地址和通话开始和结束时间。 使用此报告中的信息可深入了解你的组织中的 PSTN 使用情况，并帮助你调查、规划和制定业务决策。

## <a name="view-the-report"></a>查看报告

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**分析" & 报告** > **使用情况报告**。 在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 " **PSTN 使用情况报告**"。
2. 在 "**日期范围**" 下，选择7天或28天的预定义范围，或设置自定义范围，然后选择 "**运行报表**"。

## <a name="interpret-the-report"></a>解释报告

### <a name="calling-plans"></a>通话套餐

![管理中心中的呼叫计划 PSTN 使用情况报告报告的屏幕截图](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "使用编号标注的 Microsoft 团队管理中心中的 PSTN 使用情况报告的屏幕截图")

|标注 |说明  |
|--------|-------------|
|**1**   |可查看最近7天、28天或您设置的自定义日期范围内的趋势的报表 |
|**2**   |每个报表都有一个生成日期的日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |X 轴表示特定报表的选定日期范围。 Y 轴是选定时间段内的调用总数。 <br>将鼠标悬停在给定日期的点上可查看该日期的总通话。  |
|**4**   |该表为您提供了每次通话的 PSTN 使用情况的细目。 <ul><li>**时间戳（UTC）** 是呼叫开始的时间。</li><li>"**显示名称**" 是用户的显示名称。 你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。</li><li>**用户名**是用户的登录名。</li><li>"**电话号码**" 是为拨入电话接收呼叫的号码，或者是为拨出电话拨出的号码。</li><li>**呼叫类型**指示呼叫是 PSTN 出站通话还是入站呼叫以及呼叫类型，例如由用户或音频会议发出的呼叫。 您可能看到的通话类型包括：<br><br>**团队用户呼叫类型**<ul><li>**user_in** -用户收到入站 PSTN 呼叫。</li><li>**user_out** -用户发出了出站 PSTN 呼叫</li><li>**user_out_conf** -用户向呼叫添加了两个或多个 PSTN 参与者，例如三向电话会议</li><li>**user_out_transfer** -用户已将呼叫转移到 PSTN 号码</li><li>**user_out_forwarding** -用户将呼叫转移到 PSTN 号码</li><li>**conf_in** -到音频会议桥的入站呼叫</li><li>**conf_out** -来自音频会议桥的出站呼叫通常是向会议添加 PSTN 号码</li></ul><br>**团队机器人呼叫类型**<ul><li>**ucap_in** -对团队机器人（如自动助理或呼叫队列）的入站 PSTN 呼叫</li><li>**ucap_out** -来自团队机器人（如自动助理或呼叫队列）的出站 PSTN 呼叫</li></ul><br><li>拨**叫的**号码。</li><li>"**国家或地区**" 是已拨打的国家或地区。</li><li>"**来源**" 表示发出呼叫的号码。</li><li>**从 "国家或地区**" 是呼叫所在的国家或地区。</li><li>"**费用**" 表示为您的帐户收取的通话金额或通话费用。 </li><li>**货币**是用于计算通话费用的货币类型。 </li><li>" **持续时间**"是接听呼叫的时间。</li><li>**国内/国际**根据用户的位置告诉你呼叫是国内（在国家或地区）还是国际（位于国家或地区外）。</li><li>通话**id**是呼叫的呼叫 id。 它是呼叫 Microsoft 支持时可以使用的呼叫的标识符。</li><li>"**号码类型**" 是用户的电话号码类型，例如免费号码的服务。 </li><li>**国家或地区**是使用位置。 </li> <li>"**会议 id** " 是音频会议的会议 id。 </li><li>**功能**是用于通话的许可证。 您可能看到的许可证类型包括：<ul><li>**MCOPSTNPP** -通讯信用点数</li><li>**MCOPSTN1** -国内通话计划（3000，美国/1200 最少欧盟计划）</li><li>**MCOPSTN2** -国际通话计划</li><li>**MCOPSTN5** -国内通话计划（120分钟通话计划）</li><li>**MCOPSTN6** -国内通话计划（240分钟通话计划）</li><li>**MCOMEETADD** -音频会议</li><li>**MCOMEETACPEA** -每分钟支付的音频会议</li></ul></li></ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |选择 "**筛选**" 以按用户名或呼叫类型筛选报告 |
|**7**   |选择 "**全屏**" 以全屏模式查看报表。 |
|**个**   |你可以将报表导出到 CSV 文件，以便脱机分析。 单击 "**导出到 Excel**"，然后在 "**下载**" 选项卡上，单击 "**下载**" 以在准备就绪后下载报告。|

### <a name="direct-routing"></a>直接路由

![管理中心中直接路由 PSTN 使用情况报告报告的屏幕截图](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "使用编号标注的 Microsoft 团队管理中心中的直接路由 PSTN 使用报告的屏幕截图")

|标注 |说明  |
|--------|-------------|
|**1**   |可查看过去7天或28天的趋势的报告。 |
|**2**   |每个报表都有一个生成日期的日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |X 轴表示特定报表的选定日期范围。 Y 轴是选定时间段内的调用总数。<br>将鼠标悬停在给定日期的点上可查看该日期的总通话。  |
|**4**   |该表为您提供了每次通话的 PSTN 使用情况的细目。 <ul><li>**时间戳（UTC）** 是呼叫开始的时间。</li><li>"**显示名称**" 是用户的显示名称。 你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。 名称也可以是 bot 的名称，例如呼叫队列或云自动助理。 </li><li>**Sip 地址**是接收或进行呼叫的用户或 BOT 的 sip 地址。</li><li>**呼叫方号码**是指发出呼叫的用户或机器人的号码。 </li><li>**被叫方号码**是指接收呼叫的用户或机器人的号码。 在对团队的入站呼叫中，该用户将成为团队用户，在来自团队的出站呼叫中，它将成为 PSTN 用户。 </li><li>**呼叫类型**指示呼叫是 PSTN 出站通话还是入站呼叫以及呼叫类型，例如由用户或音频会议发出的呼叫。 您可能看到的呼叫类型包括：<br><br>**团队用户呼叫类型**<ul><li>**dr_in** -用户收到入站 PSTN 呼叫</li><li>**dr_out** -用户发出了出站 PSTN 呼叫</li><li>**dr_out_user_conf** -用户向呼叫添加了 PSTN 参与者</li><li>**user_out_transfer** -用户已将呼叫转移到 PSTN 号码</li><li>**dr_out_user_forwarding** -用户将呼叫转移到 PSTN 号码</li><li>**dr_out_user_transfer** -用户已将呼叫转移到 PSTN 号码</li><li>**dr_emergency_out** -用户拨打了紧急电话</li></ul><br>**团队机器人呼叫类型**<ul><li>**dr_in_ucap** -到团队机器人（如自动助理或呼叫队列）的入站 PSTN 呼叫</li><li>**dr_out_ucap** -来自团队机器人（如自动助理或呼叫队列）的出站 PSTN 呼叫</li></ul><br><li>**被叫**方指接收呼叫的用户的号码。</li><li>"**开始时间（UTC）** " 是 SIP 代理在来自出站呼叫（团队/BOT 到 PSTN 用户）上从 SBC 收到最终答案（sip 消息 "200 OK"），或者在入站呼叫（由团队/BOT 的 PSTN 用户）将邀请发送到团队后端中的下一个跃点之后的时间。 </li><li>**邀请时间（UTC）** 是指从团队用户或机器人调用到 sbc 的出站呼叫发送初始邀请的时间，或者通过从 SBC 直接路由的 SIP 代理组件呼叫接收到团队或机器人呼叫的入站呼叫发送。</li><li>**失败时间（UTC）** 是呼叫失败的时间。 仅限失败的通话。 最终 SIP 代码、最终 Microsoft 子代码和最终 SIP 短语提供了呼叫失败的原因，并可帮助进行故障排除。 </li><li>**结束时间（UTC）** 是通话结束的时间（仅适用于成功的呼叫）。</li><li>" **持续时间**"是接听呼叫的时间。</li><li>"**号码类型**" 是用户的电话号码类型，例如免费号码的服务。 </li><li>"**媒体绕过**" 指示是否为媒体旁路启用了主干。 </li> <li>**SBC FQDN**是会话边界控制器（SBC）的完全限定的域名（FQDN）。 </li><li>**媒体的 Azure 区域**是在非旁路呼叫中用作媒体路径的数据中心。 </li><li>用于发送**信号的 Azure 区域**是用于发送绕过和非绕过呼叫的信号的数据中心。 </li><li>**事件类型**是通话的事件类型。 您将看到成功的通话成功，并且尝试进行失败的通话。 </li><li>**最终 SIP 代码**是通话结束的代码。</li><li>**最终 Microsoft 子代码**是指示发生的特定操作的代码。</li><li>**最终 sip 短语**是 sip 代码和 Microsoft 子代码的说明。</li><li>**相关 ID**是呼叫的唯一标识符，可在呼叫 Microsoft 支持时使用。</li><li>**共享的相关性 ID**仅在可下载的 CSV 文件中可见，并且在门户中不存在。 共享相关 ID 至少存在于两个相关的通话中。 请参阅下面的详细说明。</li></ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |选择 "**全屏**" 以全屏模式查看报表。 |
|**7**   |选择 "**导出到 Excel** " 以将数据下载到逗号分隔的文件（CSV）中，以便脱机分析或将其用作帐单系统的输入。 |

#### <a name="callercallee-fields-considerations"></a>"调用方/被调用方" 字段注意事项

根据呼叫方向，呼叫方或被叫方名称可以包含非 E164 号码。

这些字段可以来自客户 SBC。 SBC 可以发送到直接路由的三种格式： E. 164 个数字、非 E、164个数字和字符串。

- 从具有 E-164 个号码的用户到另一个也有164个号码的用户发送了 e. 164 个电话号码。 
- 从非 E-164 个号码拨打电话。 通过直接路由与直接路由的第三方 PBX 互连的用户可以呼叫团队用户。 在这种情况下，呼叫方号码可以是任何非 E. 164 号，例如 + 1001。 
- 垃圾邮件发送者呼叫，而不是显示数字，而只是一个名称，例如 "内部收入服务"。 此字符串将显示在报表中。

#### <a name="about-shared-correlation-id"></a>关于共享的相关 ID

共享相关 ID 仅存在于你下载的导出的 Excel 文件中，并且指示两个或多个调用相互关联。 下面介绍了不同的方案，以及何时存在共享的相关 ID。

1.  在团队客户端上名为 "团队用户 1" 的 pstn 终结点上的 PSTN 用户1，呼叫类型 Dr_In，相关 ID 57f28917-42k5-4c0c-9433-79734873f2ac，没有共享的相关 ID。
2.  团队用户1在 PSTN 终结点上名为 PSTN 用户1的团队客户端上，呼叫类型 Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4，没有共享的相关 ID。
3.  在团队客户端上称为团队用户2的 pstn 终结点上的 PSTN 用户1，呼叫类型 Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9、共享相关 ID f45e9a25-9f94-46e7-a457-84f5940efde9。
4.  与相关 ID 为 "f45e9a25-9f94-46e7-a457-84f5940efde9" 的现有呼叫3。 使用团队用户2进行呼叫的 PSTN 用户1。 团队用户2已转移（盲人或咨询）对团队或 PSTN 用户的呼叫、呼叫类型 Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0、共享相关 ID f45e9a25-9f94-46e7-a457-84f5940efde9。

## <a name="exporting-the-reports"></a>导出报表
单击 "**导出到 Excel**"，然后在 "**下载**" 选项卡上，单击 "**下载**" 以在准备就绪后下载报告。 导出过程可能需要几秒钟到几分钟才能完成，具体取决于数据的数量。

此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 导出的文件包含在联机报表中不可用的其他字段。 这些可用于疑难解答和自动化工作流。

 您将收到名为 "**调用. 导出 ...`[identifier]`" 的 zip 文件。zip**"，其中标识符是可用于疑难解答的导出的唯一 ID。

如果既有通话计划又有直接路由，则导出的文件可能包含两个产品的数据。 PSTN 使用报告文件将具有文件名 "**PSTN.`[UTC date]`"。csv**"和直接路由"**DirectRouting`[UTC date]`"。csv**"。

 除了 PSTN 和直接路由文件，存档中还包含带有所选导出时间范围和功能的文件 "**参数. json**"。

导出的文件采用逗号分隔值（CSV）格式，符合[RFC 4180](https://tools.ietf.org/html/rfc4180)标准。 可以在 Excel 或任何其他符合标准的编辑器中打开文件，无需任何转换。

CSV 的第一行包含列名称。 所有日期均为 UTC，格式为[ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 。

### <a name="exported-pstn-usage-report"></a>导出的 PSTN 使用情况报告

 您可以从当前日期导出一年的数据，除非特定国家/地区的法规禁止将数据保留12个月。

| # | 名称 | [数据类型（SQL Server）](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | 说明 |
| :-: | :-: | :-: |:------------------- |
| 0 | UsageId | `uniqueidentifier` | 唯一的呼叫标识符 |
| 1 | 通话 ID | `nvarchar(64)` | 通话标识符。 不保证唯一性 |
| ppls-2 | 会议 ID | `nvarchar(64)` | 音频会议的 ID |
| 3 | 用户位置 | `nvarchar(2)` | 用户的国家/地区代码， [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
| 4 | AAD ObjectId | `uniqueidentifier` | 在 Azure Active Directory 中调用用户的 ID。<br/> 对于 bot 呼叫类型（ucap_in，ucap_out），此和其他用户信息将为 null/空 |
| 5 | UPN | `nvarchar(128)` | Azure Active Directory 中的 UserPrincipalName （登录名称）。<br/>这通常与用户的 SIP 地址相同，并且可以与用户的电子邮件地址相同 |
| 6 | 用户显示名称 | `nvarchar(128)` | 用户的显示名称 |
| 7 | 来电显示 | `nvarchar(128)` | 为拨入电话或拨出电话拨出的电话号码接收呼叫的号码。 [E. 164](https://en.wikipedia.org/wiki/E.164)格式 |
| 个 | 呼叫类型 | `nvarchar(32)` | 呼叫是 PSTN 出站通话还是入站呼叫以及呼叫类型，例如由用户或音频会议发出的呼叫 |
| db-9 | 号码类型 | `nvarchar(16)` | 用户的电话号码类型，例如免费号码的服务 |
| 10 | 国内/国际 | `nvarchar(16)` | 呼叫是国内的（在国家或地区内）还是国际（在国家或地区之外）基于用户的位置 |
| 11 | 已拨目标 | `nvarchar(64)` | 拨打的国家或地区 |
| 至 | 目标号码 | `nvarchar(32)` | 以[164](https://en.wikipedia.org/wiki/E.164)格式拨打的号码 |
| 13 | 开始时间 | `datetimeoffset` | 通话开始时间 |
| 14 | 结束时间 | `datetimeoffset` | 通话结束时间 |
| 岁 | 持续秒数 | `int` | 通话的连接时间 |
| utf-16 | 连接费 | `numeric(16, 2)` | 连接费价格 |
| 日 | 收费 | `numeric(16, 2)` | 为您的帐户收取的通话金额或通话费用 |
| 18 | 货币 | `nvarchar(3)` | 用于计算通话费用的货币类型（[ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)） |
| 19 | 能 | `nvarchar(32)` | 用于通话的许可证 |

### <a name="exported-direct-routing-usage-report"></a>已导出直接路由使用情况报告

您可以从当前日期导出最多五个月（150天）的数据，除非特定于国家的法规禁止保留该时间段的数据。

| # | 名称 | [数据类型（SQL Server）](https://docs.microsoft.com/sql/t-sql/data-types/data-types-transact-sql) | 说明 |
| :-: | :-: | :-: |:------------------- |
| 0 | True&correlationid | `uniqueidentifier` | 唯一的呼叫标识符 |
| 1 | SIP 地址 | `nvarchar(128)` | 发出或接收呼叫的用户或 bot 的地址。<br/>请注意，在 Azure Active Directory 中实际是 UserPrincipalName （UPN，登录名称），后者通常与 SIP 地址相同 |
| ppls-2 | 显示名称 | `nvarchar(128)` | 在 Office 365 门户中设置的用户或呼叫机器人（例如呼叫队列或自动助理）的名称 |
| 3 | 用户所在国 | `nvarchar(2)` | 用户的国家/地区代码， [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
| 4 | 邀请时间 | `datetimeoffset` | 当初始邀请从团队用户或机器人呼叫发送到 SBC，或在入站到团队或 bot 通过 SBC 直接路由的 SIP 代理组件呼叫时收到。 |
| 5 | 开始时间 | `datetimeoffset` | SIP 代理在来自出站（团队/Bot 到 PSTN 用户）的 SBC 中收到最终答案（SIP 消息 "200 OK"）的时间，或在入站呼叫（从团队/Bot 的 PSTN 用户）将邀请发送到团队后端的下一跃点之后。<br/>对于失败的和未应答的呼叫，这可能等于 "邀请" 或 "失败" 时间 |
| 6 | 失败时间 | `datetimeoffset` | 仅存在失败（未完全建立）通话的情况 |
| 7 | 结束时间 | `datetimeoffset` | 仅适用于成功（完全建立的）通话。 通话结束的时间 |
| 个 | 持续时间（秒） | `int` | 通话持续时间 |
| db-9 | 成功 | `nvarchar(3)` | "是/否"。 成功或尝试 |
| 10 | 来电显示号码 | `nvarchar(32)` | 发出呼叫的用户或机器人的号码。 在入站到团队用户呼叫时，它将是 PSTN 用户，在来自团队用户的出站用户呼叫中，将成为团队用户编号 |
| 至 | 被呼叫方号码 | `nvarchar(32)` | 接收呼叫的用户或机器人的号码。 在入站到团队用户呼叫它将是团队用户，在来自团队用户的出站用户呼叫将是 PSTN 用户 |
| 13 | 呼叫类型 | `nvarchar(32)` | 呼叫类型和方向 |
| 14 | 媒体的 Azure 区域 | `nvarchar(8)` | 用于非绕过呼叫的媒体路径的数据中心 |
| 岁 | 用于发送信号的 Azure 区域 | `nvarchar(8)` | 用于发送绕过和非绕过调用的信号的数据中心 |
| utf-16 | 最终 SIP 代码 | `int` | 通话结束的代码， [RFC 3261](https://tools.ietf.org/html/rfc3261) |
| 日 | 最终 Microsoft 子代码 | `int` | 除了 SIP 代码，Microsoft 还拥有指示特定问题的子代码 |
| 18 | 最终 SIP 短语 | `nvarchar(256)` | SIP 代码和 Microsoft 子代码的说明 |
| 19 | SBC FQDN | `nvarchar(64)` | 会话边界控制器的完全限定的域名 |
| 名 | 媒体绕过 | `nvarchar(3)` | "是/否"。 指示是否为媒体绕过启用了主干 |
| 21日 | 共享的相关 ID | `uniqueidentifier` | 指示两个或多个通话是相关的 |


## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
