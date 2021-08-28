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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 了解如何打开和使用呼叫质量仪表板，并获取呼叫质量的摘要报告。
ms.openlocfilehash: a6f39fe728a6616e8f70edb86d18e8cc27cc8501
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58637047"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>如何设置呼叫质量仪表板

使用管理员凭据 (登录时) CQD (Microsoft 呼叫质量 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 仪表板) 。 或者转到管理Teams并选择"呼叫 **质量仪表板"。** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="管理中心中"呼叫质量仪表板"按钮Teams屏幕截图":::

在打开的页面上，单击 **"登录"** 并输入全局管理员帐户或Microsoft Teams管理员帐户信息。 首次登录后，CQD 将开始收集和处理数据。 请记住，可能需要一小时或几小时才能处理足够的数据，才能在报告中显示有意义的结果。

CQD 显示 2019 年 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 级别的呼叫和会议质量。 

> [!IMPORTANT]
> 若要在 2019 Skype for Business Server CQD，必须[配置呼叫数据连接器](/skypeforbusiness/hybrid/configure-call-data-connector)。 在 [启动之前，请参阅规划](/skypeforbusiness/hybrid/plan-call-data-connector) 呼叫数据连接器。


## <a name="assign-admin-roles-for-access-to-cqd"></a>分配管理员角色以访问 CQD

为 [需要](/microsoft-365/admin/add-users/about-admin-roles) 使用该 CQD 的用户分配用于访问 CQD 的角色。

如果希望非管理员用户 (（例如支持工程师和技术支持) ）使用呼叫质量仪表板，可以分配以下角色之一来授予对 CQD 的访问权限。 


|&nbsp;  |查看报表  |查看 EUII 字段  |创建报表  |Upload生成数据  |
|---------|:-------:|:-------:|:-------:|:-------:|
|全局管理员     |是         |是         |是         |是         |
|Teams 管理员     |是         |是         |是         |是         |
|Teams 通信管理员     |是         |是         |是         |是         |
|Teams 通信支持工程师     |是         |是         |是         |否         |
|Teams通信支持专家     |是         |否         |是         |否         |
|Skype for Business管理员     |是         |是         |是         |是         |
|全局阅读器 |是         |是         |是         |否         |
|报表读者<sup>1</sup>     |是         |否         |是         |否         |

<sup>1</sup>除了阅读 CQD 报告外，报告读者还可以查看管理[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)中心内的所有活动报告以及来自"采用情况"内容包Microsoft 365[报告](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)。

> [!NOTE]
> 如果未看到 [EUII (](CQD-data-and-reports.md#euii-data) 最终用户可识别信息) 并且你拥有允许查看此信息的角色之一，请记住，CQD 仅将 EUII 保留 28 天。 将删除超过 28 天。

有关这些角色的信息，请参阅[关于Office 365角色](/office365/admin/add-users/about-admin-roles)。


首次登录后，CQD 将开始收集和处理数据。




## <a name="use-power-bi-to-analyze-cqd-data"></a>使用Power BI分析 CQD 数据

2020 年 1 月新增功能[：Power BI CQD 的查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可Power BI模板，可用于分析和报告 CQD 数据。

请参阅[使用Power BI分析 CQD 数据](CQD-Power-BI-query-templates.md)以了解更多信息。


## <a name="related-topics"></a>相关主题

[改进和监视呼叫质量Teams](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[Upload租户和建筑物数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报表](CQD-data-and-reports.md)

[使用 CQD 管理呼叫和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和度量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用Power BI分析 CQD 数据](CQD-Power-BI-query-templates.md)
