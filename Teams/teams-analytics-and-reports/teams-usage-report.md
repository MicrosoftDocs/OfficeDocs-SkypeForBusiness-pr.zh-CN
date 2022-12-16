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
ms.openlocfilehash: ef5011ebbfbcbb62332c1fd9a43b19ce2b25b0ff
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436688"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams 使用情况报告

通过 Microsoft Teams 管理中心的 Teams 使用情况报告，可概要了解 Teams 中的活跃用户和频道数等使用活动，从而能快速查看组织中有多少用户正在使用 Teams 进行通信和协作。 你可查看团队的使用情况信息，包括每个团队中的活跃用户和频道数量、来宾数和消息数。

通过更多有关内部和外部用户的信息，你现在可以衡量团队中内部和外部 [共享频道](/Teams/shared-channels.md) 内的协作。 例如，团队中的活动共享频道和外部活动用户等指标可帮助管理员衡量团队中共享频道之间的协作。

## <a name="view-the-usage-report"></a>查看使用情况报告

你必须是全局管理员、全局读取者和报表读取者，或者是 Teams 服务管理员才能在 Teams 管理中心查看报表。 请参阅 [Teams 管理员角色管理 Teams](../using-admin-roles.md) ，了解管理员角色和权限。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击“**分析”&报告** > **使用情况报告**。 在“ **查看报表** ”选项卡上的“ **报表**”下，选择“ **Teams 使用情况**”。
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    ![Teams 管理中心中 Teams 使用情况报告的屏幕截图，其中包含标注。](../media/teams-reports-teams-usage-with-callouts2.png "Teams 管理中心中 Teams 使用情况报告的屏幕截图，其中包含标注")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 Teams 使用情况活动报告，了解过去 7 天、30 天、90 天和 180 天的趋势。 |
|**2**   |每个报表包含此报表的生成日期。 报告通常反映活动时间延迟 24-48 小时。 |
|**3**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴表示活跃项目或活动的计数。</li> </ul>将鼠标悬停在表示给定日期中某项目或活动的点可查看该项目或活动在该给定日期的实例数量。|
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击“  **内部活动用户**”、“ **活动来宾**”、“  **活动频道**”、“ **帖子**”等，仅查看与每个用户相关的信息。 更改此选项不会更改表格中的信息。 |
|**5**   |表格按团队细分显示了使用情况。 <ul><li>**团队名称** 是团队的显示名称。 可以单击团队名称转到Microsoft Teams 管理中心中的团队设置页。 </li> <li>**团队 ID** 是唯一的团队标识符。 </li> <li>**类型** 是指团队是私人团队还是公共团队。</li> <li>**内部活动用户** 数是活动用户的数量，包括在该团队中执行指定时间段内操作的来宾。 <br/>内部用户和来宾位于同一租户中，但不相同。</li><li>**活动来宾** 是在指定时间段内在该团队中执行操作的来宾数。</li> <li>**外部活动用户** (新) 是外部组织在资源中在该团队中执行操作（例如团队中的共享频道）的活动用户数。 <br/> 外部用户在不同的租户中有自己的标识，与来宾帐户不同。</li><li>**活动频道** 是团队中在指定时间段内至少有一个活动用户的频道数。 这包括专用、公共和共享频道。 </li><li>**活动共享频道** (新) 是团队中在指定时间段内至少有一个活动内部或外部用户的共享频道数。 </li> <li>**组织会议总数** 是用户在指定时间段内组织的一次计划、定期、计划外和未分类会议的总和。 </li><li>**帖子** 是指定时间段内频道中所有帖子消息的数量。</li> <li>**答复** 是指定时间段内通道中所有答复消息的数量。</li> <li>**提及** 是指定时间段内消息中使用的所有提及数。</li><li>**反应** 是指定时间段内对消息的所有反应数。</li><li>**紧急消息** 是指定时间段内所有紧急消息的数量。</li><li>**频道消息** 是团队用户在指定时间段内在团队聊天中发布的唯一消息数。</li> </li> </ul>请注意，如果团队不再存在，则名称在表中显示为“--”。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**6**   |选择“**编辑列**”可在表格中添加或删除列。|
|**7**   |将报表导出到 CSV 文件以供脱机分析。 选择“ **导出到 Excel** ”图标，报表将在浏览器中下载。|
|**8** |顶部图中表示的时序数据显示了针对整个租户聚合的不同使用情况指标|
|**9** |下半部分表示的表格数据显示了每个团队聚合的不同使用情况指标|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]


## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使 Teams 用户活动报告中的数据匿名，你必须是全局管理员。 全局管理员可以在报表及其导出中使用 MD5 哈希) 隐藏 (身份信息，例如显示名称、组名称、电子邮件和 AAD ID。

1. 在“Microsoft 365 管理中心”中，转到 **“设置** > **组织设置”**，然后在“**服务**”选项卡下，选择“**报表**”。
    
2. 选择“ **报表**”，然后选择“ **在所有报表中显示隐藏的用户、组和站点名称**”。 此设置将应用于 Microsoft 365 管理中心 中的使用情况报告以及 Teams 管理中心。
  
3. 选择 **“保存更改**”。

> [!NOTE]
> 启用此设置将取消标识 [Teams 用户活动报表](user-activity-report.md)、 [Teams 设备使用情况报告](device-usage-report.md)和 [Teams 使用情况报告中](teams-usage-report.md)的用户、组和站点名称信息。 从 2021 年 9 月 1 日开始，此设置默认为每个人启用，这是我们持续承诺的一部分，以帮助保护重要信息并使公司能够支持其本地隐私法。 
>
>此设置也适用于 Microsoft 365 管理中心、Microsoft Graph 和 Power BI 中的 Microsoft 365 个使用情况报告。

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
