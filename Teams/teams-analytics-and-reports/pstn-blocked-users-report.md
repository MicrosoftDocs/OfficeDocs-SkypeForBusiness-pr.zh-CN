---
title: Microsoft TeamsPSTN 阻止的用户报告
author: cichur
ms.author: v-cichur
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
description: 使用管理中心中的 PSTN Microsoft Teams报告，大致了解组织阻止Teams PSTN 呼叫的用户。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809332"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="60ab5-103">Microsoft TeamsPSTN 阻止的用户报告</span><span class="sxs-lookup"><span data-stu-id="60ab5-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="60ab5-104">PSTN 管理中心中的 PSTN 阻止用户Microsoft Teams显示组织中被阻止在 Teams 中拨打 PSTN 呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="60ab5-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="60ab5-105">您可以查看有关每个被阻止用户（包括其分配的电话号码）和阻止他们进行呼叫的原因的信息。</span><span class="sxs-lookup"><span data-stu-id="60ab5-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="60ab5-106">查看 PSTN 阻止的用户报告</span><span class="sxs-lookup"><span data-stu-id="60ab5-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="60ab5-107">在管理中心的左侧导航Microsoft Teams，单击 **"分析**"&  >  **报告使用情况报告"。**</span><span class="sxs-lookup"><span data-stu-id="60ab5-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="60ab5-108">在"**查看报表"** 选项卡上的"报告 **"下**，选择 **"PSTN 阻止的用户"，** 然后单击"**运行报告"。**</span><span class="sxs-lookup"><span data-stu-id="60ab5-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="60ab5-109">![管理中心中 PSTN 阻止的用户报告报告的屏幕截图](../media/teams-reports-pstn-blocked-users-with-callouts.png "PSTN 阻止的用户报告的屏幕截图，Microsoft Teams带编号标注的用户")</span><span class="sxs-lookup"><span data-stu-id="60ab5-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="60ab5-110">解释报告</span><span class="sxs-lookup"><span data-stu-id="60ab5-110">Interpret the report</span></span>

|<span data-ttu-id="60ab5-111">标注</span><span class="sxs-lookup"><span data-stu-id="60ab5-111">Callout</span></span> |<span data-ttu-id="60ab5-112">说明</span><span class="sxs-lookup"><span data-stu-id="60ab5-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="60ab5-113">**1**</span><span class="sxs-lookup"><span data-stu-id="60ab5-113">**1**</span></span>   |<span data-ttu-id="60ab5-114">每个报表都有一个生成日期。</span><span class="sxs-lookup"><span data-stu-id="60ab5-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="60ab5-115">报表通常反映活动时间的 24 至 48 小时延迟。</span><span class="sxs-lookup"><span data-stu-id="60ab5-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="60ab5-116">**2**</span><span class="sxs-lookup"><span data-stu-id="60ab5-116">**2**</span></span>   |<span data-ttu-id="60ab5-117">X 轴是日期。</span><span class="sxs-lookup"><span data-stu-id="60ab5-117">The X axis is the date.</span></span> <span data-ttu-id="60ab5-118">Y 轴表示用户数。</span><span class="sxs-lookup"><span data-stu-id="60ab5-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="60ab5-119">将鼠标悬停在给定日期的点上，查看该日期被阻止的用户数。</span><span class="sxs-lookup"><span data-stu-id="60ab5-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="60ab5-120">**3**</span><span class="sxs-lookup"><span data-stu-id="60ab5-120">**3**</span></span>   |<span data-ttu-id="60ab5-121">下表提供了阻止进行 PSTN 呼叫的所有用户的细分。</span><span class="sxs-lookup"><span data-stu-id="60ab5-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="60ab5-122">它显示分配电话系统音频会议的所有用户，并提供有关每个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="60ab5-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="60ab5-123">**显示** 名称显示名称用户的名称。</span><span class="sxs-lookup"><span data-stu-id="60ab5-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="60ab5-124">可以单击显示名称转到管理中心中的用户设置Microsoft Teams页面。</span><span class="sxs-lookup"><span data-stu-id="60ab5-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="60ab5-125">**电话** 是分配给用户的数量。</span><span class="sxs-lookup"><span data-stu-id="60ab5-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="60ab5-126">**被阻止** 的原因是阻止用户进行调用的原因。</span><span class="sxs-lookup"><span data-stu-id="60ab5-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="60ab5-127">**阻止的操作** 会告知用户被阻止还是未阻止在 Teams 中拨打 PSTN。</span><span class="sxs-lookup"><span data-stu-id="60ab5-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="60ab5-128">**阻止时间** 是用户被 (UTC) 的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="60ab5-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="60ab5-129">要查看希望在表格中显示的信息，请确保向表格添加了相关列。</span><span class="sxs-lookup"><span data-stu-id="60ab5-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="60ab5-130">**4**</span><span class="sxs-lookup"><span data-stu-id="60ab5-130">**4**</span></span>   |<span data-ttu-id="60ab5-131">选择“**编辑列**”可在表格中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="60ab5-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="60ab5-132">**5**</span><span class="sxs-lookup"><span data-stu-id="60ab5-132">**5**</span></span>   |<span data-ttu-id="60ab5-133">选择 **"全屏** "以全屏模式查看报表。</span><span class="sxs-lookup"><span data-stu-id="60ab5-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="60ab5-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="60ab5-134">Related topics</span></span>

- [<span data-ttu-id="60ab5-135">Teams 分析和报告</span><span class="sxs-lookup"><span data-stu-id="60ab5-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)