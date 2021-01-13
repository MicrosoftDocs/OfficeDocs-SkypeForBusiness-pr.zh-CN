---
title: Microsoft Teams PSTN 阻止的用户报告
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
description: 使用 Microsoft Teams 管理中心中的 PSTN 阻止用户报告，大致了解被阻止进行 PSTN 呼叫的组织的 Teams 用户。
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
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="7e4c0-103">Microsoft Teams PSTN 阻止的用户报告</span><span class="sxs-lookup"><span data-stu-id="7e4c0-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="7e4c0-104">Microsoft Teams 管理中心中的 PSTN 被阻止用户报告显示组织中被阻止在 Teams 中拨打 PSTN 呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="7e4c0-105">您可以查看有关每个被阻止用户（包括其分配的电话号码）以及阻止他们进行呼叫的原因的信息。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="7e4c0-106">查看 PSTN 阻止的用户报告</span><span class="sxs-lookup"><span data-stu-id="7e4c0-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="7e4c0-107">在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"分析&报告**  >  **使用情况报告**。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="7e4c0-108">在"**查看报告"** 选项卡上的 **"报告"** 下，选择 **"PSTN 阻止** 的用户"，然后单击"运行 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="7e4c0-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="7e4c0-109">![管理中心中 PSTN 阻止的用户报告报告的屏幕截图](../media/teams-reports-pstn-blocked-users-with-callouts.png "Microsoft Teams 管理中心中 PSTN 被阻止的用户报告的屏幕截图，其中标注编号")</span><span class="sxs-lookup"><span data-stu-id="7e4c0-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="7e4c0-110">解释报告</span><span class="sxs-lookup"><span data-stu-id="7e4c0-110">Interpret the report</span></span>

|<span data-ttu-id="7e4c0-111">标注</span><span class="sxs-lookup"><span data-stu-id="7e4c0-111">Callout</span></span> |<span data-ttu-id="7e4c0-112">说明</span><span class="sxs-lookup"><span data-stu-id="7e4c0-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="7e4c0-113">**1**</span><span class="sxs-lookup"><span data-stu-id="7e4c0-113">**1**</span></span>   |<span data-ttu-id="7e4c0-114">每个报表都有一个生成日期。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="7e4c0-115">报表通常反映活动时间的 24 至 48 小时延迟。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="7e4c0-116">**2**</span><span class="sxs-lookup"><span data-stu-id="7e4c0-116">**2**</span></span>   |<span data-ttu-id="7e4c0-117">X 轴是日期。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-117">The X axis is the date.</span></span> <span data-ttu-id="7e4c0-118">Y 轴表示用户数。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="7e4c0-119">将鼠标悬停在给定日期上的点上以查看该日期被阻止的用户数。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="7e4c0-120">**3**</span><span class="sxs-lookup"><span data-stu-id="7e4c0-120">**3**</span></span>   |<span data-ttu-id="7e4c0-121">下表提供了阻止进行 PSTN 呼叫的所有用户的细分。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="7e4c0-122">它显示分配有电话系统或音频会议的所有用户，并为你提供有关每个用户的信息。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="7e4c0-123">**显示** 名称显示名称用户的名称。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="7e4c0-124">可以单击显示名称转到 Microsoft Teams 管理中心中的用户设置页面。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="7e4c0-125">**电话** 是分配给用户的号码。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="7e4c0-126">**被阻止** 的原因是阻止用户进行调用的原因。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="7e4c0-127">**阻止的操作**  会告知用户被阻止还是被阻止在 Teams 中拨打 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="7e4c0-128">**阻止时间** 是用户被 (UTC) 的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="7e4c0-129">要查看希望在表格中显示的信息，请确保向表格添加了相关列。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="7e4c0-130">**4**</span><span class="sxs-lookup"><span data-stu-id="7e4c0-130">**4**</span></span>   |<span data-ttu-id="7e4c0-131">选择“**编辑列**”可在表格中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="7e4c0-132">**5**</span><span class="sxs-lookup"><span data-stu-id="7e4c0-132">**5**</span></span>   |<span data-ttu-id="7e4c0-133">选择 **"全屏** "以全屏模式查看报表。</span><span class="sxs-lookup"><span data-stu-id="7e4c0-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="7e4c0-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="7e4c0-134">Related topics</span></span>

- [<span data-ttu-id="7e4c0-135">Teams 分析和报告</span><span class="sxs-lookup"><span data-stu-id="7e4c0-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)