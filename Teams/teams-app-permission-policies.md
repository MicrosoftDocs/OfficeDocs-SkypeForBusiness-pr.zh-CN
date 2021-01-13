---
title: 在 Microsoft Teams 中管理应用权限策略
author: cichur
ms.author: v-cichur
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
description: 了解 Microsoft Teams 中的应用权限策略，以及如何使用它们来控制哪些应用可供组织用户使用。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802492"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="16147-103">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="16147-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="16147-104">作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。</span><span class="sxs-lookup"><span data-stu-id="16147-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="16147-105">你可以允许或阻止 Microsoft、第三方和组织发布的所有应用或特定应用。</span><span class="sxs-lookup"><span data-stu-id="16147-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="16147-106">阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。</span><span class="sxs-lookup"><span data-stu-id="16147-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="16147-107">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="16147-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="16147-108">在 Microsoft Teams 管理中心中管理应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="16147-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="16147-109">可以使用全局策略 (组织范围内的默认) 策略，也可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="16147-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="16147-110">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="16147-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="16147-111">编辑或分配策略后，可能需要几个小时更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="16147-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![应用权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="16147-113">组织范围的应用设置会覆盖全局策略以及你创建并分配给用户的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="16147-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="16147-114">如果你的组织已在 Teams 上，你在 Microsoft 365 管理中心的租户范围设置中配置的应用设置将反映在"管理应用"页面上的组织范围[应用设置](manage-apps.md)中。 </span><span class="sxs-lookup"><span data-stu-id="16147-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="16147-115">如果你是 Teams 的新用户且刚刚入门，默认情况下，全局策略中允许所有应用。</span><span class="sxs-lookup"><span data-stu-id="16147-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="16147-116">这包括由 Microsoft、第三方和组织发布的应用。</span><span class="sxs-lookup"><span data-stu-id="16147-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="16147-117">例如，假设你想要阻止所有第三方应用，并允许 Microsoft 为贵组织的 HR 团队提供特定应用。</span><span class="sxs-lookup"><span data-stu-id="16147-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="16147-118">首先，转到"管理应用"[](manage-apps.md)页面，确保允许 HR 团队使用的应用在组织级别。</span><span class="sxs-lookup"><span data-stu-id="16147-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="16147-119">然后，创建名为 HR 应用权限策略的自定义策略，将其设置为阻止和允许所需的应用，并将其分配给 HR 团队中的用户。</span><span class="sxs-lookup"><span data-stu-id="16147-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="16147-120">如果在 Microsoft 365 政府社区云 (GCC) 环境中部署了 Teams，请参阅"管理 [Microsoft 365](#manage-org-wide-app-settings-for-microsoft-365-government) 政府版组织范围内的应用设置"，详细了解 GCC 独有的第三方应用设置。</span><span class="sxs-lookup"><span data-stu-id="16147-120">If you deployed Teams in a Microsoft 365 Government Community Cloud (GCC) environment, see [Manage org-wide app settings for Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="16147-121">创建自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="16147-121">Create a custom app permission policy</span></span>

<span data-ttu-id="16147-122">如果要控制组织中不同用户组可用的应用，请创建并分配一个或多个自定义应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="16147-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="16147-123">你可以根据应用是由 Microsoft、第三方还是你的组织发布的，创建和分配单独的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="16147-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="16147-124">必须知道，创建自定义策略后，如果在组织范围内的应用设置中禁用了第三方应用，则不能更改该策略。</span><span class="sxs-lookup"><span data-stu-id="16147-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="16147-125">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **权限策略"。**</span><span class="sxs-lookup"><span data-stu-id="16147-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="16147-126">单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="16147-126">Click **Add**.</span></span> <br>
    <span data-ttu-id="16147-127">![新应用权限策略的屏幕截图](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="16147-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="16147-128">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="16147-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="16147-129">在 **"Microsoft 应用**、 **第三方** 应用"和" **自定义应用**"下，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="16147-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="16147-130">**允许所有应用**</span><span class="sxs-lookup"><span data-stu-id="16147-130">**Allow all apps**</span></span>
    - <span data-ttu-id="16147-131">**允许特定应用并阻止所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="16147-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="16147-132">**阻止特定应用并允许其他所有应用**</span><span class="sxs-lookup"><span data-stu-id="16147-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="16147-133">**阻止所有应用**</span><span class="sxs-lookup"><span data-stu-id="16147-133">**Block all apps**</span></span>

5. <span data-ttu-id="16147-134">如果选择" **允许特定应用"并阻止其他** 应用，请添加要允许的应用：</span><span class="sxs-lookup"><span data-stu-id="16147-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="16147-135">选择 **"允许应用"。**</span><span class="sxs-lookup"><span data-stu-id="16147-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="16147-136">搜索要允许的应用，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="16147-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="16147-137">搜索结果将筛选为应用发布者， (**Microsoft 应用**、第三方应用或自定义 **应用) 。**</span><span class="sxs-lookup"><span data-stu-id="16147-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="16147-138">选择应用列表后，单击"允许 **"。**</span><span class="sxs-lookup"><span data-stu-id="16147-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="16147-139">同样，如果选择了"阻止 **特定应用"并允许** 其他所有应用，请搜索并添加要阻止的应用，然后单击"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="16147-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="16147-140">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="16147-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="16147-141">编辑应用权限策略</span><span class="sxs-lookup"><span data-stu-id="16147-141">Edit an app permission policy</span></span>

<span data-ttu-id="16147-142">可以使用 Microsoft Teams 管理中心编辑策略，包括你创建的全局策略和自定义策略。</span><span class="sxs-lookup"><span data-stu-id="16147-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="16147-143">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **权限策略"。**</span><span class="sxs-lookup"><span data-stu-id="16147-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="16147-144">单击策略名称左侧选择策略，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="16147-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="16147-145">在此处，进行您需要的更改。</span><span class="sxs-lookup"><span data-stu-id="16147-145">From here, make the changes that you want.</span></span> <span data-ttu-id="16147-146">你可以根据应用发布者管理设置，并基于允许/阻止设置添加和删除应用。</span><span class="sxs-lookup"><span data-stu-id="16147-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="16147-147">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="16147-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="16147-148">向用户分配自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="16147-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a><span data-ttu-id="16147-149">管理 Microsoft 365 政府版组织范围内的应用设置</span><span class="sxs-lookup"><span data-stu-id="16147-149">Manage org-wide app settings for Microsoft 365 Government</span></span>  

<span data-ttu-id="16147-150">在 Teams 的 Microsoft 365 政府版 - GCC 部署中，必须了解以下内容，了解 GCC 独有的第三方应用设置。</span><span class="sxs-lookup"><span data-stu-id="16147-150">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="16147-151">在 GCC 中，默认情况下会阻止所有第三方应用。</span><span class="sxs-lookup"><span data-stu-id="16147-151">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="16147-152">此外，你将在 Microsoft Teams 管理中心的应用权限策略页面上看到有关管理第三方应用的以下说明。</span><span class="sxs-lookup"><span data-stu-id="16147-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC 中应用权限策略的屏幕截图](media/app-permission-policies-gcc.png)

<span data-ttu-id="16147-154">使用组织范围内的应用设置来控制用户是否可以安装第三方应用。</span><span class="sxs-lookup"><span data-stu-id="16147-154">Use org-wide app settings to control whether users can install third-party apps.</span></span> <span data-ttu-id="16147-155">组织范围的应用设置控制所有用户的行为，并覆盖分配给用户的其他任何应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="16147-155">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="16147-156">可以使用它们来控制恶意或有问题的应用。</span><span class="sxs-lookup"><span data-stu-id="16147-156">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="16147-157">在"**权限策略"** 页上，选择 **"组织范围的应用设置"。**</span><span class="sxs-lookup"><span data-stu-id="16147-157">On the **Permission policies** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="16147-158">然后，可以在面板中配置想要的设置。</span><span class="sxs-lookup"><span data-stu-id="16147-158">You can then configure the settings you want in the panel.</span></span>

    ![组织范围内应用设置的屏幕截图](media/app-permission-policies-gcc-org-wide.png)
    
2. <span data-ttu-id="16147-160">在第 **三方应用下**，关闭或打开这些设置以控制对第三方应用的访问：</span><span class="sxs-lookup"><span data-stu-id="16147-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="16147-161">**允许第三方应用**：控制用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="16147-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="16147-162">如果关闭此设置，用户将无法安装或使用任何第三方应用。</span><span class="sxs-lookup"><span data-stu-id="16147-162">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="16147-163">在 Teams 的 Microsoft 365 政府版 - GCC 部署中，此设置默认关闭。</span><span class="sxs-lookup"><span data-stu-id="16147-163">In a Microsoft 365 Government - GCC deployment of Teams, this setting is off by default.</span></span>
    - <span data-ttu-id="16147-164">**允许默认情况下发布到** 应用商店的任何新第三方应用：这控制发布到 Teams 应用商店的新第三方应用在 Teams 中是否自动可用。</span><span class="sxs-lookup"><span data-stu-id="16147-164">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="16147-165">只有在允许第三方应用时，才能设置此选项。</span><span class="sxs-lookup"><span data-stu-id="16147-165">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="16147-166">在 **"阻止的应用**"下，添加要在整个组织中阻止的应用。</span><span class="sxs-lookup"><span data-stu-id="16147-166">Under **Blocked apps**, add the apps you want to block across your organization.</span></span> <span data-ttu-id="16147-167">在 Teams 的 Microsoft 365 政府版 - GCC 部署中，所有第三方应用默认添加到此列表。</span><span class="sxs-lookup"><span data-stu-id="16147-167">In a Microsoft 365 Government - GCC deployment of Teams, all third-party apps are added to this list by default.</span></span> <span data-ttu-id="16147-168">对于希望在你的组织中允许的任何第三方应用，请从此阻止的应用列表中删除该应用。</span><span class="sxs-lookup"><span data-stu-id="16147-168">For any third-party app you want to allow in your organization, remove the app from this blocked apps list.</span></span> <span data-ttu-id="16147-169">当你在组织范围内阻止应用时，你的所有用户都会自动阻止该应用，无论应用权限策略中是否允许该应用</span><span class="sxs-lookup"><span data-stu-id="16147-169">When you block an app org-wide, the app is automatically blocked for all your users, regardless of whether it's allowed in any app permission policies</span></span>
4. <span data-ttu-id="16147-170">单击 **"** 保存"，使组织范围内的应用设置生效。</span><span class="sxs-lookup"><span data-stu-id="16147-170">Click **Save** for org-wide app settings to take effect.</span></span>

<span data-ttu-id="16147-171">如前所述，若要允许第三方应用，可以编辑和使用全局 (组织范围内的默认) 策略，也可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="16147-171">As mentioned earlier, to allow third-party apps, you can either edit and use the global (Org-wide default) policy or create and assign custom policies.</span></span>

## <a name="faq"></a><span data-ttu-id="16147-172">常见问题</span><span class="sxs-lookup"><span data-stu-id="16147-172">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="16147-173">使用应用权限策略</span><span class="sxs-lookup"><span data-stu-id="16147-173">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="16147-174">权限策略影响哪些应用交互？</span><span class="sxs-lookup"><span data-stu-id="16147-174">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="16147-175">权限策略通过控制最终用户的安装、发现和交互来控制应用使用情况。</span><span class="sxs-lookup"><span data-stu-id="16147-175">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="16147-176">无论分配了哪些权限策略，管理员仍可在 Microsoft Teams 管理中心管理应用。</span><span class="sxs-lookup"><span data-stu-id="16147-176">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="16147-177">我能否控制 LOB () 业务线？</span><span class="sxs-lookup"><span data-stu-id="16147-177">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="16147-178">是的，可以使用应用权限策略来控制自定义 LOB 应用 () 分发。</span><span class="sxs-lookup"><span data-stu-id="16147-178">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="16147-179">可以创建自定义策略或编辑全局策略，以根据组织的需求允许或阻止自定义应用。</span><span class="sxs-lookup"><span data-stu-id="16147-179">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="16147-180">应用权限策略如何与固定的应用和应用设置策略相关？</span><span class="sxs-lookup"><span data-stu-id="16147-180">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="16147-181">可以将应用设置策略与应用权限策略一同使用。</span><span class="sxs-lookup"><span data-stu-id="16147-181">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="16147-182">预固定应用从用户启用的应用集进行选择。</span><span class="sxs-lookup"><span data-stu-id="16147-182">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="16147-183">此外，如果用户的应用权限策略阻止应用设置策略中的应用，则该应用不会显示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="16147-183">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="16147-184">我可以使用应用权限策略来限制上传自定义应用吗？</span><span class="sxs-lookup"><span data-stu-id="16147-184">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="16147-185">可以在"管理应用"页面上使用组织范围的设置，或使用应用设置策略来限制为组织上传自定义应用。</span><span class="sxs-lookup"><span data-stu-id="16147-185">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="16147-186">若要限制特定用户上传自定义应用，请使用自定义应用策略。</span><span class="sxs-lookup"><span data-stu-id="16147-186">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="16147-187">若要了解有关详细信息，请参阅["在 Teams 中管理自定义应用策略和设置"。](teams-custom-app-policies-and-settings.md)</span><span class="sxs-lookup"><span data-stu-id="16147-187">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="16147-188">阻止应用是否适用于 Teams 移动客户端？</span><span class="sxs-lookup"><span data-stu-id="16147-188">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="16147-189">是的，当你阻止应用时，该应用被阻止在所有 Teams 客户端上。</span><span class="sxs-lookup"><span data-stu-id="16147-189">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="16147-190">用户体验</span><span class="sxs-lookup"><span data-stu-id="16147-190">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="16147-191">当应用被阻止时，用户体验如何？</span><span class="sxs-lookup"><span data-stu-id="16147-191">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="16147-192">用户无法与阻止的应用或应用的功能（例如机器人、选项卡和消息传送扩展）交互。</span><span class="sxs-lookup"><span data-stu-id="16147-192">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="16147-193">在共享上下文（例如团队或群组聊天）中，机器人仍然可以向该上下文的所有参与者发送消息。</span><span class="sxs-lookup"><span data-stu-id="16147-193">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="16147-194">Teams 会向用户指示应用何时被阻止。</span><span class="sxs-lookup"><span data-stu-id="16147-194">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="16147-195">例如，当应用被阻止时，用户无法执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="16147-195">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="16147-196">个人或聊天或团队添加应用</span><span class="sxs-lookup"><span data-stu-id="16147-196">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="16147-197">将消息发送到应用的机器人</span><span class="sxs-lookup"><span data-stu-id="16147-197">Send messages to the app’s bot</span></span>
- <span data-ttu-id="16147-198">执行将信息发送回应用的按钮操作，例如可操作消息</span><span class="sxs-lookup"><span data-stu-id="16147-198">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="16147-199">查看应用的选项卡</span><span class="sxs-lookup"><span data-stu-id="16147-199">View the app’s tab</span></span>
- <span data-ttu-id="16147-200">设置连接器以接收通知</span><span class="sxs-lookup"><span data-stu-id="16147-200">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="16147-201">使用应用的消息传送扩展</span><span class="sxs-lookup"><span data-stu-id="16147-201">Use the app’s messaging extension</span></span>

<span data-ttu-id="16147-202">旧门户允许在组织级别控制应用，这意味着当应用被阻止时，将阻止组织中所有用户使用该应用。</span><span class="sxs-lookup"><span data-stu-id="16147-202">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="16147-203">在"管理应用 ["页面上阻止](manage-apps.md) 应用的工作方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="16147-203">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="16147-204">对于分配给特定用户的应用权限策略，如果允许然后阻止具有机器人或连接器功能的应用，并且如果应用仅允许共享上下文中的一些用户，则没有该应用权限的群组聊天或频道的成员可以看到机器人或连接器发布的消息历史记录和消息，但无法与其交互。</span><span class="sxs-lookup"><span data-stu-id="16147-204">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="16147-205">相关主题</span><span class="sxs-lookup"><span data-stu-id="16147-205">Related topics</span></span>

[<span data-ttu-id="16147-206">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="16147-206">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="16147-207">在 Teams 中向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="16147-207">Assign policies to your users in Teams</span></span>](assign-policies.md)
