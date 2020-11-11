---
title: 在 Microsoft Teams 中设置假日
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: 了解如何在 Microsoft 团队中设置用于自动助理的假日。
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993468"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="877a1-103">在 Microsoft Teams 中设置假日</span><span class="sxs-lookup"><span data-stu-id="877a1-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="877a1-104">你可以使用 "团队假日" 功能来提供备用消息，并向呼叫者发送特定日期和时间的呼叫者，以便在部门、呼叫队列或组织中的人员关注不同的工作时间，或者不提供。</span><span class="sxs-lookup"><span data-stu-id="877a1-104">You can use the Teams Holidays feature to provide alternate messages and routing to callers for specific dates and times when departments, call queues or people in your organization will be following different working hours or won't be available.</span></span> <span data-ttu-id="877a1-105">例如，你可能会在你的组织关闭时为新年日历创建一个假期。</span><span class="sxs-lookup"><span data-stu-id="877a1-105">For example, you might create a holiday for New Year's day when your organization may be closed.</span></span>

<span data-ttu-id="877a1-106">您在此处创建的假日在 [设置自动助理](create-a-phone-system-auto-attendant.md)时可用，每个人都有自己的问候语和呼叫路由设置。</span><span class="sxs-lookup"><span data-stu-id="877a1-106">The holidays you create here are available when you [set up an auto attendant](create-a-phone-system-auto-attendant.md), each with its own greeting and call routing settings.</span></span>

## <a name="create-a-holiday"></a><span data-ttu-id="877a1-107">创建节日</span><span class="sxs-lookup"><span data-stu-id="877a1-107">Create a holiday</span></span>

<span data-ttu-id="877a1-108">创建假日</span><span class="sxs-lookup"><span data-stu-id="877a1-108">To create a holiday</span></span>

1. <span data-ttu-id="877a1-109">在 "Microsoft 团队管理中心" 中，转到 " **组织范围的设置**  >  **假日** "。</span><span class="sxs-lookup"><span data-stu-id="877a1-109">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="877a1-110">选择 " **新建假日** "。</span><span class="sxs-lookup"><span data-stu-id="877a1-110">Select **New holiday**.</span></span>

3. <span data-ttu-id="877a1-111">输入假日的名称。</span><span class="sxs-lookup"><span data-stu-id="877a1-111">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="877a1-112">选择 " **添加新日期** "。</span><span class="sxs-lookup"><span data-stu-id="877a1-112">Select **Add new date**.</span></span>

5. <span data-ttu-id="877a1-113">在 " **开始时间** " 下，选择日历图标，然后选择希望假日开始的日期。</span><span class="sxs-lookup"><span data-stu-id="877a1-113">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

6. <span data-ttu-id="877a1-114">使用下拉列表选择假日的开始时间。</span><span class="sxs-lookup"><span data-stu-id="877a1-114">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="877a1-115">在 " **结束时间** " 下，选择日历图标，然后选择希望假日结束的日期。</span><span class="sxs-lookup"><span data-stu-id="877a1-115">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span>

8. <span data-ttu-id="877a1-116">使用下拉列表选择节假日的结束时间。</span><span class="sxs-lookup"><span data-stu-id="877a1-116">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="877a1-117">**结束时间** 必须晚于 **开始时间** 。</span><span class="sxs-lookup"><span data-stu-id="877a1-117">The **End time** must be after the **Start time**.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="877a1-118">如果该假日适用于一个全天 (即24小时内) ，则 " **结束时间** " 应设置为 "下一天"，时间设置为 12:00 AM。</span><span class="sxs-lookup"><span data-stu-id="877a1-118">If the holiday is for one full day (i.e., a 24 hour period), the **End time** should be set to the next day and the time to 12:00 AM.</span></span> <span data-ttu-id="877a1-119">例如，如果您的组织在新的一年1月1日关闭，请将 **开始时间** 设置为 1 12:00 年1月，并将 **结束时间** 设置为1月2日 @ 12:00 AM。</span><span class="sxs-lookup"><span data-stu-id="877a1-119">For example, if your organization is closed on January 1 for New Year's day, set the **Start time** to January 1 12:00 AM and set the **End time** to January 2 @ 12:00 AM.</span></span>

9. <span data-ttu-id="877a1-120">（可选）为定期假日添加更多日期。</span><span class="sxs-lookup"><span data-stu-id="877a1-120">Optionally, add more dates for recurring holidays.</span></span>

10. <span data-ttu-id="877a1-121">选择 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="877a1-121">Select **Save**.</span></span>

    ![日期设置为三年的假日用户界面的屏幕截图](media/holidays-set-up.png)

## <a name="change-a-holiday"></a><span data-ttu-id="877a1-123">更改假日</span><span class="sxs-lookup"><span data-stu-id="877a1-123">Change a holiday</span></span>

<span data-ttu-id="877a1-124">更改假日</span><span class="sxs-lookup"><span data-stu-id="877a1-124">To change a holiday</span></span>

1. <span data-ttu-id="877a1-125">在 "Microsoft 团队管理中心" 中，转到 " **组织范围的设置**  >  **假日** "。</span><span class="sxs-lookup"><span data-stu-id="877a1-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="877a1-126">从列表中选择该假日。</span><span class="sxs-lookup"><span data-stu-id="877a1-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="877a1-127">在 " **开始时间** " 下，选择日历图标，然后选择希望假日开始的日期。</span><span class="sxs-lookup"><span data-stu-id="877a1-127">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

4. <span data-ttu-id="877a1-128">使用下拉列表选择假日的开始时间。</span><span class="sxs-lookup"><span data-stu-id="877a1-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="877a1-129">在 " **结束时间** " 下，选择日历图标，然后选择希望假日结束的日期。</span><span class="sxs-lookup"><span data-stu-id="877a1-129">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span> 

6. <span data-ttu-id="877a1-130">使用下拉列表选择节假日的结束时间。</span><span class="sxs-lookup"><span data-stu-id="877a1-130">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="877a1-131">**结束时间** 必须晚于 **开始时间** 。</span><span class="sxs-lookup"><span data-stu-id="877a1-131">The **End time** must be after the **Start time**.</span></span>  

7. <span data-ttu-id="877a1-132">选择 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="877a1-132">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="877a1-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="877a1-133">Related topics</span></span>

<span data-ttu-id="877a1-134">[规划团队自动助理和呼叫队列](plan-auto-attendant-call-queue.md)？</span><span class="sxs-lookup"><span data-stu-id="877a1-134">[Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md)?</span></span>
