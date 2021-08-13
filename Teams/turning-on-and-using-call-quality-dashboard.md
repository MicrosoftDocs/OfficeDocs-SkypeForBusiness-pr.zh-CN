---
title: '设置呼叫质量仪表板 (CQD) '
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
ms.openlocfilehash: cf4c6d56e4fa646495383b4998e80789d9cdaca67b9cc35d07f613cda4e70b85
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300448"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>如何设置呼叫质量仪表板

打开 Microsoft 呼叫质量仪表板 (CQD) ， (管理员 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 凭据登录) 。 或转到管理Teams中心，然后选择呼叫 **质量仪表板**。 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="管理中心内呼叫质量仪表板按钮Teams屏幕截图":::

在打开的页面上，单击"**登录"，** 然后输入全局管理员帐户或Microsoft Teams管理员帐户信息。 首次登录后，CQD 将开始收集和处理数据。 请记住，可能需要一个或多个时间才能处理足够的数据，才能在报告内显示有意义的结果。

CQD 显示 2019 年 10 月 Microsoft Teams、Skype for Business Online 和 Skype for Business Server级别的通话和会议质量。 

> [!IMPORTANT]
> 若要将 CQD 与 Skype for Business Server 2019 一起使用，必须[配置呼叫数据连接器](/skypeforbusiness/hybrid/configure-call-data-connector)。 在 [启动之前，请参阅规划](/skypeforbusiness/hybrid/plan-call-data-connector) 呼叫数据连接器。


## <a name="assign-admin-roles-for-access-to-cqd"></a>分配管理员角色以访问 CQD

[将](/microsoft-365/admin/add-users/about-admin-roles)访问 CQD 的角色分配给需要使用该 CQD 的用户。

如果希望非管理员用户 (支持工程师和支持人员) 使用呼叫质量仪表板，您可以为这些用户分配以下角色之一，从而授予对 CQD 的访问权限。 


|&nbsp;  |查看报告  |查看 EUII 字段  |创建报表  |Upload生成数据  |
|---------|:-------:|:-------:|:-------:|:-------:|
|全局管理员     |是         |是         |是         |是         |
|Teams管理员     |是         |是         |是         |是         |
|Teams 通信管理员     |是         |是         |是         |是         |
|Teams 通信支持工程师     |是         |是         |是         |否         |
|Teams 通信支持专家     |是         |否         |是         |否         |
|Skype for Business 管理员     |是         |是         |是         |是         |
|全局读取者 |是         |是         |是         |否         |
|报告读者<sup>1</sup>     |是         |否         |是         |否         |

<sup>1</sup>除了阅读 CQD 报告之外，报告读者还可以查看管理[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)中心内的所有活动报表以及来自"采用"内容包Microsoft 365[报告](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)。

> [!NOTE]
> 如果没有看到 [EUII (](CQD-data-and-reports.md#euii-data) 最终用户可识别信息) 并且你具有允许查看此信息的角色之一，请记住，CQD 仅将 EUII 保留 28 天。 任何超过 28 天的时间都将被删除。

有关这些角色详细信息，请参阅关于Office 365[角色](/office365/admin/add-users/about-admin-roles)。


首次登录后，CQD 将开始收集和处理数据。 截至 2019 年 12 月，你仍然可以访问较旧版本的 CQD (cqd.lync.com) ，尽管旧门户提供了指向最新 CQD (cqd.teams.microsoft.com) 。 最终，将停用较早版本的 CQD。 自 2020 年 7 月 1 日起，较旧版本的 CQD 从最新的 CQD 访问数据。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>从以前版本的 CQD 迁移生成数据和报表

> [!IMPORTANT]
> 自 2020 年 7 月 1 日起，您无法再从旧的 CQD 迁移生成数据和 https://CQD.lync.com) (。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 数据

2020 年 1 月新增功能[：下载Power BI CQD 的查询模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可Power BI模板，可用于分析和报告 CQD 数据。

阅读[使用Power BI分析 CQD 数据](CQD-Power-BI-query-templates.md)以了解更多信息。


## <a name="related-topics"></a>相关主题

[改进和监视呼叫质量Teams](monitor-call-quality-qos.md)

[什么是 CQD？](CQD-what-is-call-quality-dashboard.md)

[上传租户和建筑物数据](CQD-upload-tenant-building-data.md)

[CQD 数据和报告](CQD-data-and-reports.md)

[使用 CQD 管理通话和会议质量](quality-of-experience-review-guide.md)

[CQD 中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的流分类](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 数据](CQD-Power-BI-query-templates.md)
