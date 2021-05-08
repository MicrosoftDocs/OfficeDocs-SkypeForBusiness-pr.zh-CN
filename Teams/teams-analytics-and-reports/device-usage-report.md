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
description: 了解如何使用 Teams 管理中心中的Microsoft Teams设备使用情况报告来查看组织中用户如何连接到 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d47888884ce86bfa56546a9df600ce958380e0d
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478352"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="13418-103">Microsoft Teams 设备使用情况报告</span><span class="sxs-lookup"><span data-stu-id="13418-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="13418-104">Teams管理中心中的Microsoft Teams使用情况报告提供了用户如何连接到 Teams。</span><span class="sxs-lookup"><span data-stu-id="13418-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="13418-105">可以使用报表查看整个组织使用的设备，包括Teams移动设备使用的设备数。</span><span class="sxs-lookup"><span data-stu-id="13418-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-device-usage-report"></a><span data-ttu-id="13418-106">查看设备使用情况报告</span><span class="sxs-lookup"><span data-stu-id="13418-106">View the device usage report</span></span>

1. <span data-ttu-id="13418-107">在管理中心的左侧导航Microsoft Teams，单击 **"分析**"&  >  **报告使用情况报告"。**</span><span class="sxs-lookup"><span data-stu-id="13418-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="13418-108">在"**查看报表"** 选项卡上的"报表 **"** 下 **，Teams设备使用情况"。**</span><span class="sxs-lookup"><span data-stu-id="13418-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="13418-109">在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。</span><span class="sxs-lookup"><span data-stu-id="13418-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="13418-110">![屏幕截图：Teams管理中心中的设备使用情况Teams标注](../media/teams-reports-device-usage-with-callouts.png "屏幕截图：Teams管理中心中的设备使用情况Teams标注")</span><span class="sxs-lookup"><span data-stu-id="13418-110">![Screenshot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="13418-111">解释报告</span><span class="sxs-lookup"><span data-stu-id="13418-111">Interpret the report</span></span>

|<span data-ttu-id="13418-112">标注</span><span class="sxs-lookup"><span data-stu-id="13418-112">Callout</span></span> |<span data-ttu-id="13418-113">说明</span><span class="sxs-lookup"><span data-stu-id="13418-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="13418-114">**1**</span><span class="sxs-lookup"><span data-stu-id="13418-114">**1**</span></span>   |<span data-ttu-id="13418-115">可以查看Teams使用情况报表，了解过去 7 天或 30 天的趋势。</span><span class="sxs-lookup"><span data-stu-id="13418-115">The Teams device usage report can be viewed for trends over the last 7 days or 30 days.</span></span>  |
|<span data-ttu-id="13418-116">**2**</span><span class="sxs-lookup"><span data-stu-id="13418-116">**2**</span></span>   |<span data-ttu-id="13418-117">每个报表都有一个生成报告的日期。</span><span class="sxs-lookup"><span data-stu-id="13418-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="13418-118">报告通常反映活动时间延迟 24 小时。</span><span class="sxs-lookup"><span data-stu-id="13418-118">The reports usually reflect a 24 hour latency from time of activity.</span></span> |
|<span data-ttu-id="13418-119">**3**</span><span class="sxs-lookup"><span data-stu-id="13418-119">**3**</span></span>   |<ul><li><span data-ttu-id="13418-120">图表上的 X 轴表示用于 (Windows、Mac、Linux、iOS、Android **电话、Web**) 设备Teams。 </span><span class="sxs-lookup"><span data-stu-id="13418-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="13418-121">Y 轴表示所选时段内使用设备的用户数。</span><span class="sxs-lookup"><span data-stu-id="13418-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="13418-122">将鼠标悬停在表示设备的栏上，以查看使用该设备连接到 Teams。</span><span class="sxs-lookup"><span data-stu-id="13418-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="13418-123">**4**</span><span class="sxs-lookup"><span data-stu-id="13418-123">**4**</span></span>   |<span data-ttu-id="13418-124">下表按用户提供了设备使用情况的细分。</span><span class="sxs-lookup"><span data-stu-id="13418-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="13418-125">**用户名** 是显示名称的用户名。</span><span class="sxs-lookup"><span data-stu-id="13418-125">**Username** is the display name of the user.</span></span> <span data-ttu-id="13418-126">可以单击显示名称转到管理中心中的用户设置Microsoft Teams页面。</span><span class="sxs-lookup"><span data-stu-id="13418-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="13418-127">**Windows** 在基于计算机的 Teams 桌面客户端中处于活动状态，则Windows选择。</span><span class="sxs-lookup"><span data-stu-id="13418-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="13418-128">**如果用户在 macOS** 计算机上在 Teams桌面客户端中处于活动状态，则选择 Mac。</span><span class="sxs-lookup"><span data-stu-id="13418-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="13418-129">**如果用户** 在 Linux 计算机上在 Teams桌面客户端中处于活动状态，则选择 Linux。</span><span class="sxs-lookup"><span data-stu-id="13418-129">**Linux** is selected if the user was active in the Teams desktop client on a Linux computer.</span></span> </li> <li><span data-ttu-id="13418-130">**如果用户在 iOS** 的移动客户端上处于活动状态，Teams iOS。</span><span class="sxs-lookup"><span data-stu-id="13418-130">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="13418-131">**如果用户在 Android** 的移动客户端上处于活动状态，Teams Android 手机。</span><span class="sxs-lookup"><span data-stu-id="13418-131">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><li><span data-ttu-id="13418-132">**如果用户** 在 Web 客户端上处于活动状态，则Teams Web。</span><span class="sxs-lookup"><span data-stu-id="13418-132">**Web** is selected if the user was active on the Teams web client.</span></span> <li><span data-ttu-id="13418-133">**"上次** 活动"是用户 (上次) UTC 时间Teams的日期。</span><span class="sxs-lookup"><span data-stu-id="13418-133">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="13418-134">请注意，如果 Azure AD 中不再存在用户帐户，则用户名在表中显示为"--"。</span><span class="sxs-lookup"><span data-stu-id="13418-134">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="13418-135">要查看希望在表格中显示的信息，请确保向表格添加了相关列。</span><span class="sxs-lookup"><span data-stu-id="13418-135">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="13418-136">**5**</span><span class="sxs-lookup"><span data-stu-id="13418-136">**5**</span></span>   |<span data-ttu-id="13418-137">选择“**编辑列**”可在表格中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="13418-137">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="13418-138">**6**</span><span class="sxs-lookup"><span data-stu-id="13418-138">**6**</span></span>   |<span data-ttu-id="13418-139">可以将报表导出到 CSV 文件进行脱机分析。</span><span class="sxs-lookup"><span data-stu-id="13418-139">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="13418-140">单击 **"导出Excel"，** 然后在"下载"选项卡上，单击"下载"，在报表准备就绪后下载报表。 </span><span class="sxs-lookup"><span data-stu-id="13418-140">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="13418-141">![显示导出报表的"下载"选项卡的屏幕截图](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="13418-141">![Screenshot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|


## <a name="make-the-user-specific-data-anonymous"></a><span data-ttu-id="13418-142">使用户特定的数据匿名</span><span class="sxs-lookup"><span data-stu-id="13418-142">Make the user specific data anonymous</span></span>

<span data-ttu-id="13418-143">若要使设备使用情况Teams数据匿名，您必须是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="13418-143">To make the data in Teams device usage report anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="13418-144">这会在报表及其导出中隐藏显示名称、电子邮件和 AAD ID 等可识别信息。</span><span class="sxs-lookup"><span data-stu-id="13418-144">This will hide identifiable information such as display name, email and AAD ID in report and their export.</span></span>

1. <span data-ttu-id="13418-145">在Microsoft 365管理中心，转到"设置 Org设置"，在"服务" \> **选项卡** 下，选择"报表 **"。**</span><span class="sxs-lookup"><span data-stu-id="13418-145">In Microsoft 365 admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="13418-146">选择 **"报告**"，然后选择"**显示匿名标识符"。**</span><span class="sxs-lookup"><span data-stu-id="13418-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="13418-147">此设置既应用于管理中心中的使用情况Microsoft 365，也适用于Teams中心。</span><span class="sxs-lookup"><span data-stu-id="13418-147">This setting gets applied both to the usage reports in Microsoft 365 admin center as well as Teams admin center.</span></span>
  
3. <span data-ttu-id="13418-148">选择"**保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="13418-148">Select **Save changes**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="13418-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="13418-149">Related topics</span></span>

- [<span data-ttu-id="13418-150">Teams 分析和报告</span><span class="sxs-lookup"><span data-stu-id="13418-150">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
