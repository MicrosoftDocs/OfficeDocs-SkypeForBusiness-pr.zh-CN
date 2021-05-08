---
title: Microsoft TeamsPSTN 使用情况报告
author: cichur
ms.author: v-cichur
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
description: 了解如何使用 Teams 管理中心Microsoft Teams PSTN 使用情况报告，获取组织中呼叫和音频会议使用情况的概述。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 402e602e9f15beef30f0c44901398fa22b63c807
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262664"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft TeamsPSTN 使用情况报告

Microsoft Teams 管理中心Teams PSTN (公用电话交换网) 使用情况报告概述了贵组织的呼叫和音频会议活动。 如果使用 Microsoft 作为电话运营商，可以查看呼叫计划的详细呼叫活动;如果使用自己的电话运营商，可以查看直接路由的详细呼叫活动。

" **呼叫计划** "选项卡显示的信息包括用户在入站和出站 PSTN 呼叫中花费的时间以及这些呼叫的费用。 " **直接路由** "选项卡显示信息，包括 SIP 地址和呼叫开始时间和结束时间。 使用此报告中的信息深入了解组织的 PSTN 使用情况，并帮助调查、计划和做出业务决策。

> [!NOTE]
> 如果您有 Telstra 或 Softbank 呼叫计划，则 PSTN 使用报告中不会显示任何呼叫详细信息记录。 有关报告需求，请联系 Telstra 或 Softbank。 

## <a name="view-the-pstn-usage-report"></a>查看 PSTN 使用情况报告

1. 在管理中心的左侧导航Microsoft Teams，单击 **"分析**"&  >  **报告使用情况报告"。** 在"**查看报表"** 选项卡上的"报表 **"下**，选择 **"PSTN 使用情况报告"。**
2. 在 **"日期范围**"下，选择预定义的 7 天或 28 天范围，或设置自定义范围，然后选择"运行 **报表"。**

## <a name="interpret-the-report"></a>解释报告

### <a name="calling-plans"></a>通话套餐

[![管理中心中的呼叫计划 PSTN 使用情况报告报告的屏幕截图](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png "管理中心内带编号标注Microsoft Teams PSTN 使用情况报告的屏幕截图")](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看报表，了解过去 7 天、28 天或设置的自定义日期范围的趋势 |
|**2**   |每个报表都有一个生成日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |X 轴是特定报表的选定日期范围。 Y 轴是所选时段内通话总数。 <br>将鼠标悬停在给定日期上的点上以查看该日期的总调用。  |
|**4**   |下表提供了每个呼叫的 PSTN 使用情况明细。 <ul><li>**UTC (时间戳)** 表示调用开始的时间。</li><li>**显示** 名称显示名称用户的名称。 可以单击显示名称转到管理中心中的用户设置Microsoft Teams页面。</li><li>**用户名** 是用户的登录名。</li><li>**电话号码** 是接收入站呼叫呼叫的号码或为出站呼叫拨打的号码。</li><li>**呼叫** 类型是呼叫是 PSTN 出站呼叫还是入站呼叫，以及呼叫类型，例如用户拨打的呼叫还是音频会议呼叫。 你可能会看到的调用类型包括：<br><br>**Teams用户呼叫类型**<ul><li>**user_in** - 用户收到入站 PSTN 呼叫。</li><li>**user_out** - 用户拨打了出站 PSTN 呼叫</li><li>**user_out_conf** - 用户向呼叫添加了两个或多个 PSTN 参与者，例如三方电话会议</li><li>**user_out_transfer** - 用户将呼叫转接到 PSTN 号码</li><li>**user_out_forwarding** - 用户将呼叫转发到 PSTN 号码</li><li>**conf_in** - 音频会议网桥的入站呼叫</li><li>**conf_out** - 音频会议网桥的出站呼叫通常向会议添加 PSTN 号码</li></ul><br>**Teams机器人调用类型**<ul><li>**ucap_in** - 自动助理或呼叫Teams机器人的入站 PSTN 呼叫</li><li>**ucap_out** - 来自自动助理或呼叫Teams机器人的出站 PSTN 呼叫</li></ul><br><li>**被呼叫** 者是拨打的号码。</li><li>**"拨打国家** /地区"是拨打的"国家/地区"。</li><li>**从** 调用是拨打该呼叫的号码。</li><li>**"从国家** /地区"是呼叫的拨打国家/地区。</li><li>**"** 费用"是向帐户收取的通话费用或金额。 </li><li>**货币** 是用于计算调用成本的货币类型。 </li><li>" **持续时间**"是接听呼叫的时间。</li><li>**根据用户** 的位置，国内/国际 (是国家/地区) 还是 (国家/地区) 国内呼叫。</li><li>**呼叫 ID** 是呼叫的呼叫 ID。 它是呼叫 Microsoft 支持人员时可以使用的呼叫标识符。</li><li>**号码** 类型是用户的电话号码类型，例如免费电话号码的服务。 </li><li>**"国家/地区** "是使用位置。 </li> <li>**会议 ID** 是音频会议的会议 ID。 </li><li>**功能** 是用于调用的许可证。 可能看到的许可证类型包括：<ul><li>**MCOEV 或 MCOEV_VIRTUALUSER 或 MCOEV_VIRTUALUSER_GOV** - 语音应用程序，例如自动助理或呼叫队列</li><li>**FREECALL** - 如果出现阻止我们定价呼叫的技术问题，该呼叫将免费提供，并且将显示此功能</li><li>**MCOPSTN1** - 国内呼叫 (3000 分钟美国/1200 分钟欧盟套餐) </li><li>**MCOPSTN2** - 国际呼叫计划</li><li>**MCOPSTN5** - 国内呼叫计划 (120 分钟呼叫计划) </li><li>**MCOPSTN6** - 国内呼叫 (240 分钟呼叫) </li><li>**MCOPSTN8** - 未与其他呼叫计划一样跨用户进行 (120 分钟国内呼叫计划) </li><li>**MCOPSTN9** - 国际呼叫计划</li><li>**MCOPSTNCAP** - 公用电话</li><li>**MCOPSTNPP** - 通信信用额度</li><li>**MCOMEETADD** - 音频会议</li><li>**MCOMEETADD_DIALOUT_US** - 音频会议美国和加拿大拨出计划</li><li>**MCOMEETADD_CN_GLOBAL** - 适用于非中国用户的音频会议</li><li>**MCOMEETADD_TATA** - Tata Communications Connections</li><li>**MCOMEETACPEA** - 音频会议按分钟付费 </li><li>**MCOMEETACPEA_GOV** - 政府音频会议按分钟付费</li></ul></li></ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |选择 **"** 筛选"，按用户名或呼叫类型筛选报表 |
|**7**   |选择 **"全屏** "以全屏模式查看报表。 |
|**8**   |可以将报表导出到 CSV 文件进行脱机分析。 单击 **"导出Excel"，** 然后在"下载"选项卡上，单击"下载"，在报表准备就绪后下载报表。 |

### <a name="direct-routing"></a>直接路由

[![管理中心中的直接路由 PSTN 使用报告报告的屏幕截图](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png "管理中心内直接路由 PSTN 使用情况Microsoft Teams标注的屏幕截图")](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看该报告，了解过去 7 天或 28 天的趋势。 |
|**2**   |每个报表都有一个生成日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |X 轴是特定报表的选定日期范围。 Y 轴是所选时段内通话总数。<br>将鼠标悬停在给定日期上的点上以查看该日期的总调用。  |
|**4**   |下表提供了每个呼叫的 PSTN 使用情况明细。 <ul><li>**UTC (时间戳)** 表示调用开始的时间。</li><li>**显示** 名称显示名称用户的名称。 可以单击显示名称转到管理中心中的用户设置Microsoft Teams页面。 该名称还可以是机器人的名称，例如呼叫队列或云自动助理。 </li><li>**SIP 地址** 是接收或拨打呼叫的用户或机器人的 SIP 地址。</li><li>**呼叫者** 号码是发起呼叫的用户或机器人的号码。 </li><li>**被呼叫者** 号码是接收呼叫的用户或机器人的号码。 在向用户Teams入站呼叫时，Teams用户，从用户Teams出站呼叫时，它将是 PSTN 用户。 </li><li>**呼叫** 类型是呼叫是 PSTN 出站呼叫还是入站呼叫，以及呼叫类型，例如用户拨打的呼叫还是音频会议呼叫。 你可能会看到的呼叫类型包括：<br><br>**Teams用户呼叫类型**<ul><li>**dr_in** - 用户收到入站 PSTN 呼叫</li><li>**dr_out** - 用户拨打了出站 PSTN 呼叫</li><li>**dr_out_user_conf** - 用户向呼叫添加了 PSTN 参与者</li><li>**user_out_transfer** - 用户将呼叫转接到 PSTN 号码</li><li>**dr_out_user_forwarding** - 用户将呼叫转发到 PSTN 号码</li><li>**dr_out_user_transfer** - 用户将呼叫转接到 PSTN 号码</li><li>**dr_emergency_out** - 用户进行了紧急呼叫</li></ul><br>**Teams机器人调用类型**<ul><li>**dr_in_ucap** - 自动助理或呼叫队列Teams机器人的入站 PSTN 呼叫</li><li>**dr_out_ucap** - 来自自动助理或呼叫Teams机器人的出站 PSTN 呼叫</li></ul><br><li>**"调用** "表示接收呼叫的用户数。</li><li>开始时间 **(UTC)** 是 SIP 代理在出站呼叫 (Teams/) 机器人上从 SBC 收到最终应答 (SIP 消息"200 OK") 的时间，或者 SIP 代理在入站呼叫 (PSTN 用户上向 Teams/Bot) 发送到 Teams 后端内下一跃点的邀请后的时间。 </li><li>邀请 **时间 (UTC)** 是在从 Teams 用户或机器人调用到 SBC 的出站呼叫上发送初始邀请，或者从 SBC 直接路由的 SIP 代理组件在 Teams 或机器人调用的入站呼叫上收到邀请的时间。</li><li>**UTC (失败)** 是调用失败的时间。 仅适用于失败的调用。 最终 SIP 代码、最终 Microsoft 子代码和最终 SIP 短语提供调用失败的原因，可帮助进行故障排除。 </li><li>**UTC (结束)** 表示调用结束时间 (仅针对成功的) 。</li><li>" **持续时间**"是接听呼叫的时间。</li><li>**号码** 类型是用户的电话号码类型，例如免费电话号码的服务。 </li><li>**媒体** 旁路指示中继是否启用了媒体旁路。 </li> <li>**SBC FQDN** 是会话边界控制器 (FQDN) 的完全限定域名 (SBC) 。 </li><li>**用于媒体的 Azure** 区域是在非绕过调用中用作媒体路径的数据中心。 </li><li>**用于 Signaling 的 Azure** 区域是数据中心，用于对绕过和非绕过调用发出信号。 </li><li>**事件** 类型是调用的事件类型。 你将看到成功调用成功和尝试失败的调用。 </li><li>**最终 SIP** 代码是结束调用的代码。</li><li>**最终 Microsoft 子代码** 是一个代码，用于指示发生的特定操作。</li><li>**最终的 SIP** 短语是 SIP 代码和 Microsoft 子代码的说明。</li><li>**关联 ID** 是调用 Microsoft 支持时可以使用的呼叫的唯一标识符。</li><li>**共享关联 ID** 仅在可下载的 CSV 文件中可见，在门户中不存在。 共享关联 ID 存在于至少两个相关调用中。 请参阅下面的详细说明。</li></ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |选择 **"全屏** "以全屏模式查看报表。 |
|**7**   |选择 **"导出Excel，** 在 CSV (CSV) 中下载数据，或将其用作计费系统的输入。 |

#### <a name="callercallee-fields-considerations"></a>调用方/被调用方字段注意事项

根据呼叫方向，呼叫者或被呼叫者姓名可以包含非 E164 号码。

这些字段可以来自客户 SBC () 。 SBC 可以发送到直接路由的三种格式：E.164 数字、非 E.164 数字和字符串。

- E.164 电话号码，来自具有 E.164 号码的用户，以及具有 E.164 号码的用户。 
- 从非 E.164 号码呼叫。 来自与直接路由互连的第三方 PBX 的用户向用户Teams呼叫。 在这种情况下，呼叫者号码可能是任何非 E.164 号码，例如 +1001。 
- 垃圾邮件发送者调用 ，并且不会显示数字，而只显示一个名称，例如"内部收入服务"。 此字符串将显示在报告中。

#### <a name="about-shared-correlation-id"></a>关于共享关联 ID

共享关联 ID 仅存在于你下载Excel导出的关联文件中，并指示两个或多个调用相关。 下面介绍了不同的方案，以及存在共享关联 ID 的情况。

1.    在 Teams 客户端上名为 Teams User 1 的 PSTN 终结点上的 PSTN 用户 1，呼叫类型为 Dr_In，相关 ID 为 57f28917-42k5-4c0c-9433-79734873f2ac，没有共享关联 ID。
2.    TeamsPSTN 终结点上名为 PSTN 用户 1 的 Teams 客户端上的用户 1，呼叫类型为 Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4，没有共享关联 ID。
3.    PSTN 终结点上的 PSTN 用户 1 Teams客户端上名为 Teams 用户 2， 调用类型 Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9，共享关联 ID f45e9a25-9f94-46e7-a457-84f5940efde9。
4.    关联 ID 为"f45e9a25-9f94-46e7-a457-84f5940efde9"的现有调用 3。 与用户 2 通话中的 PSTN Teams 1。 Teams用户 2 已 (失明或) 咨询Teams PSTN 用户、 调用类型 Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0，共享关联 ID f45e9a25-9f94-46e7-a457-84f5940efde9。

## <a name="exporting-the-reports"></a>导出报表
单击 **"导出Excel"，** 然后在"下载"选项卡上，单击"下载"，在报表准备就绪后下载报表。  导出过程可能需要几秒钟到几分钟才能完成，具体取决于数据量。

此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 导出的文件包含联机报告中不可用的其他字段。 这些可用于故障排除和自动化工作流。

 将收到名为 **"Calls.Export"的 zip 文件。 `[identifier]`.zip"，** 标识符是导出的唯一 ID，可用于故障排除。

如果同时具有"呼叫计划"和"直接路由"，则导出的文件可能包含这两个产品的数据。 PSTN 使用情况报告文件将包含文件名 **"PSTN.calls"。 `[UTC date]`.csv"** 和直接路由 "**DirectRouting.calls。 `[UTC date]`.csv"。**

 除了 PSTN 和直接路由文件外，存档还包含文件 **"parameters.js"，** 以及选定的导出时间范围和功能。

导出的文件采用逗号分隔值 (CSV) 格式，符合 [RFC 4180](https://tools.ietf.org/html/rfc4180) 标准。 文件可以在任何符合Excel编辑器中打开，而无需任何转换。

CSV 的第一行包含列名称。 所有日期均采用 UTC 和 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 格式。

### <a name="exported-pstn-usage-report"></a>导出的 PSTN 使用情况报告

 除非国家/地区特定的法规禁止将数据保留 12 个月，否则可以导出自当前日期起最多一年的数据。

> [!div class="has-no-wrap"]  
> | # | 名称 | [数据类型 (SQL Server) ](/sql/t-sql/data-types/data-types-transact-sql) | 说明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 唯一调用标识符 |
> | 1 | 呼叫 ID | `nvarchar(64)` | 调用标识符。 不保证唯一 |
> | 2 | 会议 ID | `nvarchar(64)` | 音频会议的 ID |
> | 3 | 用户位置 | `nvarchar(2)` | 用户的国家/地区代码 [，ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | 在 Azure Active Directory 中调用用户的 ID。<br/> 对于机器人调用类型，此信息和其他用户信息将为 null/空 (ucap_in ucap_out)  |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName () 登录Azure Active Directory。<br/>这通常与用户的 SIP 地址相同，并且可以与用户的电子邮件地址相同 |
> | 6 | 用户显示名称 | `nvarchar(128)` | 用户的显示名称 |
> | 7 | 来电显示 | `nvarchar(128)` | 接收入站呼叫呼叫的号码或为出站呼叫拨打的号码。 [E.164](https://en.wikipedia.org/wiki/E.164) 格式 |
> | 8 | 呼叫类型 | `nvarchar(32)` | 呼叫是 PSTN 出站呼叫还是入站呼叫，以及呼叫类型，例如用户拨打的呼叫还是音频会议呼叫 |
> | 9 | 数字类型 | `nvarchar(16)` | 用户的电话号码类型，例如免费电话号码的服务 |
> | 10 | 国内/国际 | `nvarchar(16)` | 该呼叫是 (国家/地区) 还是 (国家/地区) 或区域外部的国内和国际呼叫。 |
> | 11 | 目标已拨号 | `nvarchar(64)` | 拨打的"国家/地区" |
> | 12 | 目标号码 | `nvarchar(32)` | 以 [E.164 格式拨打的](https://en.wikipedia.org/wiki/E.164) 号码 |
> | 13 | 开始时间 | `datetimeoffset` | 通话开始时间 |
> | 14 | 结束时间 | `datetimeoffset` | 呼叫结束时间 |
> | 15 | 持续时间秒数 | `int` | 呼叫已连接多久 |
> | 16 | 连接费用 | `numeric(16, 2)` | 连接费用价格 |
> | 17 | 费用 | `numeric(16, 2)` | 向您的帐户收取的呼叫金额或费用 |
> | 18 | 货币 | `nvarchar(3)` | 用于计算调用 [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) (费用的货币)  |
> | 19 | 功能 | `nvarchar(32)` | 用于呼叫的许可证 |

### <a name="exported-direct-routing-usage-report"></a>导出的直接路由使用情况报告

除非国家/地区特定的法规禁止保留该时间段的数据，否则 (从当前日期开始) 150 天内导出数据。

> [!div class="has-no-wrap"]  
> | # | 名称 | [数据类型 (SQL Server) ](/sql/t-sql/data-types/data-types-transact-sql) | 说明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | 唯一调用标识符 |
> | 1 | SIP 地址 | `nvarchar(128)` | 进行或接收呼叫的用户或机器人的地址。<br/>请注意，这实际上是 UserPrincipalName (UPN，) 登录Azure Active Directory，这通常与 SIP 地址相同 |
> | 2 | 显示名称 | `nvarchar(128)` | 用户或呼叫机器人的名称，例如 (管理中心自动助理) 呼叫队列Microsoft 365名称 |
> | 3 | 用户国家/地区 | `nvarchar(2)` | 用户的国家/地区代码 [，ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | 邀请时间 | `datetimeoffset` | 当初始邀请在出站时Teams用户或机器人调用 SBC，或者从 SBC 直接路由的 SIP 代理组件在入站到 Teams 或机器人调用时收到 |
> | 5 | 开始时间 | `datetimeoffset` | SIP 代理从出站 (Teams/机器人上的 SBC 收到最终答案 (SIP 消息"200 正常") 给 PSTN 用户) 的时间，或者 SIP 代理在入站呼叫 (PSTN 用户上向 Teams/Bot) 发送 Teams 后端内的下一跃点邀请后的时间。<br/>对于失败和未接听的调用，这相当于邀请或失败时间 |
> | 6 | 故障时间 | `datetimeoffset` | 仅适用于未完全建立 (失败的) 调用 |
> | 7 | 结束时间 | `datetimeoffset` | 仅对于成功建立 (调用) 存在。 通话结束的时间 |
> | 8 | 持续时间 (秒)  | `int` | 通话持续时间 |
> | 9 | 成功 | `nvarchar(3)` | 是/否。 成功或尝试 |
> | 10 | 呼叫者号码 | `nvarchar(32)` | 进行呼叫的用户或机器人的数量。 在团队用户呼叫的入站时，它将是 PSTN 用户，从 Teams 用户呼叫出站时，它将是Teams号码 |
> | 12 | 被呼叫者号码 | `nvarchar(32)` | 收到呼叫的用户或机器人的号码。 在团队用户的入站呼叫中，它将是Teams用户，在用户从Teams出站时，它将是 PSTN 用户 |
> | 13 | 呼叫类型 | `nvarchar(32)` | 呼叫类型和方向 |
> | 14 | 用于媒体的 Azure 区域 | `nvarchar(8)` | 用于非绕过呼叫中的媒体路径的数据中心 |
> | 15 | 用于 Signaling 的 Azure 区域 | `nvarchar(8)` | 用于发出绕过和非绕过呼叫信号的数据中心 |
> | 16 | 最终 SIP 代码 | `int` | 结束调用的代码 [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | 最终 Microsoft 子代码 | `int` | 除了 SIP 代码之外，Microsoft 还有自己的子代码用于指示特定问题 |
> | 18 | 最终 SIP 短语 | `nvarchar(256)` | SIP 代码和 Microsoft 子代码的说明 |
> | 19 | SBC FQDN | `nvarchar(64)` | 会话边界控制器的完全限定域名 |
> | 20 | 媒体旁路 | `nvarchar(3)` | 是/否。 指示是否为媒体旁路启用了中继 |
> | 21 | 共享关联 ID | `uniqueidentifier` | 指示两个或多个调用相关 |


## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)