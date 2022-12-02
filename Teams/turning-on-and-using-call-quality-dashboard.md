---
title: 呼叫质量仪表板 (CQD) 设置
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 了解如何打开和使用通话质量仪表板，并获取通话质量摘要报告。
ms.openlocfilehash: 5f3b9fbb42199892136569ac179907b18da4e460
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245705"
---
# <a name="set-up-the-call-quality-dashboard"></a>设置通话质量仪表板

使用管理员凭据) 登录时[https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)打开Microsoft通话质量仪表板 ( (CQD) 。 或者转到 Teams 管理中心，选择“分析” **&报告** > **通话质量仪表板**。

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 管理中心“通话质量仪表板”按钮的屏幕截图。":::

在打开的页面上，单击“**登录**”并输入全局管理员帐户或Microsoft Teams 管理员帐户信息。 首次登录后，CQD 将开始收集和处理数据。 请记住，处理足够的数据可能需要一个或几个小时才能在报表中显示有意义的结果。

CQD 在组织范围内显示 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 2019 的通话和会议质量。 

> [!IMPORTANT]
> 若要将 CQD 与 Skype for Business Server 2019 配合使用，必须[配置呼叫数据连接器](/skypeforbusiness/hybrid/configure-call-data-connector)。 在开始之前，请参阅 [计划呼叫数据连接器](/skypeforbusiness/hybrid/plan-call-data-connector) 。


## <a name="assign-admin-roles-for-access-to-cqd"></a>分配管理员角色以访问 CQD

将用于访问 CQD [的角色](/microsoft-365/admin/add-users/about-admin-roles) 分配给需要使用 CQD 的人员。

如果希望非管理员用户 (（例如支持工程师和技术支持代理）) 使用通话质量仪表板，你可以为这些用户分配以下角色之一，从而授予对 CQD 的访问权限。 


|&nbsp;  |查看报告  |查看 EUII 字段  |创建报表  |上传生成数据  |
|---------|:-------:|:-------:|:-------:|:-------:|
|全局管理员     |是         |是         |是         |是         |
|Teams 管理员     |是         |是         |是         |是         |
|Teams 通信管理员     |是         |是         |是         |是         |
|Teams 通信支持工程师     |是         |是         |是         |否         |
|Teams 通信支持专家     |是         |否         |是         |否         |
|Skype for Business管理员     |是         |是         |是         |是         |
|全局读取器 |是         |是         |是         |否         |
|报表读取者<sup>1</sup>     |是         |否         |是         |否         |

<sup>1</sup> 除了阅读 CQD 报告外，报表读者还可以查看管理中心中的所有[活动报告](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)，以及 [Microsoft 365 采用内容包](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)中的任何报告。

> [!NOTE]
> 如果你未看到 [EUII (最终用户身份信息) ](CQD-data-and-reports.md#euii-data) 并且你拥有允许查看此信息的角色之一，请记住，CQD 仅保留 EUII 28 天。 删除超过 28 天的任何内容。

有关这些角色的详细信息，请参阅[关于Office 365管理员角色](/office365/admin/add-users/about-admin-roles)。


首次登录后，CQD 将开始收集和处理数据。

## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 数据

2020 年 1 月新增功能： [下载适用于 CQD 的 Power BI 查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可用于分析和报告 CQD 数据的可自定义 Power BI 模板。

有关详细信息 [，请阅读使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md) 。

## <a name="related-topics"></a>相关主题

[改进和监视 Teams 的通话质量](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[上传租户和生成数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理通话和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)
