---
title: Microsoft Teams 设备使用情况报告
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 03/19/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何使用在 Microsoft 团队管理中心团队设备使用情况报告查看如何在组织中的用户连接到团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1915e7c2c52911e49afca6dbbb23e6ed9b74d672
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "30684022"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="07ccc-103">Microsoft Teams 设备使用情况报告</span><span class="sxs-lookup"><span data-stu-id="07ccc-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="07ccc-104">团队设备使用情况报告的 Microsoft 团队管理中心中为您提供了有关如何将用户连接到团队的信息。</span><span class="sxs-lookup"><span data-stu-id="07ccc-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="07ccc-105">您可以使用报表以在整个组织，包括多少从其移动设备时转上使用团队中查看使用的设备。</span><span class="sxs-lookup"><span data-stu-id="07ccc-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

<span data-ttu-id="07ccc-106">![团队设备使用情况报告的 Microsoft 团队管理中心中的屏幕截图](../media/teams-reports-device-usage.png "团队设备使用情况报告的 Microsoft 团队管理中心中的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="07ccc-106">![Screen shot of the Teams device usage report in the Microsoft Teams admin center](../media/teams-reports-device-usage.png "Screen shot of the Teams device usage report in the Microsoft Teams admin center")</span></span>

## <a name="view-the-report"></a><span data-ttu-id="07ccc-107">查看报告</span><span class="sxs-lookup"><span data-stu-id="07ccc-107">View the report</span></span>

1. <span data-ttu-id="07ccc-108">转到 Microsoft 团队管理中心中，在左侧导航窗格中，单击**分析 & 报告**，，然后在**报告**下选择**团队设备用法**。</span><span class="sxs-lookup"><span data-stu-id="07ccc-108">Go to the Microsoft Teams admin center, in the left navigation, click **Analytics & reports**, and then under **Report**, select **Teams device usage**.</span></span> 
2. <span data-ttu-id="07ccc-109">在**日期范围**选择区域，，然后单击**运行报告**。</span><span class="sxs-lookup"><span data-stu-id="07ccc-109">Under **Date range**, select a range, and then click **Run report**.</span></span> 

## <a name="interpret-the-report"></a><span data-ttu-id="07ccc-110">解释报表</span><span class="sxs-lookup"><span data-stu-id="07ccc-110">Interpret the report</span></span>

<span data-ttu-id="07ccc-111">![团队设备使用情况报告的 Microsoft 团队管理中心中的屏幕截图](../media/teams-reports-device-usage-with-callouts.png "带编号的标注的 Microsoft 团队管理中心中的团队设备使用率报告的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="07ccc-111">![Screen shot of the Teams device usage report in the Microsoft Teams admin center](../media/teams-reports-device-usage-with-callouts.png "Screen shot of the Teams device usage report in the Microsoft Teams admin center with numbered callouts")</span></span>

|<span data-ttu-id="07ccc-112">标号</span><span class="sxs-lookup"><span data-stu-id="07ccc-112">Callout</span></span> |<span data-ttu-id="07ccc-113">说明</span><span class="sxs-lookup"><span data-stu-id="07ccc-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="07ccc-114">**1**</span><span class="sxs-lookup"><span data-stu-id="07ccc-114">**1**</span></span>   |<span data-ttu-id="07ccc-115">可以随最近 7 天或 28 天趋势查看团队设备使用率报告。</span><span class="sxs-lookup"><span data-stu-id="07ccc-115">The Teams device usage report can be viewed for trends over the last 7 days or 28 days.</span></span>  |
|<span data-ttu-id="07ccc-116">**2**</span><span class="sxs-lookup"><span data-stu-id="07ccc-116">**2**</span></span>   |<span data-ttu-id="07ccc-117">每个报告具有报告生成的时间的日期。</span><span class="sxs-lookup"><span data-stu-id="07ccc-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="07ccc-118">报表通常反映活动时间的 24 至 48 小时延迟。</span><span class="sxs-lookup"><span data-stu-id="07ccc-118">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="07ccc-119">**3**</span><span class="sxs-lookup"><span data-stu-id="07ccc-119">**3**</span></span>   |<ul><li><span data-ttu-id="07ccc-120">图表上的 X 轴表示用于连接到团队的不同设备 (**Windows**、 **Mac**， **iOS**， **android 移动电话**)。</span><span class="sxs-lookup"><span data-stu-id="07ccc-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **iOS**, **Android Phone**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="07ccc-121">Y 轴是选定的时间段内使用的设备的用户数。</span><span class="sxs-lookup"><span data-stu-id="07ccc-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="07ccc-122">将鼠标悬停在栏表示设备，以查看使用设备连接到团队的用户数。</span><span class="sxs-lookup"><span data-stu-id="07ccc-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="07ccc-123">**4**</span><span class="sxs-lookup"><span data-stu-id="07ccc-123">**4**</span></span>   |<span data-ttu-id="07ccc-124">表为您提供了设备使用用户细分。</span><span class="sxs-lookup"><span data-stu-id="07ccc-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="07ccc-125">**显示名称**是用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="07ccc-125">**Display name** is the display name of the user.</span></span> <span data-ttu-id="07ccc-126">您可以单击转到 Microsoft 团队管理中心中的用户的设置页的显示名称。</span><span class="sxs-lookup"><span data-stu-id="07ccc-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="07ccc-127">**Windows**处于选中状态，如果用户的基于 Windows 的计算机上的团队桌面客户端中处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="07ccc-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="07ccc-128">如果用户已 macOS 计算机上的团队桌面客户端中处于活动状态，则选中**Mac** 。</span><span class="sxs-lookup"><span data-stu-id="07ccc-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="07ccc-129">**iOS**处于选中状态，如果用户处于活动状态的 iOS 团队移动客户端上。</span><span class="sxs-lookup"><span data-stu-id="07ccc-129">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="07ccc-130">如果用户上处于活动状态团队移动客户端的 Android， **android 移动电话**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="07ccc-130">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><span data-ttu-id="07ccc-131">**最后一次活动**是用户参与团队活动的最后一个日期 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="07ccc-131">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="07ccc-132">若要查看表中所需的信息，请确保将列添加到表。</span><span class="sxs-lookup"><span data-stu-id="07ccc-132">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="07ccc-133">**5**</span><span class="sxs-lookup"><span data-stu-id="07ccc-133">**5**</span></span>   |<span data-ttu-id="07ccc-134">选择**编辑列**添加或删除表中的列。</span><span class="sxs-lookup"><span data-stu-id="07ccc-134">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="07ccc-135">**6**</span><span class="sxs-lookup"><span data-stu-id="07ccc-135">**6**</span></span>   |<span data-ttu-id="07ccc-136">选择**˙˙˙**，然后**打印图表**打印图表。</span><span class="sxs-lookup"><span data-stu-id="07ccc-136">Select **˙˙˙**, and then **Print chart** to print the chart.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="07ccc-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="07ccc-137">Related topics</span></span>
- [<span data-ttu-id="07ccc-138">团队分析和报告</span><span class="sxs-lookup"><span data-stu-id="07ccc-138">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
- [<span data-ttu-id="07ccc-139">Teams 使用情况报告</span><span class="sxs-lookup"><span data-stu-id="07ccc-139">Teams usage report</span></span>](teams-usage-report.md)
- [<span data-ttu-id="07ccc-140">Teams 用户活动报告</span><span class="sxs-lookup"><span data-stu-id="07ccc-140">Teams user activity report</span></span>](user-activity-report.md)