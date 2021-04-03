---
title: 在 Microsoft Teams 管理中心管理应用
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 在 Microsoft Teams 管理中心的"管理应用"页面上了解如何管理 Teams 应用
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: b3858044c52324cb52005c70c6f3afcf91e3f617
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574191"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="5384b-103">在 Microsoft Teams 管理中心管理应用</span><span class="sxs-lookup"><span data-stu-id="5384b-103">Manage your apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="5384b-104">作为管理员，Microsoft Teams 管理中心中的"管理应用"页面是查看和管理组织的所有 Teams 应用的地方。</span><span class="sxs-lookup"><span data-stu-id="5384b-104">As an admin, the Manage apps page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="5384b-105">在这里，可以查看应用的组织级状态和属性、批准新的自定义应用或将其上载到组织的应用商店、在组织级别阻止或允许应用、将应用添加到团队、购买第三方应用的服务、查看应用请求的权限、向应用授予管理员同意，以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="5384b-105">Here, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, add apps to teams, purchase services for third-party apps, view permissions requested by apps, grant admin consent to apps, and manage org-wide app settings.</span></span>

<span data-ttu-id="5384b-106">"管理应用"页面提供所有可用应用的视图，为你提供确定在整个组织中允许或阻止哪些应用时需要的信息。</span><span class="sxs-lookup"><span data-stu-id="5384b-106">The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="5384b-107">然后，可以使用 [应用权限策略](teams-app-permission-policies.md)、 [应用设置策略](teams-app-setup-policies.md)和自定义应用策略 [和](teams-custom-app-policies-and-settings.md) 设置为组织中特定用户配置应用体验。</span><span class="sxs-lookup"><span data-stu-id="5384b-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="5384b-108">在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="5384b-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="5384b-109">必须是全局管理员或 Teams 服务管理员才能访问页面。</span><span class="sxs-lookup"><span data-stu-id="5384b-109">You must be a global admin or Teams service admin to access the page.</span></span>

> [!NOTE]
> <span data-ttu-id="5384b-110">在 Teams 部署中，Microsoft 365 政府版社区云 (GCC) 页面尚不可用。</span><span class="sxs-lookup"><span data-stu-id="5384b-110">The Manage apps page isn't available yet in Microsoft 365 Government Community Cloud (GCC) deployments of Teams.</span></span>

## <a name="view-apps"></a><span data-ttu-id="5384b-111">查看应用</span><span class="sxs-lookup"><span data-stu-id="5384b-111">View apps</span></span>

<span data-ttu-id="5384b-112">你可以查看每个应用，包括有关每个应用的以下信息。</span><span class="sxs-lookup"><span data-stu-id="5384b-112">You can view every app including the following information about each app.</span></span>

!["托管应用"页的屏幕截图](media/manage-apps.png)

- <span data-ttu-id="5384b-114">**名称**：应用名称。</span><span class="sxs-lookup"><span data-stu-id="5384b-114">**Name**: The app name.</span></span> <span data-ttu-id="5384b-115">单击应用名称转到应用详细信息页，查看有关该应用的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5384b-115">Click the app name to go to the app details page to see more information about the app.</span></span> <span data-ttu-id="5384b-116">这包括应用的说明，无论是允许还是阻止应用、版本、隐私策略、使用条款、适用于应用的类别、认证状态、支持的功能和应用 ID。</span><span class="sxs-lookup"><span data-stu-id="5384b-116">This includes a description of the app, whether it's allowed or blocked, version, privacy policy, terms of use, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="5384b-117">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="5384b-117">Here's an example:</span></span>

  ![应用的应用详细信息页的屏幕截图](media/manage-apps-app-details.png)
  
- <span data-ttu-id="5384b-119">**认证**：如果应用已通过认证，你将看到 **Microsoft 365 认证** 或 **发布者证明**。</span><span class="sxs-lookup"><span data-stu-id="5384b-119">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="5384b-120">单击该链接可查看应用的认证详细信息。</span><span class="sxs-lookup"><span data-stu-id="5384b-120">Click the link to view certification details for the app.</span></span> <span data-ttu-id="5384b-121">如果看到 **--** ""，则我们没有应用的认证信息。</span><span class="sxs-lookup"><span data-stu-id="5384b-121">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="5384b-122">若要详细了解 Teams 中的认证应用，请阅读 [Microsoft 365 应用认证计划](/teams-app-certification/all-apps)。</span><span class="sxs-lookup"><span data-stu-id="5384b-122">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](/teams-app-certification/all-apps).</span></span>  
- <span data-ttu-id="5384b-123">**发布者**：发布者的名称。</span><span class="sxs-lookup"><span data-stu-id="5384b-123">**Publisher**: Name of the publisher.</span></span>
- <span data-ttu-id="5384b-124">**发布状态**：自定义应用的发布状态。</span><span class="sxs-lookup"><span data-stu-id="5384b-124">**Publishing status**: Publishing status of custom apps.</span></span>
- <span data-ttu-id="5384b-125">**状态**：组织级别的应用状态，可以是下列其中一项：</span><span class="sxs-lookup"><span data-stu-id="5384b-125">**Status**: Status of the app at the org level, which can be one of the following:</span></span>

    - <span data-ttu-id="5384b-126">**允许**：该应用可供你组织的所有用户使用。</span><span class="sxs-lookup"><span data-stu-id="5384b-126">**Allowed**: The app is available for all users in your organization.</span></span>
    
    - <span data-ttu-id="5384b-127">**已** 阻止：应用被阻止，并且不适用于组织的任何用户。</span><span class="sxs-lookup"><span data-stu-id="5384b-127">**Blocked**: The app is blocked and not available for any users in your organization.</span></span>
    
    - <span data-ttu-id="5384b-128">**阻止组织范围**：应用在组织范围内的应用设置中受阻。</span><span class="sxs-lookup"><span data-stu-id="5384b-128">**Blocked org-wide**: The app is blocked in org-wide app settings.</span></span>
    
      <span data-ttu-id="5384b-129">必须知道，此列表示以前位于" **组织** 范围的设置"窗格中的应用的允许和阻止状态。</span><span class="sxs-lookup"><span data-stu-id="5384b-129">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="5384b-130">现在，您可以在"管理应用"页面上的组织范围内查看、阻止和 **允许应用** 。</span><span class="sxs-lookup"><span data-stu-id="5384b-130">You now view, block, and allow apps at the org-wide on the **Manage apps** page.</span></span> 
- <span data-ttu-id="5384b-131">**许可证**：指示应用是否提供软件即服务 (SaaS) 订阅进行购买。</span><span class="sxs-lookup"><span data-stu-id="5384b-131">**Licenses**: Indicates whether an app offers a Software as a Service (SaaS) subscription for purchase.</span></span> <span data-ttu-id="5384b-132">此列仅适用于第三方应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-132">This column applies only to third-party apps.</span></span> <span data-ttu-id="5384b-133">每个第三方应用将具有以下值之一：</span><span class="sxs-lookup"><span data-stu-id="5384b-133">Each third-party app will have one of the following values:</span></span>
    - <span data-ttu-id="5384b-134">**现在购买**：该应用提供 SaaS 订阅，可供购买。</span><span class="sxs-lookup"><span data-stu-id="5384b-134">**Purchase now**: The app offers a SaaS subscription and is available to purchase.</span></span>  
    - <span data-ttu-id="5384b-135">**已** 购买：该应用提供 SaaS 订阅，并且你已购买其许可证。</span><span class="sxs-lookup"><span data-stu-id="5384b-135">**Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.</span></span>
    - <span data-ttu-id="5384b-136">**- -**：应用未提供 SaaS 订阅。</span><span class="sxs-lookup"><span data-stu-id="5384b-136">**- -**: The app doesn't offer a SaaS subscription.</span></span>
- <span data-ttu-id="5384b-137">**自定义应用**：应用是否是自定义应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-137">**Custom app**: Whether the app is a custom app.</span></span>
- <span data-ttu-id="5384b-138">**权限**：指示在 Azure Active Directory (Azure AD) 注册的第三方或自定义应用是否具有需要许可的权限。</span><span class="sxs-lookup"><span data-stu-id="5384b-138">**Permissions**: Indicates whether a third-party or custom app that's registered in Azure Active Directory (Azure AD) has permissions that need consent.</span></span> <span data-ttu-id="5384b-139">会看到以下值之一：</span><span class="sxs-lookup"><span data-stu-id="5384b-139">You'll see one of the following values:</span></span>
    - <span data-ttu-id="5384b-140">**查看详细信息**：应用具有需要许可才能访问数据的权限。</span><span class="sxs-lookup"><span data-stu-id="5384b-140">**View details**: The app has permissions that require consent before the app can access data.</span></span> 
    - <span data-ttu-id="5384b-141">**-**： 应用没有需要许可的权限。</span><span class="sxs-lookup"><span data-stu-id="5384b-141">**- -**: The app doesn't have permissions that need consent.</span></span>
- <span data-ttu-id="5384b-142">**类别**：适用于应用的类别。</span><span class="sxs-lookup"><span data-stu-id="5384b-142">**Categories**: Categories that apply to the app.</span></span>
- <span data-ttu-id="5384b-143">**版本**：应用版本。</span><span class="sxs-lookup"><span data-stu-id="5384b-143">**Version**: App version.</span></span>

<span data-ttu-id="5384b-144">若要在表中查看信息，请单击右上角的"编辑列"，向表中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="5384b-144">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a><span data-ttu-id="5384b-145">将自定义应用发布到组织的应用商店</span><span class="sxs-lookup"><span data-stu-id="5384b-145">Publish a custom app to your organization's app store</span></span>

<span data-ttu-id="5384b-146">使用"管理应用"页发布专为组织构建的应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-146">Use the Manage apps page to publish apps that are built specifically for your organization.</span></span> <span data-ttu-id="5384b-147">发布自定义应用后，该应用可供组织应用商店中的用户使用。</span><span class="sxs-lookup"><span data-stu-id="5384b-147">After you publish a custom app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="5384b-148">有两种方法将自定义应用发布到组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="5384b-148">There are two ways to publish a custom app to your organization's app store.</span></span> <span data-ttu-id="5384b-149">你使用的方式取决于你获取应用的方式。</span><span class="sxs-lookup"><span data-stu-id="5384b-149">The way that you use depends on how you get the app.</span></span>

- <span data-ttu-id="5384b-150">[批准自定义应用](#approve-a-custom-app)：如果开发人员使用 Teams 应用提交 API 将应用直接提交到"管理应用"页面，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="5384b-150">[Approve a custom app](#approve-a-custom-app): Use this method if the developer submits the app directly to the Manage apps page using the Teams App Submission API.</span></span> <span data-ttu-id="5384b-151">然后，你可以直接从应用 (查看) 或拒绝应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-151">You can then review and publish (or reject) the app directly from the app details page.</span></span>
- <span data-ttu-id="5384b-152">[上传应用包](#upload-an-app-package)：如果开发人员以 .zip 格式发送给你应用包，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="5384b-152">[Upload an app package](#upload-an-app-package): Use this method if the developer sends you the app package in .zip format.</span></span> <span data-ttu-id="5384b-153">通过上传应用包发布应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-153">You publish the app by uploading the app package.</span></span>

###  <a name="approve-a-custom-app"></a><span data-ttu-id="5384b-154">批准自定义应用</span><span class="sxs-lookup"><span data-stu-id="5384b-154">Approve a custom app</span></span>

<span data-ttu-id="5384b-155">当 **开发人员使用** Teams 应用提交 API 提交应用时，"管理应用"页面上的"等待审批"小组件会通知你。</span><span class="sxs-lookup"><span data-stu-id="5384b-155">The **Pending approvals** widget on the Manage apps page notifies you when a developer submits an app by using the Teams App Submission API.</span></span> <span data-ttu-id="5384b-156">新提交的应用将列出，其发布 **状态\*\*\*\*为"已** 提交"，"**状态"** 为"已 **阻止"。**</span><span class="sxs-lookup"><span data-stu-id="5384b-156">A newly submitted app is listed with a **Publishing status** of **Submitted** and an **Status** of **Blocked**.</span></span> <span data-ttu-id="5384b-157">转到应用详细信息页以查看有关应用的详细信息，然后发布它，将"**发布状态"设置为**"发布 **"。**</span><span class="sxs-lookup"><span data-stu-id="5384b-157">Go to the app details page to see more information about the app, and then to publish it, set **Publishing status** to **Publish**.</span></span>

<span data-ttu-id="5384b-158">开发人员将更新提交到自定义应用时，也会收到通知。</span><span class="sxs-lookup"><span data-stu-id="5384b-158">You're also notified when a developer submits an update to a custom app.</span></span> <span data-ttu-id="5384b-159">然后，可以在应用详细信息 (查看) 或拒绝更新。</span><span class="sxs-lookup"><span data-stu-id="5384b-159">You can then review and publish (or reject) the update on the app details page.</span></span> <span data-ttu-id="5384b-160">对于更新的应用，所有应用权限策略和应用设置策略仍然强制实施。</span><span class="sxs-lookup"><span data-stu-id="5384b-160">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="5384b-161">有关详细信息，请参阅 [发布通过 Teams 应用](submit-approve-custom-apps.md)提交 API 提交的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-161">To learn more, see [Publish a custom app submitted through the Teams App Submission API](submit-approve-custom-apps.md).</span></span>

### <a name="upload-an-app-package"></a><span data-ttu-id="5384b-162">上传应用包</span><span class="sxs-lookup"><span data-stu-id="5384b-162">Upload an app package</span></span>

<span data-ttu-id="5384b-163">开发人员使用 [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio)创建 Teams 应用包，然后以 .zip 格式将其发送给你。</span><span class="sxs-lookup"><span data-stu-id="5384b-163">The developer creates a Teams app package using [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio), and then sends it to you in .zip format.</span></span> <span data-ttu-id="5384b-164">当你拥有应用包时，你可以将其上传到组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="5384b-164">When you have the app package, you can upload it to your organization's app store.</span></span>

<span data-ttu-id="5384b-165">若要上传新的自定义应用，请选择 **"上传** "以上传应用包。</span><span class="sxs-lookup"><span data-stu-id="5384b-165">To upload a new custom app, select **Upload** to upload the app package.</span></span> <span data-ttu-id="5384b-166">应用上传后不会突出显示，因此你需要在"管理应用"页面上搜索应用列表以找到它。</span><span class="sxs-lookup"><span data-stu-id="5384b-166">The app isn't highlighted after it's uploaded so you'll need to search the list of apps on the Manage apps page to find it.</span></span>

<span data-ttu-id="5384b-167">若要在应用上传后更新应用，请在"管理应用"页面上的应用列表中，单击应用名称，然后单击"更新 **"。**</span><span class="sxs-lookup"><span data-stu-id="5384b-167">To update an app after it's uploaded, in the list of apps on the Manage apps page, click the app name, and then click **Update**.</span></span> <span data-ttu-id="5384b-168">执行此操作会替换现有应用，并且所有应用权限策略和应用设置策略仍对更新的应用强制实施。</span><span class="sxs-lookup"><span data-stu-id="5384b-168">Doing this replaces the existing app and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="5384b-169">若要了解有关详细信息，请参阅通过 [上传应用包 发布自定义应用](upload-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="5384b-169">To learn more, see [Publish a custom app by uploading an app package](upload-custom-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="5384b-170">允许和阻止应用</span><span class="sxs-lookup"><span data-stu-id="5384b-170">Allow and block apps</span></span>

<span data-ttu-id="5384b-171">"管理应用"页面是组织级别允许或阻止单个应用的地方。</span><span class="sxs-lookup"><span data-stu-id="5384b-171">The Manage apps page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="5384b-172">它显示每个可用的应用及其当前的组织级应用状态。</span><span class="sxs-lookup"><span data-stu-id="5384b-172">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="5384b-173"> (组织级别的阻止和允许应用已从" **组织范围** 的应用设置"窗格移动到此处。) </span><span class="sxs-lookup"><span data-stu-id="5384b-173">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="5384b-174">若要允许或阻止应用，请选择它，然后单击"允许 **"或**"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="5384b-174">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="5384b-175">阻止应用时，将禁用与该应用的所有交互，并且对于组织的任何用户，该应用不会显示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="5384b-175">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="5384b-176">在"管理应用"页面上阻止或允许应用时，将阻止或允许组织中所有用户使用该应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-176">When you block or allow an app on the Manage apps page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="5384b-177">在 Teams 应用权限策略中阻止或允许应用时，会阻止或允许分配有该策略的用户使用该应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-177">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="5384b-178">若要使用户能够安装任何应用并与之交互，必须在"管理应用"页面和分配给用户的应用权限策略中允许组织级别的应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-178">For a user to be able to install and interact with any app, you must allow the app at the org level on the Manage apps page and in the app permission policy that's assigned to the user.</span></span>

 > [!NOTE]
 > <span data-ttu-id="5384b-179">若要卸载应用，请右键单击该应用，然后单击左侧的"卸载或使用更多应用"菜单。</span><span class="sxs-lookup"><span data-stu-id="5384b-179">To uninstall an app, right-click the app, and then click **Uninstall** or use the **More apps** menu on the left side.</span></span>

## <a name="add-an-app-to-a-team"></a><span data-ttu-id="5384b-180">向团队添加应用</span><span class="sxs-lookup"><span data-stu-id="5384b-180">Add an app to a team</span></span>

<span data-ttu-id="5384b-181">使用" **添加到团队"** 按钮将应用安装到团队。</span><span class="sxs-lookup"><span data-stu-id="5384b-181">You use the **Add to team** button to install an app to a team.</span></span> <span data-ttu-id="5384b-182">请记住，这仅适用于可在团队范围内安装的应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-182">Keep in mind that this is only for apps that can be installed in a team scope.</span></span> <span data-ttu-id="5384b-183">" **添加到团队** "按钮不适用于只能在个人范围内安装的应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-183">The **Add to team** button isn't available for apps that can only be installed in the personal scope.</span></span>

!["添加到团队"按钮的屏幕截图](media/manage-apps-add-app-team.png)

1. <span data-ttu-id="5384b-185">搜索你需要的应用，然后单击应用名称左侧选择该应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-185">Search for the app you want, and then select the app by clicking to the left of the app name.</span></span>
2. <span data-ttu-id="5384b-186">选择 **"添加到团队"。**</span><span class="sxs-lookup"><span data-stu-id="5384b-186">Select **Add to team**.</span></span>
3. <span data-ttu-id="5384b-187">在"**添加到团队"** 窗格中，搜索要添加应用的团队，选择团队，然后选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="5384b-187">In the **Add to team** pane, search for the team you want to add the app to, select the team, and then select **Apply**.</span></span>

## <a name="customize-an-app-in-preview"></a><span data-ttu-id="5384b-188">在预览版 (自定义应用) </span><span class="sxs-lookup"><span data-stu-id="5384b-188">Customize an app (in preview)</span></span>

<span data-ttu-id="5384b-189">现在，你可以自定义应用，以根据组织需求包含特定的外观。</span><span class="sxs-lookup"><span data-stu-id="5384b-189">You can now customize an app to include a specific look and feel according to your organization needs.</span></span> <span data-ttu-id="5384b-190">请参阅 [在 Teams 中自定义应用](customize-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="5384b-190">See [Customize apps in Teams](customize-apps.md).</span></span>

## <a name="purchase-services-for-third-party-apps"></a><span data-ttu-id="5384b-191">购买第三方应用的服务</span><span class="sxs-lookup"><span data-stu-id="5384b-191">Purchase services for third-party apps</span></span>

<span data-ttu-id="5384b-192">可以直接从"管理应用"页面搜索并购买第三方应用为组织用户提供的服务的许可证。</span><span class="sxs-lookup"><span data-stu-id="5384b-192">You can search for and purchase licenses for services offered by third-party apps for users in your organization directly from the Manage apps page.</span></span> <span data-ttu-id="5384b-193">表中的 **"** 许可证"列指示应用是否提供付费 SaaS 订阅。</span><span class="sxs-lookup"><span data-stu-id="5384b-193">The **Licenses** column in the table indicates whether an app offers a paid SaaS subscription.</span></span> <span data-ttu-id="5384b-194">单击 **"立即** 购买"查看计划和定价信息，并购买用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="5384b-194">Click **Purchase now** to view plans and pricing information and buy licenses for your users.</span></span> <span data-ttu-id="5384b-195">有关详细信息，请参阅在 Microsoft Teams 管理中心购买 Teams 第三方 [应用的服务](purchase-third-party-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="5384b-195">To learn more, see [Purchase services for Teams third-party apps in the Microsoft Teams admin center](purchase-third-party-apps.md).</span></span>

## <a name="grant-admin-consent-to-apps"></a><span data-ttu-id="5384b-196">向应用授予管理员许可</span><span class="sxs-lookup"><span data-stu-id="5384b-196">Grant admin consent to apps</span></span>

<span data-ttu-id="5384b-197">可以代表组织中所有用户查看并授予对请求权限的应用的许可。</span><span class="sxs-lookup"><span data-stu-id="5384b-197">You can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="5384b-198">你这样做，以便用户不必在启动应用时查看并接受应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="5384b-198">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="5384b-199">" **权限"** 列指示应用是否具有需要许可的权限。</span><span class="sxs-lookup"><span data-stu-id="5384b-199">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="5384b-200">对于在 Azure  AD 中注册并拥有需要许可的权限的每个应用，你将看到"查看详细信息"链接。</span><span class="sxs-lookup"><span data-stu-id="5384b-200">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="5384b-201">有关详细信息，请参阅在 Microsoft Teams 管理中心中查看应用权限 [并授予管理员许可](app-permissions-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5384b-201">To learn more, see [View app permissions and grant admin consent in the Microsoft Teams admin center](app-permissions-admin-center.md).</span></span>

## <a name="view-resource-specific-consent-permissions"></a><span data-ttu-id="5384b-202">查看特定于资源的许可权限</span><span class="sxs-lookup"><span data-stu-id="5384b-202">View resource-specific consent permissions</span></span>

<span data-ttu-id="5384b-203">RSC (资源) 权限允许团队所有者授予应用访问和修改团队数据的许可。</span><span class="sxs-lookup"><span data-stu-id="5384b-203">Resource-specific consent (RSC) permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="5384b-204">RSC 权限是特定于团队的粒度权限，用于定义应用可在特定团队中执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="5384b-204">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="5384b-205">可以在应用详细信息页面的"权限"选项卡上查看 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="5384b-205">You can view RSC permissions on the **Permissions** tab of the app details page for an app.</span></span> <span data-ttu-id="5384b-206">有关详细信息，请参阅在 Microsoft Teams 管理中心中查看应用权限 [并授予管理员许可](app-permissions-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5384b-206">To learn more, see [View app permissions and grant admin consent in the Microsoft Teams admin center](app-permissions-admin-center.md).</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="5384b-207">管理组织范围内的应用设置</span><span class="sxs-lookup"><span data-stu-id="5384b-207">Manage org-wide app settings</span></span>

<span data-ttu-id="5384b-208">使用组织范围的应用设置来控制用户是否可以安装第三方应用，以及用户是否可以上载或与组织中的自定义应用进行交互。</span><span class="sxs-lookup"><span data-stu-id="5384b-208">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="5384b-209">组织范围的应用设置可控制所有用户的行为，并且可覆盖分配给用户的任何其他应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="5384b-209">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="5384b-210">你可以使用它们控制恶意应用或有问题的应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-210">You can use them to control malicious or problematic apps.</span></span>

> [!NOTE]
> <span data-ttu-id="5384b-211">若要了解如何在 Teams 的 Microsoft 365 政府版 - GCC 部署中使用组织范围内的应用设置，请参阅在 Teams 中管理 [应用权限策略](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5384b-211">To learn how to use org-wide app settings in Microsoft 365 Government - GCC deployments of Teams, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="5384b-212">在"管理应用"页上，选择 **"组织范围的应用设置"。**</span><span class="sxs-lookup"><span data-stu-id="5384b-212">On the Manage apps page, select **Org-wide app settings**.</span></span> <span data-ttu-id="5384b-213">然后，你可以在面板中配置所需的设置。</span><span class="sxs-lookup"><span data-stu-id="5384b-213">You can then configure the settings you want in the panel.</span></span>

    ![组织范围的应用设置的屏幕截图](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="5384b-215">在“**第三方应用**”下，关闭或打开这些设置以控制对第三方应用的访问权限：</span><span class="sxs-lookup"><span data-stu-id="5384b-215">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="5384b-216">**允许第三方应用**：控制用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="5384b-216">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="5384b-217">如果关闭此设置，用户将无法安装或使用任何第三方应用，并且这些应用的应用状态在表中显示为"阻止组织范围"。 </span><span class="sxs-lookup"><span data-stu-id="5384b-217">If you turn off this setting, your users won't be able to install or use any third-party apps and the app status of these apps is displayed as **Blocked org-wide** in the table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="5384b-218">当 **"允许第三方应用** "关闭时，将禁用传出 [Webhook，](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) 这意味着用户无法创建它们。</span><span class="sxs-lookup"><span data-stu-id="5384b-218">When **Allow third-party apps** is off, [outgoing webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are disabled, which means that users can't create them.</span></span> <span data-ttu-id="5384b-219">启用此设置后，将针对所有用户启用传出 Webhook，并且可以通过应用权限策略 允许或阻止传出 Webhook 应用，在用户级别[控制这些 Webhook。](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5384b-219">When this setting is on, outgoing webhooks are enabled for all users and you can control them at the user level by allowing or blocking the Outgoing Webhook app through [app permission policies](teams-app-permission-policies.md).</span></span> <br><br><span data-ttu-id="5384b-220">请注意，如果 Microsoft 应用的现有应用权限策略使用"允许特定应用并阻止所有其他应用"设置，并且希望为用户启用传出 Webhook，则向列表添加传出 Webhook 应用。 [](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5384b-220">Note that if you have existing [app permission policies](teams-app-permission-policies.md) for **Microsoft apps** that use the **Allow specific apps and block all others** setting, and you want to enable outgoing webhooks for users, add the Outgoing Webhook app to the list.</span></span>
    - <span data-ttu-id="5384b-221">**默认情况下，允许发布到应用商店的所有新的第三方应用**：控制发布到 Teams 应用商店的新第三方应用是否在 Teams 中自动可用。</span><span class="sxs-lookup"><span data-stu-id="5384b-221">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="5384b-222">仅在允许第三方应用时才能设置此选项。</span><span class="sxs-lookup"><span data-stu-id="5384b-222">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="5384b-223">在 **"自定义应用**"下，关闭或打开 **"允许与自定义应用交互"。**</span><span class="sxs-lookup"><span data-stu-id="5384b-223">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="5384b-224">此设置控制用户是否可以与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="5384b-224">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="5384b-225">要了解详细信息，请参阅[在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5384b-225">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="5384b-226">单击“**保存**”以使组织范围的应用设置生效。</span><span class="sxs-lookup"><span data-stu-id="5384b-226">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5384b-227">相关主题</span><span class="sxs-lookup"><span data-stu-id="5384b-227">Related topics</span></span>

- [<span data-ttu-id="5384b-228">Teams 中应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="5384b-228">Admin settings for apps in Teams</span></span>](admin-settings.md)