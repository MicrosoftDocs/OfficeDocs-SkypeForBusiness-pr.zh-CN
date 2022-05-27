---
title: Microsoft Teams信息保护许可证报告
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: 了解如何在Microsoft Teams管理中心使用Teams信息保护许可证报告，了解组织中的应用如何使用更改通知事件订阅 API。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fade7b4d5d89061cdc1dd5eb231a80d5ee9e8938
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681533"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams信息保护许可证报告


Teams信息保护许可证报告提供[具有许可证和付款要求的 Microsoft Graph API](/graph/teams-licenses) 的 API 使用情况见解。 此报告重点介绍在 [model=A](/graph/teams-licenses#modela-requirements) 中使用这些 API 的所有应用。 当在 [model=B](/graph/teams-licenses#modelb-requirements) 或 [评估模式](/graph/teams-licenses#evaluation-mode-default-requirements)下使用 API 时，它不会显示使用情况。 


## <a name="view-the-information-protection-license-report"></a>查看信息保护许可证报告

必须是 Teams 服务管理员才能管理这些策略。 请参阅 [Teams 管理员角色管理 Teams](../using-admin-roles.md) ，了解管理员角色和权限。

1. 在Microsoft Teams管理中心的左侧导航中，选择 **“分析”&报告** > **使用情况报告**。 在 **“查看报表**”选项卡上的 **“报** 表”下，选择 **信息保护许可证**。
2. 在 **“日期”范围** 下，选择一个区域。
3. 在 **“应用**”下，选择一个应用，然后选择 **“运行报表**”。

    ![Teams管理中心中包含标注的Teams信息保护许可证报表下拉列表的屏幕截图。](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Teams管理中心中包含标注的Teams信息保护许可证报表下拉列表的屏幕截图。")

4. 对于每个类别，可以查看有关具有许可证的用户、没有许可证的用户、种子容量和利用容量的指标。 

    ![Teams管理中心中包含标注的更改通知的Teams信息保护许可证报告摘要图表的屏幕截图。](../media/teams-info-protection-license-report-chart-with-callouts.png "Teams管理中心中包含标注的更改通知的Teams信息保护许可证报告摘要图表的屏幕截图。")

5. 可以通过单击导出按钮导出数据。 可以通过单击Teams更改通知 API 的选项卡、Teams修补程序 API、Teams导出 API (聊天) 以及Teams (团队) 导出 API 来切换表数据。 

    ![带有标注的选项卡Teams管理中心中Teams信息保护许可证报表的不同选项卡的屏幕截图。](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "带有标注的选项卡Teams管理中心中Teams信息保护许可证报表的不同选项卡的屏幕截图。")

    ![Teams管理中心中包含标注Teams信息保护许可证报告的更改通知选项卡的屏幕截图。](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Teams管理中心中包含标注Teams信息保护许可证报告的更改通知选项卡的屏幕截图。")


## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看信息保护许可证报告，了解过去三个月的趋势。 |
|**2**   |应用名称将显示使用 Microsoft 图形 API的所有应用的列表，这些应用在所选时间段内[具有许可证和付款要求](/graph/teams-licenses)。|
|**3**   |拥有有效 [许可证的](/graph/teams-licenses#required-licenses-for-modela)用户数。  |
|**4**   |没有有效 [许可证](/graph/teams-licenses#required-licenses-for-modela)的用户数。  |
|**5**   |允许应用使用的总 API 调用量，在该应用中，每个 API 调用的消耗费将向应用收取。 |
|**6**   |应用用于给定日期范围的总 API 调用量。 |
|**7**   |将报表导出到 CSV 文件以进行脱机分析。 选择 **“导出到Excel**”，然后选择“**下载”** 选项卡。选择“**下载**”以在报表准备就绪时下载报表。 此导出将仅导出当前选定的选项卡。|
|**8**   |选择要在图表中显示或隐藏它的任何特定标签。 |
|**9**   |每个选项卡显示特定 API 集的使用情况，即 [更改通知](/graph/api/resources/webhooks)、 [导出 API](/microsoftteams/export-teams-content) 和 [更新消息 API](/graph/api/message-update)。 选择一个选项卡以查看该 API 的使用情况详细信息。 |
|**10**   |**更改通知 API 使用情况**<li>**显示名称** - 触发更改通知的用户的显示名称。</li><li>**必需许可证** - 给定用户是否具有成功向应用发送更改通知所需的许可证。</li><li>**尝试计数** - 由于此用户而触发的更改通知总数。</li><li>**已发送更改通知** - 发送到应用的更改通知总数。 如果用户没有有效的许可证，则此值将小于触发的总更改通知数。</li>|
|**11**|**修补 API**<li>**显示名称** - 尝试更新消息的用户的显示名称。</li> <li>**必需许可证** - 给定用户是否具有消息成功更新所需的许可证。</li><li>**尝试计数** - 更新消息的尝试总数。</li><li>**消息修补** - 已成功更新的消息总数。</li>|
|**12**|**聊天导出 API 使用情况**<li>**显示名称** - 尝试导出用户聊天消息的用户的显示名称。</li><li>**必需许可证** - 给定用户是否具有成功导出消息所需的许可证。</li><li>**尝试计数** - 导出聊天消息的尝试总数。</li><li>**已导出消息** - 成功导出聊天消息的尝试总数。</li> |
|**13**|**团队导出 API 使用情况**<li>**显示名称** - 尝试导出该团队消息的团队的显示名称。</li><li>**尝试计数** - 导出团队消息的尝试总数。</li><li>**已导出消息** - 成功导出团队消息的尝试总数。</li> |


## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使Teams用户活动报表中的数据匿名，必须是全局管理员。 这会在报表及其导出中隐藏可识别的信息，例如显示名称、电子邮件和 Azure AD ID。

1. 在Microsoft 365 管理中心中，转到 **设置** \> **组织设置**，然后在 **“服务”** 选项卡下选择 **“报表**”。
    
2. 选择 **“报** 表”，然后选择 **“显示匿名标识符**”。 此设置同时应用于Microsoft 365 管理中心和Teams管理中心的使用情况报告。
  
3. 选择 **“保存更改**”。