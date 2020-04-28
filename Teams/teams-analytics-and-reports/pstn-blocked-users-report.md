---
title: Microsoft 团队 PSTN 已阻止用户报告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: 使用 Microsoft 团队管理中心中的 PSTN "阻止的用户" 报表，大致了解组织的团队用户是否已阻止进行 PSTN 呼叫。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 511485fa156ba448368809edf54728ada1b80be7
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904904"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="76233-103">Microsoft 团队 PSTN 已阻止用户报告</span><span class="sxs-lookup"><span data-stu-id="76233-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="76233-104">Microsoft 团队管理中心中的 PSTN "已阻止用户" 报表显示你的组织中阻止在团队中进行 PSTN 呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="76233-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="76233-105">您可以查看有关每个被阻止用户的详细信息，包括其分配的电话号码以及阻止他们进行呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="76233-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="76233-106">查看 PSTN 已阻止用户报告</span><span class="sxs-lookup"><span data-stu-id="76233-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="76233-107">在 Microsoft 团队管理中心的左侧导航中，单击 "**分析" & 报告** > **使用情况报告**。</span><span class="sxs-lookup"><span data-stu-id="76233-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="76233-108">在 "**查看报表**" 选项卡上的 "**报表**" 下，选择 " **PSTN 阻止的用户**"，然后单击 "**运行报告**"。</span><span class="sxs-lookup"><span data-stu-id="76233-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="76233-109">![管理中心的 PSTN 已阻止用户报告报告的屏幕截图](../media/teams-reports-pstn-blocked-users-with-callouts.png "Microsoft 团队管理中心中带有编号标注的 PSTN 已阻止用户报告的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="76233-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="76233-110">解释报告</span><span class="sxs-lookup"><span data-stu-id="76233-110">Interpret the report</span></span>

|<span data-ttu-id="76233-111">标注</span><span class="sxs-lookup"><span data-stu-id="76233-111">Callout</span></span> |<span data-ttu-id="76233-112">说明</span><span class="sxs-lookup"><span data-stu-id="76233-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="76233-113">**1**</span><span class="sxs-lookup"><span data-stu-id="76233-113">**1**</span></span>   |<span data-ttu-id="76233-114">每个报表都有一个生成日期的日期。</span><span class="sxs-lookup"><span data-stu-id="76233-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="76233-115">报表通常反映活动时间的 24 至 48 小时延迟。</span><span class="sxs-lookup"><span data-stu-id="76233-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="76233-116">**2**</span><span class="sxs-lookup"><span data-stu-id="76233-116">**2**</span></span>   |<span data-ttu-id="76233-117">X 轴是日期。</span><span class="sxs-lookup"><span data-stu-id="76233-117">The X axis is the date.</span></span> <span data-ttu-id="76233-118">Y 轴是用户数。</span><span class="sxs-lookup"><span data-stu-id="76233-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="76233-119">将鼠标悬停在给定日期的点上可查看该日期阻止的用户数。</span><span class="sxs-lookup"><span data-stu-id="76233-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="76233-120">**3**</span><span class="sxs-lookup"><span data-stu-id="76233-120">**3**</span></span>   |<span data-ttu-id="76233-121">该表提供阻止进行 PSTN 呼叫的所有用户的细目。</span><span class="sxs-lookup"><span data-stu-id="76233-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="76233-122">它显示已分配电话系统或音频会议的所有用户，并提供有关每个用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="76233-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="76233-123">"**显示名称**" 是用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="76233-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="76233-124">你可以单击 "显示名称" 以转到 Microsoft 团队管理中心中的用户设置页面。</span><span class="sxs-lookup"><span data-stu-id="76233-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="76233-125">"**电话**" 表示分配给用户的号码。</span><span class="sxs-lookup"><span data-stu-id="76233-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="76233-126">"已**阻止" 原因**是阻止用户进行呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="76233-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="76233-127">**阻止的操作**告诉你用户是否被阻止或取消阻止在团队中进行 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="76233-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="76233-128">"**阻塞时间**" 是阻止用户进行呼叫的日期和时间（UTC）。</span><span class="sxs-lookup"><span data-stu-id="76233-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="76233-129">要查看希望在表格中显示的信息，请确保向表格添加了相关列。</span><span class="sxs-lookup"><span data-stu-id="76233-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="76233-130">**4**</span><span class="sxs-lookup"><span data-stu-id="76233-130">**4**</span></span>   |<span data-ttu-id="76233-131">选择“**编辑列**”可在表格中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="76233-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="76233-132">**5**</span><span class="sxs-lookup"><span data-stu-id="76233-132">**5**</span></span>   |<span data-ttu-id="76233-133">选择 "**全屏**" 以全屏模式查看报表。</span><span class="sxs-lookup"><span data-stu-id="76233-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="76233-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="76233-134">Related topics</span></span>

- [<span data-ttu-id="76233-135">Teams 分析和报告</span><span class="sxs-lookup"><span data-stu-id="76233-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)