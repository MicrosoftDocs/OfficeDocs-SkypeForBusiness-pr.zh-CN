---
title: 管理 Microsoft Teams 探索体验
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 未获得 Microsoft Teams 许可的 Microsoft 365 或 Office 365 用户可以启动探索 Teams 许可证。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f27dc7e8772e25b6dcc91622cabec421e058af7b
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031478"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="dea39-103">管理 Microsoft Teams 探索许可证</span><span class="sxs-lookup"><span data-stu-id="dea39-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="dea39-p101">Microsoft Teams 探索性体验让组织中拥有 Azure 域服务（Azure AD）但未获得 Teams 许可的用户可以启动 Teams 的探索性体验。管理员可以为其组织中的用户开启或关闭此功能。The Teams Exploratory体验现在已取代了早期的 [Microsoft 商业云试用版](iw-trial-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="dea39-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization. The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="dea39-107">Teams 探索体验中包含哪些服务</span><span class="sxs-lookup"><span data-stu-id="dea39-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="dea39-108">管理员将在 Teams 探索体验中看到的服务计划有：</span><span class="sxs-lookup"><span data-stu-id="dea39-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="dea39-109">Exchange Online（计划 1）</span><span class="sxs-lookup"><span data-stu-id="dea39-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="dea39-110">适用于 Microsoft 365 或 Office 365 的流</span><span class="sxs-lookup"><span data-stu-id="dea39-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="dea39-111">MyAnalytics 提供的见解</span><span class="sxs-lookup"><span data-stu-id="dea39-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="dea39-112">Microsoft Forms（计划 E1）</span><span class="sxs-lookup"><span data-stu-id="dea39-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="dea39-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="dea39-113">Microsoft Planner</span></span>
- <span data-ttu-id="dea39-114">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="dea39-114">Microsoft Search</span></span>
- <span data-ttu-id="dea39-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="dea39-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="dea39-116">适用于 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream<sup>1</1></span><span class="sxs-lookup"><span data-stu-id="dea39-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="dea39-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dea39-117">Microsoft Teams</span></span>
- <span data-ttu-id="dea39-118">适用于 Microsoft 365 或 Office 365 的移动设备管理</span><span class="sxs-lookup"><span data-stu-id="dea39-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="dea39-119">适用于 Office 365 的 Office 移动应用</span><span class="sxs-lookup"><span data-stu-id="dea39-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="dea39-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="dea39-120">Office Online</span></span>
- <span data-ttu-id="dea39-121">适用于 Microsoft 365 或 Office 365 的 PowerApps</span><span class="sxs-lookup"><span data-stu-id="dea39-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="dea39-122">SharePoint Online（计划 1）</span><span class="sxs-lookup"><span data-stu-id="dea39-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="dea39-123">Sway</span><span class="sxs-lookup"><span data-stu-id="dea39-123">Sway</span></span>
- <span data-ttu-id="dea39-124">待办事项（计划 1）</span><span class="sxs-lookup"><span data-stu-id="dea39-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="dea39-125">Whiteboard（计划 1）</span><span class="sxs-lookup"><span data-stu-id="dea39-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="dea39-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="dea39-126">Yammer Enterprise</span></span>

  <span data-ttu-id="dea39-p102"><sup>1</sup> 从使用 Microsoft Stream 到使用 [OneDrive for Business 和 SharePoint for meeting 进行会议录制](tmr-meeting-recording-change.md)到改变将是一个分阶段的方式。 在发布时，你将可以选择加入这种体验。在11月，如果你必须选择是否要继续使用Stream。在2021年初，我们将要求所有客户使用OneDrive for Business 和 SharePoint 获取新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="dea39-p102"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt in to this experience. In November, you'll have to opt out if you want to continue using Stream. Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="dea39-131">谁有资格使用</span><span class="sxs-lookup"><span data-stu-id="dea39-131">Who's eligible</span></span>

<span data-ttu-id="dea39-132">用户符合 Teams 探索体验的标准，如果他们：</span><span class="sxs-lookup"><span data-stu-id="dea39-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="dea39-133">具有托管 Azure AD 域电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dea39-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="dea39-134">属于付费订阅的租户。</span><span class="sxs-lookup"><span data-stu-id="dea39-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="dea39-p103">必须启用用户注册应用程序和试用版（在 Microsoft 365 管理中心）。有关更多信息，请参见稍后在本文出现的[管理团队探索性体验](#manage-the-teams-exploratory-experience)。</span><span class="sxs-lookup"><span data-stu-id="dea39-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="dea39-137">谁没有资格使用</span><span class="sxs-lookup"><span data-stu-id="dea39-137">Who isn't eligible</span></span>

<span data-ttu-id="dea39-138">用户在以下情况下不适合条件：</span><span class="sxs-lookup"><span data-stu-id="dea39-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="dea39-139">目前或以前拥有的来自付费、未付费或试用版许可证的 Teams</span><span class="sxs-lookup"><span data-stu-id="dea39-139">Currently or previously had Teams from a paid, unpaid or trial license</span></span> 
- <span data-ttu-id="dea39-140">位于至少已使用或收到一个特殊 COVID 优惠的租户中。</span><span class="sxs-lookup"><span data-stu-id="dea39-140">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="dea39-141">如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该服务。</span><span class="sxs-lookup"><span data-stu-id="dea39-141">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="dea39-142">如何注册 Teams 探索体验？</span><span class="sxs-lookup"><span data-stu-id="dea39-142">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="dea39-p104">符合条件的用户可以通过登录 Teams（[teams.microsoft.com ](https://teams.microsoft.com)）来注册 Teams Exploratory 体验。将自动向他们分配此许可证，并且当组织中有人首次启动 Teams Exploratory 体验时，租户管理员将收到电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="dea39-p104">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)). They'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="dea39-145">管理 Teams 探索体验</span><span class="sxs-lookup"><span data-stu-id="dea39-145">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="dea39-146">Teams 探索体验设计为由单独的最终用户启动，你不能代表最终用户员工启动此服务。</span><span class="sxs-lookup"><span data-stu-id="dea39-146">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="dea39-p105">Teams Exploratory 体验自带 Exchange Online 许可证，但在管理员分配之前将不会分配给用户。如果用户还没有 Exchange 许可证，而管理员也未分配 Exchange Online 许可证，那么用户将无法在 Teams 中安排会议，并且可能会错过其他 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="dea39-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="dea39-149">管理员可以通过使用 **试用版应用和服务** 开关，禁用最终用户在其组织内运行 Teams 探索体验的功能。</span><span class="sxs-lookup"><span data-stu-id="dea39-149">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="dea39-150">阻止用户安装试用版应用和服务</span><span class="sxs-lookup"><span data-stu-id="dea39-150">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="dea39-151">可禁止用户安装试用版应用和服务，这会阻止用户运行 Teams 探索体验。</span><span class="sxs-lookup"><span data-stu-id="dea39-151">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="dea39-152">从 Microsoft 365 管理中心，转到“ **设置** ” > “ **组织设置** ”，选择“ **服务** ”，然后选择“ **用户自有应用和服务** ”。</span><span class="sxs-lookup"><span data-stu-id="dea39-152">From the Microsoft 365 admin center, go to **Settings** > **Org settings** , select **Services** , and then select **User owned apps and services**.</span></span>

    ![管理中心中“服务”页面的屏幕截图](media/iw-trial-services.png)

2. <span data-ttu-id="dea39-154">清除“ **允许用户安装试用版应用和服务** ”复选框。</span><span class="sxs-lookup"><span data-stu-id="dea39-154">Clear the **Let users install trial apps and services** check box.</span></span>

    ![管理中心中的“用户自有应用和服务”页面](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="dea39-156">如果你的组织不符合获取 Teams 探索体验的条件，你将看不到“ **允许用户安装试用版应用和服务** ”选项。</span><span class="sxs-lookup"><span data-stu-id="dea39-156">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="dea39-157">为拥有包含 Teams 的许可证的用户管理可用性</span><span class="sxs-lookup"><span data-stu-id="dea39-157">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="dea39-p106">已分配到包含 Teams 许可证的用户尚无资格获得 Teams 探索体验。当 Teams 服务计划开启时，用户可以登录并使用 Teams。如果已禁用服务计划，则用户无法登录，并且无法使用 Teams 探索体验。你必须拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="dea39-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="dea39-162">关闭对 Teams 的访问：</span><span class="sxs-lookup"><span data-stu-id="dea39-162">To turn off access to Teams:</span></span>

1. <span data-ttu-id="dea39-163">在 Microsoft 365 管理中心中，选择“ **用户** ” > “ **活动用户** ”。</span><span class="sxs-lookup"><span data-stu-id="dea39-163">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="dea39-164">选择用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="dea39-164">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="dea39-165">在“ **产品许可证** ”行中，选择“ **编辑** ”。</span><span class="sxs-lookup"><span data-stu-id="dea39-165">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="dea39-166">在“ **产品许可证** ”窗格中，将开关切换为“ **关闭** ”。</span><span class="sxs-lookup"><span data-stu-id="dea39-166">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理中心中的“产品许可证”页面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="dea39-168">为已在使用 Teams 探索体验的用户管理 Teams 可用性</span><span class="sxs-lookup"><span data-stu-id="dea39-168">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="dea39-p107">如果用户正在运行 Teams Exploratory 体验，你可通过删除许可证或服务计划将其关闭。你必须拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="dea39-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="dea39-171">若要关闭 Teams 探索体验许可证，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dea39-171">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="dea39-172">在 Microsoft 365 管理中心中，选择“ **用户** ” > “ **活动用户** ”。</span><span class="sxs-lookup"><span data-stu-id="dea39-172">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="dea39-173">选择用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="dea39-173">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="dea39-174">在“ **产品许可证** ”行中，选择“ **编辑** ”。</span><span class="sxs-lookup"><span data-stu-id="dea39-174">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="dea39-175">在“ **产品许可证** ”窗格中，将此探索许可证的开关切换为“ **关** ”。</span><span class="sxs-lookup"><span data-stu-id="dea39-175">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    >[!Note]
    ><span data-ttu-id="dea39-176">组织中的第一位用户启动 Teams Exploratory 体验后，将显示 Teams Exploratory 切换开关。</span><span class="sxs-lookup"><span data-stu-id="dea39-176">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="dea39-177">为拥有 Teams 探索许可证的用户管理 Teams</span><span class="sxs-lookup"><span data-stu-id="dea39-177">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="dea39-p108">可以像管理拥有普通付费许可证的用户一样管理拥有 Teams Exploratory 许可证的用户。有关更多信息，请参见[为你的组织管理Teams 设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="dea39-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="dea39-180">从 Teams 探索许可证升级用户</span><span class="sxs-lookup"><span data-stu-id="dea39-180">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="dea39-181">要从 Teams 探索许可证升级用户（必须拥有管理员权限），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dea39-181">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="dea39-182">购买包含 Teams 的订阅。</span><span class="sxs-lookup"><span data-stu-id="dea39-182">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="dea39-183">删除用户的 Teams Exploratory 订阅。</span><span class="sxs-lookup"><span data-stu-id="dea39-183">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="dea39-184">分配新购买的许可证。</span><span class="sxs-lookup"><span data-stu-id="dea39-184">Assign the newly purchased license.</span></span>

<span data-ttu-id="dea39-185">有关详细信息，请参阅 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="dea39-185">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="dea39-p109">如果 Teams Exploratory 许可证已结束，而用户没有立即升级到包含 Teams 的订阅，则他们有 30 天的宽限期，在这 30 天之后就要删除数据。用户仍然存在于 Azure 域服务中。如果用户在宽限期内添加订阅，则一旦为用户分配了新的许可证以再次启用 Teams 功能，所有内容将仍然存在。</span><span class="sxs-lookup"><span data-stu-id="dea39-p109">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="dea39-189">这对旧版 Microsoft Teams 商业云试用版许可证有何影响</span><span class="sxs-lookup"><span data-stu-id="dea39-189">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="dea39-p110">从2020年2月起，符合条件的用户可以开始使用最新的 Microsoft Teams 探索版体验。所有遗留的 Teams 商业云试用许可证将在试用版期满前自动转换为新的优惠。</span><span class="sxs-lookup"><span data-stu-id="dea39-p110">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience. All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="dea39-p111">当用户首次登录过期的 Teams 商业云试用版时，我们会自动为这些用户分配一个 Teams 探索版体验授权。在用户在登录前不会转换。</span><span class="sxs-lookup"><span data-stu-id="dea39-p111">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users. Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="dea39-194">删除 Teams 探索许可证</span><span class="sxs-lookup"><span data-stu-id="dea39-194">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="dea39-195">如果要通过 PowerShell 删除此许可证，请参阅：[使用 Office 365 PowerShell 删除用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="dea39-195">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="dea39-196">如果要通过管理门户删除此许可证，请参阅：[从组织删除用户](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="dea39-196">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="dea39-197">什么是数据保留策略？</span><span class="sxs-lookup"><span data-stu-id="dea39-197">What is the data retention policy</span></span>

<span data-ttu-id="dea39-198">请参阅 [Microsoft 365 订阅信息](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="dea39-198">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="dea39-199">Teams 探索体验持续多长时间</span><span class="sxs-lookup"><span data-stu-id="dea39-199">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="dea39-p112">在下一个 **协议周年纪念日** 或 2021 年 1 月或之后的 **续约** 之前，Microsoft Teams 探索体验无需支付额外费用。届时，使用 Microsoft 探索体验许可证的最终用户将需要转为包含 Teams 的付费许可证。在此后启动的任何 Microsoft 探索体验许可证将始终可用，且在你的下一个 **周年纪念日** 或 **续约周期** 之前无需支付额外费用。</span><span class="sxs-lookup"><span data-stu-id="dea39-p112">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021. At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams. Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="dea39-203">如果最终用户刚好在我的周年纪念或续订日期前启动 Microsoft Teams 探索体验，会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="dea39-203">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="dea39-204">在 **协议周年日** 或 **续订** 后的 90 天内启动的 Microsoft Teams 探索体验许可证无需迁移到付费许可证，直到下一个周年日或续订周期。</span><span class="sxs-lookup"><span data-stu-id="dea39-204">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="dea39-205">如果我的协议没有周年日或每年的续约日期（例如逐月协议），该怎么办</span><span class="sxs-lookup"><span data-stu-id="dea39-205">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="dea39-p113">对于没有周年纪念日或年度续约日期的协议，将会将第一个最终用户激活 Microsoft Teams 探索体验许可证后的下一年视为周年纪念日或续约日。Microsoft Teams 探索许可证上的用户必须根据本文中概述的政策，在每年的该日期之前转换为付费许可证。</span><span class="sxs-lookup"><span data-stu-id="dea39-p113">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end-user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date. Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="dea39-208">例如，如果第一位最终用户在 2020 年 6 月 19 日激活了 Microsoft Teams 探索，则他们和客户租户中的所有其他符合条件的用户必须在 2021 年 6月 19 日之前转换为 Teams 付费许可证。</span><span class="sxs-lookup"><span data-stu-id="dea39-208">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="dea39-209">在上一个探索体验许可证到期后的 3 个月内客户将被禁用并阻止开始新的探索试用许可证。</span><span class="sxs-lookup"><span data-stu-id="dea39-209">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
