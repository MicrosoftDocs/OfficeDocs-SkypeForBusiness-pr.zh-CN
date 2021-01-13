---
title: 管理自定义应用策略和设置
author: cichur
ms.author: v-cichur
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
description: 了解如何管理自定义应用策略和设置，以控制组织中哪些人可以在 Microsoft Teams 中上传自定义应用。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 4e9863508d7b10c76ed29bfcb0fec79ca7a33dc5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821002"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="d30a4-103">在 Microsoft Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="d30a4-104">若要使用 App Studio，请参阅"通过 [C#/.NET](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) 和 App Studio 开始使用 Microsoft Teams 平台"。最后一个步骤尚未运行，因此你需要下载 zip 文件，然后以旧方式将其安装在"将应用包上传到 [Microsoft Teams"](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)中。</span><span class="sxs-lookup"><span data-stu-id="d30a4-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="d30a4-105">作为管理员，可以使用自定义应用策略和设置来控制组织中哪些人可以将自定义应用上传到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="d30a4-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="d30a4-106">管理员决定哪些用户可以上传自定义应用，管理员和团队所有者可以确定您的组织中的特定团队是否允许向这些用户添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  <span data-ttu-id="d30a4-107">编辑自定义应用策略后，可能需要几个小时更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="d30a4-107">After you edit the custom app policy, it can take a few hours for changes to take effect.</span></span> <span data-ttu-id="d30a4-108">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="d30a4-108">You must be a global admin or Teams service admin to manage these policies.</span></span>

## <a name="overview-of-custom-apps"></a><span data-ttu-id="d30a4-109">自定义应用概述</span><span class="sxs-lookup"><span data-stu-id="d30a4-109">Overview of custom apps</span></span>

<span data-ttu-id="d30a4-110">用户可以通过将应用包上传到 Teams (.zip 文件) 直接上传到团队或个人上下文中。</span><span class="sxs-lookup"><span data-stu-id="d30a4-110">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="d30a4-111">这不同于通过 Teams 应用商店添加应用的方式。</span><span class="sxs-lookup"><span data-stu-id="d30a4-111">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="d30a4-112">通过上传应用包（也称为旁加载）来添加自定义应用，允许你在开发应用时测试应用，然后它才能进行广泛分发。</span><span class="sxs-lookup"><span data-stu-id="d30a4-112">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="d30a4-113">它还允许你生成一个仅供内部使用的应用，并与你的团队共享它，而无需将该应用提交到 Teams 应用商店中的 Teams 应用目录。</span><span class="sxs-lookup"><span data-stu-id="d30a4-113">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![显示应用商店中"上传自定义应用"选项的屏幕截图](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="d30a4-115">自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-115">Custom app policy and settings</span></span>

<span data-ttu-id="d30a4-116">三个组件决定了用户是否可以将自定义应用上传到团队，从而让你精细控制谁可以将自定义应用添加到团队，以及可以将自定义应用添加到哪些团队：</span><span class="sxs-lookup"><span data-stu-id="d30a4-116">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="d30a4-117">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="d30a4-117">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="d30a4-118">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-118">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="d30a4-119">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-119">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="d30a4-120">这些设置不会影响阻止第三方应用的能力。</span><span class="sxs-lookup"><span data-stu-id="d30a4-120">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="d30a4-121">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="d30a4-121">User custom app policy</span></span>

<span data-ttu-id="d30a4-122">作为应用 [设置策略的一部分](teams-app-setup-policies.md)，管理员可以使用策略设置 **"上传自定义** 应用"来控制用户是否可以将自定义应用上传到 Teams。</span><span class="sxs-lookup"><span data-stu-id="d30a4-122">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Upload custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="d30a4-123">如果此设置已关闭：</span><span class="sxs-lookup"><span data-stu-id="d30a4-123">If this setting is turned off:</span></span>

- <span data-ttu-id="d30a4-124">用户无法将自定义应用上传到组织或个人上下文中的任何团队。</span><span class="sxs-lookup"><span data-stu-id="d30a4-124">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="d30a4-125">用户可以与自定义应用交互，具体取决于组织范围的自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="d30a4-125">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="d30a4-126">如果此设置已打开：</span><span class="sxs-lookup"><span data-stu-id="d30a4-126">If this setting is turned on:</span></span>

- <span data-ttu-id="d30a4-127">用户可以将自定义应用上载到允许它的团队以及他们作为所有者的团队，具体取决于组织范围的自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="d30a4-127">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="d30a4-128">用户可以将自定义应用上传到个人上下文。</span><span class="sxs-lookup"><span data-stu-id="d30a4-128">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="d30a4-129">用户可以与自定义应用交互，具体取决于组织范围的自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="d30a4-129">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="d30a4-130">你可以编辑全局应用设置策略中的设置，以包含你需要的应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-130">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="d30a4-131">如果要为组织的不同用户组自定义 Teams，请创建并分配一个或多个自定义应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="d30a4-131">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="d30a4-132">设置用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="d30a4-132">Set a user custom app policy</span></span>

1. <span data-ttu-id="d30a4-133">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **设置策略"。**</span><span class="sxs-lookup"><span data-stu-id="d30a4-133">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="d30a4-134">单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="d30a4-134">Click **Add**.</span></span>
3. <span data-ttu-id="d30a4-135">打开或关闭"上传 **自定义应用"。**</span><span class="sxs-lookup"><span data-stu-id="d30a4-135">Turn on or turn off **Upload custom apps**.</span></span>
4. <span data-ttu-id="d30a4-136">选择想要用于策略的其他任何设置。</span><span class="sxs-lookup"><span data-stu-id="d30a4-136">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="d30a4-137">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d30a4-137">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="d30a4-138">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-138">Team custom app setting</span></span>

<span data-ttu-id="d30a4-139">管理员和团队所有者可以控制团队是否允许向团队添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-139">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="d30a4-140">此设置" **允许成员上传自定义** 应用"以及用户的自定义应用策略确定谁可以将自定义应用添加到特定团队。</span><span class="sxs-lookup"><span data-stu-id="d30a4-140">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="d30a4-141">如果此设置已关闭：</span><span class="sxs-lookup"><span data-stu-id="d30a4-141">If this setting is turned off:</span></span>

- <span data-ttu-id="d30a4-142">团队所有者可以添加自定义应用（如果其自定义应用策略允许）。</span><span class="sxs-lookup"><span data-stu-id="d30a4-142">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="d30a4-143">不是团队所有者的团队成员无法向团队添加自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-143">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="d30a4-144">如果此设置已打开：</span><span class="sxs-lookup"><span data-stu-id="d30a4-144">If this setting is turned on:</span></span>

- <span data-ttu-id="d30a4-145">团队所有者可以添加自定义应用（如果其自定义应用策略允许）。</span><span class="sxs-lookup"><span data-stu-id="d30a4-145">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="d30a4-146">不是团队所有者的团队成员可以添加自定义应用（如果其自定义应用策略允许）。</span><span class="sxs-lookup"><span data-stu-id="d30a4-146">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="d30a4-147">配置团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-147">Configure the team custom app setting</span></span>

1. <span data-ttu-id="d30a4-148">在 Teams 中，转到该团队，单击"更多 **选项"。**  >  </span><span class="sxs-lookup"><span data-stu-id="d30a4-148">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="d30a4-149">单击 **"** 设置"，然后展开 **"成员"权限**。</span><span class="sxs-lookup"><span data-stu-id="d30a4-149">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="d30a4-150">选中或清除" **允许成员上传自定义应用"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d30a4-150">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![显示团队自定义应用设置的屏幕截图](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="d30a4-152">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-152">Org-wide custom app setting</span></span>

<span data-ttu-id="d30a4-153">"**管理应用"** 页面上的"允许与自定义应用交互"组织 [](manage-apps.md)范围的自定义应用设置适用于组织中的每个人，并控制他们是否可以上传自定义应用或与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="d30a4-153">The **Allow interaction with custom apps** org-wide custom app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="d30a4-154">此设置充当用户和团队自定义应用策略设置的主开/关开关。</span><span class="sxs-lookup"><span data-stu-id="d30a4-154">This setting acts as a master on/off switch for the user and team custom app policy settings.</span></span> <span data-ttu-id="d30a4-155">它旨在充当安全事件期间的主开/关开关。</span><span class="sxs-lookup"><span data-stu-id="d30a4-155">It's intended to serve as a master on/off switch during security events.</span></span> <span data-ttu-id="d30a4-156">因此，用户和团队自定义应用策略设置不会生效，除非启用了组织范围的自定义应用设置，即使启用了用户和团队自定义应用策略设置。</span><span class="sxs-lookup"><span data-stu-id="d30a4-156">As such, user and team custom app policy settings will not take effect unless the org-wide custom app setting is enabled even if user and team custom app policy settings are enabled.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="d30a4-157">配置组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-157">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="d30a4-158">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="d30a4-158">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="d30a4-159">单击 **组织范围内的应用设置**。</span><span class="sxs-lookup"><span data-stu-id="d30a4-159">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="d30a4-160">在 **"自定义应用**"下，打开或关闭"**允许与自定义应用交互"。**</span><span class="sxs-lookup"><span data-stu-id="d30a4-160">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![显示组织范围的自定义应用设置的屏幕截图](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="d30a4-162">自定义应用策略和设置如何协同工作</span><span class="sxs-lookup"><span data-stu-id="d30a4-162">How custom app policies and settings work together</span></span>

<span data-ttu-id="d30a4-163">下表总结了自定义应用策略和设置、它们如何协同工作，以及它们对控制组织中哪些人可以将自定义应用上传到 Teams 的组合效果。</span><span class="sxs-lookup"><span data-stu-id="d30a4-163">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="d30a4-164">例如，您希望仅允许团队所有者将自定义应用上载到特定团队。</span><span class="sxs-lookup"><span data-stu-id="d30a4-164">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="d30a4-165">可以设置以下项：</span><span class="sxs-lookup"><span data-stu-id="d30a4-165">You would set the following:</span></span>
- <span data-ttu-id="d30a4-166">在 Microsoft Teams **管理中心中** 打开"允许与自定义应用交互"设置。</span><span class="sxs-lookup"><span data-stu-id="d30a4-166">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="d30a4-167">关闭" **允许成员为要限制** 其访问的每位团队上传自定义应用"。</span><span class="sxs-lookup"><span data-stu-id="d30a4-167">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="d30a4-168">在启用"上传自定义应用"设置后，在 Microsoft Teams管理中心创建并分配自定义应用设置策略，并将其分配给团队所有者。</span><span class="sxs-lookup"><span data-stu-id="d30a4-168">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **Upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="d30a4-169">组织范围的自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-169">Org-wide custom app setting</span></span> |<span data-ttu-id="d30a4-170">团队自定义应用设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-170">Team custom app setting</span></span> |<span data-ttu-id="d30a4-171">用户自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="d30a4-171">User custom app policy</span></span> |<span data-ttu-id="d30a4-172">效果</span><span class="sxs-lookup"><span data-stu-id="d30a4-172">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="d30a4-173">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-173">Off</span></span>    | <span data-ttu-id="d30a4-174">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-174">Off</span></span>    | <span data-ttu-id="d30a4-175">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-175">Off</span></span>     |<span data-ttu-id="d30a4-176">组织将阻止与所有自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="d30a4-176">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="d30a4-177">自定义应用不能由除 Teams 服务管理员或全局管理员以外的任何人上传。可以使用 PowerShell 删除自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-177">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="d30a4-178">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-178">Off</span></span>     | <span data-ttu-id="d30a4-179">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-179">Off</span></span>     | <span data-ttu-id="d30a4-180">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-180">On</span></span>        |<span data-ttu-id="d30a4-181">组织将阻止与所有自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="d30a4-181">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="d30a4-182">自定义应用不能由除 Teams 服务管理员或全局管理员以外的任何人上传。可以使用 PowerShell 删除自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-182">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="d30a4-183">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-183">Off</span></span>    | <span data-ttu-id="d30a4-184">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-184">On</span></span>        | <span data-ttu-id="d30a4-185">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-185">Off</span></span>        |<span data-ttu-id="d30a4-186">组织将阻止与所有自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="d30a4-186">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="d30a4-187">自定义应用不能由除 Teams 服务管理员或全局管理员以外的任何人上传。可以使用自定义Windows PowerShell删除自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-187">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="d30a4-188">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-188">Off</span></span>    | <span data-ttu-id="d30a4-189">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-189">On</span></span>      | <span data-ttu-id="d30a4-190">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-190">On</span></span>       |<span data-ttu-id="d30a4-191">组织将阻止与所有自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="d30a4-191">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="d30a4-192">自定义应用不能由除 Teams 服务管理员或全局管理员以外的任何人上传。可以使用 PowerShell 删除自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-192">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="d30a4-193">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-193">On</span></span>    | <span data-ttu-id="d30a4-194">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-194">Off</span></span>       | <span data-ttu-id="d30a4-195">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-195">Off</span></span>         |  <span data-ttu-id="d30a4-196">用户无法上传自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-196">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="d30a4-197">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-197">On</span></span>     | <span data-ttu-id="d30a4-198">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-198">Off</span></span>       | <span data-ttu-id="d30a4-199">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-199">On</span></span>         | <span data-ttu-id="d30a4-200">如果用户是团队所有者，他们可以将自定义应用上传到团队。</span><span class="sxs-lookup"><span data-stu-id="d30a4-200">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="d30a4-201">如果用户不是团队所有者，他们无法将自定义应用上传到团队。</span><span class="sxs-lookup"><span data-stu-id="d30a4-201">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="d30a4-202">用户可以在个人上下文中上传自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-202">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="d30a4-203">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-203">On</span></span>     | <span data-ttu-id="d30a4-204">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-204">On</span></span>     | <span data-ttu-id="d30a4-205">关</span><span class="sxs-lookup"><span data-stu-id="d30a4-205">Off</span></span>         | <span data-ttu-id="d30a4-206">用户无法上传自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-206">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="d30a4-207">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-207">On</span></span>    | <span data-ttu-id="d30a4-208">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-208">On</span></span>        | <span data-ttu-id="d30a4-209">开</span><span class="sxs-lookup"><span data-stu-id="d30a4-209">On</span></span>        | <span data-ttu-id="d30a4-210">用户可以将自定义应用上传到团队，无论该用户是否是团队所有者。</span><span class="sxs-lookup"><span data-stu-id="d30a4-210">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="d30a4-211">用户可以在个人上下文中上传自定义应用。</span><span class="sxs-lookup"><span data-stu-id="d30a4-211">The user can upload custom apps in the personal context.</span></span>       |

## <a name="related-topics"></a><span data-ttu-id="d30a4-212">相关主题</span><span class="sxs-lookup"><span data-stu-id="d30a4-212">Related topics</span></span>
 
[<span data-ttu-id="d30a4-213">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="d30a4-213">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="d30a4-214">在 Teams 中向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="d30a4-214">Assign policies to your users in Teams</span></span>](assign-policies.md)