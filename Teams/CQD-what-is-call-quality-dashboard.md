---
title: 什么是调用质量仪表板 (CQD) ？
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 了解呼叫质量仪表板 (CQD) ，以及如何使用它查看有关 Microsoft Teams 中的会议和呼叫质量的报告。
ms.openlocfilehash: 3bc3c9dcd83e4ff95a07fbffb6f07da39d254cde
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790067"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>什么是调用质量仪表板 (CQD) ？

Microsoft 呼叫质量仪表板 (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 在 **组织范围内** 显示 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 2019 的通话和会议质量。 

  
最新版本的 CQD 具有 [近实时 (NRT) 数据馈送](CQD-data-and-reports.md)，这意味着呼叫记录在通话结束后的 30 分钟内在 CQD 中可用。

无论 CQD 包含 [最终用户身份信息 (EUII) 数据](CQD-data-and-reports.md#euii-data)，其管理方式与 [整个 Microsoft 365 中的 EUII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview) 相同。

CQD 旨在帮助 Teams 管理员、Skype for Business管理员和网络工程师在组织范围内监视呼叫和会议质量。 你将使用 CQD 来帮助 **优化网络** 以提高性能质量。 当需要查看 **特定用户** 的呼叫和会议信息时，请将 CQD 数据与每个用户 [的呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)结合使用。

例如，使用 CQD 时，可以确定使用每用户呼叫分析) 观察到的用户通话质量不佳 (是由于网络问题也影响到许多其他用户。 CQD 捕获使用 Teams 或 Skype for Business 进行的单个调用体验和总体调用质量。 使用 CQD，整体模式可能会变得明显，因此网络工程师可以对呼叫质量进行明智的评估。 CQD 提供通话质量指标报告，可让你深入了解总体呼叫质量、服务器客户端流、客户端流和语音质量 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。 
  
![通话质量仪表板的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

在 CQD 中，我们鼓励你上传生成和终结点信息，以便使用Location-Enhanced报表来分析用户内部的通话质量和可靠性。 可以评估数据以确定问题是否与单个用户隔离或影响较大的用户段。 若要在 CQD 中启用构建或特定于终结点的视图，管理员必须在 CQD **租户数据上传** 页上 [传生成或终结点信息](CQD-upload-tenant-building-data.md)。

![通话质量仪表板Location-Enhanced报表的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

不要错过我们的 [“管理呼叫和会议质量](quality-of-experience-review-guide.md) ”文章，该文章为负责管理 Teams 中服务质量的 Teams 管理员或支持工程师提供深入指导。


## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 数据

2020 年 1 月新增功能： [下载适用于 CQD 的 Power BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可用于分析和报告 CQD 数据的可自定义 Power BI 模板。

阅读 [使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md) 以了解详细信息。



## <a name="related-topics"></a>相关主题

[改进和监视 Teams 的呼叫质量](monitor-call-quality-qos.md)

[设置呼叫质量仪表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[上传租户和生成数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)


[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
