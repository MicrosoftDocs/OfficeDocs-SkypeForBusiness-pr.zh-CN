---
title: '使用 CQD (设置呼叫质量) '
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
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112835"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>使用 CQD (设置呼叫质量) 

使用管理员凭据 (登录时) CQD (Microsoft 呼叫质量仪表板 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)) 。 或者转到 Teams 管理中心并选择"通话 **质量仪表板"。** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 管理中心的通话质量仪表板按钮的屏幕截图":::

在打开的页面上，单击 **"登录** "并输入全局管理员帐户或 Microsoft Teams 服务管理员帐户信息。 首次登录后，CQD 将开始收集和处理数据。 请记住，可能需要一个或多个小时才能处理足够的数据，才能在报告中显示有意义的结果。

CQD 在组织范围内显示 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 2019 的呼叫和会议质量。 

> [!IMPORTANT]
> 若要将 CQD 与 Skype for Business Server 2019 一起使用，必须配置 [呼叫数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)。 在 [启动之前，请参阅"](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) 计划呼叫数据连接器"。


## <a name="assign-admin-roles-for-access-to-cqd"></a>分配管理员角色以访问 CQD

为 [需要](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 使用该 CQD 的用户分配用于访问 CQD 的角色。

如果希望非管理员用户 (支持工程师和支持人员代理) 使用呼叫质量仪表板，您可以为这些用户分配以下角色之一，从而授予对 CQD 的访问权限。 


|  |查看报表  |查看 EUII 字段  |创建报表  |上传建筑物数据  |
|---------|:-------:|:-------:|:-------:|:-------:|
|全局管理员     |是         |是         |是         |是         |
|Teams 服务管理员     |是         |是         |是         |是         |
|Teams 通信管理员     |是         |是         |是         |是         |
|Teams 通信支持工程师     |是         |是         |是         |否         |
|Teams 通信支持专家     |是         |否         |是         |否         |
|Skype for Business 管理员     |是         |是         |是         |是         |
|全局阅读器 |是         |是         |是         |否         |
|报告读者<sup>1</sup>     |是         |否         |是         |否         |

<sup>1</sup>除阅读 CQD 报告外，报告读者还可以查看管理[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)中心内的所有活动报表和[Microsoft 365 Adoption](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)内容包的任何报表。

> [!NOTE]
> 如果未看到 EUII (标识信息) 并且具有允许查看此信息的角色之一，请记住，CQD 仅将 [EUII ](CQD-data-and-reports.md#euii-data) 保留 28 天。 删除超过 28 天任何内容。

有关这些角色详细信息，请参阅["关于 Office 365 管理员角色"。](/office365/admin/add-users/about-admin-roles)


首次登录后，CQD 将开始收集和处理数据。 从 2019 年 12 月开始，仍可以访问旧版 CQD (cqd.lync.com) ，尽管旧门户提供了指向最新 CQD (cqd.teams.microsoft.com) 。 最终，旧版本的 CQD 将解除授权。 自 2020 年 7 月 1 日起，较旧版本的 CQD 从最新的 CQD 访问数据。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>从早期版本的 CQD 迁移建筑物数据和报表

> [!IMPORTANT]
> 自 2020 年 7 月 1 日起，无法再从旧的 CQD 迁移建筑物数据和 https://CQD.lync.com) (。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 数据

2020 年 1 月新增功能 [：下载适用于 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)的 Power BI 查询模板。 可用于分析和报告 CQD 数据的可自定义 Power BI 模板。

阅读 ["使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md) "以了解更多信息。


## <a name="related-topics"></a>相关主题

[改进和监视 Teams 的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[上传租户和建筑物数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)
