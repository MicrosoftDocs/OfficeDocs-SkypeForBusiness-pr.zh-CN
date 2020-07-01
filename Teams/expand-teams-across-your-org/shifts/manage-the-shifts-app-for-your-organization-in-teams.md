---
title: 管理你的组织的倒班应用
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在组织中的一线工作人员的团队中设置和管理倒班应用。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ecc64c105bb9171942dfac912ccea4f2fa1442aa
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938351"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="f2f51-103">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="f2f51-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2f51-104">2020年6月30日生效，Microsoft StaffHub 已停用。</span><span class="sxs-lookup"><span data-stu-id="f2f51-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="f2f51-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="f2f51-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="f2f51-106">今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="f2f51-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="f2f51-107">StaffHub 已停止为2020年6月30日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="f2f51-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="f2f51-108">任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="f2f51-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="f2f51-109">若要了解详细信息，请参阅[Microsoft StaffHub 已停](microsoft-staffhub-to-be-retired.md)用。</span><span class="sxs-lookup"><span data-stu-id="f2f51-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="f2f51-110">倒班概述</span><span class="sxs-lookup"><span data-stu-id="f2f51-110">Overview of Shifts</span></span>

<span data-ttu-id="f2f51-111">Microsoft 团队中的 "移动" 应用让一线工作人员保持连接和同步。它首先构建了移动，为团队提供快速、有效的时间管理和沟通。</span><span class="sxs-lookup"><span data-stu-id="f2f51-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="f2f51-112">倒班让一线工作者和他们的经理使用自己的移动设备管理计划和保持联系。</span><span class="sxs-lookup"><span data-stu-id="f2f51-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="f2f51-113">经理负责创建、更新和管理团队的倒班计划。</span><span class="sxs-lookup"><span data-stu-id="f2f51-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="f2f51-114">他们可以向一个人发送消息（"在地面上有溢出"）或整个团队（"区域 GM 在20分钟内送达"）。</span><span class="sxs-lookup"><span data-stu-id="f2f51-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="f2f51-115">他们还可以发送策略文档、新闻公告和视频。</span><span class="sxs-lookup"><span data-stu-id="f2f51-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="f2f51-116">员工查看他们的即将到来的班次，可查看当天安排的其他人、请求交换或提供班次，以及请求下班时间。</span><span class="sxs-lookup"><span data-stu-id="f2f51-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="f2f51-117">请务必知道当前班次不支持来宾用户。</span><span class="sxs-lookup"><span data-stu-id="f2f51-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="f2f51-118">这意味着在团队中启用来宾访问时，无法将团队中的来宾添加到或使用倒班计划。</span><span class="sxs-lookup"><span data-stu-id="f2f51-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="f2f51-119">倒班的可用性</span><span class="sxs-lookup"><span data-stu-id="f2f51-119">Availability of Shifts</span></span>

<span data-ttu-id="f2f51-120">倒班在所有企业版 Sku 可用，其中有团队可用。</span><span class="sxs-lookup"><span data-stu-id="f2f51-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="f2f51-121">倒班数据的位置</span><span class="sxs-lookup"><span data-stu-id="f2f51-121">Location of Shifts data</span></span>

<span data-ttu-id="f2f51-122">倒班数据当前存储在北美、西欧和亚太地区数据中心的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="f2f51-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="f2f51-123">有关存储数据的位置的详细信息，请参阅[我的数据在哪里](http://o365datacentermap.azurewebsites.net/)？</span><span class="sxs-lookup"><span data-stu-id="f2f51-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="f2f51-124">设置倒班</span><span class="sxs-lookup"><span data-stu-id="f2f51-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="f2f51-125">启用或禁用组织中的班次</span><span class="sxs-lookup"><span data-stu-id="f2f51-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="f2f51-126">默认情况下，将为组织中的所有团队用户启用倒班。</span><span class="sxs-lookup"><span data-stu-id="f2f51-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="f2f51-127">你可以在 Microsoft 团队管理中心的 "[管理应用](../../manage-apps.md)" 页面上，关闭或打开组织级别的应用。</span><span class="sxs-lookup"><span data-stu-id="f2f51-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="f2f51-128">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="f2f51-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="f2f51-129">在应用列表中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f2f51-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="f2f51-130">若要为你的组织关闭班次，请搜索 "倒班" 应用，选择它，然后单击 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="f2f51-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="f2f51-131">若要为你的组织启用倒班，请搜索 "倒班" 应用，选择它，然后单击 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="f2f51-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="f2f51-132">启用或禁用组织中特定用户的班次</span><span class="sxs-lookup"><span data-stu-id="f2f51-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="f2f51-133">若要允许或阻止组织中的特定用户使用倒班，请确保在 "[管理应用](../../manage-apps.md)" 页面上为你的组织启用了班次，然后创建自定义应用权限策略并将其分配给这些用户。</span><span class="sxs-lookup"><span data-stu-id="f2f51-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="f2f51-134">若要了解详细信息，请参阅[管理团队中的应用权限策略](../../teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f2f51-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="f2f51-135">使用 FirstlineWorker 应用设置策略固定对团队的倒班</span><span class="sxs-lookup"><span data-stu-id="f2f51-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="f2f51-136">应用设置策略允许你自定义团队，以突出显示你的组织中的用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="f2f51-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="f2f51-137">策略中设置的应用将固定到应用程序栏，应用栏 &mdash; 位于团队桌面客户端和团队移动客户端的底部， &mdash; 用户可在其中快速轻松地访问它们。</span><span class="sxs-lookup"><span data-stu-id="f2f51-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="f2f51-138">团队包括一个内置的 FirstlineWorker 应用设置策略，可分配给你的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="f2f51-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="f2f51-139">默认情况下，该策略包括活动、班次、聊天和呼叫应用。</span><span class="sxs-lookup"><span data-stu-id="f2f51-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="f2f51-140">若要查看 FirstlineWorker 策略，请在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **应用" 设置策略**。</span><span class="sxs-lookup"><span data-stu-id="f2f51-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="f2f51-141">![FirstlineWorker 应用设置策略的屏幕截图](../../media/firstline-worker-app-setup-policy.png "Microsoft 团队管理中心中的 FirstlineWorker 应用设置策略的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="f2f51-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="f2f51-142">将 FirstlineWorker 应用设置策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="f2f51-142">Assign the FirstlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="f2f51-143">在审核日志中搜索倒班事件</span><span class="sxs-lookup"><span data-stu-id="f2f51-143">Search the audit log for Shifts events</span></span>

<span data-ttu-id="f2f51-144">**（处于预览阶段）**</span><span class="sxs-lookup"><span data-stu-id="f2f51-144">**(in preview)**</span></span>

<span data-ttu-id="f2f51-145">您可以在您的组织中搜索 "审核日志" 以查看倒班活动。</span><span class="sxs-lookup"><span data-stu-id="f2f51-145">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="f2f51-146">若要了解有关如何搜索审核日志和查看审核日志中记录的[班次活动](../../audit-log-events.md#shifts-in-teams-activities)列表的详细信息，请参阅[在审核日志中搜索团队中的事件](../../audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="f2f51-146">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="f2f51-147">在搜索审核日志之前，必须先在[安全 & 合规中心](https://protection.office.com)启用审核。</span><span class="sxs-lookup"><span data-stu-id="f2f51-147">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="f2f51-148">若要了解详细信息，请参阅[打开或关闭审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="f2f51-148">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="f2f51-149">请记住，审核数据仅在你打开审核的位置可用。</span><span class="sxs-lookup"><span data-stu-id="f2f51-149">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2f51-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="f2f51-150">Related topics</span></span>

- [<span data-ttu-id="f2f51-151">倒班一线工作者的帮助</span><span class="sxs-lookup"><span data-stu-id="f2f51-151">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="f2f51-152">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="f2f51-152">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
