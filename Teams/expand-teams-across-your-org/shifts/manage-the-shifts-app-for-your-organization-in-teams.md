---
title: 管理组织的 Shifts 应用
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 了解如何在 Teams 中为组织的一线员工设置和管理 Shifts 应用。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909086"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="b8487-103">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="b8487-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8487-104">自 2020 年 6 月 30 起，Microsoft StaffHub 已停用。</span><span class="sxs-lookup"><span data-stu-id="b8487-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="b8487-105">我们正在将 StaffHub 功能构建到 Microsoft Teams 中。</span><span class="sxs-lookup"><span data-stu-id="b8487-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b8487-106">目前，Teams 包含用于计划管理的 Shifts 应用，其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="b8487-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b8487-107">StaffHub 于 2020 年 6 月 30 日停止为所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="b8487-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="b8487-108">尝试打开 StaffHub 的任何人都会显示一条消息，指示他们下载 Teams。</span><span class="sxs-lookup"><span data-stu-id="b8487-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="b8487-109">有关详细信息，请参阅 [Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="b8487-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="b8487-110">班次概述</span><span class="sxs-lookup"><span data-stu-id="b8487-110">Overview of Shifts</span></span>

<span data-ttu-id="b8487-111">Microsoft Teams 中的 Shifts 应用可使一线员工保持连接和同步。它首先构建为移动版，为团队提供快速高效的时间管理和通信。</span><span class="sxs-lookup"><span data-stu-id="b8487-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="b8487-112">排班可让一线员工及其经理使用其移动设备管理日程安排并保持联系。</span><span class="sxs-lookup"><span data-stu-id="b8487-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="b8487-113">经理为团队创建、更新和管理排班计划。</span><span class="sxs-lookup"><span data-stu-id="b8487-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="b8487-114">他们可以向一个人发送消息 ("楼层溢出") 或者整个团队 ("区域 GM 在 20 分钟内到达") 。</span><span class="sxs-lookup"><span data-stu-id="b8487-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="b8487-115">他们还可以发送策略文档、新闻公告和视频。</span><span class="sxs-lookup"><span data-stu-id="b8487-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="b8487-116">员工查看即将到来的排班、查看安排当天的其他人、调班或调班的请求，以及请求请假。</span><span class="sxs-lookup"><span data-stu-id="b8487-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="b8487-117">必须知道 Shifts 当前不支持来宾用户。</span><span class="sxs-lookup"><span data-stu-id="b8487-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="b8487-118">这意味着在 Teams 中启用来宾访问时，无法将团队中的来宾添加到或使用排班计划。</span><span class="sxs-lookup"><span data-stu-id="b8487-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="b8487-119">有关不同平台上的 Shifts 功能的详细信息，请参阅["按平台显示 Teams 功能"。](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="b8487-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="b8487-120">班次的可用性</span><span class="sxs-lookup"><span data-stu-id="b8487-120">Availability of Shifts</span></span>

<span data-ttu-id="b8487-121">班次在 Teams 可用的所有企业 SKUS 中可用。</span><span class="sxs-lookup"><span data-stu-id="b8487-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="b8487-122">Shifts 数据的位置</span><span class="sxs-lookup"><span data-stu-id="b8487-122">Location of Shifts data</span></span>

<span data-ttu-id="b8487-123">Shifts 数据当前存储在 Azure 中，位于北美、西欧和亚太的数据中心。</span><span class="sxs-lookup"><span data-stu-id="b8487-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="b8487-124">有关数据存储位置详细信息，请参阅 ["我的数据在哪里](http://o365datacentermap.azurewebsites.net/)？"</span><span class="sxs-lookup"><span data-stu-id="b8487-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="b8487-125">设置班次</span><span class="sxs-lookup"><span data-stu-id="b8487-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="b8487-126">在组织中启用或禁用 Shifts</span><span class="sxs-lookup"><span data-stu-id="b8487-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="b8487-127">默认情况下，为组织的所有 Teams 用户启用班次。</span><span class="sxs-lookup"><span data-stu-id="b8487-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="b8487-128">可以在 Microsoft Teams 管理中心的"管理应用"页面上关闭或[](../../manage-apps.md)打开组织级别的应用。</span><span class="sxs-lookup"><span data-stu-id="b8487-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b8487-129">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="b8487-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="b8487-130">在应用列表中，执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="b8487-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="b8487-131">若要为组织关闭 Shifts，请搜索 Shifts 应用，将其选中，然后选择"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="b8487-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="b8487-132">若要为组织启用 Shifts，请搜索 Shifts 应用，将其选中，然后选择"允许 **"。**</span><span class="sxs-lookup"><span data-stu-id="b8487-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="b8487-133">为组织中特定用户启用或禁用 Shifts</span><span class="sxs-lookup"><span data-stu-id="b8487-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="b8487-134">若要允许或阻止组织中特定用户使用 Shifts，请确保在"管理应用"页面上为组织启用 Shifts，然后创建自定义[](../../manage-apps.md)应用权限策略并将其分配给这些用户。</span><span class="sxs-lookup"><span data-stu-id="b8487-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="b8487-135">若要了解有关详细信息，请参阅["在 Teams 中管理应用权限策略"。](../../teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b8487-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="b8487-136">使用 FrontlineWorker 应用设置策略将 Shifts 固定到 Teams</span><span class="sxs-lookup"><span data-stu-id="b8487-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="b8487-137">应用设置策略可让你自定义 Teams，以突出显示对组织中用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="b8487-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="b8487-138">策略中设置的应用将固定到 Teams 桌面客户端一侧的应用栏和 Teams 移动客户端的底部，用户可以在这里快速 &mdash; &mdash; 轻松地访问它们。</span><span class="sxs-lookup"><span data-stu-id="b8487-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="b8487-139">Teams 包括内置 FrontlineWorker 应用设置策略，可将其分配给组织的前端工作者。</span><span class="sxs-lookup"><span data-stu-id="b8487-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="b8487-140">默认情况下，该策略包括活动、Shifts、聊天和呼叫应用。</span><span class="sxs-lookup"><span data-stu-id="b8487-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="b8487-141">若要查看 FrontlineWorker 策略，在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams 应用**  >  **应用设置策略**。</span><span class="sxs-lookup"><span data-stu-id="b8487-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="b8487-142">![FrontlineWorker 应用设置策略的屏幕截图](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理中心中 FrontlineWorker 应用设置策略的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="b8487-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="b8487-143">将 FrontlineWorker 应用设置策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="b8487-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="b8487-144">在审核日志搜索 Shifts 事件</span><span class="sxs-lookup"><span data-stu-id="b8487-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="b8487-145">**（处于预览阶段）**</span><span class="sxs-lookup"><span data-stu-id="b8487-145">**(in preview)**</span></span>

<span data-ttu-id="b8487-146">可以搜索审核日志查看组织中 Shifts 活动。</span><span class="sxs-lookup"><span data-stu-id="b8487-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="b8487-147">若要详细了解如何搜索 审核日志并查看记录在 审核日志 中的 [Shifts](../../audit-log-events.md#shifts-in-teams-activities) 活动列表，请参阅"在 审核日志 中搜索 [活动](../../audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="b8487-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="b8487-148">在搜索安全中心审核日志，首先在安全与合规中心& [审核](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="b8487-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="b8487-149">若要了解有关详细信息，请参阅 [审核日志打开或关闭搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="b8487-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="b8487-150">请记住，只有启用审核时，审核数据才可用。</span><span class="sxs-lookup"><span data-stu-id="b8487-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8487-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="b8487-151">Related topics</span></span>

- [<span data-ttu-id="b8487-152">一线员工排班帮助</span><span class="sxs-lookup"><span data-stu-id="b8487-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="b8487-153">在 Teams 中向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b8487-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
