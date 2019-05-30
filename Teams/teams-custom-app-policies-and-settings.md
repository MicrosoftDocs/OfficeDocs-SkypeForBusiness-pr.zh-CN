---
title: 在 Microsoft Teams 中管理自定义应用策略和设置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/18/2019
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何管理自定义应用策略和设置, 以控制你的组织中可在 Microsoft 团队中上载自定义应用的人员。
ms.openlocfilehash: c1aa7489761fb27f525fbb6eb8f2056ae3dd33c8
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548658"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="94688-103">在 Microsoft Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="94688-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> <span data-ttu-id="94688-104">有关在 Microsoft 团队中管理应用的当前方法, 请参阅[管理你的组织的 Microsoft 团队设置](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365)。</span><span class="sxs-lookup"><span data-stu-id="94688-104">For the current method of managing apps in Microsoft Teams, see [Manage Microsoft Teams settings for your organization](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).</span></span>

<span data-ttu-id="94688-105">作为管理员, 你可以使用自定义应用策略和设置来控制你的组织中哪些人可以将自定义应用上载到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="94688-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="94688-106">管理员决定哪些用户可以上载自定义应用, 管理员和团队所有者可以确定你的组织中的特定团队是否允许将自定义应用添加到其中。</span><span class="sxs-lookup"><span data-stu-id="94688-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  

## <a name="overview-of-custom-apps"></a><span data-ttu-id="94688-107">自定义应用概述</span><span class="sxs-lookup"><span data-stu-id="94688-107">Overview of custom apps</span></span>

<span data-ttu-id="94688-108">用户可以直接将应用包 (在 .zip 文件中) 上载到团队或个人上下文中, 将自定义应用添加到团队。</span><span class="sxs-lookup"><span data-stu-id="94688-108">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="94688-109">这不同于通过团队应用商店添加应用的方式。</span><span class="sxs-lookup"><span data-stu-id="94688-109">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="94688-110">通过上载应用包 (也称为旁加载) 添加自定义应用, 可以在开发应用程序之前对其进行测试, 然后才可以广泛分发。</span><span class="sxs-lookup"><span data-stu-id="94688-110">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="94688-111">它还允许你构建仅供内部使用的应用, 并与你的团队共享它, 而无需将其提交到团队应用商店中的团队应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="94688-111">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![显示 "在应用商店中上载自定义应用" 选项的屏幕截图](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="94688-113">自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="94688-113">Custom app policy and settings</span></span>

<span data-ttu-id="94688-114">三个组件确定用户是否可以将自定义应用上载到团队, 使你可以精确控制哪些人可以向团队添加自定义应用, 以及可将哪些团队自定义应用添加到:</span><span class="sxs-lookup"><span data-stu-id="94688-114">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="94688-115">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="94688-115">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="94688-116">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="94688-116">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="94688-117">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="94688-117">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="94688-118">这些设置不会影响阻止第三方应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="94688-118">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="94688-119">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="94688-119">User custom app policy</span></span>

<span data-ttu-id="94688-120">作为[应用设置策略](teams-app-setup-policies.md)的一部分, 管理员可以使用策略设置 "**允许上载自定义应用**" 来控制用户是否可以将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="94688-120">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Allow uploading custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="94688-121">如果此设置已关闭:</span><span class="sxs-lookup"><span data-stu-id="94688-121">If this setting is turned off:</span></span>

- <span data-ttu-id="94688-122">用户不能将自定义应用上载到组织中的任何团队或个人上下文中。</span><span class="sxs-lookup"><span data-stu-id="94688-122">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="94688-123">用户可以与自定义应用交互, 具体取决于组织范围内的自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="94688-123">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="94688-124">如果启用此设置, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="94688-124">If this setting is turned on:</span></span>

- <span data-ttu-id="94688-125">根据组织范围内的自定义应用设置, 用户可以将自定义应用上载到允许其所有者和团队的团队。</span><span class="sxs-lookup"><span data-stu-id="94688-125">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="94688-126">用户可将自定义应用程序上载到个人上下文。</span><span class="sxs-lookup"><span data-stu-id="94688-126">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="94688-127">用户可以与自定义应用交互, 具体取决于组织范围内的自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="94688-127">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="94688-128">你可以编辑全局应用设置策略中的设置以包括所需的应用。</span><span class="sxs-lookup"><span data-stu-id="94688-128">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="94688-129">如果要为组织中的不同组用户自定义团队, 请创建并分配一个或多个自定义应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="94688-129">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="94688-130">设置用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="94688-130">Set a user custom app policy</span></span>

1. <span data-ttu-id="94688-131">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="94688-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="94688-132">选择 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="94688-132">Select **New policy**.</span></span>
3. <span data-ttu-id="94688-133">打开或关闭 "**允许上载自定义应用**"。</span><span class="sxs-lookup"><span data-stu-id="94688-133">Turn on or turn off **Allow uploading custom apps**.</span></span>
4. <span data-ttu-id="94688-134">为策略选择所需的任何其他设置。</span><span class="sxs-lookup"><span data-stu-id="94688-134">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="94688-135">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="94688-135">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="94688-136">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="94688-136">Team custom app setting</span></span>

<span data-ttu-id="94688-137">管理员和团队所有者可以控制是否允许将自定义应用添加到该团队。</span><span class="sxs-lookup"><span data-stu-id="94688-137">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="94688-138">此设置,**允许成员上载自定义应用**, 以及用户的自定义应用策略确定谁可以向特定团队添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="94688-138">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="94688-139">如果此设置已关闭:</span><span class="sxs-lookup"><span data-stu-id="94688-139">If this setting is turned off:</span></span>

- <span data-ttu-id="94688-140">如果其自定义应用策略允许, 团队所有者可以添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="94688-140">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="94688-141">不是团队所有者的团队成员无法将自定义应用添加到团队。</span><span class="sxs-lookup"><span data-stu-id="94688-141">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="94688-142">如果启用此设置, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="94688-142">If this setting is turned on:</span></span>

- <span data-ttu-id="94688-143">如果其自定义应用策略允许, 团队所有者可以添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="94688-143">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="94688-144">不是团队所有者的团队成员可以添加自定义应用 (如果其自定义应用策略允许)。</span><span class="sxs-lookup"><span data-stu-id="94688-144">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="94688-145">配置团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="94688-145">Configure the team custom app setting</span></span>

1. <span data-ttu-id="94688-146">在团队中, 转到团队, 单击 "**更多选项" ̇̇̇** > "**管理团队**"。</span><span class="sxs-lookup"><span data-stu-id="94688-146">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="94688-147">单击 "**设置**", 然后展开 "**成员权限**"。</span><span class="sxs-lookup"><span data-stu-id="94688-147">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="94688-148">选中或清除 "**允许成员上载自定义应用**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="94688-148">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![显示团队自定义应用设置的屏幕截图](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="94688-150">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="94688-150">Org-wide custom app setting</span></span>

<span data-ttu-id="94688-151">组织范围的自定义应用设置 (**允许与自定义应用交互**) 适用于你的组织中的所有人, 并控制他们是否可以上传或与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="94688-151">The org-wide custom app setting, **Allow interaction with custom apps**, applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="94688-152">此设置将替代用户和团队自定义应用策略和设置。</span><span class="sxs-lookup"><span data-stu-id="94688-152">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="94688-153">它旨在充当安全事件期间的主开/关切换。</span><span class="sxs-lookup"><span data-stu-id="94688-153">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="94688-154">配置组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="94688-154">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="94688-155">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="94688-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="94688-156">单击 "**组织范围的应用设置**"。</span><span class="sxs-lookup"><span data-stu-id="94688-156">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="94688-157">在 "**自定义应用**" 下, 打开或关闭 "**允许与自定义应用交互**"。</span><span class="sxs-lookup"><span data-stu-id="94688-157">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![显示组织范围的自定义应用设置的屏幕截图](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="94688-159">自定义应用策略和设置的协同工作方式</span><span class="sxs-lookup"><span data-stu-id="94688-159">How custom app policies and settings work together</span></span>

<span data-ttu-id="94688-160">下表汇总了自定义应用策略和设置、它们如何协同工作以及它们的合并效果, 用于控制组织中的哪些人可以将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="94688-160">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="94688-161">例如, 你希望仅允许团队所有者将自定义应用上载到特定团队。</span><span class="sxs-lookup"><span data-stu-id="94688-161">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="94688-162">您将设置以下内容:</span><span class="sxs-lookup"><span data-stu-id="94688-162">You would set the following:</span></span>
- <span data-ttu-id="94688-163">在 Microsoft 团队管理中心中启用 "**允许与自定义应用交互**" 设置。</span><span class="sxs-lookup"><span data-stu-id="94688-163">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="94688-164">关闭允许成员上载要限制访问的每个团队的**自定义应用**。</span><span class="sxs-lookup"><span data-stu-id="94688-164">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="94688-165">在 Microsoft 团队管理中心创建和分配自定义应用设置策略,**用户可以上载 "自定义应用**" 设置, 并将其分配给团队所有者。</span><span class="sxs-lookup"><span data-stu-id="94688-165">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **User can upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="94688-166">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="94688-166">Org-wide custom app setting</span></span> |<span data-ttu-id="94688-167">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="94688-167">Team custom app setting</span></span> |<span data-ttu-id="94688-168">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="94688-168">User custom app policy</span></span> |<span data-ttu-id="94688-169">事实上</span><span class="sxs-lookup"><span data-stu-id="94688-169">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="94688-170">关</span><span class="sxs-lookup"><span data-stu-id="94688-170">Off</span></span>    | <span data-ttu-id="94688-171">关</span><span class="sxs-lookup"><span data-stu-id="94688-171">Off</span></span>    | <span data-ttu-id="94688-172">关</span><span class="sxs-lookup"><span data-stu-id="94688-172">Off</span></span>     |<span data-ttu-id="94688-173">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="94688-173">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="94688-174">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="94688-174">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="94688-175">可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="94688-175">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="94688-176">关</span><span class="sxs-lookup"><span data-stu-id="94688-176">Off</span></span>     | <span data-ttu-id="94688-177">关</span><span class="sxs-lookup"><span data-stu-id="94688-177">Off</span></span>     | <span data-ttu-id="94688-178">开</span><span class="sxs-lookup"><span data-stu-id="94688-178">On</span></span>        |<span data-ttu-id="94688-179">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="94688-179">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="94688-180">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="94688-180">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="94688-181">可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="94688-181">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="94688-182">关</span><span class="sxs-lookup"><span data-stu-id="94688-182">Off</span></span>    | <span data-ttu-id="94688-183">开</span><span class="sxs-lookup"><span data-stu-id="94688-183">On</span></span>        | <span data-ttu-id="94688-184">关</span><span class="sxs-lookup"><span data-stu-id="94688-184">Off</span></span>        |<span data-ttu-id="94688-185">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="94688-185">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="94688-186">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="94688-186">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="94688-187">你可以使用 Windows PowerShell 删除自定义应用。</span><span class="sxs-lookup"><span data-stu-id="94688-187">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="94688-188">关</span><span class="sxs-lookup"><span data-stu-id="94688-188">Off</span></span>    | <span data-ttu-id="94688-189">开</span><span class="sxs-lookup"><span data-stu-id="94688-189">On</span></span>      | <span data-ttu-id="94688-190">开</span><span class="sxs-lookup"><span data-stu-id="94688-190">On</span></span>       |<span data-ttu-id="94688-191">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="94688-191">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="94688-192">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="94688-192">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="94688-193">可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="94688-193">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="94688-194">开</span><span class="sxs-lookup"><span data-stu-id="94688-194">On</span></span>    | <span data-ttu-id="94688-195">关</span><span class="sxs-lookup"><span data-stu-id="94688-195">Off</span></span>       | <span data-ttu-id="94688-196">关</span><span class="sxs-lookup"><span data-stu-id="94688-196">Off</span></span>         |  <span data-ttu-id="94688-197">用户无法上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="94688-197">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="94688-198">开</span><span class="sxs-lookup"><span data-stu-id="94688-198">On</span></span>     | <span data-ttu-id="94688-199">关</span><span class="sxs-lookup"><span data-stu-id="94688-199">Off</span></span>       | <span data-ttu-id="94688-200">开</span><span class="sxs-lookup"><span data-stu-id="94688-200">On</span></span>         | <span data-ttu-id="94688-201">如果用户是团队所有者, 则他们可以将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="94688-201">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="94688-202">如果用户不是团队所有者, 则他们无法将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="94688-202">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="94688-203">用户可以在个人上下文中上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="94688-203">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="94688-204">开</span><span class="sxs-lookup"><span data-stu-id="94688-204">On</span></span>     | <span data-ttu-id="94688-205">开</span><span class="sxs-lookup"><span data-stu-id="94688-205">On</span></span>     | <span data-ttu-id="94688-206">关</span><span class="sxs-lookup"><span data-stu-id="94688-206">Off</span></span>         | <span data-ttu-id="94688-207">用户无法上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="94688-207">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="94688-208">开</span><span class="sxs-lookup"><span data-stu-id="94688-208">On</span></span>    | <span data-ttu-id="94688-209">开</span><span class="sxs-lookup"><span data-stu-id="94688-209">On</span></span>        | <span data-ttu-id="94688-210">开</span><span class="sxs-lookup"><span data-stu-id="94688-210">On</span></span>        | <span data-ttu-id="94688-211">用户可以将自定义应用上载到团队, 无论用户是否是团队所有者。</span><span class="sxs-lookup"><span data-stu-id="94688-211">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="94688-212">用户可以在个人上下文中上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="94688-212">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="94688-213">相关主题</span><span class="sxs-lookup"><span data-stu-id="94688-213">Related topics</span></span>
- [<span data-ttu-id="94688-214">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="94688-214">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="94688-215">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="94688-215">Manage app setup policies in Microsoft Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="94688-216">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="94688-216">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
