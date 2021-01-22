---
title: 使用 Microsoft Teams 用户活动报告
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用活动报告来查看组织中用户如何使用 Microsoft Teams。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8428135d2d4baa40fd1957f6f5d02eb658732a6c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918668"
---
<a name="use-activity-reports-for-microsoft-teams"></a>使用 Microsoft Teams 用户活动报告 
========================================

可以使用 Microsoft 365 管理中心中的活动报告来查看组织中用户如何使用 Microsoft Teams。 例如，如果一些用户尚未使用 Microsoft Teams，他们可能不会知道如何入门，或者了解如何使用 Teams 提高工作效率和协作。 组织可以使用活动报告来决定在何处优先安排培训和沟通工作。

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>如何在"报告"仪表板中查看 Teams 报表

1. 在 [Microsoft 365 管理中心，](https://portal.office.com/adminportal/home)选择"**报告**  >  **使用情况"。**
 
2. 在" **使用情况** "页上， **选择** 一个报表，然后在报表列表中的 **Microsoft Teams** 下，选择要查看的报表。

## <a name="teams-activity-reports-that-are-available"></a>可用的 Teams 活动报告

目前可以查看两个活动报告：

- [Microsoft Teams 用户活动报告](#microsoft-teams-user-activity-report) 
- [Microsoft Teams 设备使用情况报告](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams 用户活动报告

Teams 用户活动报表提供用户在 Teams 中执行的最常用活动的视图。 这包括多少人参与频道中的聊天、多少人通过私人聊天消息进行通信，以及多少人参与通话或会议。 可以看到整个组织以及每个用户的此信息。

![管理中心中的用户活动报告的屏幕截图。](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>解释 Microsoft Teams 用户活动报告

可以通过查看"活动"和"用户"图表来了解Teams **用户** 活动。

![带编号标注的用户活动报告的屏幕截图。](media/teams-user-activity-report-with-callouts.png)

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 Teams 用户活动报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果单击报告中的特定时间范围，表 (7) 将显示 30 天的数据，截至报表生成日期 (2) 。 |
|**2**   |每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |" **活动** "视图按活动类型显示 Microsoft Teams 活动数。 活动类型是团队聊天消息、私人聊天消息、通话和会议的数量。 |
|**4**   |" **用户** "视图按活动类型显示用户数。 活动类型是团队聊天消息、私人聊天消息、通话和会议的数量。 |
|**5**   |图表上的 X 轴是特定报表的选定日期范围。 <ul><li>在 **活动图表中** ，Y 轴是指定活动的计数。</ul></li> <ul><li>在 **"用户"** 图表中，Y 轴表示参与团队聊天、私人聊天、通话或会议的用户数。</ul></li> |
|**6**   |你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如，在"活动"图表上，单击或点击频道消息、聊天消息、通话或 **会议**，仅查看与每个消息相关的信息。  更改此选项不会更改网格表中的信息。 |
|**7**   |报告时间范围为 180 (最广泛) 团队的列表。  活动计数因日期选择而异。 <br><br> 若要查看下表中的以下信息，请确保向表中添加列。 <ul><li>**用户名** 是用户的电子邮件地址。 您可以显示实际的电子邮件地址或使此字段匿名。</ul></li> <ul><li>**上次活动** (UTC) 是指用户上次参与 Microsoft Teams 活动的日期。</ul></li> <ul><li>**频道** 消息是用户于指定时段在团队聊天中发布的唯一消息数。</ul></li> <ul><li>**聊天** 消息是用户于指定时段在私人聊天中发布的唯一消息数。</ul></li> <ul><li>**调用** 是用户指定的时段内参与的调用数。</ul></li> <ul><li>**会议** 是用户指定时间段参与的联机会议数。</ul></li> <ul><li>**其他活动** 是用户参与的其他团队活动的数量，其中一些活动包括但不限于：点赞消息、应用、处理文件、搜索、跟踪团队和频道以及支持它们。</ul></li> <ul><li>**已删除** 指示团队是否被删除。 如果团队已删除，但报告时段有活动，则它将在网格中显示，已删除内容设置为 true。</ul></li> <ul><li>**删除日期** 是删除用户的日期。</ul></li> <ul><li>**分配的产品** 是分配给用户的产品列表。</ul></li>如果您的组织策略阻止您查看可识别用户信息的报告，您可以更改所有这些报表的隐私设置。 查看 Microsoft  365 管理中心预览版中的活动报告中的"如何隐藏[用户级别详细信息？"部分](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)。</ui> |
|**8**   |单击或点击 **"列** "以添加或删除表中的列。 |
|**9**   |单击或点击 **"导出** "以将报表数据导出到 Excel .csv 文件。 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果用户数少于 2，000，可以在报表本身的表中进行排序和筛选。 如果用户超过 2，000，必须导出数据，以便对报表进行筛选和排序。 

### <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 设备使用情况报告

Teams 设备使用情况报表提供有关用户如何连接到 Teams（包括移动应用）的信息。 此报表可帮助你了解组织中哪些设备很常用，以及有多少用户正在工作。

![Teams 设备使用情况报告的屏幕截图。](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>解释 Microsoft Teams 设备使用情况报告

可以通过查看"用户"和"分布"图表来了解Teams **设备** 使用情况。

![带编号标注的 Teams 设备使用情况报告的屏幕截图。](media/teams-device-usage-report-with-callouts.png)

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 Teams 设备报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果单击报告中的特定时间范围，表 (7) 将显示 30 天的数据，截至报表生成日期 (2) 。 |
|**2**   |每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |" **用户** "视图按设备类型显示每日用户数。 |
|**4**   |" **分布** "视图显示所选时段内按设备显示的用户数。  |
|**5**   | <ul><li>在 **"用户** "图表中，X 轴是报表的选定日期范围，Y 轴是按设备类型统计的用户数。</ul></li> <ul><li>在 **分布图** 上，X 轴显示用于连接到 Teams 的不同设备，Y 轴表示使用设备的用户数。</ul></li> |
|**6**   |你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如，在"分布"图表上，单击或点击Windows、Mac、Linux、Web、iOS 或 **Android，** 仅查看与每个图表相关的信息。     更改此选项不会更改网格表中的信息。 |
|**7**   |报告时间范围为 180 (最广泛) 团队的列表。  活动计数因日期选择而异。 <br><br> 若要在表中查看以下信息，请确保向表中添加列。 <ul><li>**用户名** 是用户的电子邮件地址。 您可以显示实际的电子邮件地址或使此字段匿名。</ul></li> <ul><li>**上次活动 (UTC)** 是指用户上次参与 Teams 活动的日期。</ul></li> <ul><li>**已删除** 指示团队是否被删除。 如果团队已删除，但报告时段有活动，则它将在网格中显示，已删除内容设置为 true。</ul></li><ul><li>**删除日期** 是删除用户的日期。</ul></li> <ul><li>**如果用户**  在基于 Windows 的电脑上的 Teams 桌面客户端中处于活动状态，则选择 Windows。</ul></li> <ul><li>**如果用户在 macOS** 计算机的 Teams 桌面客户端中处于活动状态，则选择 Mac。</ul></li>  <ul><li>**如果用户** 在 Linux 计算机的 Teams 桌面客户端中处于活动状态，则选择 Linux。</ul></li>   <ul><li>**如果用户** 在 Teams Web 客户端上处于活动状态，则选择 Web。</ul></li> <ul><li>**如果用户在适用于 iOS** 的 Teams 移动客户端上处于活动状态，则选择 iOS。</ul></li> <ul><li>**如果用户在**  Android 版 Teams 移动客户端上处于活动状态，则选择 Android 手机。</ul></li></li> <ui>如果您的组织策略阻止您查看可识别用户信息的报告，您可以更改所有这些报表的隐私设置。查看 Microsoft  365 管理中心预览版中的活动报告中的"如何隐藏[用户级别详细信息？"部分](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)。</ui> |
|**8**   |单击或点击 **"列** "以添加或删除表中的列。 |
|**9**   |单击或点击 **"导出** "以将报表数据导出到 Excel .csv 文件。 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果用户数少于 2，000，可以在报表本身的表中进行排序和筛选。 如果用户超过 2，000，必须导出数据，以便对报表进行筛选和排序。 

## <a name="who-can-access-the-teams-activity-reports"></a>谁可以访问 Teams 活动报告

分配有以下项的用户可以访问活动报告：

- 全局管理员角色
- Exchange、Skype for Business 或 SharePoint (产品特定的管理员) 
- 报告读取者角色

### <a name="reports-reader-role"></a>报告读取者角色

可以将"报告读者"角色分配给没有管理员权限，但负责推动 Teams 的采用或跟踪许可证使用情况的人。 若要了解如何分配角色，请阅读"使用 Azure Active Directory 向用户分配管理员和管理员[上的角色"。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="other-information-on-the-reports-dashboard"></a>"报表"仪表板上的其他信息

### <a name="at-a-glance-activity-widget"></a>一目了然的活动小组件

"报表"仪表板在一目了然的活动小组件中包含 Teams 的使用情况数据，通过该小组件，可跨产品查看用户如何使用 Microsoft 365 或 Office 365 中其他各种服务进行通信和协作。

![Teams 概览活动小组件屏幕截图。](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Teams 活动卡片

"报告"仪表板上的 Teams 活动卡片提供 Teams 中活动的概述，包括活动用户数，以便可以快速了解使用该服务的用户数。 单击仪表板上的活动卡片可进入 Teams 用户活动报告。 

![Teams 活动卡片的屏幕截图。](media/teams-activity-card.png)
