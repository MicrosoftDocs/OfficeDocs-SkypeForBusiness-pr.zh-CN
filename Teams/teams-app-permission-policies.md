---
title: 管理应用程序中的 Microsoft 团队的权限策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/05/2019
ms.reviewer: larryjin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解有关 Microsoft 团队和如何使用它们来控制对组织中用户可用的应用程序中的应用程序权限策略。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 47a4d3a444a0685e0a1ff568332bdc426752af4c
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30411378"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="c4abb-103">管理应用程序中的 Microsoft 团队的权限策略</span><span class="sxs-lookup"><span data-stu-id="c4abb-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="c4abb-104">作为一名管理员，您可以使用应用程序的权限策略来控制应用程序可供您的组织中的 Microsoft 团队用户。</span><span class="sxs-lookup"><span data-stu-id="c4abb-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="c4abb-105">您可以允许或阻止所有应用程序或由 Microsoft 已发布的特定应用程序第三方和您的组织。</span><span class="sxs-lookup"><span data-stu-id="c4abb-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="c4abb-106">当您阻止应用程序时，用户将无法从团队应用程序商店安装它。</span><span class="sxs-lookup"><span data-stu-id="c4abb-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="c4abb-107">管理 Microsoft 团队管理中心中的应用程序权限策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c4abb-108">可以应用设置组织范围、 使用 （组织范围内默认值） 全局策略，并创建和自定义策略分配给单个用户或组中的用户。</span><span class="sxs-lookup"><span data-stu-id="c4abb-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![应用程序权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="c4abb-110">您的组织中的用户将自动授予全局策略，除非您创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="c4abb-111">组织范围应用程序设置将覆盖全局策略和创建并向用户分配的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="c4abb-112">例如，假设您想要阻止所有第三方应用程序并允许来自 Microsoft 的特定应用程序，您的组织中的 HR 小组。</span><span class="sxs-lookup"><span data-stu-id="c4abb-112">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="c4abb-113">您可以创建名为 HR 应用程序权限策略的自定义策略，将其设置为阻止或允许应用程序所需，然后将其分配给人事部门的用户。</span><span class="sxs-lookup"><span data-stu-id="c4abb-113">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>


## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="c4abb-114">管理组织范围应用程序设置</span><span class="sxs-lookup"><span data-stu-id="c4abb-114">Manage org-wide app settings</span></span>

<span data-ttu-id="c4abb-115">使用的应用程序可在整个组织的控制组织范围应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="c4abb-115">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="c4abb-116">组织范围应用程序设置控制的所有用户的行为和替代的任何其他应用程序权限策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c4abb-116">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="c4abb-117">组织范围应用程序设置会立即生效，并可用于控制恶意或有问题的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-117">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="c4abb-118">在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **应用程序的权限策略**。</span><span class="sxs-lookup"><span data-stu-id="c4abb-118">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App permission policies**.</span></span>
2. <span data-ttu-id="c4abb-119">选择**组织范围的设置**。</span><span class="sxs-lookup"><span data-stu-id="c4abb-119">Select **Org-wide settings**.</span></span> <span data-ttu-id="c4abb-120">然后，您可以面板中配置所需的设置。</span><span class="sxs-lookup"><span data-stu-id="c4abb-120">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="c4abb-121">![组织范围应用程序设置的屏幕截图](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="c4abb-121">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="c4abb-122">在**第三方应用程序**，下关闭或打开来控制对第三方应用程序访问这些设置：</span><span class="sxs-lookup"><span data-stu-id="c4abb-122">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

- <span data-ttu-id="c4abb-123">**允许在工作组中的第三方应用程序**： 此选项控制用户是否可以使用第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-123">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
- <span data-ttu-id="c4abb-124">**允许任何新的第三方应用程序发布到默认情况下存储**： 是否将新的第三方应用程序发布到团队应用程序的存储成为团队中自动提供此控件。</span><span class="sxs-lookup"><span data-stu-id="c4abb-124">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="c4abb-125">如果允许第三方应用程序，仅可设置此选项。</span><span class="sxs-lookup"><span data-stu-id="c4abb-125">You can only set this option if you allow third-party apps.</span></span> 
- <span data-ttu-id="c4abb-126">**与自定义应用程序允许进行交互**： 此选项控制用户是否可以与自定义 (sideloaded) 应用程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="c4abb-126">**Allow interaction with custom apps**: This controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="c4abb-127">请记住，这一点不同于允许用户*上载*客户相关应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-127">Keep in mind that this is different from allowing users to *upload* customer apps.</span></span> 

4. <span data-ttu-id="c4abb-128">在**已阻止应用程序**，下搜索并添加您想要阻止在整个组织的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-128">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="c4abb-129">您可以选择从租户的应用程序目录或团队应用程序商店的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-129">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
5. <span data-ttu-id="c4abb-130">单击**另存**为组织范围应用程序设置才会生效。</span><span class="sxs-lookup"><span data-stu-id="c4abb-130">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="c4abb-131">创建自定义应用程序权限策略</span><span class="sxs-lookup"><span data-stu-id="c4abb-131">Create a custom app permission policy</span></span>

<span data-ttu-id="c4abb-132">如果您想要控制可用于不同的组织中的用户组的应用程序，创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-132">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom policies.</span></span> <span data-ttu-id="c4abb-133">您可以创建和分配单独基于是否由 Microsoft 发布应用程序的自定义策略第三方或您的组织。</span><span class="sxs-lookup"><span data-stu-id="c4abb-133">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="c4abb-134">务必要了解创建自定义策略后，您不能更改其是否组织范围的设置中禁用第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-134">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="c4abb-135">在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **应用程序的权限策略**。</span><span class="sxs-lookup"><span data-stu-id="c4abb-135">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App permission policies**.</span></span>
2. <span data-ttu-id="c4abb-136">选择**新策略**。</span><span class="sxs-lookup"><span data-stu-id="c4abb-136">Select **New policy**.</span></span>
    <span data-ttu-id="c4abb-137">![新的应用程序权限策略的屏幕截图](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="c4abb-137">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="c4abb-138">输入策略的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="c4abb-138">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="c4abb-139">在**Microsoft 应用程序**、**第三方应用程序**，和**租户的应用程序**，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="c4abb-139">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

- <span data-ttu-id="c4abb-140">**允许所有应用程序**</span><span class="sxs-lookup"><span data-stu-id="c4abb-140">**Allow all apps**</span></span>
- <span data-ttu-id="c4abb-141">**允许特定应用程序和阻止所有其他人**</span><span class="sxs-lookup"><span data-stu-id="c4abb-141">**Allow specific apps and block all others**</span></span>
- <span data-ttu-id="c4abb-142">**阻止特定应用程序，并允许所有其他人**</span><span class="sxs-lookup"><span data-stu-id="c4abb-142">**Block specific apps and allow all others**</span></span>
- <span data-ttu-id="c4abb-143">**阻止所有应用程序**</span><span class="sxs-lookup"><span data-stu-id="c4abb-143">**Block all apps**</span></span>

5. <span data-ttu-id="c4abb-144">如果您选择**允许特定应用程序和阻止其他人**，添加您希望允许的应用程序：</span><span class="sxs-lookup"><span data-stu-id="c4abb-144">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="c4abb-145">选择**允许应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4abb-145">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="c4abb-146">要允许，然后单击**添加**的应用程序的搜索。</span><span class="sxs-lookup"><span data-stu-id="c4abb-146">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="c4abb-147">搜索结果进行筛选到应用程序发布者 （**Microsoft 应用程序**，**第三方应用程序**或**租户的应用程序**）。</span><span class="sxs-lookup"><span data-stu-id="c4abb-147">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="c4abb-148">当您选择的应用程序列表时，请单击**允许**。</span><span class="sxs-lookup"><span data-stu-id="c4abb-148">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="c4abb-149">同样，如果选择了**阻止特定应用程序，并允许所有其他人**，搜索并添加您想要阻止的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-149">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="c4abb-150">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="c4abb-150">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="c4abb-151">编辑应用程序权限策略</span><span class="sxs-lookup"><span data-stu-id="c4abb-151">Edit an app permission policy</span></span>

<span data-ttu-id="c4abb-152">您可以使用的 Microsoft 团队管理中心或 Windows PowerShell 编辑策略，包括全局 （组织范围内默认值） 策略和您创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-152">You can use the Microsoft Teams admin center or Windows PowerShell to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="c4abb-153">在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **应用程序的权限策略**。</span><span class="sxs-lookup"><span data-stu-id="c4abb-153">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App permission policies**.</span></span>
2. <span data-ttu-id="c4abb-154">选择您想要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-154">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="c4abb-155">从此处，进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="c4abb-155">From here, make the changes that you want.</span></span> <span data-ttu-id="c4abb-156">您可以管理基于应用程序发布者设置和添加和删除基于允许/阻止设置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-156">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="c4abb-157">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="c4abb-157">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="c4abb-158">将自定义应用程序权限策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="c4abb-158">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="c4abb-159">您可以使用的 Microsoft 团队管理中心分配给各个用户的自定义策略或 Skype for Business PowerShell 模块，将自定义策略分配给多个用户，例如安全组或通讯组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="c4abb-159">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="c4abb-160">自定义应用程序安装策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="c4abb-160">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="c4abb-161">在 Microsoft 团队管理中心的左侧导航窗格中，转到**用户**，，然后单击用户。</span><span class="sxs-lookup"><span data-stu-id="c4abb-161">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click       the user.</span></span>
2. <span data-ttu-id="c4abb-162">旁边**分配策略**，选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="c4abb-162">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="c4abb-163">在**应用程序权限策略**中，选择要分配的应用程序权限策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="c4abb-163">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![应用程序的安装程序的权限-分配-policy.png](media/app-permission-policies-assign-policy.png)

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="c4abb-165">将自定义应用程序权限策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="c4abb-165">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="c4abb-166">您可能想要将自定义应用程序权限策略分配给已识别的多个用户。</span><span class="sxs-lookup"><span data-stu-id="c4abb-166">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="c4abb-167">例如，您可能要将策略分配给安全组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="c4abb-167">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="c4abb-168">您可以通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块 Skype 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c4abb-168">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="c4abb-169">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell Overview](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c4abb-169">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="c4abb-170">本示例中，我们将分配到 Contoso 药品 HR 项目组中的所有用户称为人力资源应用程序权限策略的自定义应用程序权限策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-170">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="c4abb-171">请确保您首次[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块的 Skype。</span><span class="sxs-lookup"><span data-stu-id="c4abb-171">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="c4abb-172">获取特定的组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="c4abb-172">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="c4abb-173">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="c4abb-173">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="c4abb-174">组中的所有用户都分配特定的应用程序权限策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-174">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="c4abb-175">本示例中，它是 HR 应用程序权限策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-175">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="c4abb-176">根据组中成员的数目，此命令可能需要几分钟才能执行。</span><span class="sxs-lookup"><span data-stu-id="c4abb-176">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="c4abb-177">常见问题</span><span class="sxs-lookup"><span data-stu-id="c4abb-177">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="c4abb-178">使用应用程序权限策略</span><span class="sxs-lookup"><span data-stu-id="c4abb-178">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="c4abb-179">可以控制行业 (LOB) 应用程序？</span><span class="sxs-lookup"><span data-stu-id="c4abb-179">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="c4abb-180">是，可以使用应用程序的权限策略来控制推出和通讯组的自定义 (LOB) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-180">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="c4abb-181">应用程序的权限策略如何固定的应用程序和应用程序设置策略相关联？</span><span class="sxs-lookup"><span data-stu-id="c4abb-181">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="c4abb-182">您可以使用与应用程序的权限策略的应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="c4abb-182">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="c4abb-183">从一组的用户启用应用程序中选择预固定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4abb-183">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="c4abb-184">此外，如果用户具有阻止应用程序在其应用程序安装策略中的应用程序权限策略，该应用程序不会出现在工作组中。</span><span class="sxs-lookup"><span data-stu-id="c4abb-184">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="c4abb-185">如何长时间才会生效的策略更改？</span><span class="sxs-lookup"><span data-stu-id="c4abb-185">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="c4abb-186">编辑全局策略，或为用户分配策略后，可以最多 24 小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="c4abb-186">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="c4abb-187">组织范围应用程序设置会立即生效。</span><span class="sxs-lookup"><span data-stu-id="c4abb-187">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="c4abb-188">阻止应用程序适用于团队移动客户端？</span><span class="sxs-lookup"><span data-stu-id="c4abb-188">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="c4abb-189">是时阻止应用程序，该应用程序阻止所有团队客户端。</span><span class="sxs-lookup"><span data-stu-id="c4abb-189">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="c4abb-190">用户体验</span><span class="sxs-lookup"><span data-stu-id="c4abb-190">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="c4abb-191">什么用户体验时阻止应用程序？</span><span class="sxs-lookup"><span data-stu-id="c4abb-191">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="c4abb-192">用户不能与阻止应用程序或其功能、 此类机器人、 制表符和消息扩展进行交互。</span><span class="sxs-lookup"><span data-stu-id="c4abb-192">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="c4abb-193">在共享上下文中，团队或组聊天中，如自动程序仍然可以向所有参与者的上下文的发送消息。</span><span class="sxs-lookup"><span data-stu-id="c4abb-193">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="c4abb-194">阻止应用程序时，向用户指明团队。</span><span class="sxs-lookup"><span data-stu-id="c4abb-194">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="c4abb-195">例如，当阻止应用程序时，用户不能执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="c4abb-195">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="c4abb-196">将应用程序添加个人或聊天或团队</span><span class="sxs-lookup"><span data-stu-id="c4abb-196">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="c4abb-197">将邮件发送到应用程序的自动程序</span><span class="sxs-lookup"><span data-stu-id="c4abb-197">Send messages to the app’s bot</span></span>
- <span data-ttu-id="c4abb-198">执行将信息发送回应用程序，例如，可操作的消息的按钮操作</span><span class="sxs-lookup"><span data-stu-id="c4abb-198">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="c4abb-199">查看应用程序的选项卡</span><span class="sxs-lookup"><span data-stu-id="c4abb-199">View the app’s tab</span></span>
- <span data-ttu-id="c4abb-200">设置连接器以接收通知</span><span class="sxs-lookup"><span data-stu-id="c4abb-200">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="c4abb-201">使用应用程序的消息扩展</span><span class="sxs-lookup"><span data-stu-id="c4abb-201">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="c4abb-202">相关主题</span><span class="sxs-lookup"><span data-stu-id="c4abb-202">Related topics</span></span>
- [<span data-ttu-id="c4abb-203">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="c4abb-203">Manage app setup policies in Microsoft Teams</span></span>](teams-app-setup-policies.md)
