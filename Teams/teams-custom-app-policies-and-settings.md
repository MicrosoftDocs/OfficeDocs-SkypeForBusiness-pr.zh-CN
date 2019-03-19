---
title: 管理 Microsoft 团队中自定义应用程序策略和设置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/18/2019
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何管理自定义应用程序策略和设置以控制哪些人在组织中可以上载的 Microsoft 团队中的自定义应用程序。
ms.openlocfilehash: f914048c33bf611c53646d7d512c6af276209960
ms.sourcegitcommit: 1337975398a750bc06d2b03a7d6eb61716dcefb0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2019
ms.locfileid: "30677217"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="b3e78-103">管理 Microsoft 团队中自定义应用程序策略和设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-103">Manage custom app policies and settings in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="b3e78-104">作为一名管理员，您可以使用自定义应用程序策略和设置以控制哪些人在您的组织可以将自定义应用程序上载到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="b3e78-104">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="b3e78-105">管理员决定哪些用户可以上载自定义应用程序，并 admins 和团队所有者可以确定组织中的特定小组是否允许向它们添加自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-105">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  

## <a name="overview-of-custom-apps"></a><span data-ttu-id="b3e78-106">自定义应用程序的概述</span><span class="sxs-lookup"><span data-stu-id="b3e78-106">Overview of custom apps</span></span>

<span data-ttu-id="b3e78-107">用户可以通过直接向团队或个人上下文中上载应用程序包 （.zip 文件） 中的，向工作组添加自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-107">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="b3e78-108">这一点不同于通过团队应用程序商店添加应用程序的方式。</span><span class="sxs-lookup"><span data-stu-id="b3e78-108">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="b3e78-109">添加自定义应用程序上载应用程序包，也称为 sideloading，允许您测试应用程序，如它正在开发的已准备好广泛之前。</span><span class="sxs-lookup"><span data-stu-id="b3e78-109">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="b3e78-110">它还允许您构建仅供内部使用应用程序，并将其与您的团队共享不提交给团队应用程序存储区中的团队应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="b3e78-110">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![上载自定义应用程序](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="b3e78-112">自定义应用程序策略和设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-112">Custom app policy and settings</span></span>

<span data-ttu-id="b3e78-113">三个组件确定用户是否可以上载自定义的应用程序到团队，这样就可以精细控制可以添加到团队的自定义应用程序，并可以将其团队需要自定义应用程序添加到：</span><span class="sxs-lookup"><span data-stu-id="b3e78-113">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="b3e78-114">用户自定义应用程序策略</span><span class="sxs-lookup"><span data-stu-id="b3e78-114">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="b3e78-115">团队自定义应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-115">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="b3e78-116">组织范围内自定义应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-116">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="b3e78-117">这些设置不会影响阻止第三方应用程序的能力。</span><span class="sxs-lookup"><span data-stu-id="b3e78-117">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="b3e78-118">用户自定义应用程序策略</span><span class="sxs-lookup"><span data-stu-id="b3e78-118">User custom app policy</span></span>

<span data-ttu-id="b3e78-119">作为[应用程序设置策略](teams-app-setup-policies.md)的一部分，管理员可以使用策略设置，**用户可以上载自定义应用程序**，来控制用户是否可以上载自定义应用程序向工作组。</span><span class="sxs-lookup"><span data-stu-id="b3e78-119">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **User can upload custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="b3e78-120">如果此设置处于关闭状态：</span><span class="sxs-lookup"><span data-stu-id="b3e78-120">If this setting is turned off:</span></span>

- <span data-ttu-id="b3e78-121">用户不能将自定义应用程序上载到任何工作组在您的组织或个人上下文中。</span><span class="sxs-lookup"><span data-stu-id="b3e78-121">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="b3e78-122">用户可以使用自定义应用程序，具体取决于组织范围内自定义应用程序设置进行交互。</span><span class="sxs-lookup"><span data-stu-id="b3e78-122">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="b3e78-123">如果启用此设置：</span><span class="sxs-lookup"><span data-stu-id="b3e78-123">If this setting is turned on:</span></span>

- <span data-ttu-id="b3e78-124">用户可以上载自定义应用程序，到允许其团队和它们所所有者，具体取决于组织范围内自定义应用程序设置的团队。</span><span class="sxs-lookup"><span data-stu-id="b3e78-124">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="b3e78-125">用户可以将自定义应用程序上载到个人上下文。</span><span class="sxs-lookup"><span data-stu-id="b3e78-125">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="b3e78-126">用户可以使用自定义应用程序，具体取决于组织范围内自定义应用程序设置进行交互。</span><span class="sxs-lookup"><span data-stu-id="b3e78-126">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="b3e78-127">您可以编辑中的全局应用程序设置策略的设置，以包含所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-127">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="b3e78-128">如果您想要自定义为不同的组织中用户组的团队，创建并分配一个或多个自定义应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="b3e78-128">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="b3e78-129">设置用户自定义应用程序策略</span><span class="sxs-lookup"><span data-stu-id="b3e78-129">Set a user custom app policy</span></span>

1. <span data-ttu-id="b3e78-130">在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **设置策略**。</span><span class="sxs-lookup"><span data-stu-id="b3e78-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="b3e78-131">选择**新策略**。</span><span class="sxs-lookup"><span data-stu-id="b3e78-131">Select **New policy**.</span></span>
3. <span data-ttu-id="b3e78-132">打开或关闭**用户可以上载自定义应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b3e78-132">Turn on or turn off **User can upload custom apps**.</span></span>
4. <span data-ttu-id="b3e78-133">选择您要为策略的任何其他设置。</span><span class="sxs-lookup"><span data-stu-id="b3e78-133">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="b3e78-134">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b3e78-134">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="b3e78-135">团队自定义应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-135">Team custom app setting</span></span>

<span data-ttu-id="b3e78-136">管理员和团队所有者可以控制团队是否允许向其添加自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-136">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="b3e78-137">此设置，**允许成员，才能上载自定义应用程序**，以及用户的自定义应用程序策略确定谁可以将自定义应用程序添加到特定的团队。</span><span class="sxs-lookup"><span data-stu-id="b3e78-137">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="b3e78-138">如果此设置处于关闭状态：</span><span class="sxs-lookup"><span data-stu-id="b3e78-138">If this setting is turned off:</span></span>

- <span data-ttu-id="b3e78-139">团队所有者可以添加自定义应用程序，如果其自定义应用程序策略允许。</span><span class="sxs-lookup"><span data-stu-id="b3e78-139">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="b3e78-140">团队成员不团队所有者无法将自定义应用程序添加到团队。</span><span class="sxs-lookup"><span data-stu-id="b3e78-140">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="b3e78-141">如果启用此设置：</span><span class="sxs-lookup"><span data-stu-id="b3e78-141">If this setting is turned on:</span></span>

- <span data-ttu-id="b3e78-142">团队所有者可以添加自定义应用程序，如果其自定义应用程序策略允许为其。</span><span class="sxs-lookup"><span data-stu-id="b3e78-142">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="b3e78-143">团队成员不团队所有者可以添加自定义应用程序，如果其自定义应用程序策略允许为其。</span><span class="sxs-lookup"><span data-stu-id="b3e78-143">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="b3e78-144">配置团队自定义应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-144">Configure the team custom app setting</span></span>

1. <span data-ttu-id="b3e78-145">在工作组，转至组中，单击**多个选项 ˙˙˙** > **管理团队**。</span><span class="sxs-lookup"><span data-stu-id="b3e78-145">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="b3e78-146">单击**设置**，然后展开**成员权限**。</span><span class="sxs-lookup"><span data-stu-id="b3e78-146">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="b3e78-147">选中或清除**允许成员，才能上载自定义应用程序**复选框。</span><span class="sxs-lookup"><span data-stu-id="b3e78-147">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![团队自定义应用程序设置](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="b3e78-149">组织范围内自定义应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-149">Org-wide custom app setting</span></span>

<span data-ttu-id="b3e78-150">组织范围内自定义应用程序设置，**与自定义应用程序允许进行交互**，适用于您的组织中的所有人，并控制是否可以上载或自定义应用程序与之交互。</span><span class="sxs-lookup"><span data-stu-id="b3e78-150">The org-wide custom app setting, **Allow interaction with custom apps**, applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="b3e78-151">此设置将覆盖用户和团队自定义应用程序策略和设置。</span><span class="sxs-lookup"><span data-stu-id="b3e78-151">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="b3e78-152">它具有适用用作安全事件期间切换开关主控形状。</span><span class="sxs-lookup"><span data-stu-id="b3e78-152">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="b3e78-153">配置组织范围内自定义应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-153">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="b3e78-154">在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **权限策略**。</span><span class="sxs-lookup"><span data-stu-id="b3e78-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="b3e78-155">单击**组织范围的应用程序设置**。</span><span class="sxs-lookup"><span data-stu-id="b3e78-155">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="b3e78-156">在**自定义应用程序**，下打开或关闭**与自定义应用程序允许进行交互**。</span><span class="sxs-lookup"><span data-stu-id="b3e78-156">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![组织范围内自定义应用程序设置](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="b3e78-158">如何自定义应用程序策略和设置协同工作</span><span class="sxs-lookup"><span data-stu-id="b3e78-158">How custom app policies and settings work together</span></span>

<span data-ttu-id="b3e78-159">此表总结了自定义应用程序策略和设置、 如何协同工作的以及其对控制您的组织中的谁可以将自定义应用程序上载到团队的组合的影响。</span><span class="sxs-lookup"><span data-stu-id="b3e78-159">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="b3e78-160">例如，假设您想要允许仅将自定义应用程序上载到特定的团队团队所有者。</span><span class="sxs-lookup"><span data-stu-id="b3e78-160">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="b3e78-161">您可设置以下各项：</span><span class="sxs-lookup"><span data-stu-id="b3e78-161">You would set the following:</span></span>
- <span data-ttu-id="b3e78-162">打开 Microsoft 团队管理中心中**允许交互自定义应用程序**设置。</span><span class="sxs-lookup"><span data-stu-id="b3e78-162">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="b3e78-163">关闭您想要限制访问每个团队**允许成员，才能上载自定义应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b3e78-163">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="b3e78-164">创建和自定义应用程序安装程序在分配策略的 Microsoft 团队管理中心使用开启，**用户可以上载自定义应用程序**设置并将其分配给团队所有者。</span><span class="sxs-lookup"><span data-stu-id="b3e78-164">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **User can upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="b3e78-165">组织范围内自定义应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-165">Org-wide custom app setting</span></span> |<span data-ttu-id="b3e78-166">团队自定义应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-166">Team custom app setting</span></span> |<span data-ttu-id="b3e78-167">用户自定义应用程序策略</span><span class="sxs-lookup"><span data-stu-id="b3e78-167">User custom app policy</span></span> |<span data-ttu-id="b3e78-168">效果</span><span class="sxs-lookup"><span data-stu-id="b3e78-168">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="b3e78-169">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-169">Off</span></span>    | <span data-ttu-id="b3e78-170">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-170">Off</span></span>    | <span data-ttu-id="b3e78-171">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-171">Off</span></span>     |<span data-ttu-id="b3e78-172">为您的组织，与所有自定义应用程序交互而被阻止。</span><span class="sxs-lookup"><span data-stu-id="b3e78-172">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="b3e78-173">自定义应用程序无法上载的任何人。</span><span class="sxs-lookup"><span data-stu-id="b3e78-173">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="b3e78-174">您可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-174">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="b3e78-175">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-175">Off</span></span>     | <span data-ttu-id="b3e78-176">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-176">Off</span></span>     | <span data-ttu-id="b3e78-177">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-177">On</span></span>        |<span data-ttu-id="b3e78-178">为您的组织，与所有自定义应用程序交互而被阻止。</span><span class="sxs-lookup"><span data-stu-id="b3e78-178">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="b3e78-179">自定义应用程序无法上载的任何人。</span><span class="sxs-lookup"><span data-stu-id="b3e78-179">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="b3e78-180">您可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-180">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="b3e78-181">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-181">Off</span></span>    | <span data-ttu-id="b3e78-182">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-182">On</span></span>        | <span data-ttu-id="b3e78-183">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-183">Off</span></span>        |<span data-ttu-id="b3e78-184">为您的组织，与所有自定义应用程序交互而被阻止。</span><span class="sxs-lookup"><span data-stu-id="b3e78-184">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="b3e78-185">自定义应用程序无法上载的任何人。</span><span class="sxs-lookup"><span data-stu-id="b3e78-185">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="b3e78-186">您可以使用 Windows PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-186">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="b3e78-187">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-187">Off</span></span>    | <span data-ttu-id="b3e78-188">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-188">On</span></span>      | <span data-ttu-id="b3e78-189">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-189">On</span></span>       |<span data-ttu-id="b3e78-190">为您的组织，与所有自定义应用程序交互而被阻止。</span><span class="sxs-lookup"><span data-stu-id="b3e78-190">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="b3e78-191">自定义应用程序无法上载的任何人。</span><span class="sxs-lookup"><span data-stu-id="b3e78-191">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="b3e78-192">您可以使用 PowerShell 删除自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-192">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="b3e78-193">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-193">On</span></span>    | <span data-ttu-id="b3e78-194">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-194">Off</span></span>       | <span data-ttu-id="b3e78-195">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-195">Off</span></span>         |  <span data-ttu-id="b3e78-196">用户无法上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-196">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="b3e78-197">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-197">On</span></span>     | <span data-ttu-id="b3e78-198">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-198">Off</span></span>       | <span data-ttu-id="b3e78-199">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-199">On</span></span>         | <span data-ttu-id="b3e78-200">如果用户是团队所有者，它们可以将自定义应用程序上载到团队。</span><span class="sxs-lookup"><span data-stu-id="b3e78-200">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="b3e78-201">如果用户不是团队所有者，他们不能将自定义应用程序上载到团队。</span><span class="sxs-lookup"><span data-stu-id="b3e78-201">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="b3e78-202">用户可以上载个人上下文中的自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-202">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="b3e78-203">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-203">On</span></span>     | <span data-ttu-id="b3e78-204">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-204">On</span></span>     | <span data-ttu-id="b3e78-205">关</span><span class="sxs-lookup"><span data-stu-id="b3e78-205">Off</span></span>         | <span data-ttu-id="b3e78-206">用户无法上载自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-206">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="b3e78-207">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-207">On</span></span>    | <span data-ttu-id="b3e78-208">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-208">On</span></span>        | <span data-ttu-id="b3e78-209">开</span><span class="sxs-lookup"><span data-stu-id="b3e78-209">On</span></span>        | <span data-ttu-id="b3e78-210">用户可以将自定义应用程序上载到团队，而不管用户是否团队所有者。</span><span class="sxs-lookup"><span data-stu-id="b3e78-210">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="b3e78-211">用户可以上载个人上下文中的自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3e78-211">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="b3e78-212">相关主题</span><span class="sxs-lookup"><span data-stu-id="b3e78-212">Related topics</span></span>
- [<span data-ttu-id="b3e78-213">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="b3e78-213">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="b3e78-214">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="b3e78-214">Manage app setup policies in Microsoft Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="b3e78-215">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="b3e78-215">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
