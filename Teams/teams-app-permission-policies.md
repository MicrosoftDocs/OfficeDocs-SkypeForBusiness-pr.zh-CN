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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: a7e8cf5e6ed4329a617a7922d4c4380fb5593b7c
ms.sourcegitcommit: 8395f91205bde549a0a92999ef00c5f5fb03fb80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2020
ms.locfileid: "44583509"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="cf3ee-103">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cf3ee-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="cf3ee-104">作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="cf3ee-105">你可以允许或阻止由 Microsoft、第三方和你的组织发布的所有应用或特定应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="cf3ee-106">阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="cf3ee-107">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="cf3ee-108">你可以在 Microsoft 团队管理中心中管理应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="cf3ee-109">可以使用全局（组织范围默认）策略，也可以创建自定义策略并将其分配给组中的单个用户或用户。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-109">You can use the global (Org-wide default) policy or create and assign custom policies to individual users or users in a group.</span></span>  

![应用权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="cf3ee-111">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-111">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="cf3ee-112">组织范围内的应用设置替代全局策略和你创建并分配给用户的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-112">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="cf3ee-113">如果您的组织已在团队中，则在 Microsoft 365 管理中心的**租户范围设置**中配置的应用设置将反映在 "[管理应用](manage-apps.md)程序" 页面上的组织范围内应用设置中。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-113">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="cf3ee-114">如果您不熟悉团队，并且只是开始使用，则默认情况下，所有应用都允许在全局策略中使用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-114">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="cf3ee-115">这包括由 Microsoft、第三方和你的组织发布的应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-115">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="cf3ee-116">例如，你希望阻止所有第三方应用，并允许 Microsoft 针对你的组织中的人力资源团队应用特定应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-116">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="cf3ee-117">首先，你将转到 "[管理应用](manage-apps.md)" 页面，并确保你希望为 HR 团队允许的应用在组织级别允许。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-117">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="cf3ee-118">然后，创建名为 HR App 权限策略的自定义策略，将其设置为阻止并允许你所需的应用，并将其分配给 HR 团队上的用户。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-118">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="cf3ee-119">如果你在 Microsoft 365 政府-GCC 环境中部署团队，请参阅适用于 gcc 的[应用权限策略](#app-permission-policies-for-gcc)，了解有关特定于 GCC 的第三方应用设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-119">If you deployed Teams in a Microsoft 365 Government - GCC environment, see [App permission policies for GCC](#app-permission-policies-for-gcc) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="cf3ee-120">创建自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cf3ee-120">Create a custom app permission policy</span></span>

<span data-ttu-id="cf3ee-121">如果你希望控制组织中不同组用户可用的应用，请创建并分配一个或多个自定义应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-121">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="cf3ee-122">你可以基于 Microsoft、第三方或你的组织发布的应用创建和分配单独的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-122">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="cf3ee-123">请务必注意，在创建自定义策略后，如果在组织范围的应用设置中禁用了第三方应用，则无法更改它。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-123">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="cf3ee-124">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-124">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="cf3ee-125">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-125">Click **Add**.</span></span> <br>
    <span data-ttu-id="cf3ee-126">![新应用权限策略的屏幕截图](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="cf3ee-126">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="cf3ee-127">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-127">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="cf3ee-128">在 " **Microsoft 应用**"、"**第三方应用**" 和 "**自定义应用**" 下，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="cf3ee-128">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="cf3ee-129">**允许所有应用**</span><span class="sxs-lookup"><span data-stu-id="cf3ee-129">**Allow all apps**</span></span>
    - <span data-ttu-id="cf3ee-130">**允许特定应用和阻止所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="cf3ee-130">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="cf3ee-131">**阻止特定应用并允许所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="cf3ee-131">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="cf3ee-132">**阻止所有应用**</span><span class="sxs-lookup"><span data-stu-id="cf3ee-132">**Block all apps**</span></span>

5. <span data-ttu-id="cf3ee-133">如果你选择 "**允许特定应用" 并阻止其他应用**，请添加你希望允许的应用：</span><span class="sxs-lookup"><span data-stu-id="cf3ee-133">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="cf3ee-134">选择 "**允许应用**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-134">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="cf3ee-135">搜索要允许的应用，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-135">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="cf3ee-136">搜索结果将筛选到应用发布者（**Microsoft 应用**、**第三方应用**或**自定义应用**）。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-136">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="cf3ee-137">选择应用列表后，单击 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-137">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="cf3ee-138">同样，如果你选择 "**阻止特定应用" 并允许所有其他应用**，请搜索并添加要阻止的应用，然后单击 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-138">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="cf3ee-139">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-139">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="cf3ee-140">编辑应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cf3ee-140">Edit an app permission policy</span></span>

<span data-ttu-id="cf3ee-141">你可以使用 Microsoft 团队管理中心编辑策略，包括全局策略和你创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-141">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="cf3ee-142">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="cf3ee-143">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-143">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="cf3ee-144">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-144">From here, make the changes that you want.</span></span> <span data-ttu-id="cf3ee-145">你可以基于应用发布者管理设置，并根据 "允许/阻止" 设置添加和删除应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-145">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="cf3ee-146">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-146">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="cf3ee-147">向用户分配自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cf3ee-147">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="cf3ee-148">你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块，以便为组中的用户分配自定义策略，例如安全组或通讯组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-148">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to users in a group, such as all users in a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="cf3ee-149">向用户分配自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cf3ee-149">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="cf3ee-150">若要向一个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cf3ee-150">To assign a policy to one user:</span></span>

1. <span data-ttu-id="cf3ee-151">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-151">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="cf3ee-152">单击用户名的左侧以选择用户，然后单击“编辑设置”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cf3ee-152">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="cf3ee-153">在 "**应用权限策略**" 下，选择要分配的应用权限策略，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-153">Under **App permission policy**, select the app permission policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="cf3ee-154">要一次为多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cf3ee-154">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="cf3ee-155">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后搜索用户或筛选视图以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-155">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="cf3ee-156">在 " **&#x2713;** " （复选标记）列中，选择用户。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-156">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="cf3ee-157">若要选择 "所有用户"，请单击表格顶部的 "&#x2713;" （复选标记）。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-157">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="cf3ee-158">单击 "**编辑设置**"，进行所需的更改，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-158">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="cf3ee-159">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cf3ee-159">Or, you can also do the following:</span></span>

1. <span data-ttu-id="cf3ee-160">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-160">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="cf3ee-161">单击策略名称的左侧以选择该策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-161">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="cf3ee-162">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-162">Select **Manage users**.</span></span>
4. <span data-ttu-id="cf3ee-163">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cf3ee-163">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="cf3ee-164">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-164">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="cf3ee-165">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-165">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="cf3ee-166">将自定义应用权限策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="cf3ee-166">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="cf3ee-167">你可能需要将自定义应用权限策略分配给已标识的多个用户。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-167">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="cf3ee-168">例如，你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-168">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="cf3ee-169">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-169">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="cf3ee-170">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-170">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="cf3ee-171">在此示例中，我们将名为 HR App 权限策略的自定义应用权限策略分配给 Contoso 制药人力资源项目组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-171">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="cf3ee-172">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-172">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="cf3ee-173">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-173">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="cf3ee-174">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-174">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="cf3ee-175">将组中的所有用户分配到特定应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-175">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="cf3ee-176">在此示例中，它是 HR 应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-176">In this example, it's HR App Permission Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="cf3ee-177">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-177">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="app-permission-policies-for-gcc"></a><span data-ttu-id="cf3ee-178">适用于 GCC 的应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cf3ee-178">App permission policies for GCC</span></span>

<span data-ttu-id="cf3ee-179">在 Microsoft 365 政府版团队部署中，请务必了解以下有关适用于 GCC 的第三方应用设置的信息。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-179">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="cf3ee-180">在 GCC 中，默认情况下将阻止所有第三方应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-180">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="cf3ee-181">此外，在 Microsoft 团队管理中心的 "应用权限策略" 页面上，你将看到以下有关管理第三方应用的说明。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-181">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC 中的应用权限策略的屏幕截图](media/app-permission-policies-gcc.png)

<span data-ttu-id="cf3ee-183">若要为你的组织中的一个用户或一组用户启用第三方应用，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cf3ee-183">To enable a third-party app for a user or a set of users in your organization, do the following:</span></span>

1. <span data-ttu-id="cf3ee-184">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"，然后在应用列表中，确认要为一组用户允许的第三方应用是否设置为 "在组织级别**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-184">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then in the list of apps, confirm that the third-party app that you want to allow for a set of users is set to **Blocked** at the org level.</span></span>

2. <span data-ttu-id="cf3ee-185">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **权限策略**"，然后编辑全局策略以阻止第三方应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-185">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**, and then edit the global policy to block the third-party app.</span></span> <span data-ttu-id="cf3ee-186">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="cf3ee-186">To do this:</span></span>
    1. <span data-ttu-id="cf3ee-187">在 "应用权限策略" 页面上，单击 "**全局（组织范围默认）**"，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-187">On the App permission policies page, click **Global (Org-wide default)**, and then click **Edit**.</span></span>
    2. <span data-ttu-id="cf3ee-188">在 "**第三方应用**" 下，选择 "**阻止特定应用并允许所有其他**应用"，添加应用，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-188">Under **Third-party apps**, select **Block specific apps and allow all others**, add the app, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf3ee-189">请务必先执行此操作，然后再转到下一步，以便在组织级别允许应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-189">It's important to do this before you go to the next step to allow the app at the org level.</span></span> <span data-ttu-id="cf3ee-190">这是因为如果在全局应用权限策略中未阻止第三方应用，则全局策略适用的所有用户都可以在组织级别允许访问第三方应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-190">This is because if the third-party app isn't blocked in the global app permission policy, all users that the global policy applies to will be able to access the third-party app when you allow it at the org level.</span></span>

3. <span data-ttu-id="cf3ee-191">允许在组织级别的第三方应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-191">Allow the third-party app at the org level.</span></span> <span data-ttu-id="cf3ee-192">若要执行此操作，请在左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-192">To do this, in the left navigation, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="cf3ee-193">在应用列表中，单击应用名称的左侧以选择应用，然后选择 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-193">In the list of apps, click to the left of the app name to select the app, and then select **Allow**.</span></span>
4. <span data-ttu-id="cf3ee-194">[创建自定义应用权限策略](#create-a-custom-app-permission-policy)以允许应用，然后[将策略分配](#assign-a-custom-app-permission-policy-to-users)给所需的用户。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-194">[Create a custom app permission policy](#create-a-custom-app-permission-policy) to allow the app, and then [assign the policy](#assign-a-custom-app-permission-policy-to-users) to the users you want.</span></span>

## <a name="faq"></a><span data-ttu-id="cf3ee-195">常见问题</span><span class="sxs-lookup"><span data-stu-id="cf3ee-195">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="cf3ee-196">使用应用权限策略</span><span class="sxs-lookup"><span data-stu-id="cf3ee-196">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="cf3ee-197">权限策略影响的应用交互是什么？</span><span class="sxs-lookup"><span data-stu-id="cf3ee-197">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="cf3ee-198">权限策略通过控制最终用户的安装、发现和交互来控制应用的使用情况。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-198">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="cf3ee-199">管理员仍然可以管理 Microsoft 团队管理中心中的应用，而不管分配给他们的权限策略如何。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-199">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="cf3ee-200">是否可以控制业务线（LOB）应用？</span><span class="sxs-lookup"><span data-stu-id="cf3ee-200">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="cf3ee-201">是的，你可以使用应用权限策略控制自定义（LOB）应用的推出和分发。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-201">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="cf3ee-202">你可以创建自定义策略或编辑全局策略，以根据你的组织的需要允许或阻止自定义应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-202">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="cf3ee-203">应用权限策略与已固定的应用和应用设置策略有何关系？</span><span class="sxs-lookup"><span data-stu-id="cf3ee-203">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="cf3ee-204">你可以将应用设置策略与应用权限策略结合使用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-204">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="cf3ee-205">已从用户的已启用应用集中选择预固定的应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-205">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="cf3ee-206">此外，如果用户具有在应用设置策略中阻止应用的应用权限策略，则该应用不会显示在团队中。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-206">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="cf3ee-207">是否可以使用应用权限策略来限制上载自定义应用程序？</span><span class="sxs-lookup"><span data-stu-id="cf3ee-207">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="cf3ee-208">你可以在 "**管理应用**" 页面上使用组织范围内的设置，或使用应用设置策略来限制为你的组织上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-208">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="cf3ee-209">若要限制特定用户上载自定义应用程序，请使用自定义应用策略。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-209">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="cf3ee-210">若要了解详细信息，请参阅[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-210">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="cf3ee-211">阻止应用是否会应用到团队移动客户端？</span><span class="sxs-lookup"><span data-stu-id="cf3ee-211">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="cf3ee-212">是的，当你阻止应用时，将阻止所有团队客户端上的应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-212">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="cf3ee-213">用户体验</span><span class="sxs-lookup"><span data-stu-id="cf3ee-213">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="cf3ee-214">应用被阻止时的用户体验？</span><span class="sxs-lookup"><span data-stu-id="cf3ee-214">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="cf3ee-215">用户无法与已阻止的应用或其功能（如 bot、选项卡和消息传递扩展）交互。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-215">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="cf3ee-216">在共享上下文（如团队或群组聊天）中，机器人仍可向该上下文的所有参与者发送消息。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-216">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="cf3ee-217">团队在应用被阻止时向用户显示。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-217">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="cf3ee-218">例如，当应用被阻止时，用户不能执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="cf3ee-218">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="cf3ee-219">将应用程序个人或聊天添加到聊天或团队</span><span class="sxs-lookup"><span data-stu-id="cf3ee-219">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="cf3ee-220">将消息发送到应用的 bot</span><span class="sxs-lookup"><span data-stu-id="cf3ee-220">Send messages to the app’s bot</span></span>
- <span data-ttu-id="cf3ee-221">执行将信息发送回应用的按钮操作，例如可操作的消息</span><span class="sxs-lookup"><span data-stu-id="cf3ee-221">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="cf3ee-222">查看应用的选项卡</span><span class="sxs-lookup"><span data-stu-id="cf3ee-222">View the app’s tab</span></span>
- <span data-ttu-id="cf3ee-223">设置连接器以接收通知</span><span class="sxs-lookup"><span data-stu-id="cf3ee-223">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="cf3ee-224">使用应用的消息扩展</span><span class="sxs-lookup"><span data-stu-id="cf3ee-224">Use the app’s messaging extension</span></span>

<span data-ttu-id="cf3ee-225">旧版门户允许在组织级别控制应用，这意味着当应用被阻止时，组织中的所有用户都将阻止该应用。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-225">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="cf3ee-226">在 "[管理应用程序](manage-apps.md)" 页面上阻止应用的工作方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-226">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="cf3ee-227">对于分配给特定用户的应用权限策略，如果允许使用支持机器人或连接器功能的应用，并且该应用仅允许共享上下文中的某些用户，则不具有该应用权限的组聊天或频道的成员可以查看由 bot 或连接器发布的邮件历史记录和消息，但无法与之交互。</span><span class="sxs-lookup"><span data-stu-id="cf3ee-227">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf3ee-228">相关主题</span><span class="sxs-lookup"><span data-stu-id="cf3ee-228">Related topics</span></span>

- [<span data-ttu-id="cf3ee-229">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="cf3ee-229">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="cf3ee-230">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="cf3ee-230">Assign policies to your users in Teams</span></span>](assign-policies.md)
