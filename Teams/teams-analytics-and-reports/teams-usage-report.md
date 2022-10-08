---
title: Microsoft Teams 使用情况报告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在 Microsoft Teams 管理中心使用 Teams 使用情况报告来概要了解组织中的 Teams 活动。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e280a32c765c989ef5d6081388ad76701be6ab1
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033790"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams 使用情况报告

通过 Microsoft Teams 管理中心的 Teams 使用情况报告，可概要了解 Teams 中的活跃用户和频道数等使用活动，从而能快速查看组织中有多少用户正在使用 Teams 进行通信和协作。 你可查看团队的使用情况信息，包括每个团队中的活跃用户和频道数量、来宾数和消息数。

使用有关内部和外部用户的更多附加信息，现在可以在团队中的内部和外部 [共享渠道](/Teams/shared-channels.md) 中度量协作。 例如，活动共享频道和团队中的外部活动用户等指标将帮助管理员跨团队中的共享渠道衡量协作。

## <a name="view-the-usage-report"></a>查看使用情况报告

你必须是全局管理员、全局读者或 Teams 服务管理员才能在 Teams 管理中心查看报表。 请参阅 [Teams 管理员角色管理 Teams](../using-admin-roles.md) ，了解管理员角色和权限。

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“分析”&报告** > **使用情况报告**。 在 **“查看报表** ”选项卡上的 **“报表**”下，选择 **“Teams 使用情况**”。
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    ![Teams 管理中心中带有标注的 Teams 使用情况报告的屏幕截图。](../media/teams-reports-teams-usage-with-callouts2.png "Teams 管理中心中带有标注的 Teams 使用情况报告的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 Teams 使用情况活动报告，了解过去 7 天、30 天、90 天和 180 天的趋势。 |
|**2**   |每个报表包含此报表的生成日期。 报告通常反映活动时间的 24-48 小时延迟。 |
|**3**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴表示活跃项目或活动的计数。</li> </ul>将鼠标悬停在表示给定日期中某项目或活动的点可查看该项目或活动在该给定日期的实例数量。|
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击  **内部活动用户**、 **活动来宾**、  **活动频道**、 **帖子** 等，仅查看与每个用户相关的信息。 更改此选项不会更改表格中的信息。 |
|**5**   |表格按团队细分显示了使用情况。 <ul><li>**团队名称** 是团队的显示名称。 可以单击团队名称，转到 Microsoft Teams 管理中心的团队设置页面。 </li> <li>**团队 ID** 是唯一的团队标识符。 </li> <li>**类型** 是指团队是私人团队还是公共团队。</li> <li>**内部活动用户** 是活动用户的数量，包括在指定时间段内在该团队中执行操作的来宾。 <br/>内部用户和来宾位于同一租户中，但不同。</li><li>**活动来宾** 是在指定时间段内在该团队中执行操作的来宾数。</li> <li>**外部活动用户** (新) 是来自外部组织的活动用户数，这些用户在该团队的资源（例如团队中的共享频道）中执行操作。 <br/> 外部用户在不同的租户中有自己的标识，与来宾帐户不同。</li><li>**活动频道** 是团队中在指定时间段内至少有一个活动用户的频道数。 这包括专用、公共和共享频道。 </li><li> (新) 的活动 **共享通道** 是团队中在指定时间段内至少有一个活动内部或外部用户的共享频道数。 </li> <li>**组织会议总数** 是用户在指定时间段内组织的一次性计划、定期、计划外和未分类会议的总和。 </li><li>**帖子** 是指定时间段内频道中所有帖子的数目。</li> <li>**答复** 是指定时间段内通道中所有答复消息的数目。</li> <li>**提及** 是指定时间段内消息中使用的所有提及数。</li><li>**反应** 是指定时间段内对消息的所有反应数。</li><li>**紧急消息** 是指定时间段内所有紧急消息的数量。</li><li>**频道消息** 是团队用户在指定时间段内在团队聊天中发布的唯一消息数。</li> </li> </ul>请注意，如果团队不再存在，则该名称在表中显示为“--”。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**6**   |选择“**编辑列**”可在表格中添加或删除列。|
|**7**   |将报表导出到 CSV 文件以进行脱机分析。 选择 **“导出到 Excel”** 图标，报表将在浏览器中下载。|
|**8** |顶部图中表示的时序数据显示为整个租户聚合的不同使用指标|
|**9** |下半部分表示的表格数据显示每个团队聚合的不同使用指标|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]


## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使 Teams 用户活动报告中的数据匿名，必须是全局管理员。 全局管理员可以使用 MD5 哈希 (隐藏可识别信息) ，例如报表中的显示名称、组名称、电子邮件和 AAD ID 及其导出。

1. 在Microsoft 365 管理中心中，转到 **“设置** > **组织设置”**，然后在 **“服务**”选项卡下选择 **“报表**”。
    
2. 选择 **“报** 表”，然后在 **所有报表中选择“显示隐藏的用户、组和网站名称**”。 此设置同时应用于Microsoft 365 管理中心和 Teams 管理中心的使用情况报告。
  
3. 选择 **“保存更改**”。

> [!NOTE]
> 启用此设置将取消识别 [Teams 用户活动报表](user-activity-report.md)、 [Teams 设备使用情况报告](device-usage-report.md)和 [Teams 使用情况报](teams-usage-report.md)表中的用户、组和站点名称信息。 从 2021 年 9 月 1 日开始，默认情况下，我们为每个人启用此设置，作为我们持续承诺的一部分，以帮助保护重要信息并使公司能够支持其本地隐私法。 
>
>此设置也适用于 Microsoft 365 管理中心、Microsoft Graph 和 Power BI 中的 Microsoft 365 使用情况报告。

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
