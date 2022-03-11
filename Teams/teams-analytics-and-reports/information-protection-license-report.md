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
description: 了解如何在 Microsoft Teams 管理中心内使用Teams信息保护许可证报告，了解组织中应用如何使用更改通知事件订阅 API。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73ce4b5720c42cdb4e468182d6290912baf95d7e
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435856"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams信息保护许可证报告


Teams信息保护许可证报告提供了具有许可证和付款[要求的 Microsoft Graph API 的 API 使用情况见解](/graph/teams-licenses)。 此报告重点介绍在 [model=A](/graph/teams-licenses#modela-requirements) 中使用这些 API 的所有应用。 在 model [=B](/graph/teams-licenses#modelb-requirements) 或评估模式下使用 API 时，它不会 [显示使用情况](/graph/teams-licenses#evaluation-mode-default-requirements)。 


## <a name="view-the-information-protection-license-report"></a>查看信息保护许可证报告

必须是 Teams 服务管理员才能管理这些策略。 请参阅 [Teams 管理员角色管理 Teams](../using-admin-roles.md) ，了解管理员角色和权限。

1. 在管理中心的左侧导航Microsoft Teams，选择 **"分析**"&" > **报表"**。 在" **查看报表"选项卡** 上的"报表 **"下**，选择" **信息保护许可证"**。
2. 在 **"日期范围**"下，选择一个范围。
3. 在 **"应用**"下，选择一个应用，然后选择" **运行报表"**。

    ![屏幕截图：Teams管理中心内包含标注Teams信息保护许可证报表的下拉列表。](../media/teams-info-protection-license-report-dropdown-with-callouts.png "屏幕截图：Teams管理中心内包含标注Teams信息保护许可证报表的下拉列表。")

4. 对于每个类别，可以查看有关具有许可证的用户、没有许可证的用户、种子设定容量和已利用容量的指标。 

    ![包含标注更改通知的 Teams 管理中心中Teams信息保护许可证报表的摘要图表的屏幕截图。](../media/teams-info-protection-license-report-chart-with-callouts.png "包含标注更改通知的 Teams 管理中心中Teams信息保护许可证报表的摘要图表的屏幕截图。")

5. 单击"导出"按钮可以导出数据。 可以通过单击 Teams 更改通知 API、Teams 修补程序 API、Teams 导出 API (聊天) 和 Teams 导出 API (团队) 选项卡来切换表数据。 

    ![带标注的选项卡的 Teams 管理中心中Teams信息保护许可证报表的屏幕截图。](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "带标注的选项卡的 Teams 管理中心中Teams信息保护许可证报表的屏幕截图。")

    ![屏幕截图，显示 Teams 管理中心内包含标注Teams信息保护许可证报表的"更改通知"选项卡。](../media/teams-info-protection-license-report-change-notification-with-callouts.png "屏幕截图，显示 Teams 管理中心内包含标注Teams信息保护许可证报表的&quot;更改通知&quot;选项卡。")


## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看信息保护许可证报告，了解过去三个月的趋势。 |
|**2**   |应用名称将显示在选定时段内使用 [Microsoft Graph API](/graph/teams-licenses) 的所有应用的列表，这些应用具有许可证和付款要求。|
|**3**   |具有有效许可证的用户 [数](/graph/teams-licenses#required-licenses-for-modela)。  |
|**4**   |没有有效许可证的用户 [数](/graph/teams-licenses#required-licenses-for-modela)。  |
|**5**   |允许对应用进行的总 API 调用量，超出此数量后，将按每个 API 调用向应用收取使用费。 |
|**6**   |应用用于给定日期范围的总 API 调用量。 |
|**7**   |将报表导出到 CSV 文件进行脱机分析。 选择 **"导出Excel**，然后选择"下载"选项卡。选择"下载"，在报表准备就绪后下载报表。 此导出将仅导出当前选定的选项卡。|
|**8**   |选择在图表中显示或隐藏该标签的任一特定标签。 |
|**9**   |每个选项卡显示一组特定 API 的使用情况，即 [更改通知](/graph/api/resources/webhooks)、 [导出 API](/microsoftteams/export-teams-content) [和更新消息 API](/graph/api/message-update)。 选择一个选项卡以查看该 API 的使用情况详细信息。 |
|**10**   |**更改通知 API 使用情况**<li>**显示名称** - 触发更改通知的用户的显示名称。</li><li>**必需许可证** - 给定用户是否具有成功向应用发送更改通知所需的许可证。</li><li>**尝试计数** - 由于此用户而触发的更改通知的总数。</li><li>**更改通知已** 发送 - 已发送到应用的更改通知的总数。 这将小于如果用户没有有效许可证时触发的总更改通知数。</li>|
|**11**|**修补 API**<li>**显示** 名称 - 尝试更新消息的用户的显示名称。</li> <li>**必需许可证** - 给定用户是否具有成功更新消息所需的许可证。</li><li>**尝试计数** - 更新消息的尝试总数。</li><li>**消息已修补** - 已成功更新的消息总数。</li>|
|**12**|**聊天导出 API 使用情况**<li>**显示** 名称 - 尝试导出用户的聊天消息的用户的显示名称。</li><li>**必需许可证** - 给定用户是否具有成功导出消息所需的许可证。</li><li>**尝试计数** - 导出聊天消息的尝试总数。</li><li>**消息导出** - 成功导出聊天消息的尝试总数。</li> |
|**13**|**团队导出 API 使用情况**<li>**显示** 名称 - 尝试导出该团队消息的团队的显示名称。</li><li>**尝试计数** - 导出团队消息的尝试总数。</li><li>**消息导出** - 成功导出团队消息的尝试总数。</li> |


## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使用户活动Teams数据匿名，你必须是全局管理员。 这会在报表及其导出中隐藏显示名称、电子邮件Azure AD ID 等可识别信息。

1. 在Microsoft 365 管理中心，转到"**设置** \> **"** 设置"选项卡下，选择"报表 **"**。
    
2. 选择 **"** 报表"，然后选择" **显示匿名标识符"**。 此设置同时应用于管理中心Microsoft 365 管理中心使用情况Teams报表。
  
3. 选择" **保存更改"**。