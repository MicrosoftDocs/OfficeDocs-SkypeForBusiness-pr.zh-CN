---
title: 在 Microsoft 团队中管理自定义应用
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 了解如何让自定义团队应用从开发到部署。
ms.openlocfilehash: a2896a2aa2b2d9750afd147b113a76637514afb6
ms.sourcegitcommit: b5c747e2daad6dd3c1d91f4e61ae6f26db5c77f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064527"
---
# <a name="manage-your-custom-apps-in-microsoft-teams"></a><span data-ttu-id="21d77-103">在 Microsoft 团队中管理自定义应用</span><span class="sxs-lookup"><span data-stu-id="21d77-103">Manage your custom apps in Microsoft Teams</span></span>

<span data-ttu-id="21d77-104">本文提供了有关如何将团队应用从开发部署到部署的端到端指南。</span><span class="sxs-lookup"><span data-stu-id="21d77-104">This article provides end-to-end guidance for how to take your Teams app from development to deployment.</span></span> <span data-ttu-id="21d77-105">本指南重点介绍应用的团队内容，面向 IT 专业人士。</span><span class="sxs-lookup"><span data-stu-id="21d77-105">This guidance focuses on the Teams aspects of the app and is intended for IT pros.</span></span> <span data-ttu-id="21d77-106">有关开发团队应用的详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">此处</a>。</span><span class="sxs-lookup"><span data-stu-id="21d77-106">For more information on developing Teams apps, see <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a>.</span></span>

![从开发到部署概述应用](media/manage-your-lob-apps.png)

## <a name="getting-started"></a><span data-ttu-id="21d77-108">入门</span><span class="sxs-lookup"><span data-stu-id="21d77-108">Getting started</span></span>

<span data-ttu-id="21d77-109">若要创建和管理团队中的自定义应用，你需要两个租户：用于开发和生产租户的测试租户。</span><span class="sxs-lookup"><span data-stu-id="21d77-109">To create and manage custom apps in Teams, you'll need two tenants: a test tenant for development and a production tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="21d77-110">如果你还没有测试租户，则可以使用 Office 365 开发人员程序快速创建一个测试租户并使用测试数据填充它。</span><span class="sxs-lookup"><span data-stu-id="21d77-110">If you don't already have a test tenant, you can quickly create one and populate it with test data using the Office 365 Developer Program.</span></span> <span data-ttu-id="21d77-111"><a href="https://developer.microsoft.com/office/dev-program" target="_blank">在此处了解详细信息</a>。</span><span class="sxs-lookup"><span data-stu-id="21d77-111"><a href="https://developer.microsoft.com/office/dev-program" target="_blank">Learn more here</a>.</span></span>

## <a name="step-1-develop-and-test"></a><span data-ttu-id="21d77-112">步骤1：开发和测试</span><span class="sxs-lookup"><span data-stu-id="21d77-112">Step 1: Develop and test</span></span>

### <a name="create-test-users"></a><span data-ttu-id="21d77-113">创建测试用户</span><span class="sxs-lookup"><span data-stu-id="21d77-113">Create test users</span></span>

<span data-ttu-id="21d77-114">请确保你的开发人员（无论是内部还是外部）在你的测试租户中具有帐户。</span><span class="sxs-lookup"><span data-stu-id="21d77-114">Make sure that your developers, whether in-house or external, have accounts in your test tenant.</span></span> <span data-ttu-id="21d77-115"><a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">了解有关添加用户的详细信息</a>。</span><span class="sxs-lookup"><span data-stu-id="21d77-115"><a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">Learn more about adding users</a>.</span></span>

### <a name="allow-custom-apps-in-the-test-tenant"></a><span data-ttu-id="21d77-116">允许在测试租户中自定义应用</span><span class="sxs-lookup"><span data-stu-id="21d77-116">Allow custom apps in the test tenant</span></span>

<span data-ttu-id="21d77-117">若要向开发人员提供测试所需的访问权限，请允许测试租户中的所有用户上载自定义应用（也称为旁加载）。</span><span class="sxs-lookup"><span data-stu-id="21d77-117">To give developers the access they need for testing, allow all users in the test tenant to upload custom apps (also known as sideloading).</span></span> <span data-ttu-id="21d77-118">这允许开发人员上载自定义应用程序，以供个人或跨测试租户使用，而无需将应用提交到团队应用商店。</span><span class="sxs-lookup"><span data-stu-id="21d77-118">This lets developers upload a custom app to be used personally or across the test tenant without having to submit the app to the Teams apps store.</span></span> <span data-ttu-id="21d77-119">上载自定义应用程序使开发人员可以在更广泛地分发应用之前对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="21d77-119">Uploading a custom app lets developers test an app before you distribute it more widely.</span></span>

<span data-ttu-id="21d77-120">若要允许用户上载自定义应用程序，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="21d77-120">To allow users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="21d77-121">启用 "**允许与自定义应用交互**" 组织范围的应用设置。</span><span class="sxs-lookup"><span data-stu-id="21d77-121">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="21d77-122">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="21d77-122">To do this:</span></span>
    1. <span data-ttu-id="21d77-123">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **管理应用**"，然后单击 "**组织范围的应用设置**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-123">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="21d77-124">在 "**自定义应用**" 下，打开 "**允许与自定义应用交互**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-124">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>

    !["允许与自定义应用交互" 组织范围内的应用设置的屏幕截图](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. <span data-ttu-id="21d77-126">在全局应用设置策略中启用 "**上载自定义应用**" 设置。</span><span class="sxs-lookup"><span data-stu-id="21d77-126">Turn on the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="21d77-127">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="21d77-127">To do this:</span></span>
    1. <span data-ttu-id="21d77-128">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **设置策略**"，然后单击 "**全局（组织范围默认）** " 策略。</span><span class="sxs-lookup"><span data-stu-id="21d77-128">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="21d77-129">打开 "**上载自定义应用**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-129">Turn on **Upload custom apps**, and then click **Save**.</span></span>

    !["上载自定义应用" 应用设置策略设置的屏幕截图](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> <span data-ttu-id="21d77-131">在团队级别还会有一个上载自定义应用设置。</span><span class="sxs-lookup"><span data-stu-id="21d77-131">There's also an upload custom app setting at the team level.</span></span> <span data-ttu-id="21d77-132">默认情况下，此设置为 "打开"。</span><span class="sxs-lookup"><span data-stu-id="21d77-132">By default this setting is on.</span></span> <span data-ttu-id="21d77-133">但是，如果开发人员无法将自定义应用上载到团队，请按照<a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">此处</a>的步骤检查设置。</span><span class="sxs-lookup"><span data-stu-id="21d77-133">However, if developers are unable to upload a custom app to a team, check the setting by following the steps <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">here</a>.</span></span>

### <a name="create-your-app"></a><span data-ttu-id="21d77-134">创建你的应用</span><span class="sxs-lookup"><span data-stu-id="21d77-134">Create your app</span></span>

<span data-ttu-id="21d77-135">开发人员现在应拥有创建你的应用所需的内容。</span><span class="sxs-lookup"><span data-stu-id="21d77-135">Developers should now have what they need to create your app.</span></span> <span data-ttu-id="21d77-136">请参阅<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">此处</a>了解相关指南。</span><span class="sxs-lookup"><span data-stu-id="21d77-136">See <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a> for guidance on that.</span></span>

## <a name="step-2-validate-in-production"></a><span data-ttu-id="21d77-137">步骤2：在生产中验证</span><span class="sxs-lookup"><span data-stu-id="21d77-137">Step 2: Validate in production</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="21d77-138">获取应用包</span><span class="sxs-lookup"><span data-stu-id="21d77-138">Get the app package</span></span>

<span data-ttu-id="21d77-139">当应用准备好在生产中使用时，开发人员应该生成一个应用包。</span><span class="sxs-lookup"><span data-stu-id="21d77-139">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="21d77-140">他们可以使用适用于该<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">应用的应用 Studio</a> 。</span><span class="sxs-lookup"><span data-stu-id="21d77-140">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="21d77-141">他们将以 .zip 格式发送文件。</span><span class="sxs-lookup"><span data-stu-id="21d77-141">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="21d77-142">Microsoft 使用<a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">这些指南</a>确保应用符合全球团队应用商店的质量和安全标准。</span><span class="sxs-lookup"><span data-stu-id="21d77-142">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a><span data-ttu-id="21d77-143">允许受信任的用户在生产租户中上载自定义应用</span><span class="sxs-lookup"><span data-stu-id="21d77-143">Allow trusted users to upload custom apps in the production tenant</span></span>

<span data-ttu-id="21d77-144">若要验证应用是否在你的生产租户中正常工作，你需要允许你的组织中的自己和/或受信任的用户上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="21d77-144">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users in your organization to upload custom apps.</span></span>  <span data-ttu-id="21d77-145">非常类似于前面的<a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">步骤</a>，你可以使用应用设置策略执行此操作。</span><span class="sxs-lookup"><span data-stu-id="21d77-145">Much like in the earlier <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">step</a>, you use app setup policies to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="21d77-146">如果你不满意将应用上载到生产租户进行验证，即使对于你自己或受信任的用户，你也可以跳过此步骤，然后按照步骤3和步骤4将 unvalidated 应用上载到租户应用商店。</span><span class="sxs-lookup"><span data-stu-id="21d77-146">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow steps 3 and 4 to upload the unvalidated app to your tenant app store.</span></span> <span data-ttu-id="21d77-147">然后，将对该应用的访问限制为仅限自己和你信任的用户。</span><span class="sxs-lookup"><span data-stu-id="21d77-147">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="21d77-148">然后，这些用户可以从租户应用商店获取该应用以执行验证。</span><span class="sxs-lookup"><span data-stu-id="21d77-148">These users can then get the app from the tenant app store to perform validation.</span></span> <span data-ttu-id="21d77-149">验证应用后，使用相同的权限策略打开 access，并将应用滚出以供生产使用。</span><span class="sxs-lookup"><span data-stu-id="21d77-149">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="21d77-150">若要允许受信任用户上载自定义应用程序，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="21d77-150">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="21d77-151">启用 "**允许与自定义应用交互**" 组织范围的应用设置。</span><span class="sxs-lookup"><span data-stu-id="21d77-151">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="21d77-152">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="21d77-152">To do this:</span></span>
    1. <span data-ttu-id="21d77-153">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **管理应用**"，然后单击 "**组织范围的应用设置**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-153">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="21d77-154">在 "**自定义应用**" 下，打开 "**允许与自定义应用交互**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-154">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="21d77-155">关闭全局应用设置策略中的 "**上载自定义应用**" 设置。</span><span class="sxs-lookup"><span data-stu-id="21d77-155">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="21d77-156">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="21d77-156">To do this:</span></span>
    1. <span data-ttu-id="21d77-157">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **设置策略**"，然后单击 "**全局（组织范围默认）** " 策略。</span><span class="sxs-lookup"><span data-stu-id="21d77-157">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="21d77-158">关闭 "**上载自定义应用**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-158">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="21d77-159">创建一个新的应用设置策略，该策略允许上载自定义应用并将其分配给你的受信任的用户集。</span><span class="sxs-lookup"><span data-stu-id="21d77-159">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="21d77-160">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="21d77-160">To do this:</span></span>
    1. <span data-ttu-id="21d77-161">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 团队管理中心</a>的左侧导航中，转到 "**团队应用** > **设置策略**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-161">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="21d77-162">为新策略提供名称和说明，打开 "**上载自定义应用**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-162">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="21d77-163">选择您创建的新策略，然后单击 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-163">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="21d77-164">搜索用户，单击 "**添加**"，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-164">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="21d77-165">重复此步骤，将策略分配给所有受信任的用户。</span><span class="sxs-lookup"><span data-stu-id="21d77-165">Repeat this step to assign the policy to all your trusted users.</span></span>

        !["添加应用程序设置策略" 页面的屏幕截图](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="21d77-167">这些用户现在可以上载应用清单，以验证应用是否在生产租户中正常工作。</span><span class="sxs-lookup"><span data-stu-id="21d77-167">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="step-3-upload-to-the-tenant-app-catalog"></a><span data-ttu-id="21d77-168">步骤3：上传到租户应用目录</span><span class="sxs-lookup"><span data-stu-id="21d77-168">Step 3: Upload to the tenant app catalog</span></span>

<span data-ttu-id="21d77-169">若要让租户应用商店中的用户可以使用该应用，请上载该应用。</span><span class="sxs-lookup"><span data-stu-id="21d77-169">To make the app available to users in the tenant app store, upload the app.</span></span> <span data-ttu-id="21d77-170">你可以在 Microsoft 团队管理中心的 "[管理应用](manage-apps.md)" 页面上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="21d77-170">You can do this on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>

![管理中心中 "管理应用" 页面的屏幕截图](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a><span data-ttu-id="21d77-172">步骤4：配置和分配权限</span><span class="sxs-lookup"><span data-stu-id="21d77-172">Step 4: Configure and assign permissions</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="21d77-173">控制对应用的访问</span><span class="sxs-lookup"><span data-stu-id="21d77-173">Control access to the app</span></span>

<span data-ttu-id="21d77-174">默认情况下，所有用户都可以在 "团队应用商店" 中访问此应用。</span><span class="sxs-lookup"><span data-stu-id="21d77-174">By default, all users have access to this app in the the Teams apps store.</span></span> <span data-ttu-id="21d77-175">若要限制和控制谁有权使用该应用程序，你可以创建并分配新的应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="21d77-175">To restrict and control who has permission to use the app, you can create and assign a new app permission policy.</span></span> <span data-ttu-id="21d77-176">请按照<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">此处</a>的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="21d77-176">Follow the steps <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">here</a>.</span></span>

!["添加应用权限策略" 页面的屏幕截图](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a><span data-ttu-id="21d77-178">固定应用以供用户发现</span><span class="sxs-lookup"><span data-stu-id="21d77-178">Pin the app for users to discover</span></span>

<span data-ttu-id="21d77-179">默认情况下，为使用户能够找到此应用，他们将必须转到 "团队应用商店" 和 "浏览" 或 "搜索"。</span><span class="sxs-lookup"><span data-stu-id="21d77-179">By default, for users to find this app they would have to go to Teams apps store and browse or search for it.</span></span> <span data-ttu-id="21d77-180">若要使用户可以轻松访问应用，可以将应用固定到团队中的应用栏。</span><span class="sxs-lookup"><span data-stu-id="21d77-180">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="21d77-181">若要执行此操作，请创建新的应用设置策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="21d77-181">To do this, create a new app setup policy and assign it to users.</span></span> <span data-ttu-id="21d77-182">请按照<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">此处</a>的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="21d77-182">Follow the steps  <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">here</a>.</span></span>

!["添加固定应用" 窗格的屏幕截图](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a><span data-ttu-id="21d77-184">步骤5：更新应用</span><span class="sxs-lookup"><span data-stu-id="21d77-184">Step 5: Update the app</span></span>

![从开发到部署概述应用](media/manage-your-lob-apps-update.png)

<span data-ttu-id="21d77-186">若要更新应用，开发人员应继续执行[步骤 1](#step-1-develop-and-test)和[步骤 2](#step-2-validate-in-production)。</span><span class="sxs-lookup"><span data-stu-id="21d77-186">To update an app, developers should continue to follow [step 1](#step-1-develop-and-test) and [step 2](#step-2-validate-in-production).</span></span>

<span data-ttu-id="21d77-187">你可以通过租户应用目录更新应用。</span><span class="sxs-lookup"><span data-stu-id="21d77-187">You can update the app through the tenant app catalog.</span></span> <span data-ttu-id="21d77-188">若要执行此操作，请在 Microsoft 团队管理中心中，转到 "**团队应用** > **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-188">To do this, in the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="21d77-189">在应用列表中，单击应用名称，然后单击 "**更新**"。</span><span class="sxs-lookup"><span data-stu-id="21d77-189">In the list of apps, click the app name, and then click **Update**.</span></span> <span data-ttu-id="21d77-190">执行此操作将替换租户应用目录中的现有应用，并且所有应用权限策略和应用设置策略都将对已更新的应用强制实施。</span><span class="sxs-lookup"><span data-stu-id="21d77-190">Doing this replaces the existing app in the tenant app catalog, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="21d77-191">最终用户更新体验</span><span class="sxs-lookup"><span data-stu-id="21d77-191">End user update experience</span></span>

<span data-ttu-id="21d77-192">在大多数情况下，完成应用更新后，最终用户将自动显示新版本。</span><span class="sxs-lookup"><span data-stu-id="21d77-192">In most cases, after you complete an app update the new version will automatically appear for end users.</span></span> <span data-ttu-id="21d77-193">但是，对<a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 团队清单</a>有一些更新需要用户接受才能完成：</span><span class="sxs-lookup"><span data-stu-id="21d77-193">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="21d77-194">已添加或删除机器人</span><span class="sxs-lookup"><span data-stu-id="21d77-194">A bot was added or removed</span></span>
* <span data-ttu-id="21d77-195">现有 bot 的 "botId" 属性已更改</span><span class="sxs-lookup"><span data-stu-id="21d77-195">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="21d77-196">现有 bot 的 "isNotificationOnly" 属性已更改</span><span class="sxs-lookup"><span data-stu-id="21d77-196">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="21d77-197">Bot 的 "supportsFiles" 属性已更改</span><span class="sxs-lookup"><span data-stu-id="21d77-197">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="21d77-198">添加或删除了消息传递扩展</span><span class="sxs-lookup"><span data-stu-id="21d77-198">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="21d77-199">添加了新的连接器</span><span class="sxs-lookup"><span data-stu-id="21d77-199">A new connector was added</span></span>
* <span data-ttu-id="21d77-200">添加了新的静态选项卡</span><span class="sxs-lookup"><span data-stu-id="21d77-200">A new static tab was added</span></span>
* <span data-ttu-id="21d77-201">添加了新的 "可配置" 选项卡</span><span class="sxs-lookup"><span data-stu-id="21d77-201">A new configurable tab was added</span></span>
* <span data-ttu-id="21d77-202">"WebApplicationInfo" 中的属性已更改</span><span class="sxs-lookup"><span data-stu-id="21d77-202">Properties inside "webApplicationInfo" changed</span></span>

![应用列表的屏幕截图，显示新版本可用的应用](media/manage-your-custom-apps-update1.png)

![应用的升级选项的屏幕截图](media/manage-your-custom-apps-update2.png)

## <a name="related-apps"></a><span data-ttu-id="21d77-205">相关应用</span><span class="sxs-lookup"><span data-stu-id="21d77-205">Related apps</span></span>

- [<span data-ttu-id="21d77-206">在 Microsoft 团队管理中心中管理你的应用</span><span class="sxs-lookup"><span data-stu-id="21d77-206">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
