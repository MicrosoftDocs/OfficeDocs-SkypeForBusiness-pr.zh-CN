---
title: 什么是通话质量仪表板（CQD）？
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 了解通话质量仪表板（CQD）以及如何使用它查看 Microsoft 团队中会议和通话质量的报告。
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088240"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>什么是通话质量仪表板（CQD）？

Microsoft 通话质量仪表板（CQD）- [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 在**组织范围级别**、Microsoft 团队、Skype for Business Online 和 Skype for business Server 2019 中显示呼叫和会议质量。 

  
最新版本的 CQD 具有[近乎实时（NRT）数据馈送](CQD-data-and-reports.md)，这意味着呼叫记录在通话结束后的30分钟内将在 CQD 中可用。

无论 CQD 包含[最终用户的可识别信息（EUII）数据](CQD-data-and-reports.md#euii-data)，其管理方式与在[Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)中的 EUII 一样。

CQD 旨在帮助团队管理员、Skype for Business 管理员和网络工程师在组织范围内监视呼叫和会议质量。 您将使用 CQD 帮助您优化您的**网络**以提高性能质量。 当你需要查看**特定用户**的调用和会议信息时，请将 CQD 数据与每用户[调用分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)结合使用。

例如，使用 CQD，你可以确定用户的通话质量不佳（使用每用户呼叫分析时看到的）是由于网络问题也会影响其他许多用户。 CQD 捕获个人通话体验和使用团队或 Skype for business 进行的总体通话质量。 通过 CQD，整体模式可能会变得显而易见，因此网络工程师可以及时了解通话质量。 CQD 提供了通话质量指标的报告，使你可以深入了解总通话质量、服务器客户端流、客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。 
  
![通话质量仪表板的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

在 CQD 中，我们鼓励你上载生成和终结点信息，使你可以使用位置增强的报表来分析用户建筑物内的通话质量和可靠性。 可以对数据进行评估，以确定问题是独立于单个用户还是影响较大的用户段。 若要在 CQD 中启用生成或特定于终结点的视图，管理员必须在 CQD**租户数据上载**页面上[上载生成或终结点信息](CQD-upload-tenant-building-data.md)。

![通话质量仪表板的位置增强的报表的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

不要错过我们的 "[管理通话和会议质量](quality-of-experience-review-guide.md)" 文章，这些文章为负责管理团队中的服务质量的团队管理员或支持工程师提供了深入指导。

## <a name="older-version-of-cqd-cqdlynccom"></a>较早版本的 CQD （CQD.lync.com）

当前版本的 CQD （ https://CQD.Teams.microsoft.com) 替换较旧版本的 CQD （ https://CQD.lync.com) 。 您仍然可以使用 CQD.lync.com （Skype for Business 管理中心提供），但从2020年7月1日起使用来自 CQD 的数据。Teams.microsoft.com。 我们将立即关闭对 CQD.lync.com 的访问，因此应转到 CQD。Teams.microsoft.com 如果还未执行此操作。

> [!IMPORTANT]
> 从2020年7月1日起，你无法再从旧的 CQD （CQD.lync.com）查看或修改你的构建或查询数据。 如果尚未从 CQD.lync.com 迁移这些数据，但仍需要它，请记录支持票证。

## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 数据

2020年1月[的新增功能：下载 CQD 的 POWER BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可用于分析和报告 CQD 数据的自定义 Power BI 模板。

已阅读 "[使用 POWER BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)" 以了解详细信息。



## <a name="related-topics"></a>相关主题

[改善和监控团队的通话质量](monitor-call-quality-qos.md)

[设置通话质量仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md)

[上载租户和生成数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报告](CQD-data-and-reports.md)

[使用 CQD 管理通话和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)


[Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)