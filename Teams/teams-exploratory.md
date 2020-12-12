---
title: 管理 Microsoft Teams Exploratory 体验
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 未获得 Microsoft Teams 许可的 Microsoft 365 或 Office 365 用户可以启动 Exploratory Teams 许可证。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: df06c03ab37a98c5ea4404d8dbd12703b07ad3ee
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611806"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="e33f8-103">管理 Microsoft Teams Exploratory 许可证</span><span class="sxs-lookup"><span data-stu-id="e33f8-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="e33f8-p101">Microsoft Teams 探索性体验让组织中拥有 Azure 域服务（Azure AD）但未获得 Teams 许可的用户可以启动 Teams 的探索性体验。管理员可以为其组织中的用户开启或关闭此功能。The Teams Exploratory体验现在已取代了早期的 [Microsoft 商业云试用版](iw-trial-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e33f8-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization. The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="e33f8-107">Teams Exploratory 体验中包含哪些服务</span><span class="sxs-lookup"><span data-stu-id="e33f8-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="e33f8-108">管理员将在 Teams Exploratory 体验中看到的服务计划有：</span><span class="sxs-lookup"><span data-stu-id="e33f8-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="e33f8-109">Exchange Online（计划 1)</span><span class="sxs-lookup"><span data-stu-id="e33f8-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="e33f8-110">适用于 Microsoft 365 或 Office 365 的流</span><span class="sxs-lookup"><span data-stu-id="e33f8-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="e33f8-111">MyAnalytics 提供的见解</span><span class="sxs-lookup"><span data-stu-id="e33f8-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="e33f8-112">Microsoft Forms（计划 E1）</span><span class="sxs-lookup"><span data-stu-id="e33f8-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="e33f8-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="e33f8-113">Microsoft Planner</span></span>
- <span data-ttu-id="e33f8-114">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="e33f8-114">Microsoft Search</span></span>
- <span data-ttu-id="e33f8-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="e33f8-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="e33f8-116">适用于 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream<sup>1</1></span><span class="sxs-lookup"><span data-stu-id="e33f8-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="e33f8-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e33f8-117">Microsoft Teams</span></span>
- <span data-ttu-id="e33f8-118">适用于 Microsoft 365 或 Office 365 的移动设备管理</span><span class="sxs-lookup"><span data-stu-id="e33f8-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="e33f8-119">适用于 Office 365 的 Office 移动应用</span><span class="sxs-lookup"><span data-stu-id="e33f8-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="e33f8-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="e33f8-120">Office Online</span></span>
- <span data-ttu-id="e33f8-121">适用于 Microsoft 365 或 Office 365 的 PowerApps</span><span class="sxs-lookup"><span data-stu-id="e33f8-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="e33f8-122">SharePoint Online（计划 1）</span><span class="sxs-lookup"><span data-stu-id="e33f8-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="e33f8-123">Sway</span><span class="sxs-lookup"><span data-stu-id="e33f8-123">Sway</span></span>
- <span data-ttu-id="e33f8-124">待办事项（计划 1）</span><span class="sxs-lookup"><span data-stu-id="e33f8-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="e33f8-125">Whiteboard（计划 1）</span><span class="sxs-lookup"><span data-stu-id="e33f8-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="e33f8-126">Yammer 企业版</span><span class="sxs-lookup"><span data-stu-id="e33f8-126">Yammer Enterprise</span></span>

  <span data-ttu-id="e33f8-127"><sup>1</sup> 将会议录制从 Microsoft Stream 改为 [OneDrive for Business 和 SharePoint](tmr-meeting-recording-change.md) 将是一种分阶段的方法。</span><span class="sxs-lookup"><span data-stu-id="e33f8-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="e33f8-128">启动时，你可以选择加入此体验。</span><span class="sxs-lookup"><span data-stu-id="e33f8-128">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="e33f8-129">在 11 月，如果想继续使用 Stream，你将必须选择退出。</span><span class="sxs-lookup"><span data-stu-id="e33f8-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="e33f8-130">2021 年初，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="e33f8-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="e33f8-131">符合资格的人员</span><span class="sxs-lookup"><span data-stu-id="e33f8-131">Who's eligible</span></span>

<span data-ttu-id="e33f8-132">用户符合 Teams 探索体验的标准，如果他们：</span><span class="sxs-lookup"><span data-stu-id="e33f8-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="e33f8-133">具有托管 Azure AD 域电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e33f8-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="e33f8-134">属于付费订阅的租户。</span><span class="sxs-lookup"><span data-stu-id="e33f8-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="e33f8-p103">必须启用用户注册应用程序和试用版（在 Microsoft 365 管理中心）。有关更多信息，请参见稍后在本文出现的[管理团队探索性体验](#manage-the-teams-exploratory-experience)。</span><span class="sxs-lookup"><span data-stu-id="e33f8-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="e33f8-137">谁没有资格使用</span><span class="sxs-lookup"><span data-stu-id="e33f8-137">Who isn't eligible</span></span>

<span data-ttu-id="e33f8-138">用户在以下情况下不适合条件：</span><span class="sxs-lookup"><span data-stu-id="e33f8-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="e33f8-139">目前或以前拥有的来自付费、未付费或试用版许可证的 Teams</span><span class="sxs-lookup"><span data-stu-id="e33f8-139">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="e33f8-140">位于至少已使用或收到一个特殊 COVID 优惠的租户中。</span><span class="sxs-lookup"><span data-stu-id="e33f8-140">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="e33f8-141">如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该服务。</span><span class="sxs-lookup"><span data-stu-id="e33f8-141">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="e33f8-142">如何注册 Teams 探索体验？</span><span class="sxs-lookup"><span data-stu-id="e33f8-142">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="e33f8-143">符合条件的用户可通过登录到 Teams 桌面版或 Web 版 ([teams.microsoft.com](https://teams.microsoft.com)) 来注册 Teams Exploratory 体验。</span><span class="sxs-lookup"><span data-stu-id="e33f8-143">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="e33f8-144">目前，不支持通过移动设备启用 Exploratory。</span><span class="sxs-lookup"><span data-stu-id="e33f8-144">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="e33f8-145">当他们注册时，系统将自动向其分配此许可证，并且租户管理员会在组织中有人首次启动 Teams Exploratory 体验时收到一封电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="e33f8-145">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="e33f8-146">管理 Teams 探索体验</span><span class="sxs-lookup"><span data-stu-id="e33f8-146">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="e33f8-147">Teams 探索体验设计为由单独的最终用户启动，你不能代表最终用户员工启动此服务。</span><span class="sxs-lookup"><span data-stu-id="e33f8-147">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="e33f8-p105">Teams Exploratory 体验自带 Exchange Online 许可证，但在管理员分配之前将不会分配给用户。如果用户还没有 Exchange 许可证，而管理员也未分配 Exchange Online 许可证，那么用户将无法在 Teams 中安排会议，并且可能会错过其他 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="e33f8-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="e33f8-150">管理员可以通过使用 **试用版应用和服务** 开关，禁用最终用户在其组织内运行 Teams 探索体验的功能。</span><span class="sxs-lookup"><span data-stu-id="e33f8-150">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="e33f8-151">阻止用户安装试用版应用和服务</span><span class="sxs-lookup"><span data-stu-id="e33f8-151">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="e33f8-152">可禁止用户安装试用版应用和服务，这会阻止用户运行 Teams 探索体验。</span><span class="sxs-lookup"><span data-stu-id="e33f8-152">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="e33f8-153">从 Microsoft 365 管理中心，转到“**设置**” > “**组织设置**”，选择“**服务**”，然后选择“**用户自有应用和服务**”。</span><span class="sxs-lookup"><span data-stu-id="e33f8-153">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![管理中心中“服务”页面的屏幕截图](media/iw-trial-services.png)

2. <span data-ttu-id="e33f8-155">清除“**允许用户安装试用版应用和服务**”的复选标记。</span><span class="sxs-lookup"><span data-stu-id="e33f8-155">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![管理中心中的“用户自有应用和服务”页面](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="e33f8-157">如果你的组织不符合获取 Teams 探索体验的条件，你将看不到“**允许用户安装试用版应用和服务**”选项。</span><span class="sxs-lookup"><span data-stu-id="e33f8-157">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="e33f8-158">为拥有包含 Teams 的许可证的用户管理可用性</span><span class="sxs-lookup"><span data-stu-id="e33f8-158">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="e33f8-p106">已分配到包含 Teams 许可证的用户尚无资格获得 Teams 探索体验。当 Teams 服务计划开启时，用户可以登录并使用 Teams。如果已禁用服务计划，则用户无法登录，并且无法使用 Teams 探索体验。你必须拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="e33f8-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="e33f8-163">关闭对 Teams 的访问：</span><span class="sxs-lookup"><span data-stu-id="e33f8-163">To turn off access to Teams:</span></span>

1. <span data-ttu-id="e33f8-164">在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="e33f8-164">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="e33f8-165">选择用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="e33f8-165">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="e33f8-166">在“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="e33f8-166">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="e33f8-167">在“**产品许可证**”窗格中，将开关切换为“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="e33f8-167">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理中心中的“产品许可证”页面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="e33f8-169">为已在使用 Teams 探索体验的用户管理 Teams 可用性</span><span class="sxs-lookup"><span data-stu-id="e33f8-169">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="e33f8-p107">如果用户正在运行 Teams Exploratory 体验，你可通过删除许可证或服务计划将其关闭。你必须拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="e33f8-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="e33f8-172">若要关闭 Teams 探索体验许可证，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e33f8-172">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="e33f8-173">在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="e33f8-173">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="e33f8-174">选择用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="e33f8-174">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="e33f8-175">在“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="e33f8-175">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="e33f8-176">在“**产品许可证**”窗格中，将此探索许可证的开关切换为“**关**”。</span><span class="sxs-lookup"><span data-stu-id="e33f8-176">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    >[!Note]
    ><span data-ttu-id="e33f8-177">组织中的第一位用户启动 Teams Exploratory 体验后，将显示 Teams Exploratory 切换开关。</span><span class="sxs-lookup"><span data-stu-id="e33f8-177">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="e33f8-178">为拥有 Teams 探索许可证的用户管理 Teams</span><span class="sxs-lookup"><span data-stu-id="e33f8-178">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="e33f8-p108">可以像管理拥有普通付费许可证的用户一样管理拥有 Teams Exploratory 许可证的用户。有关更多信息，请参见[为你的组织管理Teams 设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="e33f8-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="e33f8-181">从 Teams 探索许可证升级用户</span><span class="sxs-lookup"><span data-stu-id="e33f8-181">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="e33f8-182">要从 Teams 探索许可证升级用户（必须拥有管理员权限），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e33f8-182">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="e33f8-183">购买包含 Teams 的订阅。</span><span class="sxs-lookup"><span data-stu-id="e33f8-183">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="e33f8-184">删除用户的 Teams Exploratory 订阅。</span><span class="sxs-lookup"><span data-stu-id="e33f8-184">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="e33f8-185">分配新购买的许可证。</span><span class="sxs-lookup"><span data-stu-id="e33f8-185">Assign the newly purchased license.</span></span>

<span data-ttu-id="e33f8-186">有关详细信息，请参阅 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="e33f8-186">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="e33f8-p109">如果 Teams Exploratory 许可证已结束，而用户没有立即升级到包含 Teams 的订阅，则他们有 30 天的宽限期，在这 30 天之后就要删除数据。用户仍然存在于 Azure 域服务中。如果用户在宽限期内添加订阅，则一旦为用户分配了新的许可证以再次启用 Teams 功能，所有内容将仍然存在。</span><span class="sxs-lookup"><span data-stu-id="e33f8-p109">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="e33f8-190">这对旧版 Microsoft Teams 商业云试用版许可证有何影响</span><span class="sxs-lookup"><span data-stu-id="e33f8-190">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="e33f8-p110">从2020年2月起，符合条件的用户可以开始使用最新的 Microsoft Teams 探索版体验。所有遗留的 Teams 商业云试用许可证将在试用版期满前自动转换为新的优惠。</span><span class="sxs-lookup"><span data-stu-id="e33f8-p110">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience. All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="e33f8-p111">当用户首次登录过期的 Teams 商业云试用版时，我们会自动为这些用户分配一个 Teams 探索版体验授权。在用户在登录前不会转换。</span><span class="sxs-lookup"><span data-stu-id="e33f8-p111">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users. Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="e33f8-195">删除 Teams 探索许可证</span><span class="sxs-lookup"><span data-stu-id="e33f8-195">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="e33f8-196">如果要通过 PowerShell 删除此许可证，请参阅：[使用 Office 365 PowerShell 删除用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="e33f8-196">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="e33f8-197">如果要通过管理门户删除此许可证，请参阅：[从组织删除用户](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="e33f8-197">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="e33f8-198">什么是数据保留策略？</span><span class="sxs-lookup"><span data-stu-id="e33f8-198">What is the data retention policy</span></span>

<span data-ttu-id="e33f8-199">请参阅 [Microsoft 365 订阅信息](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="e33f8-199">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="e33f8-200">Teams 探索体验持续多长时间</span><span class="sxs-lookup"><span data-stu-id="e33f8-200">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="e33f8-201">Microsoft Teams 探索体验免费提供 12 个月（从初始用户注册开始），另外还有 30 天的宽限期。</span><span class="sxs-lookup"><span data-stu-id="e33f8-201">The Microsoft Teams Exploratory experience is available at no additional cost for 12 months (from initial user sign-up) plus an additional 30 day grace period.</span></span> <span data-ttu-id="e33f8-202">届时，Microsoft Exploratory 体验许可证的最终用户需要迁移到包含 Teams 的付费许可证。</span><span class="sxs-lookup"><span data-stu-id="e33f8-202">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="e33f8-203">相同的结束日期将适用于同一租户上的所有用户，12 个月期限从首个用户的注册日期开始。</span><span class="sxs-lookup"><span data-stu-id="e33f8-203">The same end date will apply to all users on the same tenant, with the 12-month term starting on the first user’s sign-up date.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="e33f8-204">如果最终用户刚好在我的周年纪念或续订日期前启动 Microsoft Teams 探索体验，会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="e33f8-204">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="e33f8-205">在 **协议周年日** 或 **续订** 后的 90 天内启动的 Microsoft Teams 探索体验许可证无需迁移到付费许可证，直到下一个周年日或续订周期。</span><span class="sxs-lookup"><span data-stu-id="e33f8-205">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="e33f8-206">如果我的协议没有周年日或每年的续约日期（例如逐月协议），该怎么办</span><span class="sxs-lookup"><span data-stu-id="e33f8-206">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="e33f8-207">对于无周年日或年度续订日期的协议，第一位最终用户后面的年份激活 Microsoft 团队探索体验许可证将被视为周年日或续订日期。</span><span class="sxs-lookup"><span data-stu-id="e33f8-207">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="e33f8-208">根据本文中所述的策略，必须在每年的此日期之前将拥有 Microsoft Teams 探索许可证的用户转换为付费许可证。</span><span class="sxs-lookup"><span data-stu-id="e33f8-208">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="e33f8-209">例如，如果第一位最终用户在 2020 年 6 月 19 日激活了 Microsoft Teams 探索，则他们和客户租户中的所有其他符合条件的用户必须在 2021 年 6月 19 日之前转换为 Teams 付费许可证。</span><span class="sxs-lookup"><span data-stu-id="e33f8-209">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="e33f8-210">在上一个探索体验许可证到期后的 3 个月内客户将被禁用并阻止开始新的探索试用许可证。</span><span class="sxs-lookup"><span data-stu-id="e33f8-210">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
