---
title: Microsoft 团队应用使用情况报表
author: LolaJacobsen
ms.author: lolaj
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
description: 了解如何使用 Microsoft 团队管理中心中的 "团队应用使用情况" 报表。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 565a3cb28b73a37162947859effc6ec154b59258
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938201"
---
# <a name="microsoft-teams-app-usage-report"></a><span data-ttu-id="8b2da-103">Microsoft 团队应用使用情况报表</span><span class="sxs-lookup"><span data-stu-id="8b2da-103">Microsoft Teams app usage report</span></span>

<span data-ttu-id="8b2da-104">Microsoft 团队管理中心中的 "团队应用使用情况" 报表向你提供有关用户在团队中使用哪些应用的信息。</span><span class="sxs-lookup"><span data-stu-id="8b2da-104">The Teams app usage report in the Microsoft Teams admin center provides you with information about which apps users are using in Teams.</span></span>  

## <a name="view-the-app-usage-report"></a><span data-ttu-id="8b2da-105">查看应用使用情况报表</span><span class="sxs-lookup"><span data-stu-id="8b2da-105">View the App Usage report</span></span>

1.  <span data-ttu-id="8b2da-106">在管理中心的左侧导航中 <https://admin.teams.microsoft.com> ，单击 "**分析 & 报告** \> **使用情况报告**"。</span><span class="sxs-lookup"><span data-stu-id="8b2da-106">In the left navigation of the admin center at <https://admin.teams.microsoft.com>, click **Analytics & reports** \> **Usage reports**.</span></span> <span data-ttu-id="8b2da-107">在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 "**应用使用情况**"。</span><span class="sxs-lookup"><span data-stu-id="8b2da-107">On the **View reports** tab, under **Report**, select **Apps Usage**.</span></span>

     :::image type="content" source="media/app-usage-report1.png" alt-text=""使用情况报告" 菜单项的屏幕截图":::

2.  <span data-ttu-id="8b2da-109">在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。</span><span class="sxs-lookup"><span data-stu-id="8b2da-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

      :::image type="content" source="media/app-usage-report2.png" alt-text="应用使用情况报表的屏幕截图":::

## <a name="interpret-the-report"></a><span data-ttu-id="8b2da-111">解释报告</span><span class="sxs-lookup"><span data-stu-id="8b2da-111">Interpret the report</span></span>

|<span data-ttu-id="8b2da-112">标注</span><span class="sxs-lookup"><span data-stu-id="8b2da-112">Callout</span></span> |<span data-ttu-id="8b2da-113">说明</span><span class="sxs-lookup"><span data-stu-id="8b2da-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="8b2da-114">**1**</span><span class="sxs-lookup"><span data-stu-id="8b2da-114">**1**</span></span>   |<span data-ttu-id="8b2da-115">可以查看 "团队应用使用情况" 报表，了解过去7、30或90天的趋势。</span><span class="sxs-lookup"><span data-stu-id="8b2da-115">The Teams Apps usage report can be viewed for trends over the last 7, 30 or 90 days.</span></span> |
|<span data-ttu-id="8b2da-116">**2**</span><span class="sxs-lookup"><span data-stu-id="8b2da-116">**2**</span></span>   |<span data-ttu-id="8b2da-117">每个报表都具有生成报表的日期。</span><span class="sxs-lookup"><span data-stu-id="8b2da-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="8b2da-118">报告通常反映从打开应用的时间起的24小时延迟。</span><span class="sxs-lookup"><span data-stu-id="8b2da-118">The reports usually reflect a 24-hour latency from the time an app was opened.</span></span> <br><br>![显示日期范围的应用使用情况报表的屏幕截图](media/app-usage-report3.png)|
|<span data-ttu-id="8b2da-120">**3**</span><span class="sxs-lookup"><span data-stu-id="8b2da-120">**3**</span></span>    | <ul><li><span data-ttu-id="8b2da-121">图表上的 X 轴表示特定报表的选定日期范围。</span><span class="sxs-lookup"><span data-stu-id="8b2da-121">The X axis on the charts is the selected date range for the specific report.</span></span></li><li><span data-ttu-id="8b2da-122">Y 轴表示在图表中悬停的给定日的用户数，这些用户至少已打开一个应用一次，这样做会被视为活动用户，并计入鼠标悬停时看到的总数。</span><span class="sxs-lookup"><span data-stu-id="8b2da-122">The Y axis is the number of users who for the given day hovered over in chart, those users have opened an app at least once and by doing so are considered an Active User and accrue towards the total seen on mouse hover over.</span></span></li></ul>|
|<span data-ttu-id="8b2da-123">**4**</span><span class="sxs-lookup"><span data-stu-id="8b2da-123">**4**</span></span>   |<span data-ttu-id="8b2da-124">将鼠标悬停在表示日期上的应用使用情况的点上，可查看该应用在给定日期的总活动用户的实例数。</span><span class="sxs-lookup"><span data-stu-id="8b2da-124">Hover over the dot representing an Apps Usage on a given date to see the number of instances of that App’s Total Active Users on that given date.</span></span>  |
|<span data-ttu-id="8b2da-125">**5**</span><span class="sxs-lookup"><span data-stu-id="8b2da-125">**5**</span></span>   |<span data-ttu-id="8b2da-126">将包括所有应用，但通过选择 "筛选器" 图标，可使用其他筛选器。</span><span class="sxs-lookup"><span data-stu-id="8b2da-126">All Apps will be included but by choosing the Filter icon, additional filters are available.</span></span>  |
|<span data-ttu-id="8b2da-127">**6**</span><span class="sxs-lookup"><span data-stu-id="8b2da-127">**6**</span></span>   |<span data-ttu-id="8b2da-128">该表通过应用名称向你提供活动用户和团队的细目。</span><span class="sxs-lookup"><span data-stu-id="8b2da-128">The table gives you a breakdown of active users and teams by App name.</span></span><br><ul><li><span data-ttu-id="8b2da-129">**应用名称**是团队中使用的应用的显示名称。</span><span class="sxs-lookup"><span data-stu-id="8b2da-129">**App name** is the display name of the app used in Teams.</span></span></li><li><span data-ttu-id="8b2da-130">"**活动用户**" 是指在指定时间段内至少打开过一次应用的用户数。</span><span class="sxs-lookup"><span data-stu-id="8b2da-130">**Active users** is the number of users who opened the app at least once during the specified time period.</span></span></li><li><span data-ttu-id="8b2da-131">**应用类型**是 "Microsoft" 或 "第三方" 的静态值。</span><span class="sxs-lookup"><span data-stu-id="8b2da-131">**App type** is a static value of either “Microsoft” or “Third Party”.</span></span></li><li><span data-ttu-id="8b2da-132">**活动团队**是已由团队的至少一个成员以及在指定时间段内打开应用的团队数。</span><span class="sxs-lookup"><span data-stu-id="8b2da-132">**Active teams** is the number of teams who have opened the App by at least one member of the team and during the specified time periods.</span></span></li><li><span data-ttu-id="8b2da-133">**Publisher**是应用程序的软件发行者。</span><span class="sxs-lookup"><span data-stu-id="8b2da-133">**Publisher** is the software publisher of the app.</span></span></li><li><span data-ttu-id="8b2da-134">**版本**是应用的软件版本，从应用发布者开始。</span><span class="sxs-lookup"><span data-stu-id="8b2da-134">**Version** is the software version of the app, from the app publisher.</span></span></li></ul><br><span data-ttu-id="8b2da-135">![应用使用情况报表的屏幕截图](media/app-usage-report4.png)</span><span class="sxs-lookup"><span data-stu-id="8b2da-135">![Screenshot of an Apps Usage report](media/app-usage-report4.png)</span></span>  |
|<span data-ttu-id="8b2da-136">**7**</span><span class="sxs-lookup"><span data-stu-id="8b2da-136">**7**</span></span>  |<span data-ttu-id="8b2da-137">选择“**编辑列**”可在表格中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="8b2da-137">Select **Edit columns** to add or remove columns in the table.</span></span><br><br><span data-ttu-id="8b2da-138">!["编辑栏" 页面的屏幕截图](media/app-usage-report5.png)</span><span class="sxs-lookup"><span data-stu-id="8b2da-138">![Screenshot of the Edit columns page](media/app-usage-report5.png)</span></span>  |
|<span data-ttu-id="8b2da-139">**个**</span><span class="sxs-lookup"><span data-stu-id="8b2da-139">**8**</span></span>  |<span data-ttu-id="8b2da-140">你可以将报表导出到 CSV 文件，以便脱机分析。</span><span class="sxs-lookup"><span data-stu-id="8b2da-140">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="8b2da-141">单击 "**导出到 Excel**"，然后在 "**下载**" 选项卡上，单击 "**下载**" 以在准备就绪后下载报告。</span><span class="sxs-lookup"><span data-stu-id="8b2da-141">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="8b2da-142">![下载页面的屏幕截图](media/app-usage-report7.png)</span><span class="sxs-lookup"><span data-stu-id="8b2da-142">![Screenshot of Downloads page](media/app-usage-report7.png)</span></span>  |
|<span data-ttu-id="8b2da-143">**db-9**</span><span class="sxs-lookup"><span data-stu-id="8b2da-143">**9**</span></span>   |<span data-ttu-id="8b2da-144">在 Excel 中查看报表时，你还会看到一个**Id**列，它表示应用 Id。</span><span class="sxs-lookup"><span data-stu-id="8b2da-144">When you view the report in Excel, you'll also see an **Id** column, which represents the app ID.</span></span> <span data-ttu-id="8b2da-145">团队 ID 通常是一个字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="8b2da-145">A team ID is typically an alphanumeric string.</span></span> <span data-ttu-id="8b2da-146">如果**Id**列显示为 \* \* \n \* \* \* \*，这意味着用户请求删除其信息。</span><span class="sxs-lookup"><span data-stu-id="8b2da-146">If the **Id** column shows as \*\*\n\*\*\*\*, this means that a user requested their information to be deleted.</span></span><br><span data-ttu-id="8b2da-147">![下载的 Excel 报表的屏幕截图](media/app-usage-report8.png)</span><span class="sxs-lookup"><span data-stu-id="8b2da-147">![Screenshot of the downloaded Excel report](media/app-usage-report8.png)</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="8b2da-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="8b2da-148">Related topics</span></span>

- [<span data-ttu-id="8b2da-149">Teams 分析和报告</span><span class="sxs-lookup"><span data-stu-id="8b2da-149">Teams analytics and reporting</span></span>](teams-reporting-reference.md)