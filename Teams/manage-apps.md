---
title: 在 Microsoft Teams 管理中心中管理应用
author: LanaChin
ms.author: v-lanac
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
description: 了解如何在 Microsoft Teams 管理中心的"管理应用"页面上管理 Teams 应用
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 23ff7cc90d30dc931b0677ce5ec5aa8db98981fb
ms.sourcegitcommit: e0e089f0ab217d920e128377af653f7dbfdedacf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818181"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="50dfb-103">在 Microsoft Teams 管理中心中管理应用</span><span class="sxs-lookup"><span data-stu-id="50dfb-103">Manage your apps in the Microsoft Teams admin center</span></span>
======================================================

<span data-ttu-id="50dfb-104">作为管理员，你可以在 Microsoft Teams 管理中心查看和管理组织的所有 Teams 应用的位置。</span><span class="sxs-lookup"><span data-stu-id="50dfb-104">As an admin, the Manage apps page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="50dfb-105">此处，你可以看到应用的组织级别状态和属性、批准或上传新自定义应用、在组织级别批准或允许应用、购买第三方应用的服务以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="50dfb-105">Here, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, purchase services for third-party apps, and manage org-wide app settings.</span></span>

<span data-ttu-id="50dfb-106">"管理应用程序"页面向你提供所有可用应用，提供了用于决定在组织中允许或阻止哪些应用的相关信息。</span><span class="sxs-lookup"><span data-stu-id="50dfb-106">The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="50dfb-107">然后，你可以[使用应用权限策略、应用](teams-app-permission-policies.md)[设置策略](teams-app-setup-policies.md)以及自定义[应用策略与设置](teams-custom-app-policies-and-settings.md)来为你组织中的特定用户配置应用体验。</span><span class="sxs-lookup"><span data-stu-id="50dfb-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="50dfb-108">在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。</span><span class="sxs-lookup"><span data-stu-id="50dfb-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="50dfb-109">只有全局管理员或 Teams 服务管理员才能访问该页面。</span><span class="sxs-lookup"><span data-stu-id="50dfb-109">You must be a global admin or Teams service admin to access the page.</span></span>

> [!NOTE]
> <span data-ttu-id="50dfb-110">Microsoft 365 政政版社区云中尚不提供 Teams (GCC) 应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-110">The Manage apps page isn't available yet in Microsoft 365 Government Community Cloud (GCC) deployments of Teams.</span></span>

## <a name="view-apps"></a><span data-ttu-id="50dfb-111">查看应用</span><span class="sxs-lookup"><span data-stu-id="50dfb-111">View apps</span></span>

<span data-ttu-id="50dfb-112">可以查看每个应用，包括有关每个应用的以下信息。</span><span class="sxs-lookup"><span data-stu-id="50dfb-112">You can view every app including the following information about each app.</span></span>

!["托管的应用"页面的屏幕截图](media/manage-apps.png)

- <span data-ttu-id="50dfb-114">**名称**：应用名称。</span><span class="sxs-lookup"><span data-stu-id="50dfb-114">**Name**: The app name.</span></span> <span data-ttu-id="50dfb-115">单击应用名称可以查看有关该应用程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="50dfb-115">Click the app name to see more information about the app.</span></span> <span data-ttu-id="50dfb-116">这包括应用的描述，无论是否允许或阻止、版本、适用于应用的类别、认证状态、支持的功能和应用 ID。</span><span class="sxs-lookup"><span data-stu-id="50dfb-116">This includes a description of the app, whether it's allowed or blocked, version, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="50dfb-117">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="50dfb-117">Here's an example:</span></span>

  ![应用的应用详细信息页面的屏幕截图](media/manage-apps-app-details.png)
  
- <span data-ttu-id="50dfb-119">**认证：** 如果应用已通过认证，你将看到 **Microsoft 365 认** 证或 **发布者认证**。</span><span class="sxs-lookup"><span data-stu-id="50dfb-119">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="50dfb-120">单击该链接，查看应用的认证详细信息。</span><span class="sxs-lookup"><span data-stu-id="50dfb-120">Click the link to view certification details for the app.</span></span> <span data-ttu-id="50dfb-121">如果看 **--** 见"，我们没有应用的认证信息。</span><span class="sxs-lookup"><span data-stu-id="50dfb-121">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="50dfb-122">若要深入了解 Teams 中认证的应用，请 [阅读 Microsoft 365 应用认证计划](https://docs.microsoft.com/teams-app-certification/all-apps)。</span><span class="sxs-lookup"><span data-stu-id="50dfb-122">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](https://docs.microsoft.com/teams-app-certification/all-apps).</span></span>  
- <span data-ttu-id="50dfb-123">**发布者**：发布者的名称。</span><span class="sxs-lookup"><span data-stu-id="50dfb-123">**Publisher**: Name of the publisher.</span></span>
- <span data-ttu-id="50dfb-124">**发布状态**：发布自定义应用的状态。</span><span class="sxs-lookup"><span data-stu-id="50dfb-124">**Publishing status**: Publishing status of custom apps.</span></span>
- <span data-ttu-id="50dfb-125">**状态**：位于组织级别的应用的状态，可能是以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="50dfb-125">**Status**: Status of the app at the org level, which can be one of the following:</span></span>

    - <span data-ttu-id="50dfb-126">**已允**许： 该应用面向您组织中的所有用户提供。</span><span class="sxs-lookup"><span data-stu-id="50dfb-126">**Allowed**: The app is available for all users in your organization.</span></span>
    
    - <span data-ttu-id="50dfb-127">**已阻止**：应用被阻止，并且不可供你组织中的任何用户使用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-127">**Blocked**: The app is blocked and not available for any users in your organization.</span></span>
    
    - <span data-ttu-id="50dfb-128">**阻止组织范围：应用**已在组织范围的应用设置中被阻止。</span><span class="sxs-lookup"><span data-stu-id="50dfb-128">**Blocked org-wide**: The app is blocked in org-wide app settings.</span></span>
    
      <span data-ttu-id="50dfb-129">请务必了解的是此列表示以前位于"组织范围设置"窗格上的应用的 **允许和阻止** 状态。</span><span class="sxs-lookup"><span data-stu-id="50dfb-129">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="50dfb-130">现在，你可以在"管理应用"页面上查看、阻止应用以及 **允许应用** 。</span><span class="sxs-lookup"><span data-stu-id="50dfb-130">You now view, block, and allow apps at the org-wide on the **Manage apps** page.</span></span> 
- <span data-ttu-id="50dfb-131">**许可证**：指示应用是否以服务形式作为服务 (购买) 提供软件。</span><span class="sxs-lookup"><span data-stu-id="50dfb-131">**Licenses**: Indicates whether an app offers a Software as a Service (SaaS) subscription for purchase.</span></span> <span data-ttu-id="50dfb-132">此列仅适用于第三方应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-132">This column applies only to third-party apps.</span></span> <span data-ttu-id="50dfb-133">每个第三方应用都将具有以下值之一：</span><span class="sxs-lookup"><span data-stu-id="50dfb-133">Each third-party app will have one of the following values:</span></span>
    - <span data-ttu-id="50dfb-134">**立即购买**：应用提供 SaaS 订阅，可供购买。</span><span class="sxs-lookup"><span data-stu-id="50dfb-134">**Purchase now**: The app offers a SaaS subscription and is available to purchase.</span></span>  
    - <span data-ttu-id="50dfb-135">**已购买**：应用提供 SaaS 订阅，你已为其购买了许可证。</span><span class="sxs-lookup"><span data-stu-id="50dfb-135">**Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.</span></span>
    - <span data-ttu-id="50dfb-136">**-**： 应用未提供 SaaS 订阅。</span><span class="sxs-lookup"><span data-stu-id="50dfb-136">**- -**: The app doesn't offer a SaaS subscription.</span></span>
- <span data-ttu-id="50dfb-137">**自定义应用**：应用是否是自定义应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-137">**Custom app**: Whether the app is a custom app.</span></span>
- <span data-ttu-id="50dfb-138">**类别：** 适用于应用的类别。</span><span class="sxs-lookup"><span data-stu-id="50dfb-138">**Categories**: Categories that apply to the app.</span></span>
- <span data-ttu-id="50dfb-139">**版本**：应用版本。</span><span class="sxs-lookup"><span data-stu-id="50dfb-139">**Version**: App version.</span></span>

<span data-ttu-id="50dfb-140">要在表格中查看所需的信息，请单击 **右** 上角的"编辑列"，在表格中添加或删除列。</span><span class="sxs-lookup"><span data-stu-id="50dfb-140">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a><span data-ttu-id="50dfb-141">将自定义应用发布到组织的应用商店</span><span class="sxs-lookup"><span data-stu-id="50dfb-141">Publish a custom app to your organization's app store</span></span>

<span data-ttu-id="50dfb-142">使用"管理应用"页面发布专为你的组织构建的应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-142">Use the Manage apps page to publish apps that are built specifically for your organization.</span></span> <span data-ttu-id="50dfb-143">在发布自定义应用后，它可供组织的应用商店中的用户使用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-143">After you publish a custom app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="50dfb-144">有两种方法可以将自定义应用发布到组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="50dfb-144">There are two ways to publish a custom app to your organization's app store.</span></span> <span data-ttu-id="50dfb-145">使用方式取决于获取应用的方式。</span><span class="sxs-lookup"><span data-stu-id="50dfb-145">The way that you use depends on how you get the app.</span></span>

- <span data-ttu-id="50dfb-146">[批准自定义应用](#approve-a-custom-app)：如果开发人员使用 Teams 应用提交 API 直接向"管理应用"页面提交应用，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="50dfb-146">[Approve a custom app](#approve-a-custom-app): Use this method if the developer submits the app directly to the Manage apps page using the Teams App Submission API.</span></span> <span data-ttu-id="50dfb-147">然后，你可以直接从 (详细信息页面查看并发布) 编辑或拒绝应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-147">You can then review and publish (or reject) the app directly from the app details page.</span></span>
- <span data-ttu-id="50dfb-148">[上载应用包](#upload-an-app-package)：如果开发人员以 .zip 格式向你发送应用包，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="50dfb-148">[Upload an app package](#upload-an-app-package): Use this method if the developer sends you the app package in .zip format.</span></span> <span data-ttu-id="50dfb-149">通过上载应用包发布应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-149">You publish the app by uploading the app package.</span></span>

###  <a name="approve-a-custom-app"></a><span data-ttu-id="50dfb-150">审批自定义应用</span><span class="sxs-lookup"><span data-stu-id="50dfb-150">Approve a custom app</span></span>

<span data-ttu-id="50dfb-151">" **管理应用"页面上的** 待定审批小组件会在开发人员使用 Teams 应用提交 API 提交应用时通知你。</span><span class="sxs-lookup"><span data-stu-id="50dfb-151">The **Pending approvals** widget on the Manage apps page notifies you when a developer submits an app by using the Teams App Submission API.</span></span> <span data-ttu-id="50dfb-152">会列出新提交的应用，其中**包含**已提交的发布状态和 **"被\*\*\*\*Submitted\*\*\*\*阻止状态**"。</span><span class="sxs-lookup"><span data-stu-id="50dfb-152">A newly submitted app is listed with a **Publishing status** of **Submitted** and an **Status** of **Blocked**.</span></span> <span data-ttu-id="50dfb-153">转到应用详细信息页面以查看有关应用的详细信息，然后发布该应用，将 **"发布状态"设置为\*\*\*\*"发布**"。</span><span class="sxs-lookup"><span data-stu-id="50dfb-153">Go to the app details page to see more information about the app, and then to publish it, set **Publishing status** to **Publish**.</span></span>

<span data-ttu-id="50dfb-154">开发人员向自定义应用提交更新时，你也会收到通知。</span><span class="sxs-lookup"><span data-stu-id="50dfb-154">You're also notified when a developer submits an update to a custom app.</span></span> <span data-ttu-id="50dfb-155">然后，你可以在应用详细信息页面上 (查并发布或) 名称。</span><span class="sxs-lookup"><span data-stu-id="50dfb-155">You can then review and publish (or reject) the update on the app details page.</span></span> <span data-ttu-id="50dfb-156">已对更新的应用执行所有应用权限策略和应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="50dfb-156">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="50dfb-157">若要了解详细信息 [，请参阅发布通过 Teams 应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="50dfb-157">To learn more, see [Publish a custom app submitted through the Teams App Submission API](submit-approve-custom-apps.md).</span></span>

### <a name="upload-an-app-package"></a><span data-ttu-id="50dfb-158">上载应用包</span><span class="sxs-lookup"><span data-stu-id="50dfb-158">Upload an app package</span></span>

<span data-ttu-id="50dfb-159">开发人员使用 Teams 应用 Studio 创建 [Teams 应用包](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)，然后将其通过 .zip 格式发送给你。</span><span class="sxs-lookup"><span data-stu-id="50dfb-159">The developer creates a Teams app package using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio), and then sends it to you in .zip format.</span></span> <span data-ttu-id="50dfb-160">如果你有应用包，可以将其上载到组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="50dfb-160">When you have the app package, you can upload it to your organization's app store.</span></span>

<span data-ttu-id="50dfb-161">要上载新的自定义应用，请选择" **上传** "以上载应用包。</span><span class="sxs-lookup"><span data-stu-id="50dfb-161">To upload a new custom app, select **Upload** to upload the app package.</span></span> <span data-ttu-id="50dfb-162">应用在上载之后不突出显示，因此你将需要在"管理应用"页面上搜索应用列表，才能找到它。</span><span class="sxs-lookup"><span data-stu-id="50dfb-162">The app isn't highlighted after it's uploaded so you'll need to search the list of apps on the Manage apps page to find it.</span></span>

<span data-ttu-id="50dfb-163">若要在上载应用后进行更新，请在"管理应用"页面上的应用列表中单击应用名称，然后单击" **更新**"。</span><span class="sxs-lookup"><span data-stu-id="50dfb-163">To update an app after it's uploaded, in the list of apps on the Manage apps page, click the app name, and then click **Update**.</span></span> <span data-ttu-id="50dfb-164">这样做将替换为已更新的应用，因此仍将实时使用现有的应用以及所有应用权限策略和应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="50dfb-164">Doing this replaces the existing app and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="50dfb-165">若要了解详细信息，请参阅 [通过上载应用包发布自定义应用](upload-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="50dfb-165">To learn more, see [Publish a custom app by uploading an app package](upload-custom-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="50dfb-166">允许和阻止应用</span><span class="sxs-lookup"><span data-stu-id="50dfb-166">Allow and block apps</span></span>

<span data-ttu-id="50dfb-167">在"管理应用"页中，你可以选择或阻止处于组织级别的单个应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-167">The Manage apps page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="50dfb-168">它显示每个可用的应用及其当前的组织级应用状态。</span><span class="sxs-lookup"><span data-stu-id="50dfb-168">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="50dfb-169"> ("阻止"并允许该组织级别的应用从 **组织范围内应用设置** 窗格移动到此处。) </span><span class="sxs-lookup"><span data-stu-id="50dfb-169">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="50dfb-170">若要允许或阻止应用，请选择它，然后单击"允**许"或"阻止\*\*\*\*"。**</span><span class="sxs-lookup"><span data-stu-id="50dfb-170">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="50dfb-171">当你阻止应用时，系统将禁用与该应用的所有交互，并且对于组织中的任何用户，该应用不会显示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="50dfb-171">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="50dfb-172">当在"管理应用"页面上阻止或允许使用某个应用时，组织中的所有用户都会阻止或允许该应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-172">When you block or allow an app on the Manage apps page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="50dfb-173">在 Teams 应用权限策略中阻止或允许使用某个应用时，向分配该策略的用户阻止或允许该应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-173">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="50dfb-174">为了用户能够安装任意应用并与其进行交互，你必须允许该应用在"管理应用"页面上的"管理应用"页面和分配给用户的应用权限策略中。</span><span class="sxs-lookup"><span data-stu-id="50dfb-174">For a user to be able to install and interact with any app, you must allow the app at the org level on the Manage apps page and in the app permission policy that's assigned to the user.</span></span>

 > [!NOTE]
 > <span data-ttu-id="50dfb-175">若要卸载应用，请右键单击应用，然后单击"卸载 **"或** 使用 **左侧的"更多** 应用程序"菜单。</span><span class="sxs-lookup"><span data-stu-id="50dfb-175">To uninstall an app, right-click the app and then click **Uninstall** or use the **More apps** menu on the left side.</span></span>

## <a name="purchase-services-for-third-party-apps"></a><span data-ttu-id="50dfb-176">购买第三方应用的服务</span><span class="sxs-lookup"><span data-stu-id="50dfb-176">Purchase services for third-party apps</span></span>

<span data-ttu-id="50dfb-177">可以直接从"管理应用"页面搜索和购买由第三方应用中用户提供的服务的许可证。</span><span class="sxs-lookup"><span data-stu-id="50dfb-177">You can search for and purchase licenses for services offered by third-party apps for users in your organization directly from the Manage apps page.</span></span> <span data-ttu-id="50dfb-178">下 **表** 中的"许可证"列指示应用是否提供了付费的 SaaS 订阅。</span><span class="sxs-lookup"><span data-stu-id="50dfb-178">The **Licenses** column in the table indicates whether an app offers a paid SaaS subscription.</span></span> <span data-ttu-id="50dfb-179">单击 **"立即** 购买"即可查看用户的计划和定价信息和购买许可证。</span><span class="sxs-lookup"><span data-stu-id="50dfb-179">Click **Purchase now** to view plans and pricing information and buy licenses for your users.</span></span> <span data-ttu-id="50dfb-180">若要了解详细信息， [请在 Microsoft Teams 管理中心中查看 Teams 第三方应用的购买服务](purchase-third-party-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="50dfb-180">To learn more, see [Purchase services for Teams third-party apps in the Microsoft Teams admin center](purchase-third-party-apps.md).</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="50dfb-181">管理组织范围内的应用设置</span><span class="sxs-lookup"><span data-stu-id="50dfb-181">Manage org-wide app settings</span></span>

<span data-ttu-id="50dfb-182">使用组织范围的应用设置来控制用户是否可以安装第三方应用，以及用户是否可以在你的组织中上载自定义应用或与其进行交互。</span><span class="sxs-lookup"><span data-stu-id="50dfb-182">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="50dfb-183">组织范围的应用设置管理所有用户的行为，并覆盖分配给用户的任何其他应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="50dfb-183">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="50dfb-184">你可以使用它们来控制存在音性或有问题的应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-184">You can use them to control malicious or problematic apps.</span></span>

> [!NOTE]
> <span data-ttu-id="50dfb-185">若要了解如何在 Microsoft 365 政政版中使用组织范围的应用设置 - Teams 的 GCC 部署，请参阅 Teams 中的 ["管理应用权限策略](teams-app-permission-policies.md)"。</span><span class="sxs-lookup"><span data-stu-id="50dfb-185">To learn how to use org-wide app settings in Microsoft 365 Government - GCC deployments of Teams, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="50dfb-186">在"管理应用"页面上， **选择组织范围内的应用设置**。</span><span class="sxs-lookup"><span data-stu-id="50dfb-186">On the Manage apps page, select **Org-wide app settings**.</span></span> <span data-ttu-id="50dfb-187">然后，您可以配置面板中所需的设置。</span><span class="sxs-lookup"><span data-stu-id="50dfb-187">You can then configure the settings you want in the panel.</span></span>

    ![组织范围的应用设置的屏幕截图](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="50dfb-189">在 **第三方应用下，关闭**或打开这些设置以控制对第三方应用的访问：</span><span class="sxs-lookup"><span data-stu-id="50dfb-189">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="50dfb-190">**允许第三方应用：** 此控制用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="50dfb-190">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="50dfb-191">如果关闭此设置，你的用户将不能安装或使用任何第三方应用，并且这些应用的应用状态在表中显示为 **"** 受阻止"组织范围。</span><span class="sxs-lookup"><span data-stu-id="50dfb-191">If you turn off this setting, your users won't be able to install or use any third-party apps and the app status of these apps is displayed as **Blocked org-wide** in the table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="50dfb-192">关闭 **"允许的第三方应用"** 时，将禁用传出的 [Webhooks，](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) 这意味着用户无法创建它们。</span><span class="sxs-lookup"><span data-stu-id="50dfb-192">When **Allow third-party apps** is off, [outgoing webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are disabled, which means that users can't create them.</span></span> <span data-ttu-id="50dfb-193">在此设置处于打开状态时，将为所有用户启用传出的 Webhookie，你可通过允许或阻止传出 Webhook 应用的应用权限策略来在用户 [级别控制它们](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="50dfb-193">When this setting is on, outgoing webhooks are enabled for all users and you can control them at the user level by allowing or blocking the Outgoing Webhook app through [app permission policies](teams-app-permission-policies.md).</span></span> <br><br><span data-ttu-id="50dfb-194">请注意，如果你拥有使用特定[app permission policies](teams-app-permission-policies.md)应用的 Microsoft 应用**的现有应用**权限策略 **，并阻止**其他所有设置，并且要为用户启用传出的 Webhookie，请将传出 Webhook 应用添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="50dfb-194">Note that if you have existing [app permission policies](teams-app-permission-policies.md) for **Microsoft apps** that use the **Allow specific apps and block all others** setting, and you want to enable outgoing webhooks for users, add the Outgoing Webhook app to the list.</span></span>
    - <span data-ttu-id="50dfb-195">**允许默认发布到应用商店中的任何新**第三方应用：此控制发布到 Teams 应用商店的新第三方应用是否可在 Teams 中自动提供。</span><span class="sxs-lookup"><span data-stu-id="50dfb-195">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="50dfb-196">仅当允许第三方应用时，你仅可设置此选项。</span><span class="sxs-lookup"><span data-stu-id="50dfb-196">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="50dfb-197">在 **"自定义应用**"下，关闭或打开" **允许与自定义应用进行交互**"。</span><span class="sxs-lookup"><span data-stu-id="50dfb-197">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="50dfb-198">此设置可控制用户是否可以与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="50dfb-198">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="50dfb-199">若要了解详细信息，请参阅 ["管理自定义应用策略和 Teams 中的设置](teams-custom-app-policies-and-settings.md)"。</span><span class="sxs-lookup"><span data-stu-id="50dfb-199">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="50dfb-200">单击 **"** 为组织范围的应用设置保存"以使生效。</span><span class="sxs-lookup"><span data-stu-id="50dfb-200">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="50dfb-201">相关主题</span><span class="sxs-lookup"><span data-stu-id="50dfb-201">Related topics</span></span>

- [<span data-ttu-id="50dfb-202">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="50dfb-202">Admin settings for apps in Teams</span></span>](admin-settings.md)