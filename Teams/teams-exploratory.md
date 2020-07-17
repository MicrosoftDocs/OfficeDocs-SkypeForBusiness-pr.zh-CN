---
title: 管理 Microsoft Teams Exploratory 体验
author: LolaJacobsen
ms.author: lolaj
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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99017e63ae784c7c4271454829198c7c06ecfe8e
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868459"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="fb55c-103">管理 Microsoft Teams Exploratory 许可证</span><span class="sxs-lookup"><span data-stu-id="fb55c-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="fb55c-104">借助 Microsoft Teams Exploratory 体验，组织中拥有 Azure Active Directory (AAD) 且未获得 Teams 许可的用户可以启用 Teams 的探索体验。</span><span class="sxs-lookup"><span data-stu-id="fb55c-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (AAD) and are not licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="fb55c-105">管理员可以为组织中的用户打开或关闭此功能。</span><span class="sxs-lookup"><span data-stu-id="fb55c-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="fb55c-106">以前的 [Microsoft 商业云试用版](iw-trial-teams.md)现在替换为 Teams Exploratory 体验。</span><span class="sxs-lookup"><span data-stu-id="fb55c-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="fb55c-107">Teams Exploratory 体验中包含哪些服务？</span><span class="sxs-lookup"><span data-stu-id="fb55c-107">What's in the Teams Exploratory experience?</span></span>

<span data-ttu-id="fb55c-108">管理员将在 Teams Exploratory 体验中看到的服务计划有：</span><span class="sxs-lookup"><span data-stu-id="fb55c-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>
 - <span data-ttu-id="fb55c-109">Exchange Online（计划 1)</span><span class="sxs-lookup"><span data-stu-id="fb55c-109">Exchange Online (Plan 1)</span></span>
 - <span data-ttu-id="fb55c-110">适用于 Microsoft 365 或 Office 365 的流</span><span class="sxs-lookup"><span data-stu-id="fb55c-110">Flow for Microsoft 365 or Office 365</span></span>
 - <span data-ttu-id="fb55c-111">MyAnalytics 提供的见解</span><span class="sxs-lookup"><span data-stu-id="fb55c-111">Insights by MyAnalytics</span></span>
 - <span data-ttu-id="fb55c-112">Microsoft Forms（计划 E1）</span><span class="sxs-lookup"><span data-stu-id="fb55c-112">Microsoft Forms (Plan E1)</span></span>
 - <span data-ttu-id="fb55c-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="fb55c-113">Microsoft Planner</span></span>
 - <span data-ttu-id="fb55c-114">Microsoft 搜索</span><span class="sxs-lookup"><span data-stu-id="fb55c-114">Microsoft Search</span></span>
 - <span data-ttu-id="fb55c-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="fb55c-115">Microsoft StaffHub</span></span>
 - <span data-ttu-id="fb55c-116">适用于 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="fb55c-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs</span></span>
 - <span data-ttu-id="fb55c-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb55c-117">Microsoft Teams</span></span>
 - <span data-ttu-id="fb55c-118">适用于 Microsoft 365 或 Office 365 的移动设备管理</span><span class="sxs-lookup"><span data-stu-id="fb55c-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
 - <span data-ttu-id="fb55c-119">适用于 Office 365 的 Office 移动应用</span><span class="sxs-lookup"><span data-stu-id="fb55c-119">Office Mobile Apps for Office 365</span></span> 
 - <span data-ttu-id="fb55c-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="fb55c-120">Office Online</span></span>
 - <span data-ttu-id="fb55c-121">适用于 Microsoft 365 或 Office 365 的 PowerApps</span><span class="sxs-lookup"><span data-stu-id="fb55c-121">PowerApps for Microsoft 365 or Office 365</span></span>
 - <span data-ttu-id="fb55c-122">SharePoint Online（计划 1）</span><span class="sxs-lookup"><span data-stu-id="fb55c-122">SharePoint Online (Plan 1)</span></span>
 - <span data-ttu-id="fb55c-123">Sway</span><span class="sxs-lookup"><span data-stu-id="fb55c-123">Sway</span></span>
 - <span data-ttu-id="fb55c-124">待办事项（计划 1）</span><span class="sxs-lookup"><span data-stu-id="fb55c-124">To-Do (Plan 1)</span></span>
 - <span data-ttu-id="fb55c-125">Whiteboard（计划 1）</span><span class="sxs-lookup"><span data-stu-id="fb55c-125">Whiteboard (Plan 1)</span></span>
 - <span data-ttu-id="fb55c-126">Yammer 企业版</span><span class="sxs-lookup"><span data-stu-id="fb55c-126">Yammer Enterprise</span></span>


## <a name="whos-eligible"></a><span data-ttu-id="fb55c-127">谁有资格使用？</span><span class="sxs-lookup"><span data-stu-id="fb55c-127">Who's eligible?</span></span>

<span data-ttu-id="fb55c-128">只要用户拥有托管 AAD 域电子邮件地址，且当前没有/尚未分配有 Teams 许可证，则有资格运行此体验。</span><span class="sxs-lookup"><span data-stu-id="fb55c-128">As long as the user has a managed AAD domain email address and currently does not have/haven't been assigned a Teams license, they are eligible for this experience.</span></span> <span data-ttu-id="fb55c-129">例如，如果用户拥有 Microsoft 365 商业应用版（不包括 Teams），则他们符合获取 Teams Exploratory 体验的条件。</span><span class="sxs-lookup"><span data-stu-id="fb55c-129">For example, if a user has Microsoft 365 Apps for business (which doesn't include Teams), they're eligible for the Teams Exploratory experience.</span></span>

<span data-ttu-id="fb55c-130">必须允许用户注册应用和试用版（在 Microsoft 365 管理中心中）。</span><span class="sxs-lookup"><span data-stu-id="fb55c-130">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="fb55c-131">有关详细信息，请参阅本文后面部分的[管理 Teams Exploratory 体验](#manage-the-teams-exploratory-experience)。</span><span class="sxs-lookup"><span data-stu-id="fb55c-131">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span> 


## <a name="who-isnt-eligible"></a><span data-ttu-id="fb55c-132">谁没有资格使用</span><span class="sxs-lookup"><span data-stu-id="fb55c-132">Who isn't eligible</span></span>

<span data-ttu-id="fb55c-133">如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该服务。</span><span class="sxs-lookup"><span data-stu-id="fb55c-133">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="fb55c-134">如何注册 Teams Exploratory 体验？</span><span class="sxs-lookup"><span data-stu-id="fb55c-134">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="fb55c-135">符合条件的用户可通过登录到 Teams ([teams.microsoft.com](https://teams.microsoft.com)) 注册 Teams Exploratory 体验。</span><span class="sxs-lookup"><span data-stu-id="fb55c-135">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="fb55c-136">将自动向其分配此许可证，并且租户管理员会在组织中有人首次启动 Teams Exploratory 体验时收到一封电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="fb55c-136">They will be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="fb55c-137">管理 Teams 探索性体验</span><span class="sxs-lookup"><span data-stu-id="fb55c-137">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="fb55c-138">Teams Exploratory 体验设计为由单独的最终用户启动，你不能代表最终用户员工启动此服务。</span><span class="sxs-lookup"><span data-stu-id="fb55c-138">The Teams Exploratory experience is meant to be initiated by individual end users, and you may not initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="fb55c-139">Teams Exploratory 体验附带 Exchange Online 许可证，但它不会在管理员进行分配前分配给用户。</span><span class="sxs-lookup"><span data-stu-id="fb55c-139">The Teams Exploratory experience comes with an Exchange Online license but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="fb55c-140">如果用户没有 Exchange 许可证并且管理员尚未分配 Exchange Online 许可证，则用户将无法在 Teams 中计划会议，并且可能无法使用其他 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="fb55c-140">If the user doesn't have an Exchange license already and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and may be missing other Teams functionality.</span></span>

<span data-ttu-id="fb55c-141">管理员可以通过使用**试用版应用和服务**开关，禁用最终用户在其组织内运行 Teams Exploratory 体验的功能。</span><span class="sxs-lookup"><span data-stu-id="fb55c-141">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>


### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="fb55c-142">阻止用户安装试用版应用和服务</span><span class="sxs-lookup"><span data-stu-id="fb55c-142">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="fb55c-143">可以禁用用户安装试用版应用和服务的功能，这会阻止用户运行 Teams 探索体验。</span><span class="sxs-lookup"><span data-stu-id="fb55c-143">You can turn off a user's ability to install trial apps and services, would prevent the user from running the Teams Exploratory experience.</span></span> <span data-ttu-id="fb55c-144">必须具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="fb55c-144">You must have admin privileges.</span></span> <span data-ttu-id="fb55c-145">若要详细了解管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](teams-exploratory.md)。</span><span class="sxs-lookup"><span data-stu-id="fb55c-145">To learn more about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](teams-exploratory.md)</span></span>

1. <span data-ttu-id="fb55c-146">从 [Microsoft 365 管理中心](https://portal.office.com/adminportal/home)，转到**设置** > **设置**，选择**服务**，然后选择**用户自有应用和服务**。</span><span class="sxs-lookup"><span data-stu-id="fb55c-146">From the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), go to **Settings** > **Settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![管理中心中“服务”页面的屏幕截图](media/iw-trial-services.png)

2. <span data-ttu-id="fb55c-148">清除**允许用户安装试用版应用和服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="fb55c-148">Clear the **Let users install trial apps and services** check box.</span></span>

    ![管理中心中“用户自有应用和服务”页面的屏幕截图](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="fb55c-150">如果你的组织不符合获取 Teams Exploratory 的条件，你将看不到“**允许用户安装试用版应用和服务**”选项。</span><span class="sxs-lookup"><span data-stu-id="fb55c-150">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="fb55c-151">为拥有包含 Teams 的许可证的用户管理可用性</span><span class="sxs-lookup"><span data-stu-id="fb55c-151">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="fb55c-152">分配了包含 Teams 的许可证的用户不符合获取 Teams Exploratory 的条件。</span><span class="sxs-lookup"><span data-stu-id="fb55c-152">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="fb55c-153">启用 Teams 服务计划时，用户可登录并使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="fb55c-153">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="fb55c-154">如果禁用服务计划，则用户无法登录，并且 Teams Exploratory 体验不可用。</span><span class="sxs-lookup"><span data-stu-id="fb55c-154">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="fb55c-155">必须具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="fb55c-155">You must have admin privileges.</span></span> 

<span data-ttu-id="fb55c-156">关闭对 Teams 的访问：</span><span class="sxs-lookup"><span data-stu-id="fb55c-156">To turn off access to Teams:</span></span>

1. <span data-ttu-id="fb55c-157">在 [Microsoft 365 管理中心](https://portal.office.com/adminportal/home)中，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="fb55c-157">In the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="fb55c-158">选择用户姓名旁的框。</span><span class="sxs-lookup"><span data-stu-id="fb55c-158">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="fb55c-159">在右侧的“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="fb55c-159">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="fb55c-160">在“**产品许可证**”窗格中，将开关切换为“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="fb55c-160">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![管理中心中的“产品许可证”页面的屏幕截图。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="fb55c-162">为已在使用 Teams Exploratory 体验的用户管理团队可用性</span><span class="sxs-lookup"><span data-stu-id="fb55c-162">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="fb55c-163">如果用户运行 Teams Exploratory 体验，则可以通过删除许可证或服务计划将其关闭。</span><span class="sxs-lookup"><span data-stu-id="fb55c-163">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="fb55c-164">必须具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="fb55c-164">You must have admin privileges.</span></span> 

<span data-ttu-id="fb55c-165">若要关闭 Teams Exploratory 体验许可证，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fb55c-165">To turn off the the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="fb55c-166">在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="fb55c-166">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="fb55c-167">选择用户姓名旁的框。</span><span class="sxs-lookup"><span data-stu-id="fb55c-167">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="fb55c-168">在右侧的“**产品许可证**”行中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="fb55c-168">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="fb55c-169">在“**产品许可证**”窗格中，将此 Exploratory 许可证的开关切换为“**关**”。</span><span class="sxs-lookup"><span data-stu-id="fb55c-169">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>
   
    >[!Note]
    ><span data-ttu-id="fb55c-170">组织中的第一位用户启动 Teams Exploratory 体验后，将显示 Teams Exploratory 切换开关。</span><span class="sxs-lookup"><span data-stu-id="fb55c-170">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="fb55c-171">为拥有 Teams Exploratory 许可证的用户管理 Teams</span><span class="sxs-lookup"><span data-stu-id="fb55c-171">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="fb55c-172">你可以管理拥有 Teams Exploratory 许可证的用户，就像管理具有常规付费许可证的用户一样。</span><span class="sxs-lookup"><span data-stu-id="fb55c-172">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="fb55c-173">有关详细信息，请参阅[为你的组织管理 Teams 设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="fb55c-173">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="fb55c-174">从 Teams Exploratory 许可证升级用户</span><span class="sxs-lookup"><span data-stu-id="fb55c-174">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="fb55c-175">要从 Teams Exploratory 许可证升级用户（必须拥有管理员权限），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fb55c-175">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following:</span></span>

1. <span data-ttu-id="fb55c-176">购买包含 Teams 的订阅。</span><span class="sxs-lookup"><span data-stu-id="fb55c-176">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="fb55c-177">删除用户的 Teams Exploratory 订阅。</span><span class="sxs-lookup"><span data-stu-id="fb55c-177">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="fb55c-178">分配新购买的许可证。</span><span class="sxs-lookup"><span data-stu-id="fb55c-178">Assign the newly purchased license.</span></span>

<span data-ttu-id="fb55c-179">有关详细信息，请参阅 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="fb55c-179">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="fb55c-180">如果 Teams Exploratory 许可证到期，而用户未立即升级到包含 Teams 的订阅，则不删除该用户数据。</span><span class="sxs-lookup"><span data-stu-id="fb55c-180">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, the user data is not removed.</span></span> <span data-ttu-id="fb55c-181">该用户仍保留在 Azure Active Directory 中，且 Teams 中的所有数据都将保留。</span><span class="sxs-lookup"><span data-stu-id="fb55c-181">The user still exists in Azure Active Directory and all data within Teams still remains.</span></span> <span data-ttu-id="fb55c-182">一旦向该用户分配新的许可证来重新启用 Teams 功能，则所有内容仍将存在。</span><span class="sxs-lookup"><span data-stu-id="fb55c-182">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.</span></span> 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="fb55c-183">这对旧版 Microsoft Teams 商业云试用版许可证有何影响？</span><span class="sxs-lookup"><span data-stu-id="fb55c-183">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses?</span></span>

<span data-ttu-id="fb55c-184">从 2020 年 2 月起，符合条件的用户可开始使用最新的 Microsoft Teams Exploratory 体验。</span><span class="sxs-lookup"><span data-stu-id="fb55c-184">As of February, 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="fb55c-185">所有旧版 Teams 商业云试用版许可证将在试用版到期前自动转换为新的服务。</span><span class="sxs-lookup"><span data-stu-id="fb55c-185">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="fb55c-186">当用户首次登录到其过期的 Teams 商业云试用版时，我们会自动向该用户分配 Teams Exploratory 体验许可证。</span><span class="sxs-lookup"><span data-stu-id="fb55c-186">When a user signs in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to that user.</span></span> <span data-ttu-id="fb55c-187">用户在登录前不会进行转换。</span><span class="sxs-lookup"><span data-stu-id="fb55c-187">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="fb55c-188">删除 Teams Exploratory 许可证</span><span class="sxs-lookup"><span data-stu-id="fb55c-188">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="fb55c-189">如果要通过 PowerShell 删除此许可证，请参阅：[使用 Office 365 PowerShell 删除用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="fb55c-189">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="fb55c-190">如果要通过管理门户删除此许可证，请参阅[从组织删除用户](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="fb55c-190">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="fb55c-191">Teams Exploratory 体验持续多长时间？</span><span class="sxs-lookup"><span data-stu-id="fb55c-191">How long does the Teams Exploratory experience last?</span></span>

<span data-ttu-id="fb55c-192">在 2021 年 1 月或之后的下一个**协议周年日**或**续订**前，使用 Microsoft Teams 探索体验都是免费的。</span><span class="sxs-lookup"><span data-stu-id="fb55c-192">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="fb55c-193">届时，Microsoft Exploratory 体验许可证的最终用户需要迁移到包含 Teams 的付费许可证。</span><span class="sxs-lookup"><span data-stu-id="fb55c-193">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="fb55c-194">此后启动的任何 Microsoft 探索体验许可证在下一个**周年日**或**续订**周期前一直都是免费的。</span><span class="sxs-lookup"><span data-stu-id="fb55c-194">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span> 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a><span data-ttu-id="fb55c-195">如果最终用户刚好在我的周年纪念或续订日期前启动 Microsoft Teams Exploratory 体验，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="fb55c-195">What happens if an end user initiates the Microsoft Teams Exploratory experience just before my anniversary or renewal date?</span></span>

<span data-ttu-id="fb55c-196">在**协议周年日**或**续订**后的 90 天内启动的 Microsoft Teams 探索体验许可证无需迁移到付费许可证，直到下一个周年日或续订周期。</span><span class="sxs-lookup"><span data-stu-id="fb55c-196">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** will not be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span> 

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="fb55c-197">如果我的协议没有周年日或每年的续约日期（例如逐月协议），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb55c-197">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)?</span></span>

<span data-ttu-id="fb55c-198">对于无周年日或年度续订日期的协议，第一位最终用户后面的年份激活 Microsoft 团队探索体验许可证将被视为周年日或续订日期。</span><span class="sxs-lookup"><span data-stu-id="fb55c-198">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="fb55c-199">根据上述策略，必须在每年的此日期之前将拥有 Microsoft Teams 探索许可证的用户转换为付费许可证。</span><span class="sxs-lookup"><span data-stu-id="fb55c-199">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined above.</span></span>

<span data-ttu-id="fb55c-200">例如，如果第一位最终用户在 2020 年 6 月 19 日激活了 Microsoft Teams 探索，则他们和客户租户中的所有其他符合条件的用户必须在 2021 年 6月 19 日之前转换为 Teams 付费许可证。</span><span class="sxs-lookup"><span data-stu-id="fb55c-200">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span> 

