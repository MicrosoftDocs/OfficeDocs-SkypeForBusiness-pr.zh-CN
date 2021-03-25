---
title: '设置 CQD (呼叫质量) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
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
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 了解如何打开和使用呼叫质量仪表板，并获取呼叫质量的摘要报告。
ms.openlocfilehash: 2d671de0e2ddc5d4c2a4e321cf90e2e2f0dbe770
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162685"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>设置 CQD (呼叫质量) 

使用管理员凭据 (登录时) CQD (Microsoft 呼叫 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 质量仪表板) 。 或者转到 Teams 管理中心并选择"呼叫 **质量仪表板"。** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 管理中心中"通话质量仪表板"按钮的屏幕截图":::

在打开的页面上，单击 **"登录"并** 输入全局管理员帐户或 Microsoft Teams 服务管理员帐户信息。 首次登录后，CQD 将开始收集和处理数据。 请记住，可能需要一小时或几小时才能处理足够的数据，才能在报告中显示有意义的结果。

CQD 在组织范围内显示 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 2019 的呼叫和会议质量。 

> [!IMPORTANT]
> 若要将 CQD 与 Skype for Business Server 2019 一起使用，必须配置 [呼叫数据连接器](/skypeforbusiness/hybrid/configure-call-data-connector)。 在 [启动之前，请参阅规划](/skypeforbusiness/hybrid/plan-call-data-connector) 呼叫数据连接器。


## <a name="assign-admin-roles-for-access-to-cqd"></a>分配管理员角色以访问 CQD

为 [需要](/microsoft-365/admin/add-users/about-admin-roles) 使用该 CQD 的用户分配用于访问 CQD 的角色。

如果希望非管理员用户 (（例如支持工程师和技术支持) ）使用呼叫质量仪表板，可以分配以下角色之一，从而授予对 CQD 的访问权限。 


|  |查看报表  |查看 EUII 字段  |创建报表  |上传建筑物数据  |
|---------|:-------:|:-------:|:-------:|:-------:|
|全局管理员     |是         |是         |是         |是         |
|Teams 服务管理员     |是         |是         |是         |是         |
|Teams 通信管理员     |是         |是         |是         |是         |
|Teams 通信支持工程师     |是         |是         |是         |否         |
|Teams 通信支持专家     |是         |否         |是         |否         |
|Skype for Business 管理员     |是         |是         |是         |是         |
|全局阅读器 |是         |是         |是         |否         |
|报表读者<sup>1</sup>     |是         |否         |是         |否         |

<sup>1</sup>除阅读 CQD 报告外，报表读者还可以查看管理[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)中心内的所有活动报告和[Microsoft 365 Adoption 内容包的任何报告](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)。

> [!NOTE]
> 如果未看到 [EUII (](CQD-data-and-reports.md#euii-data) 最终用户可识别信息) 并且具有允许查看此信息的角色之一，请记住，CQD 仅保留 EUII 28 天。 将删除超过 28 天任何内容。

有关这些角色的信息，请参阅关于 [Office 365 管理员角色](/office365/admin/add-users/about-admin-roles)。


首次登录后，CQD 将开始收集和处理数据。 从 2019 年 12 月开始，仍可以访问旧版 CQD (cqd.lync.com) ，尽管旧门户提供了指向最新 CQD (cqd.teams.microsoft.com) 。 最终，较旧版本的 CQD 将停用。 从 2020 年 7 月 1 日开始，较旧版本的 CQD 从最新的 CQD 访问数据。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>从早期版本的 CQD 迁移建筑物数据和报表

> [!IMPORTANT]
> 自 2020 年 7 月 1 日起，无法再从旧的 CQD 迁移建筑物数据和 https://CQD.lync.com) (。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 数据

2020 年 1 月新增功能 [：下载适用于 CQD 的 Power BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可用于分析和报告 CQD 数据的可自定义 Power BI 模板。

请阅读 [使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md) 以了解更多信息。


## <a name="related-topics"></a>相关主题

[改进和监视 Teams 的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[上传租户和建筑物数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)