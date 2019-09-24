---
title: Microsoft Teams 分析和报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.analyticsandreports.overview
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解 Microsoft 团队管理中心提供的团队报表。
appliesto:
- Microsoft Teams
ms.openlocfilehash: de405a89b74a5e772e0f3d58027592d2e6ae4289
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131569"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams 分析和报告

Microsoft 团队管理中心提供了适用于 Microsoft 团队的新分析和报告体验。 你可以运行不同的报表，获取有关你的组织中的用户如何使用团队的见解。 例如，你可以通过频道和聊天消息以及他们用于连接到团队的设备类型来查看通信的用户数。 你的组织可以使用报表中的信息更好地了解使用模式、帮助制定业务决策以及通知培训和沟通工作。

## <a name="how-to-access-the-reports"></a>如何访问报表

若要访问报表，您必须是 Office 365、团队服务管理员或 Skype for business 管理员中的全局管理员。 转到 Microsoft 团队管理中心，在左侧导航中，选择 "**分析 & 报表**"，然后在 "**报表**" 下，选择要运行的报表。

> [!NOTE]
> Microsoft 团队管理中心中的报表与 "Microsoft 365 管理中心" 中的 Office 365 报表中的团队的活动报表分开。 有关 Microsoft 365 管理中心中的活动报表的详细信息，请参阅[microsoft 365 管理中心中的团队活动报表](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>团队报告参考

下面是 Microsoft 团队管理中心提供的团队报表的列表，以及每个报表中可用的一些信息的概述。

我们正在不断改进团队报告体验和添加功能。 随着时间的推移，我们将在 "Microsoft 团队管理中心" 中将其他功能构建到报表中并添加新报表。

|报告  |测量什么？ |
|---------|---------|
|[Teams 使用情况报告](teams-usage-report.md)  |  活动用户<br/>团队和频道中的活动用户<br/>活动频道<br/>彩信<br/>团队的隐私设置<br/>团队中的来宾   |
|[Teams 用户活动报告](user-activity-report.md)  |  1:1 呼叫用户参与<br/>在团队聊天中发布的用户的消息<br/>在私人聊天中发布的用户的消息<br/>用户的上次活动日期     |
|[Teams 设备使用报告](device-usage-report.md)   |  Windows 用户<br/>Mac 用户<br/>iOS 用户<br/>Android 手机用户     |
|[团队实时事件使用率报告](teams-live-event-usage-report.md)   |  总视图数<br>开始时间<br>事件状态<br>组织者<br>演示者<br>者<br>录制设置<br>生产类型    |
|[团队 PSTN 已阻止用户报告](pstn-blocked-users-report.md)   |  显示名称<br>电话号码<br>原因<br>操作类型<br>操作日期和时间   |
|[团队 PSTN 使用报告-通话计划](pstn-usage-report.md#calling-plans)|  时间戳<br>用户名<br>电话号码<br>呼叫类型 <br>调用到<br>至国家或地区 <br>调用 <br>从国家或地区<br>收费<br>货币<br>持续时间<br>国内/国际<br>通话 ID<br>号码类型<br>国家或地区<br>会议 ID<br>功能（许可证）|
|[团队 PSTN 使用报告-直接路由](pstn-usage-report.md#direct-routing)  |  时间戳<br>显示名称<br>SIP 地址<br>电话号码 <br>呼叫类型<br>调用到<br>开始时间<br>邀请时间<br>失败时间<br>结束时间<br>持续时间<br>号码类型<br>媒体绕过<br>SBC FQDN<br>Azure 区域<br>事件类型<br>最终 SIP 代码<br>最终 Microsoft 子代码<br>最终 SIP 短语<br>Coorelation ID  |

> [!NOTE]
> 团队报表显示活动用户和活动团队的数据。 例如，如果您的组织中的用户在您为报表指定的日期范围内没有在团队中处于活动状态，则该报表中不会包含该用户的数据。
