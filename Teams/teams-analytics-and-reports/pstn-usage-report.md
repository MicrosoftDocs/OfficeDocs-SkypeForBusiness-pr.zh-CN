---
title: Microsoft 团队 PSTN 使用报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: 了解如何使用 Microsoft 团队管理中心中的 "团队 PSTN 使用情况" 报表大致了解组织中的通话和音频会议使用情况。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89d33f15401d25767c905f16e38d93744d7929c3
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570563"
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
|**4**   |该表为您提供了每次通话的 PSTN 使用情况的细目。 <ul><li>**时间戳（UTC）** 是呼叫开始的时间。</li><li>"**显示名称**" 是用户的显示名称。 你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。</li><li>**用户名**是用户的登录名。</li><li>"**电话号码**" 是为拨入电话接收呼叫的号码，或者是为拨出电话拨出的号码。</li><li>**呼叫类型**指示呼叫是 PSTN 出站通话还是入站呼叫以及呼叫类型，例如由用户或音频会议发出的呼叫。 您可能看到的通话类型包括：<br><br>**团队用户呼叫类型**<ul><li>**user_in** -用户收到了入站 PSTN 呼叫。</li><li>**user_out** -用户发出了出站 PSTN 呼叫</li><li>**user_out_conf** -用户向呼叫添加了两个或多个 PSTN 参与者，例如三向电话会议</li><li>**user_out_transfer** -用户已将呼叫转移到 PSTN 号码</li><li>**user_out_forwarding** -用户将呼叫转移到 PSTN 号码</li><li>**conf_in** -到音频会议桥的入站呼叫</li><li>**conf_out** -来自音频会议桥的出站呼叫通常是向会议添加 PSTN 号码</li></ul><br>**团队机器人呼叫类型**<ul><li>**ucap_in** -到团队机器人（如自动助理或呼叫队列）的入站 PSTN 呼叫</li><li>**ucap_out** -来自团队机器人（如自动助理或呼叫队列）的出站 PSTN 呼叫</li></ul><br><li>拨**叫的**号码。</li><li>"**国家或地区**" 是已拨打的国家或地区。</li><li>"**来源**" 表示发出呼叫的号码。</li><li>**从 "国家或地区**" 是呼叫所在的国家或地区。</li><li>"**费用**" 表示为您的帐户收取的通话金额或通话费用。 </li><li>**货币**是用于计算通话费用的货币类型。 </li><li>" **持续时间**"是接听呼叫的时间。</li><li>**国内/国际**根据用户的位置告诉你呼叫是国内（在国家或地区）还是国际（位于国家或地区外）。</li><li>通话**id**是呼叫的呼叫 id。 它是呼叫 Microsoft 支持时可以使用的呼叫的唯一标识符。</li><li>"**号码类型**" 是用户的电话号码类型，例如免费号码的服务。 </li><li>**国家或地区**是使用位置。 </li> <li>"**会议 id** " 是音频会议的会议 id。 </li><li>**功能**是用于通话的许可证。 您可能看到的许可证类型包括：<ul><li>**MCOPSTNPP** -通讯信用点数</li><li>**MCOPSTN1** -国内通话计划（3000，美国/1200 最少欧盟计划）</li><li>**MCOPSTN2** -国际通话计划</li><li>**MCOPSTN5** -国内通话计划（120分钟通话计划）</li><li>**MCOPSTN6** -国内通话计划（240分钟通话计划）</li><li>**MCOMEETADD** -音频会议</li><li>**MCOMEETACPEA** -每分钟支付的音频会议</li></ul></li></ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
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
|**4**   |该表为您提供了每次通话的 PSTN 使用情况的细目。 <ul><li>**时间戳（UTC）** 是呼叫开始的时间。</li><li>"**显示名称**" 是用户的显示名称。 你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。</li><li>**Sip 地址**是接收或进行呼叫的用户的 sip 地址。</li><li>**电话号码**是发出呼叫的用户的号码。 </li><li>**呼叫类型**指示呼叫是 PSTN 出站通话还是入站呼叫以及呼叫类型，例如由用户或音频会议发出的呼叫。 您可能看到的通话类型包括：<br><br>**团队用户呼叫类型**<ul><li>**dr_in** -用户收到了入站 PSTN 呼叫</li><li>**dr_out** -用户发出了出站 PSTN 呼叫</li><li>**dr_out_user_conf** -用户向呼叫添加了 PSTN 参与者</li><li>**user_out_transfer** -用户已将呼叫转移到 PSTN 号码</li><li>**dr_out_user_forwarding** -用户将呼叫转移到 PSTN 号码</li><li>**dr_out_user_transfer** -用户已将呼叫转移到 PSTN 号码</li><li>**dr_emergency_out** -用户拨打紧急电话</li></ul><br>**团队机器人呼叫类型**<ul><li>**dr_in_ucap** -到团队机器人（如自动助理或呼叫队列）的入站 PSTN 呼叫</li><li>**dr_out_ucap** -来自团队机器人（如自动助理或呼叫队列）的出站 PSTN 呼叫</li></ul><br><li>**被叫**方指接收呼叫的用户的号码。</li><li>"**开始时间（UTC）** " 是呼叫连接的时间。</li><li>**邀请时间（UTC）** 是启动呼叫的时间。</li><li>**失败时间（UTC）** 是呼叫失败的时间。 （仅限失败的通话。）</li><li>**结束时间（UTC）** 是通话结束的时间。 （仅限成功通话。）</li><li>" **持续时间**"是接听呼叫的时间。</li><li>"**号码类型**" 是用户的电话号码类型，例如免费号码的服务。 </li><li>**媒体绕过**指示是否已为媒体旁路启用了主干 </li> <li>**SBC FQDN**是会话边界控制器（SBC）的完全限定的域名（FQDN）。 </li><li>**Azure 区域**是用于发送信号的数据中心。</li><li>**事件类型**是通话的事件类型。 您将看到成功的通话成功，并且尝试进行失败的通话。 </li><li>**最终 SIP 代码**是通话结束的代码。</li><li>**最终 Microsoft 子代码**是指示发生的特定操作的代码。</li><li>**最终 sip 短语**是 sip 代码和 Microsoft 子代码的说明。</li><li>**COORELATION ID**是呼叫的唯一标识符，可在呼叫 Microsoft 支持时使用。</li></ul> 要查看希望在表格中显示的信息，请确保向表格添加了相关列。|
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |选择 "**全屏**" 以全屏模式查看报表。 |

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)