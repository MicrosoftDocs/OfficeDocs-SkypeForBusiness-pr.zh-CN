---
title: 使用Power BI分析用于存储的 CQD Microsoft Teams
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
ms.localizationpriority: medium
description: 使用Power BI分析 CQD 数据Microsoft Teams。
ms.openlocfilehash: 4a96a53454f1f4d89feed3ea87342a7991d7975c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013766"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>使用Power BI分析用于存储的 CQD Microsoft Teams

2020 年 1 月新增功能[：Power BI CQD 的查询模板](https://www.microsoft.com/download/details.aspx?id=102291)。 可Power BI模板，可用于分析和报告 CQD 数据。

对于 Teams 中的 (CQD) 报表，如果希望使用 Power BI 查询和报告数据，请下载 CQD Power BI 模板。 打开模板时Power BI，系统会提示使用 CQD 管理员凭据登录。 可以自定义这些查询模板，并将其分发给组织中具有管理员许可证Power BI CQD 管理员权限的任何人。

在使用这些 PBIT 文件之前，需要使用下载中包含的 *MicrosoftCallQuality.pqx* 文件安装 [Microsoft CQD](CQD-Power-BI-connector.md)的 Power BI [连接器](https://www.microsoft.com/download/details.aspx?id=102291)。 

请确保拥有正确的[CQD 访问角色](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)，以访问Power BI报告。 

|&nbsp;|&nbsp;|
|---------|---------|
|<strong> (New！) </strong>CQD Teams 自动助理 &调用队列历史 Report.pbit     |  此模板提供以下三个报告：</p><li>自动助理 - 显示对进入自动助理的呼叫的分析。</li><li>呼叫队列 - 显示对进入呼叫队列的呼叫的分析。</li><li>代理时间线 - 显示呼叫队列调用中处于活动状态的代理的时间线视图。</li><br>若要了解有关详细信息，请阅读自动助理 &[队列历史报告"。](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |此报告集成了建筑物和 EUII 数据，旨在让你从单个用户向上钻取，以找出导致该用户通话质量不佳的上游根本原因 (例如，该用户位于遇到网络问题) 的大楼中。         |
|CQD 位置增强 Report.pbit     | 重新设想 CQD SPD 位置报告。 包括 9 个报告，通过生成或按用户提供呼叫质量、构建 WiFi、可靠性和呼叫 (RMC) 信息和其他钻取信息。  请确保上传建筑物数据，以最大化报告体验。        |
|CQD 移动设备 Report.pbit     | 提供专门针对移动设备用户的见解，包括呼叫质量、可靠性和评价我的呼叫。 在 Android、iOS) 中查看移动网络、WiFi 网络和移动操作系统 (报表。        |
|CQD PSTN 直接路由 Report.pbit     |提供特定于通过直接路由的 PSTN 呼叫的见解。 有关详细信息，请阅读使用 [CQD PSTN 直接路由报告](CQD-PSTN-report.md)。         |
|CQD 摘要 Report.pbit     |更好的可视化效果、改进的呈现方式、更高的信息密度和滚动日期。 使用这些报表可以更轻松地识别离群值。 使用易于使用的交互式地图按位置深入了解呼叫质量。 9 个新报表：</p>- 总体质量<br>- 整体可靠性<br>- RMC ("我的呼叫) 总体<br>- 会议质量<br>- P2P 质量<br>- 会议可靠性<br>- P2P 可靠性<br>- 会议 RMC<br>- P2P RMC         |
|<strong> (New！) </strong>CQD Teams利用率报告.pbit     | 显示组织中用户如何使用Teams以及使用多少。 请确保上传建筑物数据，以最大化报告体验。 有关详细信息，请阅读使用[CQD Power BI报表查看Microsoft Teams使用情况](CQD-teams-utilization-report.md)。        |
|CQD 用户反馈 (将我的呼叫) Report.pbit     | 显示"评价我的呼叫"数据的方式，你可以轻松地使用它来帮助支持组织的呼叫。 交叉引用和逐字记录，确定最终用户教育机会。        |

> [!TIP]
> 为 CQD 数据设置Power BI报表后，将它们作为选项卡添加到频道。 在频道 **+** 中选择后，选择"Power BI"，然后查找报表。  若要了解有关详细信息，请阅读[嵌入报表，Power BI选项卡Teams。](/power-bi/service-embed-report-microsoft-teams) 请记住，只有具有 Power BI 和 CQD 管理员凭据的用户才能访问这些报告。


## <a name="related-topics"></a>相关主题

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)

[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](./monitor-call-quality-qos.md)
