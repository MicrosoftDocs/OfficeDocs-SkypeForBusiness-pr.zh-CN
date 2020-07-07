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
ms.openlocfilehash: 15698c7eeb12187ccc510a42b9a6e2120a7907cc
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042985"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="3fd7d-103">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="3fd7d-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="3fd7d-104">作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="3fd7d-105">你可以允许或阻止由 Microsoft、第三方和你的组织发布的所有应用或特定应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="3fd7d-106">阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="3fd7d-107">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="3fd7d-108">你可以在 Microsoft 团队管理中心中管理应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3fd7d-109">你可以使用全局（组织范围默认）策略或创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="3fd7d-110">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="3fd7d-111">编辑或分配策略后，可能需要几个小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![应用权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="3fd7d-113">组织范围内的应用设置替代全局策略和你创建并分配给用户的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="3fd7d-114">如果您的组织已在团队中，则在 Microsoft 365 管理中心的**租户范围设置**中配置的应用设置将反映在 "[管理应用](manage-apps.md)程序" 页面上的组织范围内应用设置中。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="3fd7d-115">如果您不熟悉团队，并且只是开始使用，则默认情况下，所有应用都允许在全局策略中使用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="3fd7d-116">这包括由 Microsoft、第三方和你的组织发布的应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="3fd7d-117">例如，你希望阻止所有第三方应用，并允许 Microsoft 针对你的组织中的人力资源团队应用特定应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="3fd7d-118">首先，你将转到 "[管理应用](manage-apps.md)" 页面，并确保你希望为 HR 团队允许的应用在组织级别允许。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="3fd7d-119">然后，创建名为 HR App 权限策略的自定义策略，将其设置为阻止并允许你所需的应用，并将其分配给 HR 团队上的用户。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="3fd7d-120">如果你在 Microsoft 365 政府社区云（GCC）环境中部署团队，请参阅[管理 microsoft 365 政府组织范围内的应用设置](#manage-org-wide-app-settings-for-microsoft-365-government)，了解有关特定于 GCC 的第三方应用设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-120">If you deployed Teams in a Microsoft 365 Government Community Cloud (GCC) environment, see [Manage org-wide app settings for Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="3fd7d-121">创建自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="3fd7d-121">Create a custom app permission policy</span></span>

<span data-ttu-id="3fd7d-122">如果你希望控制组织中不同组用户可用的应用，请创建并分配一个或多个自定义应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="3fd7d-123">你可以基于 Microsoft、第三方或你的组织发布的应用创建和分配单独的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="3fd7d-124">请务必注意，在创建自定义策略后，如果在组织范围的应用设置中禁用了第三方应用，则无法更改它。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="3fd7d-125">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="3fd7d-126">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-126">Click **Add**.</span></span> <br>
    <span data-ttu-id="3fd7d-127">![新应用权限策略的屏幕截图](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="3fd7d-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="3fd7d-128">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="3fd7d-129">在 " **Microsoft 应用**"、"**第三方应用**" 和 "**自定义应用**" 下，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3fd7d-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="3fd7d-130">**允许所有应用**</span><span class="sxs-lookup"><span data-stu-id="3fd7d-130">**Allow all apps**</span></span>
    - <span data-ttu-id="3fd7d-131">**允许特定应用和阻止所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="3fd7d-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="3fd7d-132">**阻止特定应用并允许所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="3fd7d-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="3fd7d-133">**阻止所有应用**</span><span class="sxs-lookup"><span data-stu-id="3fd7d-133">**Block all apps**</span></span>

5. <span data-ttu-id="3fd7d-134">如果你选择 "**允许特定应用" 并阻止其他应用**，请添加你希望允许的应用：</span><span class="sxs-lookup"><span data-stu-id="3fd7d-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="3fd7d-135">选择 "**允许应用**"。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="3fd7d-136">搜索要允许的应用，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="3fd7d-137">搜索结果将筛选到应用发布者（**Microsoft 应用**、**第三方应用**或**自定义应用**）。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="3fd7d-138">选择应用列表后，单击 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="3fd7d-139">同样，如果你选择 "**阻止特定应用" 并允许所有其他应用**，请搜索并添加要阻止的应用，然后单击 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="3fd7d-140">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="3fd7d-141">编辑应用权限策略</span><span class="sxs-lookup"><span data-stu-id="3fd7d-141">Edit an app permission policy</span></span>

<span data-ttu-id="3fd7d-142">你可以使用 Microsoft 团队管理中心编辑策略，包括全局策略和你创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="3fd7d-143">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="3fd7d-144">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="3fd7d-145">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-145">From here, make the changes that you want.</span></span> <span data-ttu-id="3fd7d-146">你可以基于应用发布者管理设置，并根据 "允许/阻止" 设置添加和删除应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="3fd7d-147">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="3fd7d-148">向用户分配自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="3fd7d-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a><span data-ttu-id="3fd7d-149">管理 Microsoft 365 政府组织范围内的应用设置</span><span class="sxs-lookup"><span data-stu-id="3fd7d-149">Manage org-wide app settings for Microsoft 365 Government</span></span>  

<span data-ttu-id="3fd7d-150">在 Microsoft 365 政府版团队部署中，请务必了解以下有关适用于 GCC 的第三方应用设置的信息。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-150">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="3fd7d-151">在 GCC 中，默认情况下将阻止所有第三方应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-151">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="3fd7d-152">此外，在 Microsoft 团队管理中心的 "应用权限策略" 页面上，你将看到以下有关管理第三方应用的说明。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC 中的应用权限策略的屏幕截图](media/app-permission-policies-gcc.png)

<span data-ttu-id="3fd7d-154">使用组织范围内的应用设置控制用户是否可以安装第三方应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-154">Use org-wide app settings to control whether users can install third-party apps.</span></span> <span data-ttu-id="3fd7d-155">组织范围内的应用设置控制所有用户的行为，并替代分配给用户的任何其他应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-155">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="3fd7d-156">你可以使用它们控制恶意或有问题的应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-156">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="3fd7d-157">在 "**权限策略**" 页面上，选择 "**组织范围内的应用设置**"。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-157">On the **Permission policies** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="3fd7d-158">然后，你可以在面板中配置所需的设置。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-158">You can then configure the settings you want in the panel.</span></span>

    ![组织范围内的应用设置的屏幕截图](media/app-permission-policies-gcc-org-wide.png)
    
2. <span data-ttu-id="3fd7d-160">在 "**第三方应用**" 下，关闭或打开这些设置以控制对第三方应用的访问：</span><span class="sxs-lookup"><span data-stu-id="3fd7d-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="3fd7d-161">**允许第三方应用**：此操作控制用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="3fd7d-162">如果关闭此设置，你的用户将无法安装或使用任何第三方应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-162">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="3fd7d-163">在 Microsoft 365 政府版团队部署中，此设置默认情况下处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-163">In a Microsoft 365 Government - GCC deployment of Teams, this setting is off by default.</span></span>
    - <span data-ttu-id="3fd7d-164">**默认情况下允许发布到应用商店的任何新第三方应用**：这将控制发布到团队应用商店的新的第三方应用是否会自动在团队中可用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-164">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="3fd7d-165">仅当你允许第三方应用时，你才能设置此选项。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-165">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="3fd7d-166">在 "已**阻止的应用**" 下，添加要在组织内阻止的应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-166">Under **Blocked apps**, add the apps you want to block across your organization.</span></span> <span data-ttu-id="3fd7d-167">在 Microsoft 365 政府版团队部署中，默认情况下，所有第三方应用都添加到此列表中。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-167">In a Microsoft 365 Government - GCC deployment of Teams, all third-party apps are added to this list by default.</span></span> <span data-ttu-id="3fd7d-168">对于你想要在你的组织中允许的任何第三方应用，请从此 "阻止的应用" 列表中删除该应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-168">For any third-party app you want to allow in your organization, remove the app from this blocked apps list.</span></span> <span data-ttu-id="3fd7d-169">当你阻止应用组织范围时，将对所有用户自动阻止应用，无论是否允许在任何应用权限策略中使用它</span><span class="sxs-lookup"><span data-stu-id="3fd7d-169">When you block an app org-wide, the app is automatically blocked for all your users, regardless of whether it's allowed in any app permission policies</span></span>
4. <span data-ttu-id="3fd7d-170">单击 "**保存**" 以使组织范围内的应用设置生效。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-170">Click **Save** for org-wide app settings to take effect.</span></span>

<span data-ttu-id="3fd7d-171">如前面所述，若要允许第三方应用，您可以编辑和使用全局（组织范围默认）策略，或者创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-171">As mentioned earlier, to allow third-party apps, you can either edit and use the global (Org-wide default) policy or create and assign custom policies.</span></span>

## <a name="faq"></a><span data-ttu-id="3fd7d-172">常见问题</span><span class="sxs-lookup"><span data-stu-id="3fd7d-172">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="3fd7d-173">使用应用权限策略</span><span class="sxs-lookup"><span data-stu-id="3fd7d-173">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="3fd7d-174">权限策略影响的应用交互是什么？</span><span class="sxs-lookup"><span data-stu-id="3fd7d-174">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="3fd7d-175">权限策略通过控制最终用户的安装、发现和交互来控制应用的使用情况。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-175">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="3fd7d-176">管理员仍然可以管理 Microsoft 团队管理中心中的应用，而不管分配给他们的权限策略如何。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-176">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="3fd7d-177">是否可以控制业务线（LOB）应用？</span><span class="sxs-lookup"><span data-stu-id="3fd7d-177">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="3fd7d-178">是的，你可以使用应用权限策略控制自定义（LOB）应用的推出和分发。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-178">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="3fd7d-179">你可以创建自定义策略或编辑全局策略，以根据你的组织的需要允许或阻止自定义应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-179">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="3fd7d-180">应用权限策略与已固定的应用和应用设置策略有何关系？</span><span class="sxs-lookup"><span data-stu-id="3fd7d-180">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="3fd7d-181">你可以将应用设置策略与应用权限策略结合使用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-181">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="3fd7d-182">已从用户的已启用应用集中选择预固定的应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-182">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="3fd7d-183">此外，如果用户具有在应用设置策略中阻止应用的应用权限策略，则该应用不会显示在团队中。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-183">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="3fd7d-184">是否可以使用应用权限策略来限制上载自定义应用程序？</span><span class="sxs-lookup"><span data-stu-id="3fd7d-184">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="3fd7d-185">你可以在 "**管理应用**" 页面上使用组织范围内的设置，或使用应用设置策略来限制为你的组织上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-185">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="3fd7d-186">若要限制特定用户上载自定义应用程序，请使用自定义应用策略。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-186">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="3fd7d-187">若要了解详细信息，请参阅[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-187">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="3fd7d-188">阻止应用是否会应用到团队移动客户端？</span><span class="sxs-lookup"><span data-stu-id="3fd7d-188">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="3fd7d-189">是的，当你阻止应用时，将阻止所有团队客户端上的应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-189">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="3fd7d-190">用户体验</span><span class="sxs-lookup"><span data-stu-id="3fd7d-190">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="3fd7d-191">应用被阻止时的用户体验？</span><span class="sxs-lookup"><span data-stu-id="3fd7d-191">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="3fd7d-192">用户无法与已阻止的应用或其功能（如 bot、选项卡和消息传递扩展）交互。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-192">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="3fd7d-193">在共享上下文（如团队或群组聊天）中，机器人仍可向该上下文的所有参与者发送消息。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-193">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="3fd7d-194">团队在应用被阻止时向用户显示。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-194">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="3fd7d-195">例如，当应用被阻止时，用户不能执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="3fd7d-195">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="3fd7d-196">将应用程序个人或聊天添加到聊天或团队</span><span class="sxs-lookup"><span data-stu-id="3fd7d-196">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="3fd7d-197">将消息发送到应用的 bot</span><span class="sxs-lookup"><span data-stu-id="3fd7d-197">Send messages to the app’s bot</span></span>
- <span data-ttu-id="3fd7d-198">执行将信息发送回应用的按钮操作，例如可操作的消息</span><span class="sxs-lookup"><span data-stu-id="3fd7d-198">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="3fd7d-199">查看应用的选项卡</span><span class="sxs-lookup"><span data-stu-id="3fd7d-199">View the app’s tab</span></span>
- <span data-ttu-id="3fd7d-200">设置连接器以接收通知</span><span class="sxs-lookup"><span data-stu-id="3fd7d-200">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="3fd7d-201">使用应用的消息扩展</span><span class="sxs-lookup"><span data-stu-id="3fd7d-201">Use the app’s messaging extension</span></span>

<span data-ttu-id="3fd7d-202">旧版门户允许在组织级别控制应用，这意味着当应用被阻止时，组织中的所有用户都将阻止该应用。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-202">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="3fd7d-203">在 "[管理应用程序](manage-apps.md)" 页面上阻止应用的工作方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-203">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="3fd7d-204">对于分配给特定用户的应用权限策略，如果允许使用支持机器人或连接器功能的应用，并且该应用仅允许共享上下文中的某些用户，则不具有该应用权限的组聊天或频道的成员可以查看由 bot 或连接器发布的邮件历史记录和消息，但无法与之交互。</span><span class="sxs-lookup"><span data-stu-id="3fd7d-204">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3fd7d-205">相关主题</span><span class="sxs-lookup"><span data-stu-id="3fd7d-205">Related topics</span></span>

[<span data-ttu-id="3fd7d-206">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="3fd7d-206">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="3fd7d-207">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="3fd7d-207">Assign policies to your users in Teams</span></span>](assign-policies.md)
