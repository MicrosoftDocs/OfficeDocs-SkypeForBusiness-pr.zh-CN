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
ms.openlocfilehash: 27123e6e943f7dc570098c36732fd0d1ba09e8af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283708"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="a76d5-103">在 Microsoft Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="a76d5-104">作为管理员, 你可以使用自定义应用策略和设置来控制你的组织中哪些人可以将自定义应用上载到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-104">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="a76d5-105">管理员决定哪些用户可以上载自定义应用, 管理员和团队所有者可以确定你的组织中的特定团队是否允许将自定义应用添加到其中。</span><span class="sxs-lookup"><span data-stu-id="a76d5-105">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  

## <a name="overview-of-custom-apps"></a><span data-ttu-id="a76d5-106">自定义应用概述</span><span class="sxs-lookup"><span data-stu-id="a76d5-106">Overview of custom apps</span></span>

<span data-ttu-id="a76d5-107">用户可以直接将应用包 (在 .zip 文件中) 上载到团队或个人上下文中, 将自定义应用添加到团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-107">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="a76d5-108">这不同于通过团队应用商店添加应用的方式。</span><span class="sxs-lookup"><span data-stu-id="a76d5-108">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="a76d5-109">通过上载应用包 (也称为旁加载) 添加自定义应用, 可以在开发应用程序之前对其进行测试, 然后才可以广泛分发。</span><span class="sxs-lookup"><span data-stu-id="a76d5-109">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="a76d5-110">它还允许你构建仅供内部使用的应用, 并与你的团队共享它, 而无需将其提交到团队应用商店中的团队应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="a76d5-110">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![上载自定义应用程序](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="a76d5-112">自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-112">Custom app policy and settings</span></span>

<span data-ttu-id="a76d5-113">三个组件确定用户是否可以将自定义应用上载到团队, 使你可以精确控制哪些人可以向团队添加自定义应用, 以及可将哪些团队自定义应用添加到:</span><span class="sxs-lookup"><span data-stu-id="a76d5-113">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="a76d5-114">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="a76d5-114">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="a76d5-115">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-115">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="a76d5-116">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-116">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="a76d5-117">这些设置不会影响阻止第三方应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="a76d5-117">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="a76d5-118">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="a76d5-118">User custom app policy</span></span>

<span data-ttu-id="a76d5-119">作为[应用设置策略](teams-app-setup-policies.md)的一部分, 管理员可以使用策略设置 "**允许上载自定义应用**" 来控制用户是否可以将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-119">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Allow uploading custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="a76d5-120">如果此设置已关闭:</span><span class="sxs-lookup"><span data-stu-id="a76d5-120">If this setting is turned off:</span></span>

- <span data-ttu-id="a76d5-121">用户不能将自定义应用上载到组织中的任何团队或个人上下文中。</span><span class="sxs-lookup"><span data-stu-id="a76d5-121">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="a76d5-122">用户可以与自定义应用交互, 具体取决于组织范围内的自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="a76d5-122">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="a76d5-123">如果启用此设置, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="a76d5-123">If this setting is turned on:</span></span>

- <span data-ttu-id="a76d5-124">根据组织范围内的自定义应用设置, 用户可以将自定义应用上载到允许其所有者和团队的团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-124">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="a76d5-125">用户可将自定义应用程序上载到个人上下文。</span><span class="sxs-lookup"><span data-stu-id="a76d5-125">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="a76d5-126">用户可以与自定义应用交互, 具体取决于组织范围内的自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="a76d5-126">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="a76d5-127">你可以编辑全局应用设置策略中的设置以包括所需的应用。</span><span class="sxs-lookup"><span data-stu-id="a76d5-127">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="a76d5-128">如果要为组织中的不同组用户自定义团队, 请创建并分配一个或多个自定义应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="a76d5-128">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="a76d5-129">设置用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="a76d5-129">Set a user custom app policy</span></span>

1. <span data-ttu-id="a76d5-130">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="a76d5-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="a76d5-131">选择 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="a76d5-131">Select **New policy**.</span></span>
3. <span data-ttu-id="a76d5-132">打开或关闭 "**允许上载自定义应用**"。</span><span class="sxs-lookup"><span data-stu-id="a76d5-132">Turn on or turn off **Allow uploading custom apps**.</span></span>
4. <span data-ttu-id="a76d5-133">为策略选择所需的任何其他设置。</span><span class="sxs-lookup"><span data-stu-id="a76d5-133">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="a76d5-134">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a76d5-134">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="a76d5-135">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-135">Team custom app setting</span></span>

<span data-ttu-id="a76d5-136">管理员和团队所有者可以控制是否允许将自定义应用添加到该团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-136">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="a76d5-137">此设置,**允许成员上载自定义应用**, 以及用户的自定义应用策略确定谁可以向特定团队添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="a76d5-137">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="a76d5-138">如果此设置已关闭:</span><span class="sxs-lookup"><span data-stu-id="a76d5-138">If this setting is turned off:</span></span>

- <span data-ttu-id="a76d5-139">如果其自定义应用策略允许, 团队所有者可以添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="a76d5-139">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="a76d5-140">不是团队所有者的团队成员无法将自定义应用添加到团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-140">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="a76d5-141">如果启用此设置, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="a76d5-141">If this setting is turned on:</span></span>

- <span data-ttu-id="a76d5-142">如果其自定义应用策略允许, 团队所有者可以添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="a76d5-142">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="a76d5-143">不是团队所有者的团队成员可以添加自定义应用 (如果其自定义应用策略允许)。</span><span class="sxs-lookup"><span data-stu-id="a76d5-143">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="a76d5-144">配置团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-144">Configure the team custom app setting</span></span>

1. <span data-ttu-id="a76d5-145">在团队中, 转到团队, 单击 "**更多选项" ̇̇̇** > "**管理团队**"。</span><span class="sxs-lookup"><span data-stu-id="a76d5-145">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="a76d5-146">单击 "**设置**", 然后展开 "**成员权限**"。</span><span class="sxs-lookup"><span data-stu-id="a76d5-146">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="a76d5-147">选中或清除 "**允许成员上载自定义应用**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a76d5-147">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![团队自定义应用设置](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="a76d5-149">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-149">Org-wide custom app setting</span></span>

<span data-ttu-id="a76d5-150">组织范围的自定义应用设置 (**允许与自定义应用交互**) 适用于你的组织中的所有人, 并控制他们是否可以上传或与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="a76d5-150">The org-wide custom app setting, **Allow interaction with custom apps**, applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="a76d5-151">此设置将替代用户和团队自定义应用策略和设置。</span><span class="sxs-lookup"><span data-stu-id="a76d5-151">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="a76d5-152">它旨在充当安全事件期间的主开/关切换。</span><span class="sxs-lookup"><span data-stu-id="a76d5-152">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="a76d5-153">配置组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-153">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="a76d5-154">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="a76d5-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="a76d5-155">单击 "**组织范围的应用设置**"。</span><span class="sxs-lookup"><span data-stu-id="a76d5-155">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="a76d5-156">在 "**自定义应用**" 下, 打开或关闭 "**允许与自定义应用交互**"。</span><span class="sxs-lookup"><span data-stu-id="a76d5-156">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![组织范围的自定义应用设置](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="a76d5-158">自定义应用策略和设置的协同工作方式</span><span class="sxs-lookup"><span data-stu-id="a76d5-158">How custom app policies and settings work together</span></span>

<span data-ttu-id="a76d5-159">下表汇总了自定义应用策略和设置、它们如何协同工作以及它们的合并效果, 用于控制组织中的哪些人可以将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-159">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="a76d5-160">例如, 你希望仅允许团队所有者将自定义应用上载到特定团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-160">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="a76d5-161">您将设置以下内容:</span><span class="sxs-lookup"><span data-stu-id="a76d5-161">You would set the following:</span></span>
- <span data-ttu-id="a76d5-162">在 Microsoft 团队管理中心中启用 "**允许与自定义应用交互**" 设置。</span><span class="sxs-lookup"><span data-stu-id="a76d5-162">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="a76d5-163">关闭允许成员上载要限制访问的每个团队的**自定义应用**。</span><span class="sxs-lookup"><span data-stu-id="a76d5-163">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="a76d5-164">在 Microsoft 团队管理中心创建和分配自定义应用设置策略,**用户可以上载 "自定义应用**" 设置, 并将其分配给团队所有者。</span><span class="sxs-lookup"><span data-stu-id="a76d5-164">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **User can upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="a76d5-165">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-165">Org-wide custom app setting</span></span> |<span data-ttu-id="a76d5-166">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-166">Team custom app setting</span></span> |<span data-ttu-id="a76d5-167">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="a76d5-167">User custom app policy</span></span> |<span data-ttu-id="a76d5-168">事实上</span><span class="sxs-lookup"><span data-stu-id="a76d5-168">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="a76d5-169">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-169">Off</span></span>    | <span data-ttu-id="a76d5-170">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-170">Off</span></span>    | <span data-ttu-id="a76d5-171">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-171">Off</span></span>     |<span data-ttu-id="a76d5-172">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="a76d5-172">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="a76d5-173">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="a76d5-173">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="a76d5-174">可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="a76d5-174">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="a76d5-175">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-175">Off</span></span>     | <span data-ttu-id="a76d5-176">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-176">Off</span></span>     | <span data-ttu-id="a76d5-177">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-177">On</span></span>        |<span data-ttu-id="a76d5-178">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="a76d5-178">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="a76d5-179">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="a76d5-179">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="a76d5-180">可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="a76d5-180">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="a76d5-181">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-181">Off</span></span>    | <span data-ttu-id="a76d5-182">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-182">On</span></span>        | <span data-ttu-id="a76d5-183">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-183">Off</span></span>        |<span data-ttu-id="a76d5-184">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="a76d5-184">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="a76d5-185">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="a76d5-185">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="a76d5-186">你可以使用 Windows PowerShell 删除自定义应用。</span><span class="sxs-lookup"><span data-stu-id="a76d5-186">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="a76d5-187">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-187">Off</span></span>    | <span data-ttu-id="a76d5-188">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-188">On</span></span>      | <span data-ttu-id="a76d5-189">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-189">On</span></span>       |<span data-ttu-id="a76d5-190">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="a76d5-190">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="a76d5-191">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="a76d5-191">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="a76d5-192">可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="a76d5-192">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="a76d5-193">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-193">On</span></span>    | <span data-ttu-id="a76d5-194">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-194">Off</span></span>       | <span data-ttu-id="a76d5-195">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-195">Off</span></span>         |  <span data-ttu-id="a76d5-196">用户无法上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="a76d5-196">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="a76d5-197">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-197">On</span></span>     | <span data-ttu-id="a76d5-198">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-198">Off</span></span>       | <span data-ttu-id="a76d5-199">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-199">On</span></span>         | <span data-ttu-id="a76d5-200">如果用户是团队所有者, 则他们可以将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-200">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="a76d5-201">如果用户不是团队所有者, 则他们无法将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="a76d5-201">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="a76d5-202">用户可以在个人上下文中上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="a76d5-202">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="a76d5-203">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-203">On</span></span>     | <span data-ttu-id="a76d5-204">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-204">On</span></span>     | <span data-ttu-id="a76d5-205">关</span><span class="sxs-lookup"><span data-stu-id="a76d5-205">Off</span></span>         | <span data-ttu-id="a76d5-206">用户无法上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="a76d5-206">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="a76d5-207">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-207">On</span></span>    | <span data-ttu-id="a76d5-208">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-208">On</span></span>        | <span data-ttu-id="a76d5-209">开</span><span class="sxs-lookup"><span data-stu-id="a76d5-209">On</span></span>        | <span data-ttu-id="a76d5-210">用户可以将自定义应用上载到团队, 无论用户是否是团队所有者。</span><span class="sxs-lookup"><span data-stu-id="a76d5-210">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="a76d5-211">用户可以在个人上下文中上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="a76d5-211">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="a76d5-212">相关主题</span><span class="sxs-lookup"><span data-stu-id="a76d5-212">Related topics</span></span>
- [<span data-ttu-id="a76d5-213">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="a76d5-213">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="a76d5-214">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="a76d5-214">Manage app setup policies in Microsoft Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="a76d5-215">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="a76d5-215">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
