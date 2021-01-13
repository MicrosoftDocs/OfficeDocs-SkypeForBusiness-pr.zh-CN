---
title: Microsoft Teams 设备使用情况报告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用 Microsoft Teams 管理中心中的 Teams 设备使用情况报告来查看组织中用户如何连接到 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 292632972396f5d4300fa2526f01e69a5555ff45
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815642"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="07492-103">Microsoft Teams 设备使用情况报告</span><span class="sxs-lookup"><span data-stu-id="07492-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="07492-104">Microsoft Teams 管理中心中的 Teams 设备使用情况报告提供有关用户如何连接到 Teams 的信息。</span><span class="sxs-lookup"><span data-stu-id="07492-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="07492-105">可以使用报表查看整个组织使用的设备，包括移动时有多少设备从移动设备使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="07492-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-device-usage-report"></a><span data-ttu-id="07492-106">查看设备使用情况报表</span><span class="sxs-lookup"><span data-stu-id="07492-106">View the device usage report</span></span>

1. <span data-ttu-id="07492-107">在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"分析&报告**  >  **使用情况报告**。</span><span class="sxs-lookup"><span data-stu-id="07492-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="07492-108">在"**查看报表"** 选项卡上的 **"** 报表"下，**选择"Teams 设备使用情况"。**</span><span class="sxs-lookup"><span data-stu-id="07492-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="07492-109">在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。</span><span class="sxs-lookup"><span data-stu-id="07492-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="07492-110">![Teams 管理中心中带标注的 Teams 设备使用情况报告的屏幕截图](../media/teams-reports-device-usage-with-callouts.png "Teams 管理中心中带标注的 Teams 设备使用情况报告的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="07492-110">![Screenshot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="07492-111">解释报告</span><span class="sxs-lookup"><span data-stu-id="07492-111">Interpret the report</span></span>

|<span data-ttu-id="07492-112">标注</span><span class="sxs-lookup"><span data-stu-id="07492-112">Callout</span></span> |<span data-ttu-id="07492-113">说明</span><span class="sxs-lookup"><span data-stu-id="07492-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="07492-114">**1**</span><span class="sxs-lookup"><span data-stu-id="07492-114">**1**</span></span>   |<span data-ttu-id="07492-115">可以查看 Teams 设备使用情况报告，了解过去 7 天或 30 天的趋势。</span><span class="sxs-lookup"><span data-stu-id="07492-115">The Teams device usage report can be viewed for trends over the last 7 days or 30 days.</span></span>  |
|<span data-ttu-id="07492-116">**2**</span><span class="sxs-lookup"><span data-stu-id="07492-116">**2**</span></span>   |<span data-ttu-id="07492-117">每个报表都有一个生成报告的日期。</span><span class="sxs-lookup"><span data-stu-id="07492-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="07492-118">报告通常反映活动时间为 24 小时的延迟。</span><span class="sxs-lookup"><span data-stu-id="07492-118">The reports usually reflect a 24 hour latency from time of activity.</span></span> |
|<span data-ttu-id="07492-119">**3**</span><span class="sxs-lookup"><span data-stu-id="07492-119">**3**</span></span>   |<ul><li><span data-ttu-id="07492-120">图表上的 X 轴表示用于连接到 Teams (Windows、Mac、Linux、iOS、Android     **Phone、Web**) 设备。 </span><span class="sxs-lookup"><span data-stu-id="07492-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="07492-121">Y 轴表示所选时段内使用设备的用户数。</span><span class="sxs-lookup"><span data-stu-id="07492-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="07492-122">将鼠标悬停在表示设备的栏上，以查看使用该设备连接到 Teams 的用户数。</span><span class="sxs-lookup"><span data-stu-id="07492-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="07492-123">**4**</span><span class="sxs-lookup"><span data-stu-id="07492-123">**4**</span></span>   |<span data-ttu-id="07492-124">下表提供了按用户分类的设备使用情况。</span><span class="sxs-lookup"><span data-stu-id="07492-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="07492-125">**用户名** 是显示名称的用户名。</span><span class="sxs-lookup"><span data-stu-id="07492-125">**Username** is the display name of the user.</span></span> <span data-ttu-id="07492-126">可以单击显示名称转到 Microsoft Teams 管理中心中的用户设置页面。</span><span class="sxs-lookup"><span data-stu-id="07492-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="07492-127">**如果用户** 在基于 Windows 的电脑上的 Teams 桌面客户端中处于活动状态，则选择 Windows。</span><span class="sxs-lookup"><span data-stu-id="07492-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="07492-128">**如果用户在 macOS** 计算机的 Teams 桌面客户端中处于活动状态，则选择 Mac。</span><span class="sxs-lookup"><span data-stu-id="07492-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="07492-129">**如果用户** 在 Linux 计算机的 Teams 桌面客户端中处于活动状态，则选择 Linux。</span><span class="sxs-lookup"><span data-stu-id="07492-129">**Linux** is selected if the user was active in the Teams desktop client on a Linux computer.</span></span> </li> <li><span data-ttu-id="07492-130">**如果用户在适用于 iOS** 的 Teams 移动客户端上处于活动状态，则选择 iOS。</span><span class="sxs-lookup"><span data-stu-id="07492-130">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="07492-131">**如果用户在 Android** 版 Teams 移动客户端上处于活动状态，则选择 Android 手机。</span><span class="sxs-lookup"><span data-stu-id="07492-131">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><li><span data-ttu-id="07492-132">**如果用户** 在 Teams Web 客户端上处于活动状态，则选择 Web。</span><span class="sxs-lookup"><span data-stu-id="07492-132">**Web** is selected if the user was active on the Teams web client.</span></span> <li><span data-ttu-id="07492-133">**上次活动** 是用户 (Utc) 的最后一天。</span><span class="sxs-lookup"><span data-stu-id="07492-133">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="07492-134">请注意，如果 Azure AD 中不再存在用户帐户，则用户名在表中显示为"--"。</span><span class="sxs-lookup"><span data-stu-id="07492-134">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="07492-135">要查看希望在表格中显示的信息，请确保向表格添加了相关列。</span><span class="sxs-lookup"><span data-stu-id="07492-135">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="07492-136">**5**</span><span class="sxs-lookup"><span data-stu-id="07492-136">**5**</span></span>   |<span data-ttu-id="07492-137">选择“**编辑列**”可在表格中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="07492-137">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="07492-138">**6**</span><span class="sxs-lookup"><span data-stu-id="07492-138">**6**</span></span>   |<span data-ttu-id="07492-139">可以将报表导出到 CSV 文件进行脱机分析。</span><span class="sxs-lookup"><span data-stu-id="07492-139">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="07492-140">单击 **"导出到 Excel"，** 然后在"下载"选项卡上单击"下载"，在报表准备就绪后下载报表。</span><span class="sxs-lookup"><span data-stu-id="07492-140">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="07492-141">![显示导出报表的"下载"选项卡的屏幕截图](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="07492-141">![Screenshot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="07492-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="07492-142">Related topics</span></span>

- [<span data-ttu-id="07492-143">Teams 分析和报告</span><span class="sxs-lookup"><span data-stu-id="07492-143">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
