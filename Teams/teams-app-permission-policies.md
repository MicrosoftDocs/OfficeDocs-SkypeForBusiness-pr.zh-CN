---
title: 在 Microsoft Teams 中管理应用权限策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
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
description: 了解 Microsoft 团队中的应用权限策略以及如何使用它们控制你的组织中的用户可以使用哪些应用程序。
f1keywords:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 8c42b4e2a8bf569d5aee6b2b822e81fc39ebfd81
ms.sourcegitcommit: 5932ec62a42d7b392fa31c6a2a3462389ac24b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573752"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="eaf6f-103">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="eaf6f-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="eaf6f-104">作为管理员，你可以使用应用权限策略控制你的组织中的 Microsoft 团队用户可用的应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="eaf6f-105">你可以允许或阻止由 Microsoft、第三方和你的组织发布的所有应用或特定应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="eaf6f-106">阻止应用时，用户无法从团队应用商店安装它。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="eaf6f-107">你可以在 Microsoft 团队管理中心中管理应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="eaf6f-108">你可以应用组织范围内的设置，使用全局（组织范围默认）策略，并为组中的单个用户或用户创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![应用权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="eaf6f-110">除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="eaf6f-111">组织范围内的应用设置替代全局策略和你创建并分配给用户的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="eaf6f-112">如果你的组织已在团队中，则在 Microsoft 365 管理中心的**租户范围设置**中配置的应用设置将反映在组织范围的应用设置中。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-112">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings.</span></span> <span data-ttu-id="eaf6f-113">如果您不熟悉团队，并且只是开始使用，则默认情况下，所有应用都允许在全局策略中使用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-113">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="eaf6f-114">这包括由 Microsoft、第三方和你的组织发布的应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-114">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="eaf6f-115">例如，你希望阻止所有第三方应用，并允许 Microsoft 针对你的组织中的人力资源团队应用特定应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-115">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="eaf6f-116">你将创建名为 HR App 权限策略的自定义策略，将其设置为阻止并允许你所需的应用，然后将其分配给 HR 团队上的用户。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-116">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="eaf6f-117">如果你在 Microsoft 365 政府-GCC 环境中部署团队，请参阅适用于 gcc 的[应用权限策略](#app-permission-policies-for-gcc)，了解有关特定于 GCC 的第三方应用设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-117">If you deployed Teams in a Microsoft 365 Government - GCC environment, see [App permission policies for GCC](#app-permission-policies-for-gcc) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="eaf6f-118">管理组织范围内的应用设置</span><span class="sxs-lookup"><span data-stu-id="eaf6f-118">Manage org-wide app settings</span></span>

<span data-ttu-id="eaf6f-119">使用组织范围内的应用设置来控制哪些应用在你的组织中可用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-119">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="eaf6f-120">组织范围内的应用设置控制所有用户的行为，并替代分配给用户的任何其他应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-120">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="eaf6f-121">你可以使用它们控制恶意或有问题的应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-121">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="eaf6f-122">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-122">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="eaf6f-123">选择 "**组织范围的设置**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-123">Select **Org-wide settings**.</span></span> <span data-ttu-id="eaf6f-124">然后，你可以在面板中配置所需的设置。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-124">You can then configure the settings you want in the panel.</span></span> 
    <span data-ttu-id="eaf6f-125">![组织范围内的应用设置的屏幕截图](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="eaf6f-125">![Screenshot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="eaf6f-126">在 "**第三方应用**" 下，关闭或打开这些设置以控制对第三方应用的访问：</span><span class="sxs-lookup"><span data-stu-id="eaf6f-126">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="eaf6f-127">**允许团队中的第三方**：这将控制用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-127">**Allow third-party in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="eaf6f-128">**默认情况下允许发布到应用商店的任何新第三方应用**：这将控制发布到团队应用商店的新的第三方应用是否会自动在团队中可用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-128">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="eaf6f-129">仅当你允许第三方应用时，你才能设置此选项。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-129">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="eaf6f-130">在 "**自定义应用**" 下，关闭或打开 "**允许与自定义应用交互**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-130">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="eaf6f-131">此设置控制用户是否可以与自定义（旁加载）应用交互。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-131">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="eaf6f-132">请记住，这与允许用户*上载*自定义应用程序不同。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-132">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="eaf6f-133">在 "已**阻止的应用**" 下，搜索并添加要在组织内阻止的应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-133">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="eaf6f-134">你可以从租户应用程序目录或团队应用商店中选择 "应用"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-134">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="eaf6f-135">单击 "**保存**" 以使组织范围内的应用设置生效。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-135">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="eaf6f-136">创建自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="eaf6f-136">Create a custom app permission policy</span></span>

<span data-ttu-id="eaf6f-137">如果你希望控制组织中不同组用户可用的应用，请创建并分配一个或多个自定义应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-137">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="eaf6f-138">你可以基于 Microsoft、第三方或你的组织发布的应用创建和分配单独的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-138">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="eaf6f-139">请务必注意，在创建自定义策略后，如果在组织范围的设置中禁用了第三方应用，则无法对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-139">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="eaf6f-140">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-140">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="eaf6f-141">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-141">Click **Add**.</span></span>
    <span data-ttu-id="eaf6f-142">![新应用权限策略的屏幕截图](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="eaf6f-142">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="eaf6f-143">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-143">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="eaf6f-144">在 " **Microsoft 应用**"、**第三方应用**和**租户应用**下，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="eaf6f-144">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="eaf6f-145">**允许所有应用**</span><span class="sxs-lookup"><span data-stu-id="eaf6f-145">**Allow all apps**</span></span>
    - <span data-ttu-id="eaf6f-146">**允许特定应用和阻止所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="eaf6f-146">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="eaf6f-147">**阻止特定应用并允许所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="eaf6f-147">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="eaf6f-148">**阻止所有应用**</span><span class="sxs-lookup"><span data-stu-id="eaf6f-148">**Block all apps**</span></span>

5. <span data-ttu-id="eaf6f-149">如果你选择 "**允许特定应用" 并阻止其他应用**，请添加你希望允许的应用：</span><span class="sxs-lookup"><span data-stu-id="eaf6f-149">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="eaf6f-150">选择 "**允许应用**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-150">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="eaf6f-151">搜索要允许的应用，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-151">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="eaf6f-152">搜索结果将筛选到应用发布者（**Microsoft 应用**、**第三方应用**或**租户应用**）。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-152">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="eaf6f-153">选择应用列表后，单击 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-153">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="eaf6f-154">同样，如果你选择 "**阻止特定应用" 并允许所有其他应用**，请搜索并添加要阻止的应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-154">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="eaf6f-155">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-155">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="eaf6f-156">编辑应用权限策略</span><span class="sxs-lookup"><span data-stu-id="eaf6f-156">Edit an app permission policy</span></span>

<span data-ttu-id="eaf6f-157">你可以使用 Microsoft 团队管理中心编辑策略，包括全局策略和你创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-157">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="eaf6f-158">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-158">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="eaf6f-159">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-159">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="eaf6f-160">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-160">From here, make the changes that you want.</span></span> <span data-ttu-id="eaf6f-161">你可以基于应用发布者管理设置，并根据 "允许/阻止" 设置添加和删除应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-161">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="eaf6f-162">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-162">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="eaf6f-163">向用户分配自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="eaf6f-163">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="eaf6f-164">你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块，以便向用户组（如安全组或通讯组中的所有用户）分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-164">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as all users in a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-a-user"></a><span data-ttu-id="eaf6f-165">向用户分配自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="eaf6f-165">Assign a custom app permission policy to a user</span></span>

1. <span data-ttu-id="eaf6f-166">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-166">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="eaf6f-167">通过单击用户名左侧的用户选择用户，然后单击 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-167">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="eaf6f-168">在 "**应用权限策略**" 下，选择要分配的应用权限策略，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-168">Under **App permission policy**, select the app permission policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="eaf6f-169">若要一次为多个用户分配策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-169">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="eaf6f-170">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eaf6f-170">Or, you can also do the following:</span></span>

1. <span data-ttu-id="eaf6f-171">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-171">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="eaf6f-172">通过单击策略名称的左侧，选择策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-172">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="eaf6f-173">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-173">Select **Manage users**.</span></span>
4. <span data-ttu-id="eaf6f-174">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-174">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="eaf6f-175">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-175">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="eaf6f-176">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-176">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="eaf6f-177">将自定义应用权限策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="eaf6f-177">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="eaf6f-178">你可能需要将自定义应用权限策略分配给已标识的多个用户。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-178">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="eaf6f-179">例如，你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-179">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="eaf6f-180">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-180">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="eaf6f-181">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-181">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="eaf6f-182">在此示例中，我们将名为 HR App 权限策略的自定义应用权限策略分配给 Contoso 制药人力资源项目组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-182">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="eaf6f-183">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-183">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="eaf6f-184">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-184">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="eaf6f-185">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-185">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="eaf6f-186">将组中的所有用户分配到特定应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-186">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="eaf6f-187">在此示例中，它是 HR 应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-187">In this example, it's HR App Permission Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="eaf6f-188">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-188">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="app-permission-policies-for-gcc"></a><span data-ttu-id="eaf6f-189">适用于 GCC 的应用权限策略</span><span class="sxs-lookup"><span data-stu-id="eaf6f-189">App permission policies for GCC</span></span>

<span data-ttu-id="eaf6f-190">在 Microsoft 365 政府版团队部署中，请务必了解以下有关适用于 GCC 的第三方应用设置的信息。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-190">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="eaf6f-191">在 GCC 中，默认情况下将阻止所有第三方应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-191">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="eaf6f-192">此外，在 Microsoft 团队管理中心的 "应用权限策略" 页面上，你将看到以下有关管理第三方应用的说明。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-192">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC 中的应用权限策略的屏幕截图](media/app-permission-policies-gcc.png)

<span data-ttu-id="eaf6f-194">若要为你的组织中的一个用户或一组用户启用第三方应用，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="eaf6f-194">To enable a third-party app for a user or a set of users in your organization, do the following:</span></span>

1. <span data-ttu-id="eaf6f-195">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-195">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="eaf6f-196">确认要为一组用户允许的第三方应用在组织级别被阻止。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-196">Confirm that the third-party app that you want to allow for a set of users is blocked at the org level.</span></span> <span data-ttu-id="eaf6f-197">若要执行此操作，请单击 "**组织范围的设置**"，然后在 "已**阻止的应用**" 下，检查以确保应用已列出。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-197">To do this, click **Org-wide settings**, and then under **Blocked apps**, check to make sure the app is listed.</span></span>
3. <span data-ttu-id="eaf6f-198">编辑全局策略以阻止第三方应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-198">Edit the global policy to block the third-party app.</span></span> <span data-ttu-id="eaf6f-199">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="eaf6f-199">To do this:</span></span>
    1. <span data-ttu-id="eaf6f-200">在 "应用权限策略" 页面上，单击 "**全局（组织范围默认）**"，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-200">On the App permission policies page, click **Global (Org-wide default)**, and then click **Edit**.</span></span>
    2. <span data-ttu-id="eaf6f-201">在 "**第三方应用**" 下，选择 "**阻止特定应用并允许所有其他**应用"，添加应用，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-201">Under **Third-party apps**, select **Block specific apps and allow all others**, add the app, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eaf6f-202">请务必先执行此操作，然后再转到下一步，以便在组织级别允许应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-202">It's important to do this before you go to the next step to allow the app at the org level.</span></span> <span data-ttu-id="eaf6f-203">这是因为如果全局策略中未阻止第三方应用，则全局策略适用的所有用户都可以在组织级别允许访问第三方应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-203">This is because if the third-party app isn't blocked in the global policy, all users that the global policy applies to will be able to access the third-party app when you allow it at the org level.</span></span>

4. <span data-ttu-id="eaf6f-204">允许在组织级别的第三方应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-204">Allow the third-party app at the org level.</span></span> <span data-ttu-id="eaf6f-205">若要执行此操作，请单击 "**组织范围设置**" 下的 "已**阻止的应用**"，从列表中删除应用，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-205">To do this, click **Org-wide settings**, under **Blocked apps**, remove the app from the list, and then click **Save**.</span></span>
5. <span data-ttu-id="eaf6f-206">[创建自定义应用权限策略](#create-a-custom-app-permission-policy)以允许应用，然后[将策略分配](#assign-a-custom-app-permission-policy-to-users)给所需的用户。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-206">[Create a custom app permission policy](#create-a-custom-app-permission-policy) to allow the app, and then [assign the policy](#assign-a-custom-app-permission-policy-to-users) to the users you want.</span></span>

## <a name="faq"></a><span data-ttu-id="eaf6f-207">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="eaf6f-207">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="eaf6f-208">使用应用权限策略</span><span class="sxs-lookup"><span data-stu-id="eaf6f-208">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="eaf6f-209">是否可以控制业务线（LOB）应用？</span><span class="sxs-lookup"><span data-stu-id="eaf6f-209">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="eaf6f-210">是的，你可以使用应用权限策略控制自定义（LOB）应用的推出和分发。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-210">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="eaf6f-211">你可以创建自定义策略或编辑全局策略，以根据你的组织的需要允许或阻止自定义应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-211">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="eaf6f-212">应用权限策略与已固定的应用和应用设置策略有何关系？</span><span class="sxs-lookup"><span data-stu-id="eaf6f-212">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="eaf6f-213">你可以将应用设置策略与应用权限策略结合使用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-213">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="eaf6f-214">已从用户的已启用应用集中选择预固定的应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-214">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="eaf6f-215">此外，如果用户具有在应用设置策略中阻止应用的应用权限策略，则该应用不会显示在团队中。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-215">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="eaf6f-216">是否可以使用应用权限策略来限制上载自定义应用（也称为旁加载）？</span><span class="sxs-lookup"><span data-stu-id="eaf6f-216">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="eaf6f-217">在应用权限策略中使用组织范围内的设置来限制为你的组织上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-217">Use org-wide settings in app permission policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="eaf6f-218">若要限制特定用户上载自定义应用程序，请使用自定义应用策略。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-218">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="eaf6f-219">若要了解详细信息，请参阅[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-219">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="eaf6f-220">阻止应用是否会应用到团队移动客户端？</span><span class="sxs-lookup"><span data-stu-id="eaf6f-220">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="eaf6f-221">是的，当你阻止应用时，将阻止所有团队客户端上的应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-221">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="eaf6f-222">用户体验</span><span class="sxs-lookup"><span data-stu-id="eaf6f-222">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="eaf6f-223">应用被阻止时的用户体验？</span><span class="sxs-lookup"><span data-stu-id="eaf6f-223">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="eaf6f-224">用户无法与已阻止的应用或其功能（如 bot、选项卡和消息传递扩展）交互。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-224">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="eaf6f-225">在共享上下文（如团队或群组聊天）中，机器人仍可向该上下文的所有参与者发送消息。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-225">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="eaf6f-226">团队在应用被阻止时向用户显示。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-226">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="eaf6f-227">例如，当应用被阻止时，用户不能执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="eaf6f-227">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="eaf6f-228">将应用程序个人或聊天添加到聊天或团队</span><span class="sxs-lookup"><span data-stu-id="eaf6f-228">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="eaf6f-229">将消息发送到应用的 bot</span><span class="sxs-lookup"><span data-stu-id="eaf6f-229">Send messages to the app’s bot</span></span>
- <span data-ttu-id="eaf6f-230">执行将信息发送回应用的按钮操作，例如可操作的消息</span><span class="sxs-lookup"><span data-stu-id="eaf6f-230">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="eaf6f-231">查看应用的选项卡</span><span class="sxs-lookup"><span data-stu-id="eaf6f-231">View the app’s tab</span></span>
- <span data-ttu-id="eaf6f-232">设置连接器以接收通知</span><span class="sxs-lookup"><span data-stu-id="eaf6f-232">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="eaf6f-233">使用应用的消息扩展</span><span class="sxs-lookup"><span data-stu-id="eaf6f-233">Use the app’s messaging extension</span></span>

<span data-ttu-id="eaf6f-234">旧版门户允许在组织级别控制应用，这意味着当应用被阻止时，组织中的所有用户都将阻止该应用。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-234">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="eaf6f-235">应用权限策略中的组织范围的应用设置的工作方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-235">The org-wide app setting in app permission policies works exactly the same way.</span></span>

<span data-ttu-id="eaf6f-236">对于分配给特定用户的应用权限策略，如果允许使用机器人或连接器功能的应用，并且已被阻止，并且如果仅为共享上下文中的某些用户允许该应用，则不具有该应用权限的组聊天或频道的成员 可以查看由机器人或连接器发布的邮件历史记录和消息，但不能与其进行交互。</span><span class="sxs-lookup"><span data-stu-id="eaf6f-236">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="eaf6f-237">相关主题</span><span class="sxs-lookup"><span data-stu-id="eaf6f-237">Related topics</span></span>
- [<span data-ttu-id="eaf6f-238">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="eaf6f-238">Admin settings for apps in Teams</span></span>](admin-settings.md)
