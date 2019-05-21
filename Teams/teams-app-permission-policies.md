---
title: 在 Microsoft Teams 中管理应用权限策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
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
description: 了解 Microsoft 团队中的应用权限策略以及如何使用它们控制你的组织中的用户可以使用哪些应用程序。
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: d15346370015843eeb497cce7fa85928e77c96d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298888"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="cfbec-103">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cfbec-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="cfbec-104">作为管理员, 你可以使用应用权限策略控制你的组织中的 Microsoft 团队用户可用的应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="cfbec-105">你可以允许或阻止由 Microsoft、第三方和你的组织发布的所有应用或特定应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="cfbec-106">阻止应用时, 用户无法从团队应用商店安装它。</span><span class="sxs-lookup"><span data-stu-id="cfbec-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="cfbec-107">你可以在 Microsoft 团队管理中心中管理应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="cfbec-108">你可以应用组织范围内的设置, 使用全局 (组织范围默认) 策略, 并为组中的单个用户或用户创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![应用权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="cfbec-110">除非你创建并分配自定义策略, 否则你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="cfbec-111">组织范围内的应用设置替代全局策略和你创建并分配给用户的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="cfbec-112">例如, 你希望阻止所有第三方应用, 并允许 Microsoft 针对你的组织中的人力资源团队应用特定应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-112">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="cfbec-113">你将创建名为 HR App 权限策略的自定义策略, 将其设置为阻止并允许你所需的应用, 然后将其分配给 HR 团队上的用户。</span><span class="sxs-lookup"><span data-stu-id="cfbec-113">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="cfbec-114">管理组织范围内的应用设置</span><span class="sxs-lookup"><span data-stu-id="cfbec-114">Manage org-wide app settings</span></span>

<span data-ttu-id="cfbec-115">使用组织范围内的应用设置来控制哪些应用在你的组织中可用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-115">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="cfbec-116">组织范围内的应用设置控制所有用户的行为, 并替代分配给用户的任何其他应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-116">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="cfbec-117">组织范围内的应用设置会立即生效, 你可以使用它们控制恶意或有问题的应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-117">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="cfbec-118">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-118">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="cfbec-119">选择 "**组织范围的设置**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-119">Select **Org-wide settings**.</span></span> <span data-ttu-id="cfbec-120">然后, 你可以在面板中配置所需的设置。</span><span class="sxs-lookup"><span data-stu-id="cfbec-120">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="cfbec-121">![组织范围的应用设置的屏幕截图](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="cfbec-121">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="cfbec-122">在 "**第三方应用**" 下, 关闭或打开这些设置以控制对第三方应用的访问:</span><span class="sxs-lookup"><span data-stu-id="cfbec-122">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="cfbec-123">**允许团队中的第三方应用**: 这将控制用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-123">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="cfbec-124">**默认情况下允许发布到应用商店的任何新第三方应用**: 这将控制发布到团队应用商店的新的第三方应用是否会自动在团队中可用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-124">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="cfbec-125">仅当你允许第三方应用时, 你才能设置此选项。</span><span class="sxs-lookup"><span data-stu-id="cfbec-125">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="cfbec-126">在 "**自定义应用**" 下, 关闭或打开 "**允许与自定义应用交互**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-126">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="cfbec-127">此设置控制用户是否可以与自定义 (旁加载) 应用交互。</span><span class="sxs-lookup"><span data-stu-id="cfbec-127">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="cfbec-128">请记住, 这与允许用户*上载*自定义应用程序不同。</span><span class="sxs-lookup"><span data-stu-id="cfbec-128">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="cfbec-129">在 "已**阻止的应用**" 下, 搜索并添加要在组织内阻止的应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-129">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="cfbec-130">你可以从租户应用程序目录或团队应用商店中选择 "应用"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-130">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="cfbec-131">单击 "**保存**" 以使组织范围内的应用设置生效。</span><span class="sxs-lookup"><span data-stu-id="cfbec-131">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="cfbec-132">创建自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cfbec-132">Create a custom app permission policy</span></span>

<span data-ttu-id="cfbec-133">如果你希望控制组织中不同组用户可用的应用, 请创建并分配一个或多个自定义应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-133">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="cfbec-134">你可以基于 Microsoft、第三方或你的组织发布的应用创建和分配单独的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-134">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="cfbec-135">请务必注意, 在创建自定义策略后, 如果在组织范围的设置中禁用了第三方应用, 则无法对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="cfbec-135">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="cfbec-136">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-136">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="cfbec-137">选择 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-137">Select **New policy**.</span></span>
    <span data-ttu-id="cfbec-138">![新应用权限策略的屏幕截图](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="cfbec-138">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="cfbec-139">输入策略的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="cfbec-139">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="cfbec-140">在 " **Microsoft 应用**"、**第三方应用**和**租户应用**下, 选择下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="cfbec-140">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="cfbec-141">**允许所有应用**</span><span class="sxs-lookup"><span data-stu-id="cfbec-141">**Allow all apps**</span></span>
    - <span data-ttu-id="cfbec-142">**允许特定应用和阻止所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="cfbec-142">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="cfbec-143">**阻止特定应用并允许所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="cfbec-143">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="cfbec-144">**阻止所有应用**</span><span class="sxs-lookup"><span data-stu-id="cfbec-144">**Block all apps**</span></span>

5. <span data-ttu-id="cfbec-145">如果你选择 "**允许特定应用" 并阻止其他应用**, 请添加你希望允许的应用:</span><span class="sxs-lookup"><span data-stu-id="cfbec-145">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="cfbec-146">选择 "**允许应用**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-146">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="cfbec-147">搜索要允许的应用, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-147">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="cfbec-148">搜索结果将筛选到应用发布者 (**Microsoft 应用**、**第三方应用**或**租户应用**)。</span><span class="sxs-lookup"><span data-stu-id="cfbec-148">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="cfbec-149">选择应用列表后, 单击 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-149">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="cfbec-150">同样, 如果你选择 "**阻止特定应用" 并允许所有其他应用**, 请搜索并添加要阻止的应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-150">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="cfbec-151">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cfbec-151">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="cfbec-152">编辑应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cfbec-152">Edit an app permission policy</span></span>

<span data-ttu-id="cfbec-153">你可以使用 Microsoft 团队管理中心编辑策略, 包括全局 (组织范围默认) 策略和你创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="cfbec-154">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-154">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="cfbec-155">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-155">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="cfbec-156">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="cfbec-156">From here, make the changes that you want.</span></span> <span data-ttu-id="cfbec-157">你可以基于应用发布者管理设置, 并根据 "允许/阻止" 设置添加和删除应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-157">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="cfbec-158">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cfbec-158">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="cfbec-159">向用户分配自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cfbec-159">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="cfbec-160">你可以使用 Microsoft 团队管理中心向单个用户或 Skype for business PowerShell 模块分配自定义策略, 以便为多个用户分配自定义策略, 例如安全组或通讯组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="cfbec-160">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfbec-161">我们建议仅使用 PowerShell 为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-161">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="cfbec-162">使用 Microsoft 团队管理中心创建、编辑和管理策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-162">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a><span data-ttu-id="cfbec-163">向单个用户分配自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cfbec-163">Assign a custom app permission policy to individual users</span></span>

1. <span data-ttu-id="cfbec-164">在 Microsoft 团队管理中心的左侧导航中, 转到 "**用户**", 然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-164">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="cfbec-165">在 "**分配的策略**" 旁边, 选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-165">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="cfbec-166">在 "**应用权限策略**" 下, 选择要分配的应用权限策略, 然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-166">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![app-setup-permission-assign-policy](media/app-permission-policies-assign-policy.png)

<span data-ttu-id="cfbec-168">你还可以将应用权限策略分配给一个或多个用户, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="cfbec-168">You can also assign an app permission policy to one or more users as follows:</span></span>

1. <span data-ttu-id="cfbec-169">转到**Microsoft 团队管理中心** > **团队应用** > **权限策略**。</span><span class="sxs-lookup"><span data-stu-id="cfbec-169">Go to **Microsoft Teams admin center** > **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="cfbec-170">通过单击策略名称的左侧, 选择策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-170">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="cfbec-171">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-171">Select **Manage users**.</span></span>
4. <span data-ttu-id="cfbec-172">在 "**管理用户**" 窗格中, 按 "显示名称" 或 "按用户名搜索用户", 选择名称, 然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-172">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="cfbec-173">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="cfbec-173">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="cfbec-174">完成添加用户后, 请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="cfbec-174">When you are finished adding users, select **Save**.</span></span>
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="cfbec-175">将自定义应用权限策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="cfbec-175">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="cfbec-176">你可能需要将自定义应用权限策略分配给已标识的多个用户。</span><span class="sxs-lookup"><span data-stu-id="cfbec-176">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="cfbec-177">例如, 你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-177">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="cfbec-178">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cfbec-178">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="cfbec-179">有关使用 PowerShell 管理团队的详细信息, 请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cfbec-179">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="cfbec-180">在此示例中, 我们将名为 HR App 权限策略的自定义应用权限策略分配给 Contoso 制药人力资源项目组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="cfbec-180">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="cfbec-181">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤, 确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="cfbec-181">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="cfbec-182">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="cfbec-182">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="cfbec-183">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="cfbec-183">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="cfbec-184">将组中的所有用户分配到特定应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-184">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="cfbec-185">在此示例中, 它是 HR 应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="cfbec-185">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="cfbec-186">此命令可能需要几分钟才能执行, 具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="cfbec-186">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="cfbec-187">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="cfbec-187">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="cfbec-188">使用应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cfbec-188">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="cfbec-189">是否可以控制业务线 (LOB) 应用？</span><span class="sxs-lookup"><span data-stu-id="cfbec-189">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="cfbec-190">是的, 你可以使用应用权限策略控制自定义 (LOB) 应用的推出和分发。</span><span class="sxs-lookup"><span data-stu-id="cfbec-190">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="cfbec-191">应用权限策略与已固定的应用和应用设置策略有何关系？</span><span class="sxs-lookup"><span data-stu-id="cfbec-191">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="cfbec-192">你可以将应用设置策略与应用权限策略结合使用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-192">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="cfbec-193">已从用户的已启用应用集中选择预固定的应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-193">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="cfbec-194">此外, 如果用户具有在应用设置策略中阻止应用的应用权限策略, 则该应用不会显示在团队中。</span><span class="sxs-lookup"><span data-stu-id="cfbec-194">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="cfbec-195">是否可以使用应用权限策略来限制上载自定义应用 (也称为旁加载)？</span><span class="sxs-lookup"><span data-stu-id="cfbec-195">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="cfbec-196">若要了解有关如何限制上载自定义应用的详细信息, 请参阅[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="cfbec-196">To learn more about how to restrict uploading custom apps, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="cfbec-197">策略更改需要多长时间才能生效？</span><span class="sxs-lookup"><span data-stu-id="cfbec-197">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="cfbec-198">编辑全局策略或向用户分配策略后, 所做的更改可能需要长达24小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="cfbec-198">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="cfbec-199">组织范围内的应用设置会立即生效。</span><span class="sxs-lookup"><span data-stu-id="cfbec-199">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="cfbec-200">阻止应用是否会应用到团队移动客户端？</span><span class="sxs-lookup"><span data-stu-id="cfbec-200">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="cfbec-201">是的, 当你阻止应用时, 将阻止所有团队客户端上的应用。</span><span class="sxs-lookup"><span data-stu-id="cfbec-201">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="cfbec-202">用户体验</span><span class="sxs-lookup"><span data-stu-id="cfbec-202">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="cfbec-203">应用被阻止时的用户体验？</span><span class="sxs-lookup"><span data-stu-id="cfbec-203">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="cfbec-204">用户无法与已阻止的应用或其功能 (如 bot、选项卡和消息传递扩展) 交互。</span><span class="sxs-lookup"><span data-stu-id="cfbec-204">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="cfbec-205">在共享上下文 (如团队或群组聊天) 中, 机器人仍可向该上下文的所有参与者发送消息。</span><span class="sxs-lookup"><span data-stu-id="cfbec-205">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="cfbec-206">团队在应用被阻止时向用户显示。</span><span class="sxs-lookup"><span data-stu-id="cfbec-206">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="cfbec-207">例如, 当应用被阻止时, 用户不能执行以下任一操作:</span><span class="sxs-lookup"><span data-stu-id="cfbec-207">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="cfbec-208">将应用程序个人或聊天添加到聊天或团队</span><span class="sxs-lookup"><span data-stu-id="cfbec-208">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="cfbec-209">将消息发送到应用的 bot</span><span class="sxs-lookup"><span data-stu-id="cfbec-209">Send messages to the app’s bot</span></span>
- <span data-ttu-id="cfbec-210">执行将信息发送回应用的按钮操作, 例如可操作的消息</span><span class="sxs-lookup"><span data-stu-id="cfbec-210">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="cfbec-211">查看应用的选项卡</span><span class="sxs-lookup"><span data-stu-id="cfbec-211">View the app’s tab</span></span>
- <span data-ttu-id="cfbec-212">设置连接器以接收通知</span><span class="sxs-lookup"><span data-stu-id="cfbec-212">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="cfbec-213">使用应用的消息扩展</span><span class="sxs-lookup"><span data-stu-id="cfbec-213">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="cfbec-214">相关主题</span><span class="sxs-lookup"><span data-stu-id="cfbec-214">Related topics</span></span>
- [<span data-ttu-id="cfbec-215">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="cfbec-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="cfbec-216">在 Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="cfbec-216">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="cfbec-217">在 Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="cfbec-217">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
