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
ms.openlocfilehash: ff84b1dc161aa5b8ab99a74509fa7a93a1a9b270
ms.sourcegitcommit: 6e492297a886ff8c7894a6469965e63d1b806184
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2021
ms.locfileid: "51399139"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="af513-103">管理 Microsoft Teams Exploratory 许可证</span><span class="sxs-lookup"><span data-stu-id="af513-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="af513-104">借助 Microsoft Teams 探索 体验，组织中拥有 Azure Active Directory (Azure AD) 且未获得 Teams 许可的用户可以启用 Teams 的探索体验。</span><span class="sxs-lookup"><span data-stu-id="af513-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="af513-105">管理员可以为组织中的用户打开或关闭此功能。</span><span class="sxs-lookup"><span data-stu-id="af513-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="af513-106">以前的 [Microsoft 商业云试用版]() 现已替换为 Teams 探索体验。</span><span class="sxs-lookup"><span data-stu-id="af513-106">The earlier [Microsoft Commercial Cloud Trial]() is now replaced by the Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="af513-107">Teams Exploratory 体验中包含哪些服务</span><span class="sxs-lookup"><span data-stu-id="af513-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="af513-108">管理员将在 Teams Exploratory 体验中看到的服务计划有：</span><span class="sxs-lookup"><span data-stu-id="af513-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="af513-109">Exchange Online（计划 1)</span><span class="sxs-lookup"><span data-stu-id="af513-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="af513-110">适用于 Microsoft 365 或 Office 365 的流</span><span class="sxs-lookup"><span data-stu-id="af513-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="af513-111">MyAnalytics 提供的见解</span><span class="sxs-lookup"><span data-stu-id="af513-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="af513-112">Microsoft Forms（计划 E1）</span><span class="sxs-lookup"><span data-stu-id="af513-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="af513-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="af513-113">Microsoft Planner</span></span>
- <span data-ttu-id="af513-114">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="af513-114">Microsoft Search</span></span>
- <span data-ttu-id="af513-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="af513-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="af513-116">适用于 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream<sup>1</1></span><span class="sxs-lookup"><span data-stu-id="af513-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="af513-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af513-117">Microsoft Teams</span></span>
- <span data-ttu-id="af513-118">适用于 Microsoft 365 或 Office 365 的移动设备管理</span><span class="sxs-lookup"><span data-stu-id="af513-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="af513-119">适用于 Office 365 的 Office 移动应用</span><span class="sxs-lookup"><span data-stu-id="af513-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="af513-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="af513-120">Office Online</span></span>
- <span data-ttu-id="af513-121">适用于 Microsoft 365 或 Office 365 的 PowerApps</span><span class="sxs-lookup"><span data-stu-id="af513-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="af513-122">SharePoint Online（计划 1）</span><span class="sxs-lookup"><span data-stu-id="af513-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="af513-123">Sway</span><span class="sxs-lookup"><span data-stu-id="af513-123">Sway</span></span>
- <span data-ttu-id="af513-124">待办事项（计划 1）</span><span class="sxs-lookup"><span data-stu-id="af513-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="af513-125">Whiteboard（计划 1）</span><span class="sxs-lookup"><span data-stu-id="af513-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="af513-126">Yammer 企业版</span><span class="sxs-lookup"><span data-stu-id="af513-126">Yammer Enterprise</span></span>

  <span data-ttu-id="af513-127"><sup>1</sup> 将会议录制从 Microsoft Stream 改为 [OneDrive for Business 和 SharePoint](tmr-meeting-recording-change.md) 将是一种分阶段的方法。</span><span class="sxs-lookup"><span data-stu-id="af513-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="af513-128">启动时，你可以选择加入此体验。</span><span class="sxs-lookup"><span data-stu-id="af513-128">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="af513-129">在 11 月，如果想继续使用 Stream，你将必须选择退出。</span><span class="sxs-lookup"><span data-stu-id="af513-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="af513-130">2021 年初，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="af513-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="af513-131">符合资格的人员</span><span class="sxs-lookup"><span data-stu-id="af513-131">Who's eligible</span></span>

<span data-ttu-id="af513-132">用户符合 Teams 探索体验的标准，如果他们：</span><span class="sxs-lookup"><span data-stu-id="af513-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="af513-133">具有托管 Azure AD 域电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="af513-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="af513-134">属于付费订阅的租户。</span><span class="sxs-lookup"><span data-stu-id="af513-134">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="af513-135">没有有效的 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="af513-135">Do not have an active Teams license.</span></span>
- <span data-ttu-id="af513-136">不在创建许可证分配策略的租户中。</span><span class="sxs-lookup"><span data-stu-id="af513-136">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="af513-p103">必须启用用户注册应用程序和试用版（在 Microsoft 365 管理中心）。有关更多信息，请参见稍后在本文出现的[管理团队探索性体验](#manage-the-teams-exploratory-experience)。</span><span class="sxs-lookup"><span data-stu-id="af513-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="af513-139">谁没有资格使用</span><span class="sxs-lookup"><span data-stu-id="af513-139">Who isn't eligible</span></span>

<span data-ttu-id="af513-140">用户在以下情况下不适合条件：</span><span class="sxs-lookup"><span data-stu-id="af513-140">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="af513-141">目前或以前拥有的来自付费、未付费或试用版许可证的 Teams</span><span class="sxs-lookup"><span data-stu-id="af513-141">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="af513-142">位于至少已使用或收到一个特殊 COVID 优惠的租户中。</span><span class="sxs-lookup"><span data-stu-id="af513-142">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="af513-143">如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该服务。</span><span class="sxs-lookup"><span data-stu-id="af513-143">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="af513-144">如何注册 Teams 探索体验？</span><span class="sxs-lookup"><span data-stu-id="af513-144">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="af513-145">符合条件的用户可通过登录到 Teams 桌面版或 Web 版 ([teams.microsoft.com](https://teams.microsoft.com)) 来注册 Teams Exploratory 体验。</span><span class="sxs-lookup"><span data-stu-id="af513-145">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="af513-146">目前，不支持通过移动设备启用 Exploratory。</span><span class="sxs-lookup"><span data-stu-id="af513-146">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="af513-147">当他们注册时，系统将自动向其分配此许可证，并且租户管理员会在组织中有人首次启动 Teams Exploratory 体验时收到一封电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="af513-147">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="af513-148">管理 Teams 探索体验</span><span class="sxs-lookup"><span data-stu-id="af513-148">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="af513-149">Teams 探索体验设计为由单独的最终用户启动，你不能代表最终用户员工启动此服务。</span><span class="sxs-lookup"><span data-stu-id="af513-149">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="af513-p105">Teams Exploratory 体验自带 Exchange Online 许可证，但在管理员分配之前将不会分配给用户。如果用户还没有 Exchange 许可证，而管理员也未分配 Exchange Online 许可证，那么用户将无法在 Teams 中安排会议，并且可能会错过其他 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="af513-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="af513-152">管理员可以通过使用 **试用版应用和服务** 开关，禁用最终用户在其组织内运行 Teams 探索体验的功能。</span><span class="sxs-lookup"><span data-stu-id="af513-152">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="af513-153">阻止用户安装试用版应用和服务</span><span class="sxs-lookup"><span data-stu-id="af513-153">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="af513-154">可禁止用户安装试用版应用和服务，这会阻止用户运行 Teams 探索体验。</span><span class="sxs-lookup"><span data-stu-id="af513-154">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="af513-155">从 Microsoft 365 管理中心，转到“**设置**” > “**组织设置**”，选择“**服务**”，然后选择“**用户自有应用和服务**”。</span><span class="sxs-lookup"><span data-stu-id="af513-155">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![管理中心中“服务”页面的屏幕截图](media/iw-trial-services.png)

2. <span data-ttu-id="af513-157">清除“**允许用户安装试用版应用和服务**”的复选标记。</span><span class="sxs-lookup"><span data-stu-id="af513-157">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![管理中心中的“用户自有应用和服务”页面](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="af513-159">如果你的组织不符合获取 Teams 探索体验的条件，你将看不到“**允许用户安装试用版应用和服务**”选项。</span><span class="sxs-lookup"><span data-stu-id="af513-159">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="af513-160">为拥有包含 Teams 的许可证的用户管理可用性</span><span class="sxs-lookup"><span data-stu-id="af513-160">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="af513-p106">已分配到包含 Teams 许可证的用户尚无资格获得 Teams 探索体验。当 Teams 服务计划开启时，用户可以登录并使用 Teams。如果已禁用服务计划，则用户无法登录，并且无法使用 Teams 探索体验。你必须拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="af513-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="af513-165">关闭对 Teams 的访问：</span><span class="sxs-lookup"><span data-stu-id="af513-165">To turn off access to Teams:</span></span>

1. <span data-ttu-id="af513-166">在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="af513-166">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="af513-167">选择用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="af513-167">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="af513-168">在“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="af513-168">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="af513-169">在“**产品许可证**”窗格中，将开关切换为“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="af513-169">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理中心中的“产品许可证”页面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="af513-171">为已在使用 Teams 探索体验的用户管理 Teams 可用性</span><span class="sxs-lookup"><span data-stu-id="af513-171">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="af513-p107">如果用户正在运行 Teams Exploratory 体验，你可通过删除许可证或服务计划将其关闭。你必须拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="af513-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="af513-174">若要关闭 Teams 探索体验许可证，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="af513-174">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="af513-175">在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="af513-175">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="af513-176">选择用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="af513-176">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="af513-177">在“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="af513-177">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="af513-178">在“**产品许可证**”窗格中，将此探索许可证的开关切换为“**关**”。</span><span class="sxs-lookup"><span data-stu-id="af513-178">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="af513-179">组织中的第一位用户启动 Teams Exploratory 体验后，将显示 Teams Exploratory 切换开关。</span><span class="sxs-lookup"><span data-stu-id="af513-179">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="af513-180">为拥有 Teams 探索许可证的用户管理 Teams</span><span class="sxs-lookup"><span data-stu-id="af513-180">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="af513-p108">可以像管理拥有普通付费许可证的用户一样管理拥有 Teams Exploratory 许可证的用户。有关更多信息，请参见[为你的组织管理Teams 设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="af513-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="af513-183">从 Teams 探索许可证升级用户</span><span class="sxs-lookup"><span data-stu-id="af513-183">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="af513-184">要从 Teams 探索许可证升级用户（必须拥有管理员权限），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="af513-184">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="af513-185">购买包含 Teams 的订阅。</span><span class="sxs-lookup"><span data-stu-id="af513-185">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="af513-186">删除用户的 Teams Exploratory 订阅。</span><span class="sxs-lookup"><span data-stu-id="af513-186">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="af513-187">分配新购买的许可证。</span><span class="sxs-lookup"><span data-stu-id="af513-187">Assign the newly purchased license.</span></span>

<span data-ttu-id="af513-188">有关详细信息，请参阅 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="af513-188">For more information, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="af513-p109">如果 Teams Exploratory 许可证已结束，而用户没有立即升级到包含 Teams 的订阅，则他们有 30 天的宽限期，在这 30 天之后就要删除数据。用户仍然存在于 Azure 域服务中。如果用户在宽限期内添加订阅，则一旦为用户分配了新的许可证以再次启用 Teams 功能，所有内容将仍然存在。</span><span class="sxs-lookup"><span data-stu-id="af513-p109">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="af513-192">这对旧版 Microsoft Teams 商业云试用版许可证有何影响</span><span class="sxs-lookup"><span data-stu-id="af513-192">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="af513-p110">从2020年2月起，符合条件的用户可以开始使用最新的 Microsoft Teams 探索版体验。所有遗留的 Teams 商业云试用许可证将在试用版期满前自动转换为新的优惠。</span><span class="sxs-lookup"><span data-stu-id="af513-p110">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience. All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="af513-p111">当用户首次登录过期的 Teams 商业云试用版时，我们会自动为这些用户分配一个 Teams 探索版体验授权。在用户在登录前不会转换。</span><span class="sxs-lookup"><span data-stu-id="af513-p111">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users. Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="af513-197">删除 Teams 探索许可证</span><span class="sxs-lookup"><span data-stu-id="af513-197">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="af513-198">如果要通过 PowerShell 删除此许可证，请参阅：[使用 Office 365 PowerShell 删除用户帐户的许可证](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="af513-198">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="af513-199">如果要通过管理门户删除此许可证，请参阅：[从组织删除用户](/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="af513-199">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="af513-200">什么是数据保留策略？</span><span class="sxs-lookup"><span data-stu-id="af513-200">What is the data retention policy</span></span>

<span data-ttu-id="af513-201">请参阅 [Microsoft 365 订阅信息](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="af513-201">See [Microsoft 365 subscription information](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="af513-202">Teams 探索体验持续多长时间</span><span class="sxs-lookup"><span data-stu-id="af513-202">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="af513-203">自 2021 年初起，Teams Exploratory 作为12个月的订阅（从初始用户注册开始），面向所有新客户。</span><span class="sxs-lookup"><span data-stu-id="af513-203">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="af513-204">当组织中第一个用户注册 Teams Exploratory 时，新的 Teams Exploratory 订阅将启动，并且将在 12 个月后过期。</span><span class="sxs-lookup"><span data-stu-id="af513-204">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="af513-205">12个月的期限从第一个用户的注册日开始，这有效期将适用于同一租户中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="af513-205">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="af513-206">体验的结束日期是在组织层面进行配置的，这意味着它将适用于同一组织的所有用户。</span><span class="sxs-lookup"><span data-stu-id="af513-206">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="af513-207">例如，用户 1 于 2021 年 1 月 1 日注册订阅。</span><span class="sxs-lookup"><span data-stu-id="af513-207">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="af513-208">这将在 2021 年 12 月 31 日启动订阅结束日期。</span><span class="sxs-lookup"><span data-stu-id="af513-208">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="af513-209">另一个用户 User 2 于 2021 年 10 月 1 日注册订阅。</span><span class="sxs-lookup"><span data-stu-id="af513-209">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="af513-210">用户 2 可使用 Teams Exploratory 两个月，因为用户 1 和 用户 2 都属于同一个组织都订阅，所以他们的订阅都将于2021年12月31日结束。</span><span class="sxs-lookup"><span data-stu-id="af513-210">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="af513-211">在 12 个月的 Teams Exploratory 体验结束后，管理员应该怎么做</span><span class="sxs-lookup"><span data-stu-id="af513-211">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="af513-212">在 12 个月的订阅结束时，管理员应将其所有 Teams Exploratory 用户转换为包括 Teams 的付费许可证。</span><span class="sxs-lookup"><span data-stu-id="af513-212">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="af513-213">确保在Teams Exploratory订阅到期前完成这项工作至关重要，以避免对用户的体验造成任何干扰。</span><span class="sxs-lookup"><span data-stu-id="af513-213">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>


> [!NOTE]
> <span data-ttu-id="af513-214">在上一个探索体验许可证到期后的 3 个月内客户将被禁用并阻止开始新的探索试用许可证。</span><span class="sxs-lookup"><span data-stu-id="af513-214">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>

<span data-ttu-id="af513-215">有关详细信息，请参阅上文中的 [Teams Exploratory中升级用户](#upgrade-users-from-the-teams-exploratory-license))。</span><span class="sxs-lookup"><span data-stu-id="af513-215">For more information, see [Upgrade users from the Teams Exploratory license](#upgrade-users-from-the-teams-exploratory-license)), above in this article.</span></span>
