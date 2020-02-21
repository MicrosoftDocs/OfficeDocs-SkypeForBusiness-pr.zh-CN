---
title: 在 Microsoft Teams 中管理自定义应用策略和设置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何管理自定义应用策略和设置，以控制你的组织中可在 Microsoft 团队中上载自定义应用的人员。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
ms.openlocfilehash: 86bf441f6dfa74b243f1a6e64139a32b8b94d7fa
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161628"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="57b1a-103">在 Microsoft Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="57b1a-104">若要使用应用 Studio，请参阅[Microsoft 团队平台上使用 c #/.NET 和应用 studio 的入门](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio)。最后一步尚不起作用，因此你需要下载 zip 并在将[应用包上载到 Microsoft 团队](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)时以旧方式安装它。</span><span class="sxs-lookup"><span data-stu-id="57b1a-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="57b1a-105">作为管理员，你可以使用自定义应用策略和设置来控制你的组织中哪些人可以将自定义应用上载到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="57b1a-106">管理员决定哪些用户可以上载自定义应用，管理员和团队所有者可以确定你的组织中的特定团队是否允许将自定义应用添加到其中。</span><span class="sxs-lookup"><span data-stu-id="57b1a-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  <span data-ttu-id="57b1a-107">编辑自定义应用策略后，所做的更改可能需要长达24小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="57b1a-107">After you edit the custom app policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="overview-of-custom-apps"></a><span data-ttu-id="57b1a-108">自定义应用概述</span><span class="sxs-lookup"><span data-stu-id="57b1a-108">Overview of custom apps</span></span>

<span data-ttu-id="57b1a-109">用户可以直接将应用包（在 .zip 文件中）上载到团队或个人上下文中，将自定义应用添加到团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-109">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="57b1a-110">这不同于通过团队应用商店添加应用的方式。</span><span class="sxs-lookup"><span data-stu-id="57b1a-110">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="57b1a-111">通过上载应用包（也称为旁加载）添加自定义应用，可以在开发应用程序之前对其进行测试，然后才可以广泛分发。</span><span class="sxs-lookup"><span data-stu-id="57b1a-111">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="57b1a-112">它还允许你构建仅供内部使用的应用，并与你的团队共享它，而无需将其提交到团队应用商店中的团队应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="57b1a-112">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![显示应用商店中的 "上载自定义应用" 选项的屏幕截图](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="57b1a-114">自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-114">Custom app policy and settings</span></span>

<span data-ttu-id="57b1a-115">三个组件确定用户是否可以将自定义应用上载到团队，使你可以精确控制哪些人可以向团队添加自定义应用，以及可将哪些团队自定义应用添加到：</span><span class="sxs-lookup"><span data-stu-id="57b1a-115">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="57b1a-116">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="57b1a-116">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="57b1a-117">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-117">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="57b1a-118">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-118">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="57b1a-119">这些设置不会影响阻止第三方应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="57b1a-119">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="57b1a-120">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="57b1a-120">User custom app policy</span></span>

<span data-ttu-id="57b1a-121">作为[应用设置策略](teams-app-setup-policies.md)的一部分，管理员可以使用策略设置 "**上载自定义应用**" 来控制用户是否可以将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-121">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Upload custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="57b1a-122">如果此设置已关闭：</span><span class="sxs-lookup"><span data-stu-id="57b1a-122">If this setting is turned off:</span></span>

- <span data-ttu-id="57b1a-123">用户不能将自定义应用上载到组织中的任何团队或个人上下文中。</span><span class="sxs-lookup"><span data-stu-id="57b1a-123">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="57b1a-124">用户可以与自定义应用交互，具体取决于组织范围内的自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="57b1a-124">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="57b1a-125">如果启用此设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="57b1a-125">If this setting is turned on:</span></span>

- <span data-ttu-id="57b1a-126">根据组织范围内的自定义应用设置，用户可以将自定义应用上载到允许其所有者和团队的团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-126">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="57b1a-127">用户可将自定义应用程序上载到个人上下文。</span><span class="sxs-lookup"><span data-stu-id="57b1a-127">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="57b1a-128">用户可以与自定义应用交互，具体取决于组织范围内的自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="57b1a-128">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="57b1a-129">你可以编辑全局应用设置策略中的设置以包括所需的应用。</span><span class="sxs-lookup"><span data-stu-id="57b1a-129">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="57b1a-130">如果要为组织中的不同组用户自定义团队，请创建并分配一个或多个自定义应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="57b1a-130">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="57b1a-131">设置用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="57b1a-131">Set a user custom app policy</span></span>

1. <span data-ttu-id="57b1a-132">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="57b1a-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="57b1a-133">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="57b1a-133">Click **Add**.</span></span>
3. <span data-ttu-id="57b1a-134">打开或关闭 "**上载自定义应用**"。</span><span class="sxs-lookup"><span data-stu-id="57b1a-134">Turn on or turn off **Upload custom apps**.</span></span>
4. <span data-ttu-id="57b1a-135">为策略选择所需的任何其他设置。</span><span class="sxs-lookup"><span data-stu-id="57b1a-135">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="57b1a-136">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="57b1a-136">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="57b1a-137">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-137">Team custom app setting</span></span>

<span data-ttu-id="57b1a-138">管理员和团队所有者可以控制是否允许将自定义应用添加到该团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-138">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="57b1a-139">此设置，**允许成员上载自定义应用**，以及用户的自定义应用策略确定谁可以向特定团队添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="57b1a-139">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="57b1a-140">如果此设置已关闭：</span><span class="sxs-lookup"><span data-stu-id="57b1a-140">If this setting is turned off:</span></span>

- <span data-ttu-id="57b1a-141">如果其自定义应用策略允许，团队所有者可以添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="57b1a-141">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="57b1a-142">不是团队所有者的团队成员无法将自定义应用添加到团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-142">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="57b1a-143">如果启用此设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="57b1a-143">If this setting is turned on:</span></span>

- <span data-ttu-id="57b1a-144">如果其自定义应用策略允许，团队所有者可以添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="57b1a-144">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="57b1a-145">不是团队所有者的团队成员可以添加自定义应用（如果其自定义应用策略允许）。</span><span class="sxs-lookup"><span data-stu-id="57b1a-145">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="57b1a-146">配置团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-146">Configure the team custom app setting</span></span>

1. <span data-ttu-id="57b1a-147">在团队中，转到团队，单击 "**更多选项" ̇̇̇** > "**管理团队**"。</span><span class="sxs-lookup"><span data-stu-id="57b1a-147">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="57b1a-148">单击 "**设置**"，然后展开 "**成员权限**"。</span><span class="sxs-lookup"><span data-stu-id="57b1a-148">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="57b1a-149">选中或清除 "**允许成员上载自定义应用**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="57b1a-149">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![显示团队自定义应用设置的屏幕截图](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="57b1a-151">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-151">Org-wide custom app setting</span></span>

<span data-ttu-id="57b1a-152">"[管理应用](manage-apps.md)" 页面上的 "**允许与自定义应用进行交互**" 组织范围内的自定义应用设置适用于你组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="57b1a-152">The **Allow interaction with custom apps** org-wide custom app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="57b1a-153">此设置将替代用户和团队自定义应用策略和设置。</span><span class="sxs-lookup"><span data-stu-id="57b1a-153">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="57b1a-154">它旨在充当安全事件期间的主开/关切换。</span><span class="sxs-lookup"><span data-stu-id="57b1a-154">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="57b1a-155">配置组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-155">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="57b1a-156">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="57b1a-156">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="57b1a-157">单击 "**组织范围的应用设置**"。</span><span class="sxs-lookup"><span data-stu-id="57b1a-157">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="57b1a-158">在 "**自定义应用**" 下，打开或关闭 "**允许与自定义应用交互**"。</span><span class="sxs-lookup"><span data-stu-id="57b1a-158">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![显示组织范围的自定义应用设置的屏幕截图](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="57b1a-160">自定义应用策略和设置的协同工作方式</span><span class="sxs-lookup"><span data-stu-id="57b1a-160">How custom app policies and settings work together</span></span>

<span data-ttu-id="57b1a-161">下表汇总了自定义应用策略和设置、它们如何协同工作以及它们的合并效果，用于控制组织中的哪些人可以将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-161">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="57b1a-162">例如，你希望仅允许团队所有者将自定义应用上载到特定团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-162">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="57b1a-163">您将设置以下内容：</span><span class="sxs-lookup"><span data-stu-id="57b1a-163">You would set the following:</span></span>
- <span data-ttu-id="57b1a-164">在 Microsoft 团队管理中心中启用 "**允许与自定义应用交互**" 设置。</span><span class="sxs-lookup"><span data-stu-id="57b1a-164">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="57b1a-165">关闭允许成员上载要限制访问的每个团队的**自定义应用**。</span><span class="sxs-lookup"><span data-stu-id="57b1a-165">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="57b1a-166">在 "**上载自定义应用**" 设置处于打开状态的情况下，在 Microsoft 团队管理中心中创建和分配自定义应用设置策略，并将其分配给团队所有者。</span><span class="sxs-lookup"><span data-stu-id="57b1a-166">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **Upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="57b1a-167">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-167">Org-wide custom app setting</span></span> |<span data-ttu-id="57b1a-168">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-168">Team custom app setting</span></span> |<span data-ttu-id="57b1a-169">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="57b1a-169">User custom app policy</span></span> |<span data-ttu-id="57b1a-170">事实上</span><span class="sxs-lookup"><span data-stu-id="57b1a-170">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="57b1a-171">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-171">Off</span></span>    | <span data-ttu-id="57b1a-172">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-172">Off</span></span>    | <span data-ttu-id="57b1a-173">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-173">Off</span></span>     |<span data-ttu-id="57b1a-174">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="57b1a-174">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="57b1a-175">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="57b1a-175">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="57b1a-176">可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="57b1a-176">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="57b1a-177">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-177">Off</span></span>     | <span data-ttu-id="57b1a-178">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-178">Off</span></span>     | <span data-ttu-id="57b1a-179">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-179">On</span></span>        |<span data-ttu-id="57b1a-180">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="57b1a-180">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="57b1a-181">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="57b1a-181">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="57b1a-182">可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="57b1a-182">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="57b1a-183">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-183">Off</span></span>    | <span data-ttu-id="57b1a-184">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-184">On</span></span>        | <span data-ttu-id="57b1a-185">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-185">Off</span></span>        |<span data-ttu-id="57b1a-186">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="57b1a-186">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="57b1a-187">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="57b1a-187">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="57b1a-188">你可以使用 Windows PowerShell 删除自定义应用。</span><span class="sxs-lookup"><span data-stu-id="57b1a-188">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="57b1a-189">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-189">Off</span></span>    | <span data-ttu-id="57b1a-190">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-190">On</span></span>      | <span data-ttu-id="57b1a-191">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-191">On</span></span>       |<span data-ttu-id="57b1a-192">将阻止你的组织与所有自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="57b1a-192">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="57b1a-193">任何人都无法上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="57b1a-193">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="57b1a-194">可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="57b1a-194">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="57b1a-195">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-195">On</span></span>    | <span data-ttu-id="57b1a-196">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-196">Off</span></span>       | <span data-ttu-id="57b1a-197">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-197">Off</span></span>         |  <span data-ttu-id="57b1a-198">用户无法上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="57b1a-198">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="57b1a-199">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-199">On</span></span>     | <span data-ttu-id="57b1a-200">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-200">Off</span></span>       | <span data-ttu-id="57b1a-201">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-201">On</span></span>         | <span data-ttu-id="57b1a-202">如果用户是团队所有者，则他们可以将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-202">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="57b1a-203">如果用户不是团队所有者，则他们无法将自定义应用上载到团队。</span><span class="sxs-lookup"><span data-stu-id="57b1a-203">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="57b1a-204">用户可以在个人上下文中上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="57b1a-204">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="57b1a-205">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-205">On</span></span>     | <span data-ttu-id="57b1a-206">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-206">On</span></span>     | <span data-ttu-id="57b1a-207">关</span><span class="sxs-lookup"><span data-stu-id="57b1a-207">Off</span></span>         | <span data-ttu-id="57b1a-208">用户无法上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="57b1a-208">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="57b1a-209">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-209">On</span></span>    | <span data-ttu-id="57b1a-210">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-210">On</span></span>        | <span data-ttu-id="57b1a-211">开</span><span class="sxs-lookup"><span data-stu-id="57b1a-211">On</span></span>        | <span data-ttu-id="57b1a-212">用户可以将自定义应用上载到团队，无论用户是否是团队所有者。</span><span class="sxs-lookup"><span data-stu-id="57b1a-212">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="57b1a-213">用户可以在个人上下文中上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="57b1a-213">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="57b1a-214">相关主题</span><span class="sxs-lookup"><span data-stu-id="57b1a-214">Related topics</span></span>
 
- [<span data-ttu-id="57b1a-215">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="57b1a-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
