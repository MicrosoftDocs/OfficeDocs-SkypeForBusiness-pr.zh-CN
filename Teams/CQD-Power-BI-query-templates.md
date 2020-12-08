---
title: 使用 Power BI 分析 Microsoft 团队的 CQD 数据
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 Power BI 分析 Microsoft 团队的 CQD 数据。
ms.openlocfilehash: a06a3cb76cd778c132b3e8745b279035e875f16e
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588325"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>使用 Power BI 分析 Microsoft 团队的 CQD 数据

2020年1月 [的新增功能：下载 CQD 的 POWER BI 查询模板](https://www.microsoft.com/download/details.aspx?id=102291)。 可用于分析和报告 CQD 数据的自定义 Power BI 模板。

对于通话质量仪表板 (CQD) 团队中的报表，如果你希望使用 Power BI 查询和报告数据，请下载我们的 CQD Power BI 模板。 打开 Power BI 中的模板时，系统将提示你通过 CQD 管理员凭据登录。 你可以自定义这些查询模板，并将其分发给你组织中具有 Power BI 许可证和 CQD 管理员权限的任何人。

在你可以使用这些 PBIT 文件之前，你需要使用 [下载](https://www.microsoft.com/download/details.aspx?id=102291)中包含的 *MicrosoftCallQuality* 文件 [安装 Microsoft CQD 的 Power BI 连接器](CQD-Power-BI-connector.md)。 

请确保你拥有访问 Power BI 报表的正确 [CQD 访问角色](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 。 

|  |  |
|---------|---------|
|<strong> (New！ ) </strong> CQD 团队自动助理 & 呼叫队列历史报告。 pbit     |  此模板提供以下三个报表：</p><li>自动助理-显示进入自动助理的通话的分析。</li><li>呼叫队列–显示进入通话队列的通话的分析。</li><li>代理日程表–显示呼叫队列呼叫中处于活动状态的代理的日程表视图。</li><br>若要了解详细信息，请阅读 [自动助理 & 呼叫队列历史记录报告](aa-cq-cqd-historical-reports.md)。        |
|CQD 帮助台报告。 pbit     |集成生成和 EUII 数据时，此报表旨在让你从单个用户向上钻取，以查找该用户的不良通话质量的上游根本原因 (例如，用户在遇到网络问题的大楼中) 。         |
|CQD Location 增强的报告。 pbit     | Imagining CQD SPD 位置报告。 包括9个报表，提供通话质量、建筑物 WiFi、可靠性以及通过 RMC) 信息，使用其他 thrus 通过构建或用户进行 (呼叫。  请确保上载建筑物数据以最大化报告体验。        |
|CQD 移动设备报表。 pbit     | 提供专门针对移动设备用户进行调整的见解，包括通话质量、可靠性和费率我的通话。 查看 (Android、iOS) 的移动网络、WiFi 网络和移动操作系统报告。        |
|CQD PSTN 直接路由报告。 pbit     |为通过直接路由进行的 PSTN 呼叫提供特定的见解。 若要了解详细信息，请 [使用 CQD PSTN 直接路由报告](CQD-PSTN-report.md)进行阅读。         |
|CQD 摘要报告。 pbit     |更好的可视化效果、改进的演示文稿、增加的信息密度和滚动日期。 这些报表使标识符离群离群更容易。 通过易于使用的交互式地图按位置深化通话质量。 9个新报表：</p>-整体质量<br>-整体可靠性<br>-RMC () 整体通话费率<br>-会议质量<br>-P2P 质量<br>-会议可靠性<br>-P2P 可靠性<br>-会议 RMC<br>-P2P RMC         |
|<strong> (New！ ) </strong> CQD 团队使用情况报告。 pbit     | 显示组织中的用户使用团队的方式和数量。 请确保上载建筑物数据以最大化报告体验。 若要了解详细信息，请参阅 [使用 CQD POWER BI 报表查看 Microsoft 团队的利用率](CQD-teams-utilization-report.md)。        |
|CQD 用户反馈 (评价我的通话) 报告。 pbit     | 显示使用一种可轻松地帮助支持组织通话的方式对我的通话数据进行评级。 与 verbatims 的交叉参考以识别最终用户教育机会。        |

> [!TIP]
> 为 CQD 数据设置 Power BI 报表后，将其作为选项卡添加到频道。 **+** 在频道中选择后，选择 " **Power BI** "，然后查找报表。 若要了解详细信息，请参阅 [团队的 POWER BI 选项卡的嵌入报表](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams)。 请记住，只有具有 Power BI 许可证和 CQD 管理员凭据的用户才能访问这些报表。


## <a name="related-topics"></a>相关主题

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)

[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)
 
