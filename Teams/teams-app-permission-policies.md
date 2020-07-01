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
ms.openlocfilehash: 83a06357402b44c5c15932211e562e488c2a2d5a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938471"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="1b0c8-103">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="1b0c8-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="1b0c8-104">作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="1b0c8-105">你可以允许或阻止由 Microsoft、第三方和你的组织发布的所有应用或特定应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="1b0c8-106">阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="1b0c8-107">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="1b0c8-108">你可以在 Microsoft 团队管理中心中管理应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1b0c8-109">你可以使用全局（组织范围默认）策略或创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="1b0c8-110">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="1b0c8-111">编辑或分配策略后，可能需要几个小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![应用权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="1b0c8-113">组织范围内的应用设置替代全局策略和你创建并分配给用户的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="1b0c8-114">如果您的组织已在团队中，则在 Microsoft 365 管理中心的**租户范围设置**中配置的应用设置将反映在 "[管理应用](manage-apps.md)程序" 页面上的组织范围内应用设置中。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="1b0c8-115">如果您不熟悉团队，并且只是开始使用，则默认情况下，所有应用都允许在全局策略中使用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="1b0c8-116">这包括由 Microsoft、第三方和你的组织发布的应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="1b0c8-117">例如，你希望阻止所有第三方应用，并允许 Microsoft 针对你的组织中的人力资源团队应用特定应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="1b0c8-118">首先，你将转到 "[管理应用](manage-apps.md)" 页面，并确保你希望为 HR 团队允许的应用在组织级别允许。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="1b0c8-119">然后，创建名为 HR App 权限策略的自定义策略，将其设置为阻止并允许你所需的应用，并将其分配给 HR 团队上的用户。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="1b0c8-120">如果你在 Microsoft 365 政府-GCC 环境中部署团队，请参阅适用于 gcc 的[应用权限策略](#app-permission-policies-for-gcc)，了解有关特定于 GCC 的第三方应用设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-120">If you deployed Teams in a Microsoft 365 Government - GCC environment, see [App permission policies for GCC](#app-permission-policies-for-gcc) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="1b0c8-121">创建自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="1b0c8-121">Create a custom app permission policy</span></span>

<span data-ttu-id="1b0c8-122">如果你希望控制组织中不同组用户可用的应用，请创建并分配一个或多个自定义应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="1b0c8-123">你可以基于 Microsoft、第三方或你的组织发布的应用创建和分配单独的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="1b0c8-124">请务必注意，在创建自定义策略后，如果在组织范围的应用设置中禁用了第三方应用，则无法更改它。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="1b0c8-125">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="1b0c8-126">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-126">Click **Add**.</span></span> <br>
    <span data-ttu-id="1b0c8-127">![新应用权限策略的屏幕截图](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="1b0c8-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="1b0c8-128">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="1b0c8-129">在 " **Microsoft 应用**"、"**第三方应用**" 和 "**自定义应用**" 下，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1b0c8-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="1b0c8-130">**允许所有应用**</span><span class="sxs-lookup"><span data-stu-id="1b0c8-130">**Allow all apps**</span></span>
    - <span data-ttu-id="1b0c8-131">**允许特定应用和阻止所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="1b0c8-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="1b0c8-132">**阻止特定应用并允许所有其他应用**</span><span class="sxs-lookup"><span data-stu-id="1b0c8-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="1b0c8-133">**阻止所有应用**</span><span class="sxs-lookup"><span data-stu-id="1b0c8-133">**Block all apps**</span></span>

5. <span data-ttu-id="1b0c8-134">如果你选择 "**允许特定应用" 并阻止其他应用**，请添加你希望允许的应用：</span><span class="sxs-lookup"><span data-stu-id="1b0c8-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="1b0c8-135">选择 "**允许应用**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="1b0c8-136">搜索要允许的应用，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="1b0c8-137">搜索结果将筛选到应用发布者（**Microsoft 应用**、**第三方应用**或**自定义应用**）。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="1b0c8-138">选择应用列表后，单击 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="1b0c8-139">同样，如果你选择 "**阻止特定应用" 并允许所有其他应用**，请搜索并添加要阻止的应用，然后单击 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="1b0c8-140">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="1b0c8-141">编辑应用权限策略</span><span class="sxs-lookup"><span data-stu-id="1b0c8-141">Edit an app permission policy</span></span>

<span data-ttu-id="1b0c8-142">你可以使用 Microsoft 团队管理中心编辑策略，包括全局策略和你创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="1b0c8-143">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="1b0c8-144">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="1b0c8-145">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-145">From here, make the changes that you want.</span></span> <span data-ttu-id="1b0c8-146">你可以基于应用发布者管理设置，并根据 "允许/阻止" 设置添加和删除应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="1b0c8-147">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="1b0c8-148">向用户分配自定义应用权限策略</span><span class="sxs-lookup"><span data-stu-id="1b0c8-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="app-permission-policies-for-gcc"></a><span data-ttu-id="1b0c8-149">适用于 GCC 的应用权限策略</span><span class="sxs-lookup"><span data-stu-id="1b0c8-149">App permission policies for GCC</span></span>

<span data-ttu-id="1b0c8-150">在 Microsoft 365 政府版团队部署中，请务必了解以下有关适用于 GCC 的第三方应用设置的信息。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-150">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="1b0c8-151">在 GCC 中，默认情况下将阻止所有第三方应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-151">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="1b0c8-152">此外，在 Microsoft 团队管理中心的 "应用权限策略" 页面上，你将看到以下有关管理第三方应用的说明。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC 中的应用权限策略的屏幕截图](media/app-permission-policies-gcc.png)

<span data-ttu-id="1b0c8-154">若要为你的组织中的一个用户或一组用户启用第三方应用，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1b0c8-154">To enable a third-party app for a user or a set of users in your organization, do the following:</span></span>

1. <span data-ttu-id="1b0c8-155">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"，然后在应用列表中，确认要为一组用户允许的第三方应用是否设置为 "在组织级别**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then in the list of apps, confirm that the third-party app that you want to allow for a set of users is set to **Blocked** at the org level.</span></span>

2. <span data-ttu-id="1b0c8-156">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **权限策略**"，然后编辑全局策略以阻止第三方应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-156">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**, and then edit the global policy to block the third-party app.</span></span> <span data-ttu-id="1b0c8-157">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="1b0c8-157">To do this:</span></span>
    1. <span data-ttu-id="1b0c8-158">在 "应用权限策略" 页面上，单击 "**全局（组织范围默认）**"，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-158">On the App permission policies page, click **Global (Org-wide default)**, and then click **Edit**.</span></span>
    2. <span data-ttu-id="1b0c8-159">在 "**第三方应用**" 下，选择 "**阻止特定应用并允许所有其他**应用"，添加应用，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-159">Under **Third-party apps**, select **Block specific apps and allow all others**, add the app, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1b0c8-160">请务必先执行此操作，然后再转到下一步，以便在组织级别允许应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-160">It's important to do this before you go to the next step to allow the app at the org level.</span></span> <span data-ttu-id="1b0c8-161">这是因为如果在全局应用权限策略中未阻止第三方应用，则全局策略适用的所有用户都可以在组织级别允许访问第三方应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-161">This is because if the third-party app isn't blocked in the global app permission policy, all users that the global policy applies to will be able to access the third-party app when you allow it at the org level.</span></span>

3. <span data-ttu-id="1b0c8-162">允许在组织级别的第三方应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-162">Allow the third-party app at the org level.</span></span> <span data-ttu-id="1b0c8-163">若要执行此操作，请在左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-163">To do this, in the left navigation, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="1b0c8-164">在应用列表中，单击应用名称的左侧以选择应用，然后选择 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-164">In the list of apps, click to the left of the app name to select the app, and then select **Allow**.</span></span>
4. <span data-ttu-id="1b0c8-165">[创建自定义应用权限策略](#create-a-custom-app-permission-policy)以允许应用，然后[将策略分配](#assign-a-custom-app-permission-policy-to-users)给所需的用户。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-165">[Create a custom app permission policy](#create-a-custom-app-permission-policy) to allow the app, and then [assign the policy](#assign-a-custom-app-permission-policy-to-users) to the users you want.</span></span>

## <a name="faq"></a><span data-ttu-id="1b0c8-166">常见问题</span><span class="sxs-lookup"><span data-stu-id="1b0c8-166">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="1b0c8-167">使用应用权限策略</span><span class="sxs-lookup"><span data-stu-id="1b0c8-167">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="1b0c8-168">权限策略影响的应用交互是什么？</span><span class="sxs-lookup"><span data-stu-id="1b0c8-168">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="1b0c8-169">权限策略通过控制最终用户的安装、发现和交互来控制应用的使用情况。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-169">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="1b0c8-170">管理员仍然可以管理 Microsoft 团队管理中心中的应用，而不管分配给他们的权限策略如何。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-170">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="1b0c8-171">是否可以控制业务线（LOB）应用？</span><span class="sxs-lookup"><span data-stu-id="1b0c8-171">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="1b0c8-172">是的，你可以使用应用权限策略控制自定义（LOB）应用的推出和分发。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-172">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="1b0c8-173">你可以创建自定义策略或编辑全局策略，以根据你的组织的需要允许或阻止自定义应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-173">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="1b0c8-174">应用权限策略与已固定的应用和应用设置策略有何关系？</span><span class="sxs-lookup"><span data-stu-id="1b0c8-174">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="1b0c8-175">你可以将应用设置策略与应用权限策略结合使用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-175">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="1b0c8-176">已从用户的已启用应用集中选择预固定的应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-176">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="1b0c8-177">此外，如果用户具有在应用设置策略中阻止应用的应用权限策略，则该应用不会显示在团队中。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-177">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="1b0c8-178">是否可以使用应用权限策略来限制上载自定义应用程序？</span><span class="sxs-lookup"><span data-stu-id="1b0c8-178">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="1b0c8-179">你可以在 "**管理应用**" 页面上使用组织范围内的设置，或使用应用设置策略来限制为你的组织上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-179">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="1b0c8-180">若要限制特定用户上载自定义应用程序，请使用自定义应用策略。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-180">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="1b0c8-181">若要了解详细信息，请参阅[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-181">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="1b0c8-182">阻止应用是否会应用到团队移动客户端？</span><span class="sxs-lookup"><span data-stu-id="1b0c8-182">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="1b0c8-183">是的，当你阻止应用时，将阻止所有团队客户端上的应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-183">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="1b0c8-184">用户体验</span><span class="sxs-lookup"><span data-stu-id="1b0c8-184">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="1b0c8-185">应用被阻止时的用户体验？</span><span class="sxs-lookup"><span data-stu-id="1b0c8-185">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="1b0c8-186">用户无法与已阻止的应用或其功能（如 bot、选项卡和消息传递扩展）交互。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-186">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="1b0c8-187">在共享上下文（如团队或群组聊天）中，机器人仍可向该上下文的所有参与者发送消息。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-187">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="1b0c8-188">团队在应用被阻止时向用户显示。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-188">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="1b0c8-189">例如，当应用被阻止时，用户不能执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="1b0c8-189">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="1b0c8-190">将应用程序个人或聊天添加到聊天或团队</span><span class="sxs-lookup"><span data-stu-id="1b0c8-190">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="1b0c8-191">将消息发送到应用的 bot</span><span class="sxs-lookup"><span data-stu-id="1b0c8-191">Send messages to the app’s bot</span></span>
- <span data-ttu-id="1b0c8-192">执行将信息发送回应用的按钮操作，例如可操作的消息</span><span class="sxs-lookup"><span data-stu-id="1b0c8-192">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="1b0c8-193">查看应用的选项卡</span><span class="sxs-lookup"><span data-stu-id="1b0c8-193">View the app’s tab</span></span>
- <span data-ttu-id="1b0c8-194">设置连接器以接收通知</span><span class="sxs-lookup"><span data-stu-id="1b0c8-194">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="1b0c8-195">使用应用的消息扩展</span><span class="sxs-lookup"><span data-stu-id="1b0c8-195">Use the app’s messaging extension</span></span>

<span data-ttu-id="1b0c8-196">旧版门户允许在组织级别控制应用，这意味着当应用被阻止时，组织中的所有用户都将阻止该应用。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-196">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="1b0c8-197">在 "[管理应用程序](manage-apps.md)" 页面上阻止应用的工作方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-197">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="1b0c8-198">对于分配给特定用户的应用权限策略，如果允许使用支持机器人或连接器功能的应用，并且该应用仅允许共享上下文中的某些用户，则不具有该应用权限的组聊天或频道的成员可以查看由 bot 或连接器发布的邮件历史记录和消息，但无法与之交互。</span><span class="sxs-lookup"><span data-stu-id="1b0c8-198">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1b0c8-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="1b0c8-199">Related topics</span></span>

[<span data-ttu-id="1b0c8-200">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="1b0c8-200">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="1b0c8-201">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="1b0c8-201">Assign policies to your users in Teams</span></span>](assign-policies.md)
