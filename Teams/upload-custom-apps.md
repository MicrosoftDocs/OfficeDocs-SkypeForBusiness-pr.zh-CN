---
title: 在 Microsoft Teams 管理中心上传自定义应用
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke, vaibhava
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
description: 了解如何在 Microsoft Teams 管理中心将自定义应用上传到组织的应用商店。
ms.openlocfilehash: f1b5267fe1003d69c0d91349f5b6bc425df2b038
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831162"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="b4ebd-103">通过上传应用包发布自定义应用</span><span class="sxs-lookup"><span data-stu-id="b4ebd-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="b4ebd-104">发布自定义 Teams 应用时，该应用可供组织应用商店中的用户使用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="b4ebd-105">有两种方法可以发布自定义应用，使用方式取决于获取应用的方式。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="b4ebd-106">**本文重点介绍如何发布自定义** 应用，将应用包 (.zip 格式) 开发人员发送给你的应用包。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="b4ebd-107">当开发人员通过 Teams 应用提交 API 将应用直接提交到"管理应用"<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a>页面时，会使用另一种方法（即批准自定义应用）。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="b4ebd-108">若要详细了解该方法，请参阅"发布通过 Teams 应用提交 API 提交的自定义<a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">应用"。</a></span><span class="sxs-lookup"><span data-stu-id="b4ebd-108">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="b4ebd-109">本文提供有关如何将 Teams 应用从开发到部署到发现的端到端指南。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="b4ebd-110">本指南重点介绍应用的 Teams 方面，面向管理员和 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="b4ebd-111">有关开发 Teams 应用的信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams 开发人员文档</a>。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-111">For more information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![从开发到部署的应用的概述](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="b4ebd-113">开发</span><span class="sxs-lookup"><span data-stu-id="b4ebd-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="b4ebd-114">创建应用</span><span class="sxs-lookup"><span data-stu-id="b4ebd-114">Create your app</span></span>

<span data-ttu-id="b4ebd-115">使用 Microsoft Teams 开发人员平台，开发人员可以轻松集成自己的应用和服务，以提高工作效率、更快地做出决策，以及围绕现有内容和工作流创建协作。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="b4ebd-116">基于 Teams 平台构建的应用是 Teams 客户端与服务和工作流之间的桥梁，可将它们直接引入协作平台的上下文中。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="b4ebd-117">有关详细信息，请转到 Teams 开发人员 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">文档</a>。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-117">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="b4ebd-118">验证</span><span class="sxs-lookup"><span data-stu-id="b4ebd-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="b4ebd-119">获取应用包</span><span class="sxs-lookup"><span data-stu-id="b4ebd-119">Get the app package</span></span>

<span data-ttu-id="b4ebd-120">当应用准备好在生产环境中使用时，开发人员应生成应用包。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="b4ebd-121">他们可以使用<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio。</a></span><span class="sxs-lookup"><span data-stu-id="b4ebd-121">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="b4ebd-122">他们将以 .zip 格式发送给你文件。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="b4ebd-123">Microsoft <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">使用这些指南</a> 来确保应用符合全球 Teams 应用存储的质量和安全标准。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-123">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="b4ebd-124">允许受信任的用户上传自定义应用</span><span class="sxs-lookup"><span data-stu-id="b4ebd-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="b4ebd-125">若要验证应用在生产租户中是否正常工作，需要允许你自己和/或受信任的用户上传生产租户中的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="b4ebd-126">可以使用 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">应用设置策略</a> 来这样做。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-126">You use <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ebd-127">如果将应用上传到生产租户进行验证（即使是为自己或受信任的用户）感到不便，可以跳过此步骤，按照"上传和设置和管理"部分中的步骤将未经验证的应用发布到组织的应用商店[](#upload)。 [](#set-up-and-manage)</span><span class="sxs-lookup"><span data-stu-id="b4ebd-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="b4ebd-128">然后，仅你自己和信任的用户可以访问该应用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="b4ebd-129">然后，这些用户可以从组织的应用商店获取应用以执行验证。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="b4ebd-130">验证应用后，使用相同的权限策略打开访问权限，并推出应用供生产使用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="b4ebd-131">若要允许受信任的用户上传自定义应用，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b4ebd-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="b4ebd-132">打开" **允许与自定义应用组织** 范围内的应用交互"设置。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="b4ebd-133">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="b4ebd-133">To do this:</span></span>
    1. <span data-ttu-id="b4ebd-134">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用** 管理应用"，然后单击"  >  **组织范围的应用设置"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="b4ebd-135">在 **"自定义应用**"下，打开 **"允许与自定义应用交互**"，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="b4ebd-136">关闭全局 **应用设置策略中的** "上传自定义应用"设置。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="b4ebd-137">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="b4ebd-137">To do this:</span></span>
    1. <span data-ttu-id="b4ebd-138">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams** 应用设置策略，然后单击"全局 (组织范围内的默认)  >  策略。 </span><span class="sxs-lookup"><span data-stu-id="b4ebd-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="b4ebd-139">关闭"**上传自定义应用"，** 然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="b4ebd-140">创建允许上传自定义应用并将其分配给受信任用户集的新应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="b4ebd-141">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="b4ebd-141">To do this:</span></span>
    1. <span data-ttu-id="b4ebd-142">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams 应用** 设置策略，然后单击"添加  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="b4ebd-143">为新策略指定名称和说明，打开"上传 **自定义** 应用"，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="b4ebd-144">选择创建的新策略，并单击"**管理用户"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="b4ebd-145">搜索用户，单击"添加 **"，** 然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="b4ebd-146">重复此步骤，将策略分配给所有受信任的用户。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        !["添加应用设置策略"页的屏幕截图](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="b4ebd-148">这些用户现在可以上传应用清单，以验证应用在生产租户中是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="b4ebd-149">上传</span><span class="sxs-lookup"><span data-stu-id="b4ebd-149">Upload</span></span>

<span data-ttu-id="b4ebd-150">若要使应用可供组织应用商店中的用户使用，请上传该应用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="b4ebd-151">可以在 Microsoft Teams 管理 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">中心的"管理应用</a> "页面上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-151">You can do this on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b4ebd-152">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="b4ebd-153">单击 **"** 上传"， **单击"选择文件**"，然后选择从开发人员收到的应用包。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![在管理中心上传应用的屏幕截图](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="b4ebd-155">设置和管理</span><span class="sxs-lookup"><span data-stu-id="b4ebd-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="b4ebd-156">控制对应用的访问</span><span class="sxs-lookup"><span data-stu-id="b4ebd-156">Control access to the app</span></span>

<span data-ttu-id="b4ebd-157">默认情况下，组织中的所有用户都可以访问组织应用商店中的应用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="b4ebd-158">若要限制和控制谁有权使用应用，可以创建并分配应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="b4ebd-159">若要了解有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">"在 Teams 中管理应用权限策略"。</a></span><span class="sxs-lookup"><span data-stu-id="b4ebd-159">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="b4ebd-160">固定并安装应用供用户发现</span><span class="sxs-lookup"><span data-stu-id="b4ebd-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="b4ebd-161">默认情况下，用户若要查找应用，必须转到组织的应用商店并浏览或搜索该应用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="b4ebd-162">为了方便用户访问该应用，你可以将应用固定到 Teams 中的应用栏。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="b4ebd-163">为此，请创建应用设置策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="b4ebd-164">若要了解有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">"在 Teams 中管理应用设置策略"。</a></span><span class="sxs-lookup"><span data-stu-id="b4ebd-164">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="b4ebd-165">在审核日志搜索 Teams 应用事件</span><span class="sxs-lookup"><span data-stu-id="b4ebd-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="b4ebd-166">可以搜索应用审核日志查看组织中 Teams 应用活动。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="b4ebd-167">若要详细了解如何搜索 审核日志并查看记录在 审核日志 中的 Teams 活动列表，请参阅"在 审核日志 中搜索 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">活动</a>。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="b4ebd-168">在搜索安全中心审核日志，首先必须打开安全中心& <a href="https://protection.office.com" target="_blank">审核</a>。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="b4ebd-169">若要了解有关详细信息，请参阅 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">审核日志打开或关闭搜索</a>。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="b4ebd-170">请记住，只有启用审核时，审核数据才可用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="b4ebd-171">发现和采用</span><span class="sxs-lookup"><span data-stu-id="b4ebd-171">Discover and adopt</span></span>

<span data-ttu-id="b4ebd-172">对应用具有权限的用户可以在组织的应用商店中查找它。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="b4ebd-173">转到 **"应用 *"页上*** 的"为组织名称构建"，查找组织的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="b4ebd-174">显示已发布应用的应用页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="b4ebd-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="b4ebd-175">如果创建并分配了应用设置策略，该应用将固定到 Teams 中的应用栏，以便分配有该策略的用户轻松访问。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="b4ebd-176">更新</span><span class="sxs-lookup"><span data-stu-id="b4ebd-176">Update</span></span>

<span data-ttu-id="b4ebd-177">若要更新应用，开发人员应继续按照"开发和验证"部分中[的步骤](#validate)操作[](#develop)。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="b4ebd-178">可以在 Microsoft Teams 管理中心的"管理应用"页面上更新应用。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b4ebd-179">为此，在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="b4ebd-180">单击应用名称，然后单击"更新 **"。**</span><span class="sxs-lookup"><span data-stu-id="b4ebd-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="b4ebd-181">执行此操作会替换现有应用，并且所有应用权限策略和应用设置策略仍对更新的应用强制实施。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="b4ebd-182">最终用户更新体验</span><span class="sxs-lookup"><span data-stu-id="b4ebd-182">End user update experience</span></span>

<span data-ttu-id="b4ebd-183">在大多数情况下，完成应用更新后，最终用户会自动显示新版本。</span><span class="sxs-lookup"><span data-stu-id="b4ebd-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="b4ebd-184">但是，Microsoft <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Teams</a> 清单的一些更新需要用户验收才能完成：</span><span class="sxs-lookup"><span data-stu-id="b4ebd-184">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="b4ebd-185">添加或删除了机器人</span><span class="sxs-lookup"><span data-stu-id="b4ebd-185">A bot was added or removed</span></span>
* <span data-ttu-id="b4ebd-186">现有机器人的"botId"属性已更改</span><span class="sxs-lookup"><span data-stu-id="b4ebd-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="b4ebd-187">现有机器人的"isNotificationOnly"属性已更改</span><span class="sxs-lookup"><span data-stu-id="b4ebd-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="b4ebd-188">机器人的"supportsFiles"属性已更改</span><span class="sxs-lookup"><span data-stu-id="b4ebd-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="b4ebd-189">已添加或删除消息传送扩展</span><span class="sxs-lookup"><span data-stu-id="b4ebd-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="b4ebd-190">添加了一个新连接器</span><span class="sxs-lookup"><span data-stu-id="b4ebd-190">A new connector was added</span></span>
* <span data-ttu-id="b4ebd-191">添加了新的静态选项卡</span><span class="sxs-lookup"><span data-stu-id="b4ebd-191">A new static tab was added</span></span>
* <span data-ttu-id="b4ebd-192">添加了新的"可配置"选项卡</span><span class="sxs-lookup"><span data-stu-id="b4ebd-192">A new configurable tab was added</span></span>
* <span data-ttu-id="b4ebd-193">"webApplicationInfo"中的属性已更改</span><span class="sxs-lookup"><span data-stu-id="b4ebd-193">Properties inside "webApplicationInfo" changed</span></span>

![应用列表的屏幕截图，其中显示了提供新版本的应用](media/manage-your-custom-apps-update1.png)

![应用的升级选项屏幕截图](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="b4ebd-196">相关主题</span><span class="sxs-lookup"><span data-stu-id="b4ebd-196">Related topics</span></span>

- [<span data-ttu-id="b4ebd-197">发布通过 Teams 应用提交 API 提交的自定义应用</span><span class="sxs-lookup"><span data-stu-id="b4ebd-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="b4ebd-198">在 Microsoft Teams 管理中心管理应用</span><span class="sxs-lookup"><span data-stu-id="b4ebd-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="b4ebd-199">在 Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="b4ebd-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="b4ebd-200">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="b4ebd-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="b4ebd-201">在 Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="b4ebd-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
