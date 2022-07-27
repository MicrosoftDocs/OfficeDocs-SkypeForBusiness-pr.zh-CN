---
title: Microsoft Teams PSTN 使用情况报告
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: 了解如何在 Microsoft Teams 管理中心使用 Teams PSTN 使用情况报告，以大致了解组织中的通话和音频会议使用情况。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15c14e05c1f283971b4882cf3f6e8d3758a2d8ba
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023764"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams PSTN 使用情况报告

Microsoft Teams 管理中心中的 Teams PSTN (公共交换电话网络) 使用情况报告概述了组织中的通话和音频会议活动。 如果使用 Microsoft 作为电话运营商，可以查看通话套餐的详细通话活动;如果使用自己的电话运营商，则可以查看直接路由。

“ **呼叫计划”** 选项卡显示的信息包括用户在入站和出站 PSTN 呼叫中花费的分钟数，以及这些呼叫的成本。 “ **直接路由”** 选项卡显示包括 SIP 地址和呼叫开始时间和结束时间在内的信息。 使用此报表中的信息深入了解组织中的 PSTN 使用情况，并帮助你调查、规划和做出业务决策。

> [!NOTE]
> 如果有 Telstra 或 Softbank 呼叫计划，则不会在 PSTN 使用情况报告中看到任何呼叫详细信息记录。 请根据您的报告需求联系 Telstra 或 Softbank。 

## <a name="view-the-pstn-usage-report"></a>查看 PSTN 使用情况报告

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“分析”&报告** > **使用情况报告**。 在 **“查看报表** ”选项卡上的 **“报** 表”下，选择 **PSTN 使用情况报表**。
2. 在 **“日期”范围** 下，选择预定义的 7 天或 28 天范围，或设置自定义范围，然后选择 **“运行”报表**。

## <a name="interpret-the-report"></a>解释报告

### <a name="calling-plans"></a>通话套餐

   ![管理中心内通话套餐 PSTN 使用情况报告的屏幕截图](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![Microsoft Teams 管理中心中具有编号标注的 PSTN 使用情况报告的屏幕截图](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看报表，了解过去 7 天、28 天或设置的自定义日期范围的趋势。 |
|**2**   |每个报表都有生成日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |X 轴是特定报表的选定日期范围。 Y 轴是所选时间段内的调用总数。 <br>将鼠标悬停在给定日期上的点上，以查看该日期的总调用量。  |
|**4**   |该表提供每个调用的 PSTN 使用情况的细目。 <ul><li>**UTC)  (时间戳** 是开始调用的时间。</li><li>**显示名称** 是用户的显示名称。 可以单击显示名称，转到 Microsoft Teams 管理中心的用户设置页面。</li><li>**用户名** 是用户的登录名称。</li><li>**电话号码** 是接听入站呼叫或为出站呼叫拨号的号码。</li><li>**呼叫类型** 是呼叫是 PSTN 出站呼叫还是入站呼叫，以及呼叫类型（例如用户或音频会议的呼叫）。 你可能会看到的调用类型包括：<br><br>**Teams 用户呼叫类型**<ul><li>**user_in** - 用户收到入站 PSTN 呼叫</li><li>**user_out** - 用户放置了出站 PSTN 调用</li><li>**user_out_conf** - 用户向呼叫添加了两个或更多 PSTN 参与者，例如三向电话会议</li><li>**user_out_transfer** - 用户将呼叫转移到 PSTN 号码</li><li>**user_out_forwarding** - 用户将呼叫转发到 PSTN 号码</li><li>**conf_in** - 音频会议网桥的入站调用</li><li>**conf_out** - 音频会议网桥的出站呼叫通常用于向会议添加 PSTN 号码</li><li>**unassigned_in** - 通过呼叫计划通过未分配号码的入站 PSTN 呼叫</li></ul><br>**Teams 机器人调用类型**<ul><li>**ucap_in** - 对 Teams 机器人（例如自动助理或呼叫队列）的入站 PSTN 调用</li><li>**ucap_out** - 来自 Teams 机器人的出站 PSTN 呼叫，例如自动助理或呼叫队列</li></ul><br><li>**调用的** 号码是拨号。</li><li>**拨入国家或地区的国家或地区** 。</li><li>**调用** 的是放置调用的号码。</li><li>**从国家或地区** 是呼叫所在的国家或地区。</li><li>**费用** 是向帐户收取的电话费用或费用。 </li><li>**货币** 是用于计算调用成本的货币类型。 </li><li>" **持续时间**"是接听呼叫的时间。</li><li>**国内/国际** 会根据用户的位置告知呼叫是国家或地区内部 () 还是国家或地区以外的国际 () 。</li><li>**呼叫 ID** 是呼叫的呼叫 ID。 它是调用Microsoft 支持部门时可以使用的呼叫的标识符。</li><li>**号码类型** 是用户的电话号码类型，例如免费号码服务。 </li><li>**国家或地区** 是使用位置。 </li> <li>**会议 ID** 是音频会议的会议 ID。 </li><li>**功能** 是用于调用的许可证。 可能看到的许可证类型包括：<ul><li>**MCOEV 或MCOEV_VIRTUALUSER或MCOEV_VIRTUALUSER_GOV** - 语音应用程序，如自动助理或呼叫队列</li><li>**FREECALL** - 如果出现阻止我们为呼叫定价的技术问题，将免费提供呼叫并使用此功能显示</li><li>**MCOPSTN1** - 国内通话计划 (3000分钟美国/1200分钟欧盟计划) </li><li>**MCOPSTN2** - 国际呼叫计划</li><li>**MCOPSTN5** - 国内通话套餐 (120分钟通话套餐) </li><li>**MCOPSTN6** - 国内通话套餐 (240 分钟通话套餐) </li><li>**MCOPSTN8** - 每个用户的国内呼叫计划 120 分钟 (没有像其他呼叫计划那样跨用户共用) </li><li>**MCOPSTN9** - 国际通话计划</li><li>**MCOPSTNCAP** - 公用区域电话</li><li>**MCOPSTNPP** - 通信额度</li><li>**MCOMEETADD** - 音频会议</li><li>**MCOMEETADD_DIALOUT_US** - 美国和加拿大音频会议拨号计划</li><li>**MCOMEETADD_CN_GLOBAL** - 面向非中国用户的音频会议</li><li>**MCOMEETADD_TATA** - Tata Communications Connections</li><li>**MCOMEETACPEA** - 音频会议每分钟付费 </li><li>**MCOMEETACPEA_GOV** - 政府每分钟付费的音频会议</li></ul></li></ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |选择 **“筛选器** ”按用户名或调用类型筛选报表。 |
|**7**   |选择 **“全屏** ”以全屏模式查看报表。 |
|**8**   |可以将报表导出到 CSV 文件以进行脱机分析。 单击 **“导出到 Excel**”，然后在“ **下载”** 选项卡上单击“ **下载** ”，以便在报表准备就绪时下载报表。|

### <a name="direct-routing"></a>直接路由

   ![管理中心中直接路由 PSTN 使用情况报告的屏幕截图](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![Microsoft Teams 管理中心中具有编号标注的直接路由 PSTN 使用情况报告的屏幕截图](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看该报告，了解过去 7 天或 28 天内的趋势。 |
|**2**   |每个报表都有生成日期。 报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |X 轴是特定报表的选定日期范围。 Y 轴是所选时间段内的调用总数。<br>将鼠标悬停在给定日期上的点上，以查看该日期的总调用量。  |
|**4**   |该表提供每个调用的 PSTN 使用情况的细目。 <ul><li>**UTC)  (时间戳** 是开始调用的时间。</li><li>**显示名称** 是用户的显示名称。 可以单击显示名称，转到 Microsoft Teams 管理中心的用户设置页面。 该名称也可以是机器人的名称，例如呼叫队列或云自动助理。 </li><li>**SIP 地址** 是接收或拨打呼叫的用户或机器人的 SIP 地址。</li><li>**呼叫方号码** 是进行呼叫的用户或机器人的号码。 </li><li>**被调用方号码** 是收到呼叫的用户或机器人的号码。 在对 Teams 用户的入站调用中，它将是 Teams 用户，在 Teams 用户的出站呼叫中，它将是 PSTN 用户。 </li><li>**呼叫类型** 是呼叫是 PSTN 出站呼叫还是入站呼叫，以及呼叫类型（例如用户或音频会议的呼叫）。 你可能会看到的呼叫类型包括：<br><br>**Teams 用户呼叫类型**<ul><li>**dr_in** - 用户收到入站 PSTN 呼叫</li><li>**dr_out** - 用户放置了出站 PSTN 调用</li><li>**dr_out_user_conf** - 用户向呼叫添加了 PSTN 参与者</li><li>**dr_out_user_forwarding** - 用户将调用转发到 PSTN 号码</li><li>**dr_out_user_transfer** - 用户将呼叫转移到 PSTN 号码</li><li>**dr_emergency_out** - 用户发出紧急呼叫</li><li>**dr_unassigned_in** - 通过直接路由到未分配号码的入站 PSTN 调用</li></ul><br>**Teams 机器人调用类型**<ul><li>**dr_in_bot** - 对 Teams 机器人（例如自动助理或呼叫队列）的入站 PSTN 调用</li><li>**dr_out_bot** - 来自 Teams 机器人的出站 PSTN 呼叫，例如自动助理或呼叫队列</li></ul><br><li>**调用** 到的是接听呼叫的用户的号码。</li><li>**开始时间 (UTC)** 是 SIP 代理收到 SIP 消息“200 正常”的最终答案 (SIP 消息“200 确定”) 从 SBC 在出站呼叫 (Teams/Bot 发送到 PSTN 用户) ，或在 SIP 代理将邀请发送到 Teams 后端的下一跃点后，在入站呼叫 (PSTN 用户到 Teams/机器人) 。 </li><li>**邀请时间 (UTC)** 是在 Teams 用户或机器人调用 SBC 的出站呼叫中发送初始邀请，或者通过 SBC 直接路由的 SIP 代理组件对 Teams 或机器人调用的入站调用收到邀请的时间。</li><li>**UTC)  (失败时间** 是呼叫失败的时间。 仅适用于失败的调用。 最终 SIP 代码、最终 Microsoft 子代码和最终 SIP 短语提供了调用失败的原因，并有助于进行故障排除。 </li><li>**结束时间 (UTC)** 是仅) 成功调用 (呼叫结束的时间。</li><li>**持续时间** 是呼叫连接的时间，从邀请到呼叫结束或失败。 对于呼叫转接，持续时间包括呼叫队列中的响铃。</li><li>**号码类型** 是用户的电话号码类型，例如免费号码服务。 </li><li>**媒体旁路** 指示是否为媒体旁路启用了中继。 </li> <li>**SBC FQDN** 是会话边界控制器 (SBC) 的完全限定域名 (FQDN) 。 </li><li>**Azure Media 区域** 是非旁路调用中用作媒体路径的数据中心。 </li><li>**用于信号的 Azure 区域** 是用于对旁路和非旁路调用发出信号的数据中心。 </li><li>**事件类型** 是调用的事件类型。 你将看到成功调用和尝试失败的调用成功。 </li><li>**最终 SIP 代码** 是结束调用的代码。</li><li>**最终 Microsoft 子代码** 是一个代码，指示发生的特定操作。</li><li>**最终 SIP 短语** 是 SIP 代码和 Microsoft 子代码的说明。</li><li>**关联 ID** 是调用Microsoft 支持部门时可以使用的呼叫的唯一标识符。</li><li>**共享相关 ID** 仅在可下载的 CSV 文件中可见，在门户中不存在。 共享相关 ID 至少存在于两个相关调用中。 请参阅下面的详细说明。</li></ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |选择 **“全屏** ”以全屏模式查看报表。 |
|**7**   |选择 **“导出到 Excel** ”以下载逗号分隔文件中的数据 (CSV) 进行脱机分析，或将其用作计费系统的输入。 |

#### <a name="callercallee-fields-considerations"></a>调用方/被调用方字段注意事项

根据呼叫方向，调用方或被调用方名称可以包含非 E164 号码。

这些字段可能来自客户 SBC () 。 SBC 可以向直接路由发送三种格式：E.164 数字、非 E.164 数字和字符串。

- 从具有 E.164 号码的用户到还有 E.164 号码的用户的 E.164 电话号码。 
- 从非 E.164 号码调用。 来自与直接路由互连的第三方 PBX 的用户对 Teams 用户进行调用。 在这种情况下，调用方号码可能是任何非 E.164 号码，例如 +1001。 
- 垃圾邮件发送器调用，不显示数字，仅显示名称，例如“内部收入服务”。 此字符串将显示在报表中。

#### <a name="phone-number-obfuscation"></a>电话号码混淆
每个国家/地区的隐私要求包括混淆客户) 电话号码不拥有的外部 (。 电话号码的最后三个或四个数字替换为星号 (+123 456789***) 。 

对于传入呼叫，调用方号码会混淆，对于传出呼叫，被调用方号码会混淆。 这适用于租户管理员中心中的 PSTN 和直接路由报告、数据导出以及通过 Microsoft Graph 提供的调用日志。

混淆基于组织 (国家/地区) 的位置。 下表中未列出的国家/地区显示完整的电话号码：

| 国家 | 混淆数字数 |
| :-: | :- |
|BE - 比利时 | 3 |
|CH - 瑞士 | 4 |
|DE - 德国 | 3 |
|DK - 丹麦 | 3 |
|ES - 西班牙 | 3 |
|FI - 芬兰 | 3 |
|FR - 法国 | 4 |
|IT – 意大利 | 3 |
|NL - 荷兰 | 3 |
|NO - 挪威 | 3 |
|SE - 瑞典 | 3 |

#### <a name="about-shared-correlation-id"></a>关于共享相关 ID

共享关联 ID 仅存在于你下载的导出的 Excel 文件中，并指示两个或更多个调用是相关的。 下面介绍了不同的方案，以及共享相关 ID 的出现时间。

1.    Teams 客户端上名为 Teams User 1 的 PSTN 终结点上的 PSTN 用户 1，调用类型Dr_In，相关 ID 57f28917-42k5-4c0c-9433-79734873f2ac，无共享相关 ID。
2.    Teams 客户端上的 Teams 用户 1 在 PSTN 终结点上调用 PSTN 用户 1，调用类型Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4，无共享相关 ID。
3.    在 Teams 客户端上称为 Teams 用户 2 的 PSTN 终结点上的 PSTN 用户 1， 调用类型Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9，共享相关 ID f45e9a25-9f94-46e7-a457-84f5940efde9。
4.    具有相关 ID“f45e9a25-9f94-46e7-a457-84f5940efde9”的现有调用 3。 使用 Teams 用户 2 呼叫中的 PSTN 用户 1。 Teams 用户 2 在调用 Teams 或 PSTN 用户)  (盲目或咨询， 调用类型Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0，共享相关 ID f45e9a25-9f94-46e7-a457-84f5940efde9。

## <a name="exporting-the-reports"></a>导出报表
单击 **“导出到 Excel**”，然后在“ **下载”** 选项卡上单击“ **下载** ”，以便在报表准备就绪时下载报表。 导出过程可能需要几秒钟到几分钟才能完成，具体取决于数据的数量。

此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 导出的文件包含联机报表中不可用的其他字段。 这些可用于故障排除和自动化工作流。

 你将收到名为“Calls.Export”的 zip 文件 **。`[identifier]`.zip**“，标识符是可用于故障排除的导出的唯一 ID。

如果同时具有通话套餐和直接路由，则导出的文件可能包含这两种产品的数据。 PSTN 使用情况报告文件将具有文件名“**PSTN.calls”。`[UTC date]`.csv**“和直接路由”**DirectRouting.calls。`[UTC date]`.csv**“.

 除了 PSTN 和直接路由文件，存档还包含文件“**parameters.json**”，其中包含选定的导出时间范围和功能。

导出的文件采用逗号分隔值 (CSV) 格式，符合 [RFC 4180](https://tools.ietf.org/html/rfc4180) 标准。 可以在 Excel 或任何其他符合标准的编辑器中打开文件，而无需进行任何转换。

CSV 的第一行包含列名。 所有日期均为 UTC 和 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 格式。

### <a name="exported-pstn-usage-report"></a>导出的 PSTN 使用情况报告

 除非特定于国家/地区的法规禁止将数据保留 12 个月，否则可以从当前日期导出最多一年的数据。

> [!div class="has-no-wrap"]  
> | # | 名称 | [数据类型 (SQL Server) ](/sql/t-sql/data-types/data-types-transact-sql) | 说明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 唯一调用标识符 |
> | 1 | 呼叫 ID | `nvarchar(64)` | 调用标识符。 不保证是唯一的 |
> | 2 | 会议 ID | `nvarchar(64)` | 音频会议 ID |
> | 3 | 用户位置 | `nvarchar(2)` | 用户的国家/地区代码， [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | 在 Azure Active Directory 中调用用户 ID。<br/> 对于机器人调用类型 (ucap_in，此和其他用户信息将为 null/空，ucap_out)  |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (Azure Active Directory 中的登录名称) 。<br/>这通常与用户的 SIP 地址相同，并且可以与用户的电子邮件地址相同 |
> | 6 | 用户显示名称 | `nvarchar(128)` | 显示用户的名称 |
> | 7 | 来电显示 | `nvarchar(128)` | 接收入站呼叫呼叫的号码或为出站呼叫拨号的号码。 [E.164](https://en.wikipedia.org/wiki/E.164) 格式 |
> | 8 | 呼叫类型 | `nvarchar(32)` | 呼叫是 PSTN 出站呼叫还是入站呼叫，以及呼叫类型（例如用户或音频会议的呼叫） |
> | 9 | 数字类型 | `nvarchar(16)` | 用户的电话号码类型，例如免费号码服务 |
> | 10 | 国内/国际 | `nvarchar(16)` | 呼叫是国内 () 或国际 (以外的国家或地区，) 根据用户的位置 |
> | 11 | 目标已拨入 | `nvarchar(64)` | 已拨入的国家/地区 |
> | 12 | 目标编号 | `nvarchar(32)` | [以 E.164](https://en.wikipedia.org/wiki/E.164) 格式拨号 |
> | 13 | 开始时间 | `datetimeoffset` | 呼叫开始时间 |
> | 14 | 结束时间 | `datetimeoffset` | 呼叫结束时间 |
> | 15 | 持续时间秒 | `int` | 呼叫连接了多长时间 |
> | 16 | 连接费 | `numeric(16, 2)` | 连接费价格 |
> | 17 | 负责 | `numeric(16, 2)` | 向帐户收取的电话费用或费用 |
> | 18 | 货币 | `nvarchar(3)` | 用于计算调用成本的货币类型 ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217))  |
> | 19 | 功能 | `nvarchar(32)` | 用于呼叫的许可证 |

### <a name="exported-direct-routing-usage-report"></a>导出的直接路由使用情况报告

除非特定于国家/地区的法规禁止保留该期限的数据，否则可以从当前日期) 5 个月 (150 天导出数据。

> [!div class="has-no-wrap"]  
> | # | 名称 | [数据类型 (SQL Server) ](/sql/t-sql/data-types/data-types-transact-sql) | 说明 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | 调用标识符。 同一调用的多个腿可以共享相同的 CorrelationId |
> | 1 | AAD ObjectId | `uniqueidentifier` | 在 Azure Active Directory 中调用用户 ID。<br/> 对于机器人调用类型，此信息和其他用户信息可以为 null/空 |
> | 2 | UPN | `nvarchar(128)` | UserPrincipalName (用户或机器人的登录名称、Azure Active Directory) 。<br/>这通常与用户的 SIP 地址相同，并且可以与用户的电子邮件地址相同 |
> | 3 | 显示名称 | `nvarchar(128)` | 用户或调用机器人的名称 (例如，呼叫队列或自动助理) 设置在Microsoft 365 管理中心 |
> | 4 | 用户国家/地区 | `nvarchar(2)` | 用户的国家/地区代码， [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 5 | 邀请时间 | `datetimeoffset` | 当初始邀请从 Teams 用户或机器人在出站时发送到 SBC，或者通过 SBC 直接路由的 SIP 代理组件在入站到 Teams 或机器人调用时接收 |
> | 6 | 开始时间 | `datetimeoffset` | SIP 代理收到最终答案的时间 (SIP 消息“200 OK”) 从 SBC 在出站 (Teams/机器人到 PSTN 用户) ，或在 SIP 代理发送邀请到 Teams 内的下一跃点后端的入站调用 (PSTN 用户到 Teams/Bot) 。<br/>对于失败和未应答的调用，这可以等于邀请或失败时间 |
> | 7 | 失败时间 | `datetimeoffset` | 仅存在失败 (未完全建立) 调用 |
> | 8 | 结束时间 | `datetimeoffset` | 只有成功 (完全建立) 调用才存在。 呼叫结束的时间 |
> | 9 | 持续时间 (秒)  | `int` | 呼叫持续时间，从邀请到呼叫结束或失败。 对于呼叫转接，持续时间包括呼叫队列中的响铃。 |
> | 10 | 成功 | `nvarchar(3)` | 是/否。 成功或尝试 |
> | 11 | 调用方号码 | `nvarchar(32)` | 拨打电话的用户或机器人的数目。 在团队用户的入站呼叫中，它将是 PSTN 用户，在从 Teams 用户出站时调用它将是 Teams 用户号码 |
> | 12 | 被调用方号码 | `nvarchar(32)` | 收到呼叫的用户或机器人的数目。 在团队用户的入站呼叫中，它将是 Teams 用户，从 Teams 用户在出站时调用它将是 PSTN 用户 |
> | 13 | 呼叫类型 | `nvarchar(32)` | 呼叫类型和方向 |
> | 14 | 适用于媒体的 Azure 区域 | `nvarchar(8)` | 在非旁路调用中用于媒体路径的数据中心 |
> | 15 | 用于信号的 Azure 区域 | `nvarchar(8)` | 用于对旁路和非旁路调用发出信号的数据中心 |
> | 16 | 最终 SIP 代码 | `int` | 结束调用的代码 [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | 最终 Microsoft 子代码 | `int` | 除了 SIP 代码，Microsoft 还具有指示特定问题的子代码 |
> | 18 | 最终 SIP 短语 | `nvarchar(256)` | SIP 代码和 Microsoft 子代码的说明 |
> | 19 | SBC FQDN | `nvarchar(64)` | 会话边框控制器的完全限定域名 |
> | 20 | 媒体旁路 | `nvarchar(3)` | 是/否。 指示是否为媒体旁路启用了中继 |
> | 21 | 共享相关 ID | `uniqueidentifier` | 指示两个或多个调用相关 |


## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
- [Microsoft Graph 中的 PSTN 调用报表](/graph/api/callrecords-callrecord-getpstncalls?view=graph-rest-1.0&tabs=http)
- [Microsoft Graph 中的直接路由报表](/graph/api/callrecords-callrecord-getdirectroutingcalls?view=graph-rest-1.0&tabs=http)
