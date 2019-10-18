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
description: 了解如何使用活动报表查看组织中的用户使用的是 Microsoft 团队的方式。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f568dfdf51cb34da340e8192336f4c0c8cca19a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37565633"
---
<a name="use-activity-reports-for-microsoft-teams"></a>使用 Microsoft Teams 用户活动报告 
========================================

你可以使用 Microsoft 365 管理中心中的活动报表查看组织中的用户使用的是 Microsoft 团队的方式。 例如，如果某些用户尚不使用 Microsoft 团队，他们可能不知道如何开始使用或了解如何使用团队提高工作效率和协作性。 组织可以使用活动报告来决定在何处优先安排培训和沟通工作。

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>如何在 "报表" 仪表板中查看团队报表

1. 在[Microsoft 365 管理中心](https://portal.office.com/adminportal/home)，选择 "**报告** > **使用情况**"。
 
2. 在 "**使用情况**" 页面上，选择 "**选择报表**"，然后在报表列表中的 " **Microsoft 团队**" 下，选择要查看的报表。

## <a name="teams-activity-reports-that-are-available"></a>可用的团队活动报表

当前有两个活动报表可以查看：

- [Microsoft Teams 用户活动报告](#microsoft-teams-user-activity-report) 
- [Microsoft Teams 设备使用情况报告](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams 用户活动报告

"团队用户活动" 报表为你提供用户在团队中执行的最常见活动的视图。 这包括在频道中参与聊天的人数、通过私人聊天消息进行通信的次数以及参与通话或会议的次数。 你可以查看整个组织和每个个人用户的此信息。

![管理中心中的用户活动报表的屏幕截图。](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>解释 "Microsoft 团队用户活动" 报表

你可以查看 "**活动**" 和 "**用户**" 图表，了解团队用户活动。

![带有编号标注的用户活动报表的屏幕截图。](media/teams-user-activity-report-with-callouts.png)

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 "团队用户活动" 报表，了解过去7天、30天、90天或180天的趋势。 但是，如果你单击报表中的特定时间范围，表（7）将显示30天内的数据（最高为日期（2）的时间，表示生成报表的时间）。 |
|**2**   |每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |**活动**视图显示按活动类型显示的 Microsoft 团队活动数。 活动类型包括团队聊天消息、私人聊天消息、通话和会议的数量。 |
|**4**   |"**用户**" 视图显示活动类型的用户数。 活动类型包括团队聊天消息、私人聊天消息、通话和会议的数量。 |
|**5**   |图表上的 X 轴表示特定报表的选定日期范围。 <ul><li>在 "**活动**" 图表上，Y 轴是指定活动的计数。</ul></li> <ul><li>在 "**用户**" 图表上，Y 轴代表参与团队聊天、私人聊天、通话或会议的用户数。</ul></li> |
|**6**   |你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如，在 "**活动**" 图表上，单击或点击 "**频道消息**"、"**聊天消息**"、"**通话**" 或 "**会议**"，以仅查看与每种信息相关的信息。 更改此选择不会更改网格表中的信息。 |
|**7**   |跨越最宽（180天）报告时间范围的活动团队的列表。  活动计数将根据选择的日期而有所不同。 <br><br> 若要查看表的以下信息，请确保将列添加到表中。 <ul><li>**用户名**是用户的电子邮件地址。 您可以显示实际的电子邮件地址或将此域设置为匿名。</ul></li> <ul><li>**上次活动日期（UTC）** 指用户参与 Microsoft 团队活动的最后日期。</ul></li> <ul><li>**信道消息**表示在指定时间段内用户在团队聊天中发布的唯一消息数。</ul></li> <ul><li>"**聊天消息**" 表示指定时间段内用户在私人聊天中发布的唯一消息数。</ul></li> <ul><li>"**通话**" 表示在指定时间段内用户参与的通话次数。</ul></li> <ul><li>"**会议**" 表示用户在指定时间段内参与的联机会议数。</ul></li> <ul><li>"**其他活动**" 指用户的其他团队活动数，其中包括（但不限于）：为邮件、应用、文件、搜索、关注团队和频道以及收藏。</ul></li> <ul><li>"**已删除**" 表示团队是否已删除。 如果团队已删除，但在报告期间内有活动，则它将显示在 "已删除" 设置为 true 的网格中。</ul></li> <ul><li>"**删除日期**" 表示用户已被删除的日期。</ul></li> <ul><li>"**分配的产品**" 表示分配给用户的产品列表。</ul></li>如果你的组织的策略阻止你查看用户信息可标识的报表，你可以更改所有这些报表的隐私设置。 查看[Microsoft 365 管理中心预览版中的活动报表中](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)的 "**如何隐藏用户级别的详细信息"** 部分。</ui> |
|**个**   |单击或点击 "**列**" 以添加或删除表中的列。 |
|**db-9**   |单击或点击 "**导出**"，将报告数据导出到 Excel .csv 文件。 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果您的用户少于2000，则可以在报表本身的表中对其进行排序和筛选。 如果您有超过2000的用户，则需要导出数据以筛选和排序报表。 

### <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 设备使用情况报告

"团队设备使用情况" 报表提供有关用户如何连接到团队（包括移动应用）的信息。 此报告可帮助你了解你的组织中受欢迎的设备以及有多少用户可以在旅途中工作。

![团队设备使用情况报告的屏幕截图。](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>解释 Microsoft 团队设备使用情况报告

通过查看 "**用户**" 和 "**分布**" 图表，可了解团队设备使用情况。

![带有编号标注的团队设备使用情况报表的屏幕截图。](media/teams-device-usage-report-with-callouts.png)

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 "团队设备" 报表，了解过去7天、30天、90天或180天的趋势。 但是，如果你单击报表中的特定时间范围，表（7）将显示30天内的数据（最高为日期（2）的时间，表示生成报表的时间）。 |
|**2**   |每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。 |
|**3**   |"**用户**" 视图显示按设备类型列出的每日用户数。 |
|**4**   |"**分布**" 视图显示选定时间段内按设备列出的用户数。  |
|**5**   | <ul><li>在 "**用户**" 图表中，X 轴表示报表的选定日期范围，Y 轴表示按设备类型的用户数。</ul></li> <ul><li>在 "**分布**" 图表中，X 轴显示用于连接团队的不同设备，Y 轴表示使用该设备的用户数。</ul></li> |
|**6**   |你可以通过单击图例上的项目筛选你在图表上看到的系列。 例如，在**分布**图表上，单击或点击 " **Windows**、 **Mac**、 **Web**、 **iOS**" 或 " **Android** "，以仅查看与每个相关联的信息。 更改此选择不会更改网格表中的信息。 |
|**7**   |跨越最宽（180天）报告时间范围的活动团队的列表。  活动计数将根据选择的日期而有所不同。 <br><br> 若要查看表中的以下信息，请确保将列添加到表中。 <ul><li>**用户名**是用户的电子邮件地址。 您可以显示实际的电子邮件地址或将此域设置为匿名。</ul></li> <ul><li>**上次活动日期（UTC）** 指用户参与团队活动的最后日期。</ul></li> <ul><li>"**已删除**" 表示团队是否已删除。 如果团队已删除，但在报告期间内有活动，则它将显示在 "已删除" 设置为 true 的网格中。</ul></li><ul><li>"**删除日期**" 表示用户已被删除的日期。</ul></li> <ul><li>如果用户在基于 Windows 的计算机上的团队桌面客户端中处于活动状态，则选择 " **Windows** "。</ul></li> <ul><li>如果用户在 macOS 计算机上的团队桌面客户端中处于活动状态，则会选择**Mac** 。</ul></li>  <ul><li>如果用户在团队 Web 客户端上处于活动状态，则会选中 " **web** "。</ul></li> <ul><li>如果用户在 iOS 的团队移动客户端上处于活动状态，则选择**ios** 。</ul></li> <ul><li>如果用户在 Android 的团队移动客户端上处于活动状态，则选择 " **Android 手机**"。</ul></li></li> <ui>如果你的组织的策略阻止你查看用户信息可标识的报表，你可以更改所有这些报表的隐私设置。查看[Microsoft 365 管理中心预览版中的活动报表中](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)的 "**如何隐藏用户级别的详细信息"** 部分。</ui> |
|**个**   |单击或点击 "**列**" 以添加或删除表中的列。 |
|**db-9**   |单击或点击 "**导出**"，将报告数据导出到 Excel .csv 文件。 此操作会导出所有用户数据并允许你执行简单的排序和筛选以进行更详细的分析。 如果您的用户少于2000，则可以在报表本身的表中对其进行排序和筛选。 如果您有超过2000的用户，则需要导出数据以筛选和排序报表。 

## <a name="who-can-access-the-teams-activity-reports"></a>哪些人可以访问团队活动报表

已分配的用户可以访问活动报表：

- Office 365 全局管理员角色
- 特定于产品的管理员角色（Exchange、Skype for Business 或 SharePoint）
- 报表读者角色

### <a name="reports-reader-role"></a>报表读者角色

你可以将*报表读者*角色分配给你希望其访问这些报表的非 IT 员工。 通过将此角色分配给培训经理或业务利益干系人，你可以确保他们有权访问有助于推动和跟踪团队采纳的见解。

## <a name="other-information-on-the-reports-dashboard"></a>报表仪表板上的其他信息

### <a name="at-a-glance-activity-widget"></a>一览式活动小组件

"报表" 仪表板在 "一览式活动" 小组件中包含来自团队的使用数据，这使你可以通过使用 Office 365 中的其他各种服务来与用户进行通信和协作的交叉产品视图。

!["团队一览" 活动小组件的屏幕截图。](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>团队活动卡

"报表" 仪表板上的 "团队" 活动卡提供了团队中活动的概述，包括活动用户数，以便您可以快速了解使用该服务的用户数。 单击仪表板上的活动卡将转到 "团队用户活动" 报表。 

![团队活动卡的屏幕截图。](media/teams-activity-card.png)
