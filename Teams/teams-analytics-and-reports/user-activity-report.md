---
title: Microsoft Teams 用户活动报告
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/22/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何使用在 Microsoft 团队管理中心团队用户活动报告查看您的组织中的用户如何使用团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5ad6021f03b200e1f3216238a81cc3b691171fd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225025"
---
# <a name="microsoft-teams-user-activity-report"></a><span data-ttu-id="8b882-103">Microsoft Teams 用户活动报告</span><span class="sxs-lookup"><span data-stu-id="8b882-103">Microsoft Teams user activity report</span></span>

<span data-ttu-id="8b882-104">团队用户活动报告提供深入的组织中的用户执行团队中的活动的类型。</span><span class="sxs-lookup"><span data-stu-id="8b882-104">The Teams user activity report gives you insight into the types of activities that users in your organization perform in Teams.</span></span> <span data-ttu-id="8b882-105">例如，您可以看到多少用户进行通信 1 对 1 呼叫通过、 多少用户进行通信通道邮件通过和多少用户参与专用聊天消息。</span><span class="sxs-lookup"><span data-stu-id="8b882-105">For example, you can see how many users communicate through 1:1 calls, how many users communicate through channel messages, and how many users engage in private chat messages.</span></span>

<span data-ttu-id="8b882-106">![团队用户活动报告中的 Microsoft 团队管理中心的屏幕截图](../media/teams-reports-user-activity.png "团队用户活动报告中的 Microsoft 团队管理中心的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="8b882-106">![Screen shot of the Teams user activity report in the Microsoft Teams admin center](../media/teams-reports-user-activity.png "Screen shot of the Teams user activity report in the Microsoft Teams admin center")</span></span>

## <a name="view-the-report"></a><span data-ttu-id="8b882-107">查看报告</span><span class="sxs-lookup"><span data-stu-id="8b882-107">View the report</span></span>

1. <span data-ttu-id="8b882-108">转到 Microsoft 团队管理中心中，在左侧导航窗格中，单击**分析 & 报告**，，然后在**报告**下选择**工作组用户活动**。</span><span class="sxs-lookup"><span data-stu-id="8b882-108">Go to the Microsoft Teams admin center, in the left navigation, click **Analytics & reports**, and then under **Report**, select **Teams user activity**.</span></span> 
2. <span data-ttu-id="8b882-109">在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。</span><span class="sxs-lookup"><span data-stu-id="8b882-109">Under **Date range**, select a range, and then click **Run report**.</span></span> 

## <a name="interpret-the-report"></a><span data-ttu-id="8b882-110">解释报告</span><span class="sxs-lookup"><span data-stu-id="8b882-110">Interpret the report</span></span>

<span data-ttu-id="8b882-111">![带编号的标注的 Microsoft 团队管理中心中的团队用户活动报告的屏幕截图](../media/teams-reports-user-activity-with-callouts.png "带编号的标注的 Microsoft 团队管理中心中的团队用户活动报告的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="8b882-111">![Screenshot of the Teams user activity report in the Microsoft Teams admin center with numbered callouts](../media/teams-reports-user-activity-with-callouts.png "Screenshot of the Teams user activity report in the Microsoft Teams admin center with numbered callouts")</span></span>

|<span data-ttu-id="8b882-112">标注</span><span class="sxs-lookup"><span data-stu-id="8b882-112">Callout</span></span> |<span data-ttu-id="8b882-113">说明</span><span class="sxs-lookup"><span data-stu-id="8b882-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="8b882-114">**1**</span><span class="sxs-lookup"><span data-stu-id="8b882-114">**1**</span></span>   |<span data-ttu-id="8b882-115">可以随最近 7 天或 28 天趋势查看团队用户活动报告。</span><span class="sxs-lookup"><span data-stu-id="8b882-115">The Teams user activity report can be viewed for trends over the last 7 days or 28 days.</span></span> |
|<span data-ttu-id="8b882-116">**2**</span><span class="sxs-lookup"><span data-stu-id="8b882-116">**2**</span></span>   |<span data-ttu-id="8b882-p102">每个报表包含此报表的生成日期。报表通常反映活动时间的 24 至 48 小时延迟。</span><span class="sxs-lookup"><span data-stu-id="8b882-p102">Each report has a date for when this report was generated. The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="8b882-119">**3**</span><span class="sxs-lookup"><span data-stu-id="8b882-119">**3**</span></span>   |<ul><li><span data-ttu-id="8b882-120">图表上的 X 轴是特定报告的所选的日期范围。</span><span class="sxs-lookup"><span data-stu-id="8b882-120">The X axis on the charts is the selected date range for the specific report.</span></span> </li><li><span data-ttu-id="8b882-121">Y 轴的参与活动用户数量。</span><span class="sxs-lookup"><span data-stu-id="8b882-121">The Y axis is the number of users participating in the activity.</span></span></li></ul><span data-ttu-id="8b882-122">悬停在给定日期的给定日期查看该活动的实例数目代表活动的点。</span><span class="sxs-lookup"><span data-stu-id="8b882-122">Hover over the dot representing an activity on a given date to see the number of instances of that activity on that given date.</span></span> |
|<span data-ttu-id="8b882-123">**4**</span><span class="sxs-lookup"><span data-stu-id="8b882-123">**4**</span></span>   |<span data-ttu-id="8b882-124">可单击图例上的项目筛选要在图表上查看的内容。</span><span class="sxs-lookup"><span data-stu-id="8b882-124">You can filter what you see on the chart by clicking an item in the legend.</span></span> <span data-ttu-id="8b882-125">例如，单击**呼叫 1:1**、**通道消息**或**聊天消息**以查看仅与每个相关的信息。</span><span class="sxs-lookup"><span data-stu-id="8b882-125">For example, click **1:1 calls**, **Channel messages**, or **Chat messages** to see only the info related to each one.</span></span> <span data-ttu-id="8b882-126">更改所选内容不会更改表中的信息。</span><span class="sxs-lookup"><span data-stu-id="8b882-126">Changing the selection doesn’t change the information in the table.</span></span> |
|<span data-ttu-id="8b882-127">**5**</span><span class="sxs-lookup"><span data-stu-id="8b882-127">**5**</span></span>   |<span data-ttu-id="8b882-128">表为您提供了使用用户细分。</span><span class="sxs-lookup"><span data-stu-id="8b882-128">The table gives you a breakdown of usage by user.</span></span>   <ul><li><span data-ttu-id="8b882-129">**显示名称**是用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="8b882-129">**Display name** is the display name of the user.</span></span> <span data-ttu-id="8b882-130">您可以单击转到 Microsoft 团队管理中心中的用户的设置页的显示名称。</span><span class="sxs-lookup"><span data-stu-id="8b882-130">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span></li><li><span data-ttu-id="8b882-131">**1:1 呼叫**是用户所参与的 1 对 1 呼叫数在指定的时间段。</span><span class="sxs-lookup"><span data-stu-id="8b882-131">**1:1 calls** is the number of 1:1 calls that the user participated in during the specified time period.</span></span></li><li><span data-ttu-id="8b882-132">**通道消息**是唯一的用户发布的消息数团队聊天在指定的时间段中。</span><span class="sxs-lookup"><span data-stu-id="8b882-132">**Channel messages** is the number of unique messages that the user posted in a team chat during the specified time period.</span></span></li> <li><span data-ttu-id="8b882-133">**聊天消息**是唯一的用户发布在专用聊天指定的时间段内的消息数。</span><span class="sxs-lookup"><span data-stu-id="8b882-133">**Chat messages** is the number of unique messages that the user posted in a private chat during the specified time period.</span></span></li>  <li><span data-ttu-id="8b882-134">**最后一次活动**是用户参与团队活动的最后一个日期 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="8b882-134">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul><span data-ttu-id="8b882-135">要查看希望在表格中显示的信息，请确保向表格添加了相关列。</span><span class="sxs-lookup"><span data-stu-id="8b882-135">To see the information that you want in the table, make sure to add the columns to the table.</span></span>
|<span data-ttu-id="8b882-136">**6**</span><span class="sxs-lookup"><span data-stu-id="8b882-136">**6**</span></span>   |<span data-ttu-id="8b882-137">选择“**编辑列**”可在表格中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="8b882-137">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="8b882-138">**7**</span><span class="sxs-lookup"><span data-stu-id="8b882-138">**7**</span></span>   |<span data-ttu-id="8b882-139">选择“**˙˙˙**”，然后选择“**打印图表**”可打印图表。</span><span class="sxs-lookup"><span data-stu-id="8b882-139">Select **˙˙˙**, and then **Print chart** to print the chart.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8b882-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="8b882-140">Related topics</span></span>
- [<span data-ttu-id="8b882-141">Teams 分析和报告</span><span class="sxs-lookup"><span data-stu-id="8b882-141">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
- [<span data-ttu-id="8b882-142">Teams 使用情况报告</span><span class="sxs-lookup"><span data-stu-id="8b882-142">Teams usage report</span></span>](teams-usage-report.md)
- [<span data-ttu-id="8b882-143">Teams 设备使用报告</span><span class="sxs-lookup"><span data-stu-id="8b882-143">Teams device usage report</span></span>](device-usage-report.md)