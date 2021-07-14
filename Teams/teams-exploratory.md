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
ms.openlocfilehash: 946847793ea90e549a555cd9d100cd1ae2809fa3
ms.sourcegitcommit: f3e9989cbcc2f9f83ff94204bdd75b1e6ad43b5e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408751"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="bc730-103">管理 Microsoft Teams Exploratory 许可证</span><span class="sxs-lookup"><span data-stu-id="bc730-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="bc730-p101">通过 Microsoft Teams 探索体验，组织中具有 Azure Active Directory (Azure AD) 但未获得 Teams 许可证的用户可以启动 Teams 探索体验。管理员可以为组织中的用户打开或关闭此功能。</span><span class="sxs-lookup"><span data-stu-id="bc730-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="bc730-106">Teams Exploratory 体验中包含哪些服务</span><span class="sxs-lookup"><span data-stu-id="bc730-106">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="bc730-107">管理员将在 Teams Exploratory 体验中看到的服务计划有：</span><span class="sxs-lookup"><span data-stu-id="bc730-107">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="bc730-108">Exchange Online（计划 1)</span><span class="sxs-lookup"><span data-stu-id="bc730-108">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="bc730-109">适用于 Microsoft 365 或 Office 365 的流</span><span class="sxs-lookup"><span data-stu-id="bc730-109">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="bc730-110">MyAnalytics 提供的见解</span><span class="sxs-lookup"><span data-stu-id="bc730-110">Insights by MyAnalytics</span></span>
- <span data-ttu-id="bc730-111">Microsoft Forms（计划 E1）</span><span class="sxs-lookup"><span data-stu-id="bc730-111">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="bc730-112">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="bc730-112">Microsoft Planner</span></span>
- <span data-ttu-id="bc730-113">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="bc730-113">Microsoft Search</span></span>
- <span data-ttu-id="bc730-114">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="bc730-114">Microsoft StaffHub</span></span>
- <span data-ttu-id="bc730-115">适用于 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream<sup>1</1></span><span class="sxs-lookup"><span data-stu-id="bc730-115">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="bc730-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc730-116">Microsoft Teams</span></span>
- <span data-ttu-id="bc730-117">适用于 Microsoft 365 或 Office 365 的移动设备管理</span><span class="sxs-lookup"><span data-stu-id="bc730-117">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="bc730-118">适用于 Office 365 的 Office 移动应用</span><span class="sxs-lookup"><span data-stu-id="bc730-118">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="bc730-119">Office Online</span><span class="sxs-lookup"><span data-stu-id="bc730-119">Office Online</span></span>
- <span data-ttu-id="bc730-120">适用于 Microsoft 365 或 Office 365 的 PowerApps</span><span class="sxs-lookup"><span data-stu-id="bc730-120">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="bc730-121">SharePoint Online（计划 1）</span><span class="sxs-lookup"><span data-stu-id="bc730-121">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="bc730-122">Sway</span><span class="sxs-lookup"><span data-stu-id="bc730-122">Sway</span></span>
- <span data-ttu-id="bc730-123">待办事项（计划 1）</span><span class="sxs-lookup"><span data-stu-id="bc730-123">To-Do (Plan 1)</span></span>
- <span data-ttu-id="bc730-124">Whiteboard（计划 1）</span><span class="sxs-lookup"><span data-stu-id="bc730-124">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="bc730-125">Yammer 企业版</span><span class="sxs-lookup"><span data-stu-id="bc730-125">Yammer Enterprise</span></span>

  <span data-ttu-id="bc730-p102"><sup>1</sup> 从使用 Microsoft Stream 改为 [OneDrive for Business 和 SharePoint for meeting 进行会议录制](tmr-meeting-recording-change.md) 将分阶段进行。在启动时，你将可以选择加入这种体验。11 月时，如果希望继续使用 Stream，则必须选择退出。到 2021 年初，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="bc730-p102"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch, you'll be able to opt in to this experience. In November, you'll have to opt out if you want to continue using Stream. Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="bc730-130">符合资格的人员</span><span class="sxs-lookup"><span data-stu-id="bc730-130">Who's eligible</span></span>

<span data-ttu-id="bc730-131">用户符合 Teams 探索体验的标准，如果他们：</span><span class="sxs-lookup"><span data-stu-id="bc730-131">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="bc730-132">具有托管 Azure AD 域电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="bc730-132">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="bc730-133">属于付费订阅的租户。</span><span class="sxs-lookup"><span data-stu-id="bc730-133">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="bc730-134">没有有效的 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="bc730-134">Do not have an active Teams license.</span></span>
- <span data-ttu-id="bc730-135">不在创建许可证分配策略的租户中。</span><span class="sxs-lookup"><span data-stu-id="bc730-135">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="bc730-p103">必须启用用户注册应用程序和试用版（在 Microsoft 365 管理中心）。有关更多信息，请参见稍后在本文出现的[管理团队探索性体验](#manage-the-teams-exploratory-experience)。</span><span class="sxs-lookup"><span data-stu-id="bc730-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="bc730-138">谁没有资格使用</span><span class="sxs-lookup"><span data-stu-id="bc730-138">Who isn't eligible</span></span>

<span data-ttu-id="bc730-139">用户在以下情况下不适合条件：</span><span class="sxs-lookup"><span data-stu-id="bc730-139">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="bc730-140">当前拥有来自付费许可证或试用许可证的 Teams，或以前具有试用许可证</span><span class="sxs-lookup"><span data-stu-id="bc730-140">Currently have Teams from a paid license or trial license, or previously had trial license</span></span>
- <span data-ttu-id="bc730-141">位于至少已使用或收到一个特殊 COVID 优惠的租户中。</span><span class="sxs-lookup"><span data-stu-id="bc730-141">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="bc730-142">如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该服务。</span><span class="sxs-lookup"><span data-stu-id="bc730-142">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="bc730-143">如何注册 Teams 探索体验？</span><span class="sxs-lookup"><span data-stu-id="bc730-143">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="bc730-144">符合条件的用户可通过登录到 Teams 桌面版或 Web 版 ([teams.microsoft.com](https://teams.microsoft.com)) 来注册 Teams Exploratory 体验。</span><span class="sxs-lookup"><span data-stu-id="bc730-144">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="bc730-145">目前，不支持通过移动设备启用 Exploratory。</span><span class="sxs-lookup"><span data-stu-id="bc730-145">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="bc730-146">当他们注册时，系统将自动向其分配此许可证，并且租户管理员会在组织中有人首次启动 Teams Exploratory 体验时收到一封电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="bc730-146">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="bc730-147">管理 Teams 探索体验</span><span class="sxs-lookup"><span data-stu-id="bc730-147">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="bc730-148">Teams 探索体验设计为由单独的最终用户启动，你不能代表最终用户员工启动此服务。</span><span class="sxs-lookup"><span data-stu-id="bc730-148">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="bc730-p105">Teams Exploratory 体验自带 Exchange Online 许可证，但在管理员分配之前将不会分配给用户。如果用户还没有 Exchange 许可证，而管理员也未分配 Exchange Online 许可证，那么用户将无法在 Teams 中安排会议，并且可能会错过其他 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="bc730-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="bc730-151">管理员可以通过使用 **试用版应用和服务** 开关，禁用最终用户在其组织内运行 Teams 探索体验的功能。</span><span class="sxs-lookup"><span data-stu-id="bc730-151">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="bc730-152">阻止用户安装试用版应用和服务</span><span class="sxs-lookup"><span data-stu-id="bc730-152">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="bc730-153">可禁止用户安装试用版应用和服务，这会阻止用户运行 Teams 探索体验。</span><span class="sxs-lookup"><span data-stu-id="bc730-153">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="bc730-154">从 Microsoft 365 管理中心，转到“**设置**” > “**组织设置**”，选择“**服务**”，然后选择“**用户自有应用和服务**”。</span><span class="sxs-lookup"><span data-stu-id="bc730-154">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![管理中心中“服务”页面的屏幕截图](media/iw-trial-services.png)

2. <span data-ttu-id="bc730-156">清除“**允许用户安装试用版应用和服务**”的复选标记。</span><span class="sxs-lookup"><span data-stu-id="bc730-156">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![管理中心中的“用户自有应用和服务”页面](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="bc730-158">如果你的组织不符合获取 Teams 探索体验的条件，你将看不到“**允许用户安装试用版应用和服务**”选项。</span><span class="sxs-lookup"><span data-stu-id="bc730-158">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="bc730-159">为拥有包含 Teams 的许可证的用户管理可用性</span><span class="sxs-lookup"><span data-stu-id="bc730-159">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="bc730-p106">已分配到包含 Teams 许可证的用户尚无资格获得 Teams 探索体验。当 Teams 服务计划开启时，用户可以登录并使用 Teams。如果已禁用服务计划，则用户无法登录，并且无法使用 Teams 探索体验。你必须拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="bc730-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="bc730-164">关闭对 Teams 的访问：</span><span class="sxs-lookup"><span data-stu-id="bc730-164">To turn off access to Teams:</span></span>

1. <span data-ttu-id="bc730-165">在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="bc730-165">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="bc730-166">选择用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="bc730-166">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="bc730-167">在“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="bc730-167">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="bc730-168">在“**产品许可证**”窗格中，将开关切换为“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="bc730-168">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理中心中的“产品许可证”页面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="bc730-170">为已在使用 Teams 探索体验的用户管理 Teams 可用性</span><span class="sxs-lookup"><span data-stu-id="bc730-170">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="bc730-p107">如果用户正在运行 Teams Exploratory 体验，你可通过删除许可证或服务计划将其关闭。你必须拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="bc730-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="bc730-173">若要关闭 Teams 探索体验许可证，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bc730-173">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="bc730-174">在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="bc730-174">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="bc730-175">选择用户姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="bc730-175">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="bc730-176">在“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="bc730-176">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="bc730-177">在“**产品许可证**”窗格中，将此探索许可证的开关切换为“**关**”。</span><span class="sxs-lookup"><span data-stu-id="bc730-177">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc730-178">组织中的第一位用户启动 Teams Exploratory 体验后，将显示 Teams Exploratory 切换开关。</span><span class="sxs-lookup"><span data-stu-id="bc730-178">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="bc730-179">为拥有 Teams 探索许可证的用户管理 Teams</span><span class="sxs-lookup"><span data-stu-id="bc730-179">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="bc730-p108">可以像管理拥有普通付费许可证的用户一样管理拥有 Teams Exploratory 许可证的用户。有关更多信息，请参见[为你的组织管理Teams 设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="bc730-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-teams-exploratory"></a><span data-ttu-id="bc730-182">从 Teams 探索升级用户</span><span class="sxs-lookup"><span data-stu-id="bc730-182">Upgrade users from Teams Exploratory</span></span>

<span data-ttu-id="bc730-183">必须具有管理员权限才能从 Teams 探索升级用户。</span><span class="sxs-lookup"><span data-stu-id="bc730-183">You must have admin privileges to upgrade users from Teams Exploratory.</span></span> <span data-ttu-id="bc730-184">有关详细信息，请参阅 [从 Teams 探索试用版升级用户](upgrade-from-teams-exploratory.md)。</span><span class="sxs-lookup"><span data-stu-id="bc730-184">For more information see [Upgrade users from the Teams Exploratory trial](upgrade-from-teams-exploratory.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bc730-p110">如果 Teams 探索许可证已终止，而用户没有立即升级到包含 Teams 的订阅，则他们在 30 天宽限期之后会失去对 Teams 的访问权限。再过 30 天后，会删除用户的数据。用户仍然存在于 Azure Active Directory 中。如果向用户分配新的许可证以再次启用 Teams 功能，并且用户是在宽限期内添加的，则所有内容将仍然存在。</span><span class="sxs-lookup"><span data-stu-id="bc730-p110">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they lose access to Teams after a 30-days grace period. Another 30 days after which, the data is deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="bc730-189">删除 Teams 探索许可证</span><span class="sxs-lookup"><span data-stu-id="bc730-189">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="bc730-190">如果要通过 PowerShell 删除此许可证，请参阅：[使用 Office 365 PowerShell 删除用户帐户的许可证](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="bc730-190">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="bc730-191">如果要通过管理门户删除此许可证，请参阅：[从组织删除用户](/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="bc730-191">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="bc730-192">什么是数据保留策略？</span><span class="sxs-lookup"><span data-stu-id="bc730-192">What is the data retention policy</span></span>

<span data-ttu-id="bc730-193">请参阅 [Microsoft 365 订阅信息](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="bc730-193">See [Microsoft 365 subscription information](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="bc730-194">Teams 探索体验持续多长时间</span><span class="sxs-lookup"><span data-stu-id="bc730-194">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="bc730-195">自 2021 年初起，Teams Exploratory 作为12个月的订阅（从初始用户注册开始），面向所有新客户。</span><span class="sxs-lookup"><span data-stu-id="bc730-195">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="bc730-196">当组织中第一个用户注册 Teams Exploratory 时，新的 Teams Exploratory 订阅将启动，并且将在 12 个月后过期。</span><span class="sxs-lookup"><span data-stu-id="bc730-196">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="bc730-197">12个月的期限从第一个用户的注册日开始，这有效期将适用于同一租户中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="bc730-197">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="bc730-198">体验的结束日期是在组织层面进行配置的，这意味着它将适用于同一组织的所有用户。</span><span class="sxs-lookup"><span data-stu-id="bc730-198">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="bc730-199">例如，用户 1 于 2021 年 1 月 1 日注册订阅。</span><span class="sxs-lookup"><span data-stu-id="bc730-199">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="bc730-200">这将在 2021 年 12 月 31 日启动订阅结束日期。</span><span class="sxs-lookup"><span data-stu-id="bc730-200">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="bc730-201">另一个用户 User 2 于 2021 年 10 月 1 日注册订阅。</span><span class="sxs-lookup"><span data-stu-id="bc730-201">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="bc730-202">用户 2 可使用 Teams Exploratory 两个月，因为用户 1 和 用户 2 都属于同一个组织都订阅，所以他们的订阅都将于2021年12月31日结束。</span><span class="sxs-lookup"><span data-stu-id="bc730-202">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="bc730-203">在 12 个月的 Teams Exploratory 体验结束后，管理员应该怎么做</span><span class="sxs-lookup"><span data-stu-id="bc730-203">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="bc730-204">在 12 个月的订阅结束时，管理员应将其所有 Teams Exploratory 用户转换为包括 Teams 的付费许可证。</span><span class="sxs-lookup"><span data-stu-id="bc730-204">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="bc730-205">确保在Teams Exploratory订阅到期前完成这项工作至关重要，以避免对用户的体验造成任何干扰。</span><span class="sxs-lookup"><span data-stu-id="bc730-205">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>


> [!NOTE]
> <span data-ttu-id="bc730-206">在上一个探索体验许可证到期后的 3 个月内客户将被禁用并阻止开始新的探索试用许可证。</span><span class="sxs-lookup"><span data-stu-id="bc730-206">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>

<span data-ttu-id="bc730-207">有关详细信息，请参阅上文中的 [从 Teams 探索中升级用户](#upgrade-users-from-teams-exploratory)。</span><span class="sxs-lookup"><span data-stu-id="bc730-207">For more information, see [Upgrade users from Teams Exploratory](#upgrade-users-from-teams-exploratory), above in this article.</span></span>
