---
title: '设置通话质量仪表板 (CQD) '
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
description: 了解如何打开和使用呼叫质量仪表板，获取通话质量的摘要报告。
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918652"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>设置通话质量仪表板 (CQD) 

打开 Microsoft 通话质量仪表板 (CQD) ， [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (用管理员凭据登录) 。 或转到 "团队管理中心"，然后选择 " **呼叫质量" 仪表板** 。 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="团队管理中心中的 "呼叫质量" 仪表板按钮的屏幕截图":::

在打开的页面上，单击 " **登录** "，然后输入全局管理员帐户或 Microsoft 团队服务管理员帐户信息。 第一次登录后，CQD 将开始收集和处理数据。 请记住，可能需要一个或多个小时才能处理足够的数据，以在报表中显示有意义的结果。

CQD 显示呼叫和会议质量、组织范围级别、Microsoft 团队、Skype for business Online 和 Skype for business Server 2019。 

> [!IMPORTANT]
> 要将 CQD 与 Skype for Business Server 2019 配合使用，您必须 [配置 "呼叫数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)"。 请参阅在开始之前 [计划通话数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) 。


## <a name="assign-admin-roles-for-access-to-cqd"></a>分配管理员角色以访问 CQD

将 CQD 的 [角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 分配给需要使用它的人员。

如果您希望非管理员用户 (例如支持工程师和帮助台工程师) 使用 "呼叫质量" 仪表板，则可以为这些用户分配以下角色之一，从而提供对 CQD 的访问权限。 


|  |查看报表  |查看 EUII 字段  |创建报表  |上载构建数据  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Office 365 全局管理员     |是         |是         |是         |是         |
|Teams 服务管理员     |是         |是         |是         |是         |
|Teams 通信管理员     |是         |是         |是         |是         |
|Teams 通信支持工程师     |是         |是         |是         |否         |
|团队沟通支持专家     |是         |否         |是         |否         |
|Skype for Business 管理员     |是         |是         |是         |是         |
|Azure AD 全局阅读器 |是         |是         |是         |否         |
|Office 365 报告阅读器<sup>1</sup>     |是         |否         |是         |否         |

<sup>1</sup> 除了阅读 CQD 报表，Office 365 报表读者还可以查看管理中心中的所有 [活动报表](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) 和 [Microsoft 365 采纳内容包](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)中的所有报表。

> [!NOTE]
> 如果您没有看到 [EUII (最终用户的可识别信息) ](CQD-data-and-reports.md#euii-data) ，并且您拥有允许查看此信息的角色之一，请记住 CQD 仅保留28天的 EUII。 任何早于28天的内容都将被删除。

有关这些角色的详细信息，请参阅 [关于 Office 365 管理员角色](/office365/admin/add-users/about-admin-roles)。


第一次登录后，CQD 将开始收集和处理数据。 从2019年12月到，您仍然可以访问 CQD (cqd.lync.com) 的旧版本，尽管旧版门户提供了指向最新 CQD (cqd.teams.microsoft.com) 的链接。 最终，旧版本的 CQD 将会停止。 从2020年7月1日起，较早版本的 CQD 访问最新 CQD 中的数据。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>从早期版本的 CQD 中迁移构建数据和报表

> [!IMPORTANT]
> 从2020年7月1日起，您无法再从旧的 CQD (中进行数据和报告的迁移 https://CQD.lync.com) 。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 数据

2020年1月 [的新增功能：下载 CQD 的 POWER BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可用于分析和报告 CQD 数据的自定义 Power BI 模板。

已阅读 " [使用 POWER BI 分析 CQD 数据](CQD-Power-BI-query-templates.md) " 以了解详细信息。


## <a name="related-topics"></a>相关主题

[改善和监控团队的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[上载租户和生成数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报告](CQD-data-and-reports.md)

[使用 CQD 管理通话和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)
