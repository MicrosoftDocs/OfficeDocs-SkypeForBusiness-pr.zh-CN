---
title: 在 Microsoft 团队管理中心中管理你的应用
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 了解如何在 Microsoft 团队管理中心的 "管理应用" 页面上管理团队应用
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: bd793cc4ec6cbd27180e3babeb69c7fdc5e98ce4
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042924"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e74b6-103">在 Microsoft 团队管理中心中管理你的应用</span><span class="sxs-lookup"><span data-stu-id="e74b6-103">Manage your apps in the Microsoft Teams admin center</span></span>
======================================================

<span data-ttu-id="e74b6-104">作为管理员，Microsoft 团队管理中心中的 "**管理应用**" 页面是你在组织的应用程序目录中查看和管理所有团队应用的位置。</span><span class="sxs-lookup"><span data-stu-id="e74b6-104">As an admin, the **Manage apps** page in the Microsoft Teams admin center is where you view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="e74b6-105">在此处，你可以查看应用的组织级别状态和属性，将新的自定义应用上载到租户应用目录、阻止或允许组织级别的应用，以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="e74b6-105">Here, you can see the org-level status and properties of apps, upload new custom apps to your tenant app catalog, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="e74b6-106">"**管理应用**" 页面为你提供租户目录中所有可用应用的视图，为你提供了确定要在组织中允许或阻止哪些应用的信息。</span><span class="sxs-lookup"><span data-stu-id="e74b6-106">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="e74b6-107">然后，你可以使用[应用权限策略](teams-app-permission-policies.md)、[应用设置策略](teams-app-setup-policies.md)和[自定义应用策略和设置](teams-custom-app-policies-and-settings.md)来为你的组织中的特定用户配置应用体验。</span><span class="sxs-lookup"><span data-stu-id="e74b6-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="e74b6-108">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="e74b6-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="e74b6-109">您必须是全局管理员或团队服务管理员才能访问该页面。</span><span class="sxs-lookup"><span data-stu-id="e74b6-109">You must be a global admin or Teams service admin to access the page.</span></span>

## <a name="view-apps-in-your-tenant-app-catalog"></a><span data-ttu-id="e74b6-110">查看租户应用程序目录中的应用</span><span class="sxs-lookup"><span data-stu-id="e74b6-110">View apps in your tenant app catalog</span></span>

<span data-ttu-id="e74b6-111">你可以查看租户应用目录中的每个应用，包括有关每个应用的以下信息。</span><span class="sxs-lookup"><span data-stu-id="e74b6-111">You can view every app in your tenant app catalog including the following information about each app.</span></span>

!["托管应用" 页面的屏幕截图](media/manage-apps.png)

- <span data-ttu-id="e74b6-113">**名称**：应用名称。</span><span class="sxs-lookup"><span data-stu-id="e74b6-113">**Name**: The app name.</span></span> <span data-ttu-id="e74b6-114">单击应用名称以查看有关应用的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e74b6-114">Click the app name to see more information about the app.</span></span> <span data-ttu-id="e74b6-115">其中包括应用的说明，无论它是允许还是阻止、应用于应用的版本、认证状态、支持的功能和应用 ID。</span><span class="sxs-lookup"><span data-stu-id="e74b6-115">This includes a description of the app, whether it's allowed or blocked, version, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="e74b6-116">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="e74b6-116">Here's an example:</span></span><br><span data-ttu-id="e74b6-117"> 
![应用的 "应用详细信息" 页面的屏幕截图](media/manage-apps-app-details.png)</span><span class="sxs-lookup"><span data-stu-id="e74b6-117"> 
![Screenshot of the apps details page for an app](media/manage-apps-app-details.png)</span></span>
- <span data-ttu-id="e74b6-118">**认证**：如果应用已通过认证，你将看到**Microsoft 365 认证**或**发布商证明**。</span><span class="sxs-lookup"><span data-stu-id="e74b6-118">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="e74b6-119">单击链接以查看应用的认证详细信息。</span><span class="sxs-lookup"><span data-stu-id="e74b6-119">Click the link to view certification details for the app.</span></span> <span data-ttu-id="e74b6-120">如果你看到 " **--** "，则表示没有适用于该应用的认证信息。</span><span class="sxs-lookup"><span data-stu-id="e74b6-120">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="e74b6-121">若要了解有关团队中已认证应用的详细信息，请参阅[Microsoft 365 应用认证计划](https://docs.microsoft.com/teams-app-certification/all-apps)。</span><span class="sxs-lookup"><span data-stu-id="e74b6-121">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](https://docs.microsoft.com/teams-app-certification/all-apps).</span></span>  
- <span data-ttu-id="e74b6-122">**类别**：应用于应用的类别。</span><span class="sxs-lookup"><span data-stu-id="e74b6-122">**Categories**: Categories that apply to the app.</span></span>
- <span data-ttu-id="e74b6-123">**应用状态**： "组织" 级别的应用状态，可为下列之一：</span><span class="sxs-lookup"><span data-stu-id="e74b6-123">**App status**: Status of the app at the org level, which can be one of the following:</span></span>
    - <span data-ttu-id="e74b6-124">**允许**：应用可用于你的组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="e74b6-124">**Allowed**: The app is available for all users in your organization.</span></span>
    - <span data-ttu-id="e74b6-125">已**阻止**：应用被阻止，不能用于你的组织中的任何用户。</span><span class="sxs-lookup"><span data-stu-id="e74b6-125">**Blocked**: The app is blocked and not available for any users in your organization.</span></span>
    - <span data-ttu-id="e74b6-126">**被阻止的组织范围**：应用在组织范围内的应用设置中被阻止。</span><span class="sxs-lookup"><span data-stu-id="e74b6-126">**Blocked org-wide**: The app is blocked in org-wide app settings.</span></span> <br>
<span data-ttu-id="e74b6-127">请务必了解，此列表示以前位于**组织范围设置**窗格中的应用的 "允许" 和 "已阻止" 状态。</span><span class="sxs-lookup"><span data-stu-id="e74b6-127">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="e74b6-128">现在，你可以在 "**管理应用**" 页面上的组织范围内查看、阻止和允许应用。</span><span class="sxs-lookup"><span data-stu-id="e74b6-128">You now view, block, and allow apps at the org-wide on the **Manage apps** page.</span></span> 
- <span data-ttu-id="e74b6-129">**版本**：应用版本。</span><span class="sxs-lookup"><span data-stu-id="e74b6-129">**Version**: App version.</span></span>

<span data-ttu-id="e74b6-130">若要查看表中所需的信息，请单击右上角的 "**编辑列**" 以在表中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="e74b6-130">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="upload-a-new-app"></a><span data-ttu-id="e74b6-131">上载新应用程序</span><span class="sxs-lookup"><span data-stu-id="e74b6-131">Upload a new app</span></span>

<span data-ttu-id="e74b6-132">你可以使用你的应用程序目录来测试和分发专为你的组织构建的自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="e74b6-132">You can use your app catalog to test and distribute custom applications that are built specifically for your organization.</span></span> <span data-ttu-id="e74b6-133">团队应用包是使用[团队应用 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建的。</span><span class="sxs-lookup"><span data-stu-id="e74b6-133">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="e74b6-134">当你有应用包时，你可以将其添加到你的应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="e74b6-134">When you have the app package, you can add it to the your app catalog.</span></span> <span data-ttu-id="e74b6-135">虽然组织中的所有用户都可以查看应用程序目录，但只有全局管理员和团队服务管理员可以发布和管理它。</span><span class="sxs-lookup"><span data-stu-id="e74b6-135">While all users in your organization can view the app catalog, only global admins and Teams service admins can publish and manage it.</span></span>

<span data-ttu-id="e74b6-136">若要将新的自定义应用上载到租户应用目录，请单击 "**上传新应用**" 以将你的应用包上载为 .zip 格式。</span><span class="sxs-lookup"><span data-stu-id="e74b6-136">To upload a new custom app to your tenant app catalog, click **Upload new app** to upload your app package in .zip format.</span></span> <span data-ttu-id="e74b6-137">应用在上载后不会突出显示，因此你需要搜索你的应用目录才能找到它。</span><span class="sxs-lookup"><span data-stu-id="e74b6-137">The app isn't highlighted after it's uploaded so you'll need to search your app catalog to find it.</span></span>

<span data-ttu-id="e74b6-138">若要在上载应用后更新该应用，请在 "**管理应用**" 页面上的应用列表中单击应用名称，然后单击 "**更新**"。</span><span class="sxs-lookup"><span data-stu-id="e74b6-138">To update an app after it's uploaded, in the list of apps on the **Manage apps** page, click the app name, and then click **Update**.</span></span> <span data-ttu-id="e74b6-139">执行此操作将替换你的应用目录中的现有应用，并且所有应用权限策略和应用设置策略都将对已更新的应用保持强制。</span><span class="sxs-lookup"><span data-stu-id="e74b6-139">Doing this replaces the existing app in your app catalog and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="e74b6-140">若要了解详细信息，请参阅[管理团队中的自定义应用](manage-your-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="e74b6-140">To learn more, see [Manage your custom apps in Teams](manage-your-custom-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="e74b6-141">允许和阻止应用</span><span class="sxs-lookup"><span data-stu-id="e74b6-141">Allow and block apps</span></span>

<span data-ttu-id="e74b6-142">"**管理应用**" 页面是允许或阻止组织级别的单个应用的位置。</span><span class="sxs-lookup"><span data-stu-id="e74b6-142">The **Manage apps** page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="e74b6-143">它显示了每个可用的应用及其当前的组织级应用状态。</span><span class="sxs-lookup"><span data-stu-id="e74b6-143">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="e74b6-144">（阻止和允许组织级别的应用已从**组织范围内的应用设置**窗格移动到此处。）</span><span class="sxs-lookup"><span data-stu-id="e74b6-144">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="e74b6-145">若要允许或阻止某个应用，请将其选中，然后单击 "**允许**" 或 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="e74b6-145">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="e74b6-146">阻止应用时，将禁用与该应用的所有交互，并且该应用不会在团队中针对你的组织中的任何用户显示。</span><span class="sxs-lookup"><span data-stu-id="e74b6-146">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="e74b6-147">当你在 "**管理应用**" 页面上阻止或允许应用时，将阻止或允许组织中的所有用户使用该应用。</span><span class="sxs-lookup"><span data-stu-id="e74b6-147">When you block or allow an app on the **Manage apps** page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="e74b6-148">在团队应用权限策略中阻止或允许某个应用时，系统会阻止或允许分配该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="e74b6-148">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="e74b6-149">若要使用户能够安装任何应用并与之交互，你必须在 "管理应用" 页面上的 "**管理应用**" 页面上和分配给用户的应用权限策略中允许该应用。</span><span class="sxs-lookup"><span data-stu-id="e74b6-149">For a user to be able to install and interact with any app, you must allow the app at the org level on the **Manage apps** page and in the app permission policy that's assigned to the user.</span></span>

 > [!NOTE]
 > <span data-ttu-id="e74b6-150">若要卸载应用，请右键单击该应用，然后单击 "**卸载**" 或使用左侧面上的 "**更多应用**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="e74b6-150">To uninstall an app, right-click on the app and then click **Uninstall** or use the **More apps** menu on the lefthand side.</span></span> 

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="e74b6-151">管理组织范围内的应用设置</span><span class="sxs-lookup"><span data-stu-id="e74b6-151">Manage org-wide app settings</span></span>

<span data-ttu-id="e74b6-152">使用组织范围内的应用设置控制用户是否可以安装第三方应用以及用户是否可以上载或与你的组织中的自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="e74b6-152">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="e74b6-153">组织范围内的应用设置控制所有用户的行为，并替代分配给用户的任何其他应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="e74b6-153">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="e74b6-154">你可以使用它们控制恶意或有问题的应用。</span><span class="sxs-lookup"><span data-stu-id="e74b6-154">You can use them to control malicious or problematic apps.</span></span>

> [!NOTE]
> <span data-ttu-id="e74b6-155">"**管理应用**" 页面尚未在 Microsoft 365 政府版团队部署中可用。</span><span class="sxs-lookup"><span data-stu-id="e74b6-155">The **Manage apps** page isn't available yet in Microsoft 365 Government - GCC deployments of Teams.</span></span>  <span data-ttu-id="e74b6-156">若要了解如何使用组织范围内的应用设置来启用或禁用第三方应用，请参阅[管理团队中的应用权限策略](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e74b6-156">To learn how to use org-wide app settings to enable or disable third-party apps, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="e74b6-157">在 "**管理应用程序**" 页面上，选择 "**组织范围内的应用设置**"。</span><span class="sxs-lookup"><span data-stu-id="e74b6-157">On the **Manage apps** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="e74b6-158">然后，你可以在面板中配置所需的设置。</span><span class="sxs-lookup"><span data-stu-id="e74b6-158">You can then configure the settings you want in the panel.</span></span>

    ![组织范围内的应用设置的屏幕截图](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="e74b6-160">在 "**第三方应用**" 下，关闭或打开这些设置以控制对第三方应用的访问：</span><span class="sxs-lookup"><span data-stu-id="e74b6-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="e74b6-161">**允许第三方应用**：此操作控制用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="e74b6-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="e74b6-162">如果关闭此设置，你的用户将无法安装或使用任何第三方应用，并且这些应用的应用状态在表格中显示为**阻止的组织范围**。</span><span class="sxs-lookup"><span data-stu-id="e74b6-162">If you turn off this setting, your users won't be able to install or use any third-party apps and the app status of these apps is displayed as **Blocked org-wide** in the table.</span></span>

        <span data-ttu-id="e74b6-163">当 "**允许第三方应用**" 关闭时，将禁用[传出 webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ，这意味着用户无法创建它们。</span><span class="sxs-lookup"><span data-stu-id="e74b6-163">When **Allow third-party apps** is off, [outgoing webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are disabled, which means that users can't create them.</span></span> <span data-ttu-id="e74b6-164">当此设置处于打开状态时，将为所有用户启用传出 webhooks，无论用户是否在用户的应用权限策略中打开或关闭该设置。</span><span class="sxs-lookup"><span data-stu-id="e74b6-164">When this setting is on, outgoing webhooks are enabled for all users regardless of whether the setting is on or off in the users' app permission policy.</span></span>
    - <span data-ttu-id="e74b6-165">**默认情况下允许发布到应用商店的任何新第三方应用**：这将控制发布到团队应用商店的新的第三方应用是否会自动在团队中可用。</span><span class="sxs-lookup"><span data-stu-id="e74b6-165">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="e74b6-166">仅当你允许第三方应用时，你才能设置此选项。</span><span class="sxs-lookup"><span data-stu-id="e74b6-166">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="e74b6-167">在 "**自定义应用**" 下，关闭或打开 "**允许与自定义应用交互**"。</span><span class="sxs-lookup"><span data-stu-id="e74b6-167">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="e74b6-168">此设置控制用户是否可以与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="e74b6-168">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="e74b6-169">若要了解详细信息，请参阅[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="e74b6-169">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="e74b6-170">单击 "**保存**" 以使组织范围内的应用设置生效。</span><span class="sxs-lookup"><span data-stu-id="e74b6-170">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e74b6-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="e74b6-171">Related topics</span></span>

- [<span data-ttu-id="e74b6-172">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="e74b6-172">Admin settings for apps in Teams</span></span>](admin-settings.md)
