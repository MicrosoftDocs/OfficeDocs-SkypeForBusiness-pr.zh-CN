---
title: Microsoft Teams 应用使用情况报表
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在 Microsoft Teams 管理中心使用 Teams 应用使用情况报告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29e51e91cdc42000350a48dd0d83225e7791aea6
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460592"
---
# <a name="microsoft-teams-app-usage-report"></a><span data-ttu-id="c8d77-103">Microsoft Teams 应用使用情况报表</span><span class="sxs-lookup"><span data-stu-id="c8d77-103">Microsoft Teams app usage report</span></span>

<span data-ttu-id="c8d77-104">Microsoft Teams 管理中心中的 Teams 应用使用情况报告提供有关用户在 Teams 中使用哪些应用的信息。</span><span class="sxs-lookup"><span data-stu-id="c8d77-104">The Teams app usage report in the Microsoft Teams admin center provides you with information about which apps users are using in Teams.</span></span>  

## <a name="view-the-app-usage-report"></a><span data-ttu-id="c8d77-105">查看应用使用情况报表</span><span class="sxs-lookup"><span data-stu-id="c8d77-105">View the App Usage report</span></span>

1.  <span data-ttu-id="c8d77-106">在管理中心的左侧导航栏中，单击 <https://admin.teams.microsoft.com> **"分析**"& \> **报告使用情况报告**。</span><span class="sxs-lookup"><span data-stu-id="c8d77-106">In the left navigation of the admin center at <https://admin.teams.microsoft.com>, click **Analytics & reports** \> **Usage reports**.</span></span> <span data-ttu-id="c8d77-107">在"**查看报表"** 选项卡上的 **"** 报表"下，选择 **"应用使用情况"。**</span><span class="sxs-lookup"><span data-stu-id="c8d77-107">On the **View reports** tab, under **Report**, select **Apps Usage**.</span></span>

     :::image type="content" source="media/app-usage-report1.png" alt-text=""使用情况报告"菜单项的屏幕截图":::

2.  <span data-ttu-id="c8d77-109">在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。</span><span class="sxs-lookup"><span data-stu-id="c8d77-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

      :::image type="content" source="media/app-usage-report2.png" alt-text=""应用使用情况"报表的屏幕截图":::

## <a name="interpret-the-report"></a><span data-ttu-id="c8d77-111">解释报告</span><span class="sxs-lookup"><span data-stu-id="c8d77-111">Interpret the report</span></span>

|<span data-ttu-id="c8d77-112">标注</span><span class="sxs-lookup"><span data-stu-id="c8d77-112">Callout</span></span> |<span data-ttu-id="c8d77-113">说明</span><span class="sxs-lookup"><span data-stu-id="c8d77-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="c8d77-114">**1**</span><span class="sxs-lookup"><span data-stu-id="c8d77-114">**1**</span></span>   |<span data-ttu-id="c8d77-115">可以查看 Teams 应用使用情况报告，了解过去 7、30 或 90 天的趋势。</span><span class="sxs-lookup"><span data-stu-id="c8d77-115">The Teams Apps usage report can be viewed for trends over the last 7, 30 or 90 days.</span></span> |
|<span data-ttu-id="c8d77-116">**2**</span><span class="sxs-lookup"><span data-stu-id="c8d77-116">**2**</span></span>   |<span data-ttu-id="c8d77-117">每个报表都有一个生成报告的日期。</span><span class="sxs-lookup"><span data-stu-id="c8d77-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="c8d77-118">报告通常反映从打开应用起 24 小时的延迟。</span><span class="sxs-lookup"><span data-stu-id="c8d77-118">The reports usually reflect a 24-hour latency from the time an app was opened.</span></span> <br><br>![显示日期范围的"应用使用情况"报表的屏幕截图](media/app-usage-report3.png)|
|<span data-ttu-id="c8d77-120">**3**</span><span class="sxs-lookup"><span data-stu-id="c8d77-120">**3**</span></span>    | <ul><li><span data-ttu-id="c8d77-121">图表上的 X 轴是特定报表的选定日期范围。</span><span class="sxs-lookup"><span data-stu-id="c8d77-121">The X axis on the charts is the selected date range for the specific report.</span></span></li><li><span data-ttu-id="c8d77-122">Y 轴表示在图表中悬停在给定日期的用户数，这些用户至少打开过一次应用，通过这样做可被视为活动用户，并计入鼠标悬停时看到的总用户数。</span><span class="sxs-lookup"><span data-stu-id="c8d77-122">The Y axis is the number of users who for the given day hovered over in chart, those users have opened an app at least once and by doing so are considered an Active User and accrue towards the total seen on mouse hover over.</span></span></li></ul>|
|<span data-ttu-id="c8d77-123">**4**</span><span class="sxs-lookup"><span data-stu-id="c8d77-123">**4**</span></span>   |<span data-ttu-id="c8d77-124">将鼠标悬停在表示给定日期的应用使用情况的点上，以查看该给定日期该应用的活动用户总数的实例数。</span><span class="sxs-lookup"><span data-stu-id="c8d77-124">Hover over the dot representing an Apps Usage on a given date to see the number of instances of that App’s Total Active Users on that given date.</span></span>  |
|<span data-ttu-id="c8d77-125">**5**</span><span class="sxs-lookup"><span data-stu-id="c8d77-125">**5**</span></span>   |<span data-ttu-id="c8d77-126">将包含所有应用，但通过选择"筛选器"图标，可以使用其他筛选器。</span><span class="sxs-lookup"><span data-stu-id="c8d77-126">All Apps will be included but by choosing the Filter icon, additional filters are available.</span></span>  |
|<span data-ttu-id="c8d77-127">**6**</span><span class="sxs-lookup"><span data-stu-id="c8d77-127">**6**</span></span>   |<span data-ttu-id="c8d77-128">下表按应用名称提供了活动用户和团队的细分。</span><span class="sxs-lookup"><span data-stu-id="c8d77-128">The table gives you a breakdown of active users and teams by App name.</span></span><br><ul><li><span data-ttu-id="c8d77-129">**应用** 名称显示名称 Teams 中使用的应用的名称。</span><span class="sxs-lookup"><span data-stu-id="c8d77-129">**App name** is the display name of the app used in Teams.</span></span></li><li><span data-ttu-id="c8d77-130">**活动** 用户是在指定的时段内至少打开应用一次的用户数。</span><span class="sxs-lookup"><span data-stu-id="c8d77-130">**Active users** is the number of users who opened the app at least once during the specified time period.</span></span></li><li><span data-ttu-id="c8d77-131">**应用类型** 是"Microsoft"或"第三方"的静态值。</span><span class="sxs-lookup"><span data-stu-id="c8d77-131">**App type** is a static value of either “Microsoft” or “Third Party”.</span></span></li><li><span data-ttu-id="c8d77-132">**活动团队** 是团队中至少一个成员在指定的时段内打开应用的团队数。</span><span class="sxs-lookup"><span data-stu-id="c8d77-132">**Active teams** is the number of teams who have opened the App by at least one member of the team and during the specified time periods.</span></span></li><li><span data-ttu-id="c8d77-133">**发布者** 是应用的软件发布者。</span><span class="sxs-lookup"><span data-stu-id="c8d77-133">**Publisher** is the software publisher of the app.</span></span></li><li><span data-ttu-id="c8d77-134">**版本** 是应用的软件版本，来自应用发布者。</span><span class="sxs-lookup"><span data-stu-id="c8d77-134">**Version** is the software version of the app, from the app publisher.</span></span></li></ul><span data-ttu-id="c8d77-135"><b> 注意：</b> 目前，仅针对频道中使用的应用计算"活动用户"和"活动团队"。</span><span class="sxs-lookup"><span data-stu-id="c8d77-135"><b> Note :</b> Currently, 'Active users' and 'Active teams' are calculated for apps used in channels only.</span></span>     

<br><span data-ttu-id="c8d77-136">![应用使用情况报表的屏幕截图| | ](media/app-usage-report4.png) **7 |**  选择 **"编辑** 列"以添加或删除表中的列。</span><span class="sxs-lookup"><span data-stu-id="c8d77-136">![Screenshot of an Apps Usage report](media/app-usage-report4.png)  | |**7**  |Select **Edit columns** to add or remove columns in the table.</span></span><br><br><span data-ttu-id="c8d77-137">!["编辑列"页的 ](media/app-usage-report5.png)  屏幕截图 **| |8**  |可以将报表导出到 CSV 文件进行脱机分析。</span><span class="sxs-lookup"><span data-stu-id="c8d77-137">![Screenshot of the Edit columns page](media/app-usage-report5.png)  | |**8**  |You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="c8d77-138">单击 **"导出到 Excel"，** 然后在"下载 **"选项卡** 上单击"下载"，在报表准备就绪后下载报表。</span><span class="sxs-lookup"><span data-stu-id="c8d77-138">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="c8d77-139">!["下载"页的 ](media/app-usage-report7.png)  屏幕截图 **| |9**   |在 Excel 中查看报表时，还将看到一个 **ID** 列，它表示应用 ID。</span><span class="sxs-lookup"><span data-stu-id="c8d77-139">![Screenshot of Downloads page](media/app-usage-report7.png)  | |**9**   |When you view the report in Excel, you'll also see an **Id** column, which represents the app ID.</span></span> <span data-ttu-id="c8d77-140">团队 ID 通常是字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="c8d77-140">A team ID is typically an alphanumeric string.</span></span> <span data-ttu-id="c8d77-141">如果 **ID** 列显示为 \*\*\n\*\*\*\*，这意味着用户请求删除其信息。</span><span class="sxs-lookup"><span data-stu-id="c8d77-141">If the **Id** column shows as \*\*\n\*\*\*\*, this means that a user requested their information to be deleted.</span></span><br><span data-ttu-id="c8d77-142">![下载的 Excel 报表的屏幕截图](media/app-usage-report8.png)  |</span><span class="sxs-lookup"><span data-stu-id="c8d77-142">![Screenshot of the downloaded Excel report](media/app-usage-report8.png)  |</span></span>

## <a name="related-topics"></a><span data-ttu-id="c8d77-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="c8d77-143">Related topics</span></span>

- [<span data-ttu-id="c8d77-144">Teams 分析和报告</span><span class="sxs-lookup"><span data-stu-id="c8d77-144">Teams analytics and reporting</span></span>](teams-reporting-reference.md)