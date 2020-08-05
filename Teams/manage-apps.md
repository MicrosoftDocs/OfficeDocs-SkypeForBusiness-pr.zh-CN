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
ms.openlocfilehash: ecc03ff6a6baf1333028b949b590f3018d66e393
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552311"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="ae05a-103">在 Microsoft 团队管理中心中管理你的应用</span><span class="sxs-lookup"><span data-stu-id="ae05a-103">Manage your apps in the Microsoft Teams admin center</span></span>
======================================================

<span data-ttu-id="ae05a-104">作为管理员，Microsoft 团队管理中心中的 "管理应用" 页面是你查看和管理你的组织的所有团队应用的位置。</span><span class="sxs-lookup"><span data-stu-id="ae05a-104">As an admin, the Manage apps page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="ae05a-105">在此处，你可以查看应用的组织级别状态和属性、批准或将新的自定义应用上载到你的组织的应用商店、阻止或允许组织级别的应用，以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="ae05a-105">Here, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="ae05a-106">"管理应用" 页面提供了所有可用应用的视图，为你提供了确定要在组织中允许或阻止哪些应用的信息。</span><span class="sxs-lookup"><span data-stu-id="ae05a-106">The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="ae05a-107">然后，你可以使用[应用权限策略](teams-app-permission-policies.md)、[应用设置策略](teams-app-setup-policies.md)和[自定义应用策略和设置](teams-custom-app-policies-and-settings.md)来为你的组织中的特定用户配置应用体验。</span><span class="sxs-lookup"><span data-stu-id="ae05a-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="ae05a-108">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="ae05a-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="ae05a-109">您必须是全局管理员或团队服务管理员才能访问该页面。</span><span class="sxs-lookup"><span data-stu-id="ae05a-109">You must be a global admin or Teams service admin to access the page.</span></span>

> [!NOTE]
> <span data-ttu-id="ae05a-110">"管理应用" 页面在 Microsoft 365 政府社区中尚不可用 (GCC) 团队部署。</span><span class="sxs-lookup"><span data-stu-id="ae05a-110">The Manage apps page isn't available yet in Microsoft 365 Government Community Cloud (GCC) deployments of Teams.</span></span>

## <a name="view-apps"></a><span data-ttu-id="ae05a-111">查看应用</span><span class="sxs-lookup"><span data-stu-id="ae05a-111">View apps</span></span>

<span data-ttu-id="ae05a-112">你可以查看每个应用，包括有关每个应用的以下信息。</span><span class="sxs-lookup"><span data-stu-id="ae05a-112">You can view every app including the following information about each app.</span></span>

!["托管应用" 页面的屏幕截图](media/manage-apps.png)

- <span data-ttu-id="ae05a-114">**名称**：应用名称。</span><span class="sxs-lookup"><span data-stu-id="ae05a-114">**Name**: The app name.</span></span> <span data-ttu-id="ae05a-115">单击应用名称以查看有关应用的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ae05a-115">Click the app name to see more information about the app.</span></span> <span data-ttu-id="ae05a-116">其中包括应用的说明，无论它是允许还是阻止、应用于应用的版本、认证状态、支持的功能和应用 ID。</span><span class="sxs-lookup"><span data-stu-id="ae05a-116">This includes a description of the app, whether it's allowed or blocked, version, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="ae05a-117">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="ae05a-117">Here's an example:</span></span>

  ![应用的 "应用详细信息" 页面的屏幕截图](media/manage-apps-app-details.png)
  
- <span data-ttu-id="ae05a-119">**认证**：如果应用已通过认证，你将看到**Microsoft 365 认证**或**发布商证明**。</span><span class="sxs-lookup"><span data-stu-id="ae05a-119">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="ae05a-120">单击链接以查看应用的认证详细信息。</span><span class="sxs-lookup"><span data-stu-id="ae05a-120">Click the link to view certification details for the app.</span></span> <span data-ttu-id="ae05a-121">如果你看到 " **--** "，则表示没有适用于该应用的认证信息。</span><span class="sxs-lookup"><span data-stu-id="ae05a-121">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="ae05a-122">若要了解有关团队中已认证应用的详细信息，请参阅[Microsoft 365 应用认证计划](https://docs.microsoft.com/teams-app-certification/all-apps)。</span><span class="sxs-lookup"><span data-stu-id="ae05a-122">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](https://docs.microsoft.com/teams-app-certification/all-apps).</span></span>  

- <span data-ttu-id="ae05a-123">**Publisher**：发布者的名称。</span><span class="sxs-lookup"><span data-stu-id="ae05a-123">**Publisher**: Name of the publisher.</span></span>
- <span data-ttu-id="ae05a-124">**发布状态**：自定义应用的发布状态。</span><span class="sxs-lookup"><span data-stu-id="ae05a-124">**Publishing status**: Publishing status of custom apps.</span></span>
- <span data-ttu-id="ae05a-125">**状态**： "组织" 级别的应用状态，可为下列之一：</span><span class="sxs-lookup"><span data-stu-id="ae05a-125">**Status**: Status of the app at the org level, which can be one of the following:</span></span>

    - <span data-ttu-id="ae05a-126">**允许**：应用可用于你的组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="ae05a-126">**Allowed**: The app is available for all users in your organization.</span></span>
    
    - <span data-ttu-id="ae05a-127">已**阻止**：应用被阻止，不能用于你的组织中的任何用户。</span><span class="sxs-lookup"><span data-stu-id="ae05a-127">**Blocked**: The app is blocked and not available for any users in your organization.</span></span>
    
    - <span data-ttu-id="ae05a-128">**被阻止的组织范围**：应用在组织范围内的应用设置中被阻止。</span><span class="sxs-lookup"><span data-stu-id="ae05a-128">**Blocked org-wide**: The app is blocked in org-wide app settings.</span></span>
    
      <span data-ttu-id="ae05a-129">请务必了解，此列表示以前位于**组织范围设置**窗格中的应用的 "允许" 和 "已阻止" 状态。</span><span class="sxs-lookup"><span data-stu-id="ae05a-129">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="ae05a-130">现在，你可以在 "管理应用" 页面上的组织范围内查看、阻止和允许应用。</span><span class="sxs-lookup"><span data-stu-id="ae05a-130">You now view, block, and allow apps at the org-wide on the Manage apps page.</span></span>

- <span data-ttu-id="ae05a-131">**自定义应用**：应用是否为自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="ae05a-131">**Custom app**: Whether the app is a custom app.</span></span>

- <span data-ttu-id="ae05a-132">**类别**：应用于应用的类别。</span><span class="sxs-lookup"><span data-stu-id="ae05a-132">**Categories**: Categories that apply to the app.</span></span>

- <span data-ttu-id="ae05a-133">**版本**：应用版本。</span><span class="sxs-lookup"><span data-stu-id="ae05a-133">**Version**: App version.</span></span>

<span data-ttu-id="ae05a-134">若要查看表中所需的信息，请单击右上角的 "**编辑列**" 以在表中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="ae05a-134">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a><span data-ttu-id="ae05a-135">将自定义应用程序发布到组织的应用商店</span><span class="sxs-lookup"><span data-stu-id="ae05a-135">Publish a custom app to your organization's app store</span></span>

<span data-ttu-id="ae05a-136">使用 "管理应用程序" 页面可发布专为你的组织构建的应用。</span><span class="sxs-lookup"><span data-stu-id="ae05a-136">Use the Manage apps page to publish apps that are built specifically for your organization.</span></span> <span data-ttu-id="ae05a-137">发布自定义应用程序后，用户可以在组织的应用商店中使用它。</span><span class="sxs-lookup"><span data-stu-id="ae05a-137">After you publish a custom app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="ae05a-138">可通过两种方式将自定义应用程序发布到组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="ae05a-138">There are two ways to publish a custom app to your organization's app store.</span></span> <span data-ttu-id="ae05a-139">使用方式取决于获取应用的方式。</span><span class="sxs-lookup"><span data-stu-id="ae05a-139">The way that you use depends on how you get the app.</span></span>

- <span data-ttu-id="ae05a-140">[批准自定义应用](#approve-a-custom-app)：如果开发人员使用团队应用提交 API 将应用直接提交到 "管理应用程序" 页面，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="ae05a-140">[Approve a custom app](#approve-a-custom-app): Use this method if the developer submits the app directly to the Manage apps page using the Teams App Submission API.</span></span> <span data-ttu-id="ae05a-141">然后，你可以直接从应用详细信息页面中查看和发布 (或拒绝) 应用。</span><span class="sxs-lookup"><span data-stu-id="ae05a-141">You can then review and publish (or reject) the app directly from the app details page.</span></span>
- <span data-ttu-id="ae05a-142">[上载应用包](#upload-an-app-package)：如果开发人员以 .zip 格式发送应用包，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="ae05a-142">[Upload an app package](#upload-an-app-package): Use this method if the developer sends you the app package in .zip format.</span></span> <span data-ttu-id="ae05a-143">通过上载应用包来发布应用。</span><span class="sxs-lookup"><span data-stu-id="ae05a-143">You publish the app by uploading the app package.</span></span>

###  <a name="approve-a-custom-app"></a><span data-ttu-id="ae05a-144">批准自定义应用程序</span><span class="sxs-lookup"><span data-stu-id="ae05a-144">Approve a custom app</span></span>

<span data-ttu-id="ae05a-145">当开发人员使用团队应用提交 API 提交应用时，"管理应用" 页面上的 "**待定审批**" 小组件将通知你。</span><span class="sxs-lookup"><span data-stu-id="ae05a-145">The **Pending approvals** widget on the Manage apps page notifies you when a developer submits an app by using the Teams App Submission API.</span></span> <span data-ttu-id="ae05a-146">将列出新提交的应用，其中包含已**提交**的**发布状态**和已**阻止**的**状态**。</span><span class="sxs-lookup"><span data-stu-id="ae05a-146">A newly submitted app is listed with a **Publishing status** of **Submitted** and an **Status** of **Blocked**.</span></span> <span data-ttu-id="ae05a-147">转到应用程序详细信息页面以查看有关该应用的详细信息，然后将其发布，将**发布状态**设置为 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="ae05a-147">Go to the app details page to see more information about the app, and then to publish it, set **Publishing status** to **Publish**.</span></span>

<span data-ttu-id="ae05a-148">当开发人员提交自定义应用程序的更新时，也会收到通知。</span><span class="sxs-lookup"><span data-stu-id="ae05a-148">You're also notified when a developer submits an update to a custom app.</span></span> <span data-ttu-id="ae05a-149">然后，你可以在应用详细信息页面上查看和发布 (或拒绝) 更新。</span><span class="sxs-lookup"><span data-stu-id="ae05a-149">You can then review and publish (or reject) the update on the app details page.</span></span> <span data-ttu-id="ae05a-150">所有应用权限策略和应用设置策略对于更新的应用均保持强制实施。</span><span class="sxs-lookup"><span data-stu-id="ae05a-150">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="ae05a-151">若要了解详细信息，请参阅[发布通过团队应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="ae05a-151">To learn more, see [Publish a custom app submitted through the Teams App Submission API](submit-approve-custom-apps.md).</span></span>

### <a name="upload-an-app-package"></a><span data-ttu-id="ae05a-152">上载应用包</span><span class="sxs-lookup"><span data-stu-id="ae05a-152">Upload an app package</span></span>

<span data-ttu-id="ae05a-153">开发人员使用[团队应用 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建团队应用包，然后以 .zip 格式将其发送给您。</span><span class="sxs-lookup"><span data-stu-id="ae05a-153">The developer creates a Teams app package using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio), and then sends it to you in .zip format.</span></span> <span data-ttu-id="ae05a-154">当你有应用包时，你可以将其上传到你的组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="ae05a-154">When you have the app package, you can upload it to your organization's app store.</span></span>

<span data-ttu-id="ae05a-155">若要上传新的自定义应用程序，请选择 "**上载**" 以上载应用包。</span><span class="sxs-lookup"><span data-stu-id="ae05a-155">To upload a new custom app, select **Upload** to upload the app package.</span></span> <span data-ttu-id="ae05a-156">应用在上载后不会突出显示，因此你需要在 "管理应用" 页面上搜索应用列表以查找它。</span><span class="sxs-lookup"><span data-stu-id="ae05a-156">The app isn't highlighted after it's uploaded so you'll need to search the list of apps on the Manage apps page to find it.</span></span>

<span data-ttu-id="ae05a-157">若要在上载应用后更新该应用，请在 "管理应用" 页面上的应用列表中单击应用名称，然后单击 "**更新**"。</span><span class="sxs-lookup"><span data-stu-id="ae05a-157">To update an app after it's uploaded, in the list of apps on the Manage apps page, click the app name, and then click **Update**.</span></span> <span data-ttu-id="ae05a-158">执行此操作将替换已更新的应用的现有应用和所有应用权限策略以及应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="ae05a-158">Doing this replaces the existing app and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="ae05a-159">若要了解详细信息，请参阅[通过上载应用包来发布自定义应用](upload-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="ae05a-159">To learn more, see [Publish a custom app by uploading an app package](upload-custom-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="ae05a-160">允许和阻止应用</span><span class="sxs-lookup"><span data-stu-id="ae05a-160">Allow and block apps</span></span>

<span data-ttu-id="ae05a-161">"管理应用" 页面是允许或阻止组织级别的单个应用的位置。</span><span class="sxs-lookup"><span data-stu-id="ae05a-161">The Manage apps page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="ae05a-162">它显示了每个可用的应用及其当前的组织级应用状态。</span><span class="sxs-lookup"><span data-stu-id="ae05a-162">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="ae05a-163">" (阻止" 和 "允许组织级别的应用" 已从 "**组织范围内的应用设置**" 窗格移动到此处。 ) </span><span class="sxs-lookup"><span data-stu-id="ae05a-163">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="ae05a-164">若要允许或阻止某个应用，请将其选中，然后单击 "**允许**" 或 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="ae05a-164">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="ae05a-165">阻止应用时，将禁用与该应用的所有交互，并且该应用不会在团队中针对你的组织中的任何用户显示。</span><span class="sxs-lookup"><span data-stu-id="ae05a-165">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="ae05a-166">当你在 "管理应用" 页面上阻止或允许应用时，将阻止或允许组织中的所有用户使用该应用。</span><span class="sxs-lookup"><span data-stu-id="ae05a-166">When you block or allow an app on the Manage apps page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="ae05a-167">在团队应用权限策略中阻止或允许某个应用时，系统会阻止或允许分配该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="ae05a-167">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="ae05a-168">若要使用户能够安装任何应用并与之交互，你必须在 "管理应用" 页面上的 "管理应用" 页面上和分配给用户的应用权限策略中允许该应用。</span><span class="sxs-lookup"><span data-stu-id="ae05a-168">For a user to be able to install and interact with any app, you must allow the app at the org level on the Manage apps page and in the app permission policy that's assigned to the user.</span></span>

 > [!NOTE]
 > <span data-ttu-id="ae05a-169">若要卸载应用，请右键单击该应用，然后单击左侧的 "**卸载**" 或 "使用**更多应用程序**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="ae05a-169">To uninstall an app, right-click the app, and then click **Uninstall** or use the **More apps** menu on the left side.</span></span> 

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="ae05a-170">管理组织范围内的应用设置</span><span class="sxs-lookup"><span data-stu-id="ae05a-170">Manage org-wide app settings</span></span>

<span data-ttu-id="ae05a-171">使用组织范围内的应用设置控制用户是否可以安装第三方应用以及用户是否可以上载或与你的组织中的自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="ae05a-171">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="ae05a-172">组织范围内的应用设置控制所有用户的行为，并替代分配给用户的任何其他应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="ae05a-172">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="ae05a-173">你可以使用它们控制恶意或有问题的应用。</span><span class="sxs-lookup"><span data-stu-id="ae05a-173">You can use them to control malicious or problematic apps.</span></span>

> [!NOTE]
> <span data-ttu-id="ae05a-174">若要了解如何在 Microsoft 365 政府版团队部署中使用组织范围内的应用设置，请参阅[管理团队中的应用权限策略](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ae05a-174">To learn how to use org-wide app settings in Microsoft 365 Government - GCC deployments of Teams, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="ae05a-175">在 "管理应用程序" 页面上，选择 "**组织范围内的应用设置**"。</span><span class="sxs-lookup"><span data-stu-id="ae05a-175">On the Manage apps page, select **Org-wide app settings**.</span></span> <span data-ttu-id="ae05a-176">然后，你可以在面板中配置所需的设置。</span><span class="sxs-lookup"><span data-stu-id="ae05a-176">You can then configure the settings you want in the panel.</span></span>

    ![组织范围内的应用设置的屏幕截图](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="ae05a-178">在 "**第三方应用**" 下，关闭或打开这些设置以控制对第三方应用的访问：</span><span class="sxs-lookup"><span data-stu-id="ae05a-178">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="ae05a-179">**允许第三方应用**：此操作控制用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="ae05a-179">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="ae05a-180">如果关闭此设置，你的用户将无法安装或使用任何第三方应用，并且这些应用的应用状态在表格中显示为**阻止的组织范围**。</span><span class="sxs-lookup"><span data-stu-id="ae05a-180">If you turn off this setting, your users won't be able to install or use any third-party apps and the app status of these apps is displayed as **Blocked org-wide** in the table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="ae05a-181">当 "**允许第三方应用**" 关闭时，将禁用[传出 webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ，这意味着用户无法创建它们。</span><span class="sxs-lookup"><span data-stu-id="ae05a-181">When **Allow third-party apps** is off, [outgoing webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are disabled, which means that users can't create them.</span></span> <span data-ttu-id="ae05a-182">当此设置为 on 时，将为所有用户启用传出 webhooks，你可以通过[应用权限策略](teams-app-permission-policies.md)允许或阻止传出 Webhook 应用，在用户级别控制它们。</span><span class="sxs-lookup"><span data-stu-id="ae05a-182">When this setting is on, outgoing webhooks are enabled for all users and you can control them at the user level by allowing or blocking the Outgoing Webhook app through [app permission policies](teams-app-permission-policies.md).</span></span> <br><br><span data-ttu-id="ae05a-183">请注意，如果你具有适用于使用 "**允许特定应用" 和 "阻止所有其他应用**" 设置的**Microsoft 应用**的现有[应用权限策略](teams-app-permission-policies.md)，并且你希望为用户启用传出的 webhooks，请将传出 Webhook 应用添加到列表。</span><span class="sxs-lookup"><span data-stu-id="ae05a-183">Note that if you have existing [app permission policies](teams-app-permission-policies.md) for **Microsoft apps** that use the **Allow specific apps and block all others** setting, and you want to enable outgoing webhooks for users, add the Outgoing Webhook app to the list.</span></span>
    - <span data-ttu-id="ae05a-184">**默认情况下允许发布到应用商店的任何新第三方应用**：这将控制发布到团队应用商店的新的第三方应用是否会自动在团队中可用。</span><span class="sxs-lookup"><span data-stu-id="ae05a-184">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="ae05a-185">仅当你允许第三方应用时，你才能设置此选项。</span><span class="sxs-lookup"><span data-stu-id="ae05a-185">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="ae05a-186">在 "**自定义应用**" 下，关闭或打开 "**允许与自定义应用交互**"。</span><span class="sxs-lookup"><span data-stu-id="ae05a-186">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="ae05a-187">此设置控制用户是否可以与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="ae05a-187">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="ae05a-188">若要了解详细信息，请参阅[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ae05a-188">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="ae05a-189">单击 "**保存**" 以使组织范围内的应用设置生效。</span><span class="sxs-lookup"><span data-stu-id="ae05a-189">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae05a-190">相关主题</span><span class="sxs-lookup"><span data-stu-id="ae05a-190">Related topics</span></span>

- [<span data-ttu-id="ae05a-191">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="ae05a-191">Admin settings for apps in Teams</span></span>](admin-settings.md)
