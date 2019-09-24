---
title: Microsoft Teams 设备使用情况报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何使用 Microsoft 团队管理中心中的 "团队设备使用情况" 报表来查看组织中的用户如何连接到团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1da28ccda6394a2e88685132150516cfed2c7fc
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131621"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="fc6c1-103">Microsoft Teams 设备使用情况报告</span><span class="sxs-lookup"><span data-stu-id="fc6c1-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="fc6c1-104">Microsoft 团队管理中心中的 "团队设备使用情况" 报表为你提供有关用户如何连接到团队的信息。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="fc6c1-105">你可以使用报表查看你的组织中使用的设备，包括在旅途中使用的多个团队使用的移动设备。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-report"></a><span data-ttu-id="fc6c1-106">查看报告</span><span class="sxs-lookup"><span data-stu-id="fc6c1-106">View the report</span></span>

1. <span data-ttu-id="fc6c1-107">在 Microsoft 团队管理中心的左侧导航中，单击 "**分析" & 报告** > **使用情况报告**。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="fc6c1-108">在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 "**团队设备使用情况**"。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="fc6c1-109">在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="fc6c1-110">团队![管理员中心中使用标注的团队设备使用情况报告的屏幕截图]团队(../media/teams-reports-device-usage-with-callouts.png "管理员中心中使用标注的团队设备使用情况报告的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="fc6c1-110">![Screenshot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="fc6c1-111">解释报告</span><span class="sxs-lookup"><span data-stu-id="fc6c1-111">Interpret the report</span></span>

|<span data-ttu-id="fc6c1-112">标注</span><span class="sxs-lookup"><span data-stu-id="fc6c1-112">Callout</span></span> |<span data-ttu-id="fc6c1-113">说明</span><span class="sxs-lookup"><span data-stu-id="fc6c1-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="fc6c1-114">**1**</span><span class="sxs-lookup"><span data-stu-id="fc6c1-114">**1**</span></span>   |<span data-ttu-id="fc6c1-115">可以查看 "团队设备使用情况" 报表，了解过去7天或28天的趋势。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-115">The Teams device usage report can be viewed for trends over the last 7 days or 28 days.</span></span>  |
|<span data-ttu-id="fc6c1-116">**2**</span><span class="sxs-lookup"><span data-stu-id="fc6c1-116">**2**</span></span>   |<span data-ttu-id="fc6c1-117">每个报表都具有生成报表的日期。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="fc6c1-118">报表通常反映活动时间的 24 至 48 小时延迟。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-118">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="fc6c1-119">**3**</span><span class="sxs-lookup"><span data-stu-id="fc6c1-119">**3**</span></span>   |<ul><li><span data-ttu-id="fc6c1-120">图表上的 X 轴表示用于连接到团队的不同设备（**Windows**、 **Mac**、 **iOS**、 **Android 手机**）。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **iOS**, **Android Phone**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="fc6c1-121">Y 轴是在选定时间段内使用设备的用户数。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="fc6c1-122">将鼠标悬停在表示设备的栏上，可查看使用设备连接到团队的用户数。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="fc6c1-123">**4**</span><span class="sxs-lookup"><span data-stu-id="fc6c1-123">**4**</span></span>   |<span data-ttu-id="fc6c1-124">此表提供了用户的设备使用情况的细目。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="fc6c1-125">"**显示名称**" 是用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-125">**Display name** is the display name of the user.</span></span> <span data-ttu-id="fc6c1-126">你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="fc6c1-127">如果用户在基于 Windows 的计算机上的团队桌面客户端中处于活动状态，则选择 " **Windows** "。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="fc6c1-128">如果用户在 macOS 计算机上的团队桌面客户端中处于活动状态，则会选择**Mac** 。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="fc6c1-129">如果用户在 iOS 的团队移动客户端上处于活动状态，则选择**ios** 。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-129">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="fc6c1-130">如果用户在 Android 的团队移动客户端上处于活动状态，则选择 " **Android 手机**"。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-130">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><span data-ttu-id="fc6c1-131">"**上次活动**" 是用户参与团队活动的最后日期（UTC）。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-131">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="fc6c1-132">请注意，如果用户帐户在 Azure AD 中不再存在，则用户名在表中显示为 "-"。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-132">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="fc6c1-133">要查看希望在表格中显示的信息，请确保向表格添加了相关列。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-133">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="fc6c1-134">**5**</span><span class="sxs-lookup"><span data-stu-id="fc6c1-134">**5**</span></span>   |<span data-ttu-id="fc6c1-135">选择“**编辑列**”可在表格中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-135">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="fc6c1-136">**6**</span><span class="sxs-lookup"><span data-stu-id="fc6c1-136">**6**</span></span>   |<span data-ttu-id="fc6c1-137">你可以将报表导出到 CSV 文件，以便脱机分析。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-137">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="fc6c1-138">单击 "**导出到 Excel**"，然后在 "**下载**" 选项卡上，单击 "**下载**" 以在准备就绪后下载报告。</span><span class="sxs-lookup"><span data-stu-id="fc6c1-138">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="fc6c1-139">![显示导出报表的 "下载" 选项卡的屏幕截图](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="fc6c1-139">![Screenshot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="fc6c1-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="fc6c1-140">Related topics</span></span>

- [<span data-ttu-id="fc6c1-141">Teams 分析和报告</span><span class="sxs-lookup"><span data-stu-id="fc6c1-141">Teams analytics and reporting</span></span>](teams-reporting-reference.md)