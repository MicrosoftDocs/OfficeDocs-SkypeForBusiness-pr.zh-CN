---
title: 将自定义应用上载到 Microsoft 团队管理中心
author: lanachin
ms.author: v-lanac
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
description: 了解如何将自定义应用上载到 Microsoft 团队管理中心中的组织的应用商店。
ms.openlocfilehash: d43b19f4ada3ce6f0424a324cdea6f194575325b
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583641"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="8498e-103">通过上载应用包发布自定义应用</span><span class="sxs-lookup"><span data-stu-id="8498e-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="8498e-104">发布自定义团队应用时，用户可在组织的应用商店中使用。</span><span class="sxs-lookup"><span data-stu-id="8498e-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="8498e-105">发布自定义应用的方法有两种，使用方式取决于你获取该应用的方式。</span><span class="sxs-lookup"><span data-stu-id="8498e-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="8498e-106">**本文重点介绍如何发布自定义应用，方法是使用 (以 .zip 格式) 开发人员发送的方式上载该应用包**。</span><span class="sxs-lookup"><span data-stu-id="8498e-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="8498e-107">当开发人员通过团队应用提交 API 将应用直接提交到 "<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理应用</a>程序" 页面时，将使用另一个方法，即审批自定义应用。</span><span class="sxs-lookup"><span data-stu-id="8498e-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="8498e-108">若要了解有关该方法的详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">发布通过团队应用提交 API 提交的自定义应用</a>。</span><span class="sxs-lookup"><span data-stu-id="8498e-108">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="8498e-109">本文提供了有关如何将你的团队应用从开发转到部署到发现的端到端指南。</span><span class="sxs-lookup"><span data-stu-id="8498e-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="8498e-110">本指南重点介绍应用的团队方面，并面向管理员和 IT 专业人士。</span><span class="sxs-lookup"><span data-stu-id="8498e-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="8498e-111">有关开发团队应用的详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">团队开发人员文档</a>。</span><span class="sxs-lookup"><span data-stu-id="8498e-111">For more information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![从开发到部署概述应用](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="8498e-113">开发</span><span class="sxs-lookup"><span data-stu-id="8498e-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="8498e-114">创建你的应用</span><span class="sxs-lookup"><span data-stu-id="8498e-114">Create your app</span></span>

<span data-ttu-id="8498e-115">Microsoft 团队开发人员平台使开发人员可以轻松地集成你自己的应用和服务，以提高工作效率、更快地做出决策以及围绕现有内容和工作流创建协作。</span><span class="sxs-lookup"><span data-stu-id="8498e-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="8498e-116">在团队平台上构建的应用是团队客户端和你的服务和工作流之间的桥梁，可直接将它们引入协作平台的上下文中。</span><span class="sxs-lookup"><span data-stu-id="8498e-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="8498e-117">有关详细信息，请转到<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">团队开发人员文档</a>。</span><span class="sxs-lookup"><span data-stu-id="8498e-117">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="8498e-118">复核</span><span class="sxs-lookup"><span data-stu-id="8498e-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="8498e-119">获取应用包</span><span class="sxs-lookup"><span data-stu-id="8498e-119">Get the app package</span></span>

<span data-ttu-id="8498e-120">当应用准备好在生产中使用时，开发人员应该生成一个应用包。</span><span class="sxs-lookup"><span data-stu-id="8498e-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="8498e-121">他们可以使用适用于该<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">应用的应用 Studio</a> 。</span><span class="sxs-lookup"><span data-stu-id="8498e-121">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="8498e-122">他们将以 .zip 格式发送文件。</span><span class="sxs-lookup"><span data-stu-id="8498e-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="8498e-123">Microsoft 使用<a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">这些指南</a>确保应用符合全球团队应用商店的质量和安全标准。</span><span class="sxs-lookup"><span data-stu-id="8498e-123">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="8498e-124">允许受信任的用户上载自定义应用</span><span class="sxs-lookup"><span data-stu-id="8498e-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="8498e-125">若要验证应用是否在你的生产租户中正常工作，你需要允许你自己和/或受信任的用户在生产租户中上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="8498e-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="8498e-126">你可以使用<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">应用设置策略</a>执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8498e-126">You use <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="8498e-127">如果你不满意将应用上载到生产租户进行验证，即使对于你自己或受信任的用户，你也可以跳过此步骤，然后按照[上传](#upload)和[设置和管理](#set-up-and-manage)部分中的步骤将 unvalidated 应用发布到你的组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="8498e-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="8498e-128">然后，将对该应用的访问限制为仅限自己和你信任的用户。</span><span class="sxs-lookup"><span data-stu-id="8498e-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="8498e-129">然后，这些用户可以从您的组织的应用商店获取该应用以执行验证。</span><span class="sxs-lookup"><span data-stu-id="8498e-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="8498e-130">验证应用后，使用相同的权限策略打开 access，并将应用滚出以供生产使用。</span><span class="sxs-lookup"><span data-stu-id="8498e-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="8498e-131">若要允许受信任用户上载自定义应用程序，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8498e-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="8498e-132">启用 "**允许与自定义应用交互**" 组织范围的应用设置。</span><span class="sxs-lookup"><span data-stu-id="8498e-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="8498e-133">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="8498e-133">To do this:</span></span>
    1. <span data-ttu-id="8498e-134">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"，然后单击 "**组织范围的应用设置**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="8498e-135">在 "**自定义应用**" 下，打开 "**允许与自定义应用交互**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="8498e-136">关闭全局应用设置策略中的 "**上载自定义应用**" 设置。</span><span class="sxs-lookup"><span data-stu-id="8498e-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="8498e-137">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="8498e-137">To do this:</span></span>
    1. <span data-ttu-id="8498e-138">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **设置策略**"，然后单击 "\*\*全局 (组织范围的默认) \*\*策略"。</span><span class="sxs-lookup"><span data-stu-id="8498e-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="8498e-139">关闭 "**上载自定义应用**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="8498e-140">创建一个新的应用设置策略，该策略允许上载自定义应用并将其分配给你的受信任的用户集。</span><span class="sxs-lookup"><span data-stu-id="8498e-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="8498e-141">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="8498e-141">To do this:</span></span>
    1. <span data-ttu-id="8498e-142">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **设置策略**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="8498e-143">为新策略提供名称和说明，打开 "**上载自定义应用**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="8498e-144">选择您创建的新策略，然后单击 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="8498e-145">搜索用户，单击 "**添加**"，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="8498e-146">重复此步骤，将策略分配给所有受信任的用户。</span><span class="sxs-lookup"><span data-stu-id="8498e-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        !["添加应用程序设置策略" 页面的屏幕截图](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="8498e-148">这些用户现在可以上载应用清单，以验证应用是否在生产租户中正常工作。</span><span class="sxs-lookup"><span data-stu-id="8498e-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="8498e-149">加载</span><span class="sxs-lookup"><span data-stu-id="8498e-149">Upload</span></span>

<span data-ttu-id="8498e-150">若要让你的组织的应用商店中的用户可以使用该应用，请上载该应用。</span><span class="sxs-lookup"><span data-stu-id="8498e-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="8498e-151">你可以在 Microsoft 团队管理中心的 "<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理应用</a>" 页面上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8498e-151">You can do this on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="8498e-152">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="8498e-153">单击 "**上载**"，单击 "**选择文件**"，然后选择从开发人员处收到的应用包。</span><span class="sxs-lookup"><span data-stu-id="8498e-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![在管理中心中上载应用的屏幕截图](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="8498e-155">设置和管理</span><span class="sxs-lookup"><span data-stu-id="8498e-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="8498e-156">控制对应用的访问</span><span class="sxs-lookup"><span data-stu-id="8498e-156">Control access to the app</span></span>

<span data-ttu-id="8498e-157">默认情况下，组织中的所有用户都可以访问组织的应用商店中的应用。</span><span class="sxs-lookup"><span data-stu-id="8498e-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="8498e-158">若要限制和控制谁有权使用该应用程序，你可以创建并分配应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="8498e-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="8498e-159">若要了解详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">管理团队中的应用权限策略</a>。</span><span class="sxs-lookup"><span data-stu-id="8498e-159">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="8498e-160">固定并安装应用以供用户发现</span><span class="sxs-lookup"><span data-stu-id="8498e-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="8498e-161">默认情况下，用户可以使用该应用程序找到你的组织的应用商店所需的应用，然后浏览或搜索它。</span><span class="sxs-lookup"><span data-stu-id="8498e-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="8498e-162">若要使用户可以轻松访问应用，可以将应用固定到团队中的应用栏。</span><span class="sxs-lookup"><span data-stu-id="8498e-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="8498e-163">若要执行此操作，请创建应用设置策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="8498e-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="8498e-164">若要了解详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">管理团队中的应用设置策略</a>。</span><span class="sxs-lookup"><span data-stu-id="8498e-164">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="8498e-165">在审核日志中搜索团队应用事件</span><span class="sxs-lookup"><span data-stu-id="8498e-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="8498e-166">你可以搜索审核日志以查看你的组织中的团队应用活动。</span><span class="sxs-lookup"><span data-stu-id="8498e-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="8498e-167">若要了解有关如何搜索审核日志和查看审核日志中记录的团队活动列表的详细信息，请参阅在<a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">审核日志中搜索团队中的事件</a>。</span><span class="sxs-lookup"><span data-stu-id="8498e-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="8498e-168">在搜索审核日志之前，必须先在<a href="https://protection.office.com" target="_blank">安全 & 合规中心</a>启用审核。</span><span class="sxs-lookup"><span data-stu-id="8498e-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="8498e-169">若要了解详细信息，请参阅<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">打开或关闭审核日志搜索</a>。</span><span class="sxs-lookup"><span data-stu-id="8498e-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="8498e-170">请记住，审核数据仅在你打开审核的位置可用。</span><span class="sxs-lookup"><span data-stu-id="8498e-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="8498e-171">探索和采纳</span><span class="sxs-lookup"><span data-stu-id="8498e-171">Discover and adopt</span></span>

<span data-ttu-id="8498e-172">具有应用权限的用户可以在你的组织的应用商店中找到它。</span><span class="sxs-lookup"><span data-stu-id="8498e-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="8498e-173">转到 "应用" 页面上的 "为\***你的组织名称\*生成**" 以查找你的组织的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="8498e-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="8498e-174">显示已发布应用的 "应用" 页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="8498e-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="8498e-175">如果你创建并分配了应用设置策略，应用将固定到团队中的应用栏，以便为分配了该策略的用户轻松访问。</span><span class="sxs-lookup"><span data-stu-id="8498e-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="8498e-176">更新</span><span class="sxs-lookup"><span data-stu-id="8498e-176">Update</span></span>

<span data-ttu-id="8498e-177">若要更新应用，开发人员应继续按照 "[开发](#develop)和[验证](#validate)" 部分中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="8498e-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="8498e-178">可以在 Microsoft 团队管理中心的 "管理应用程序" 页面上更新该应用。</span><span class="sxs-lookup"><span data-stu-id="8498e-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8498e-179">若要执行此操作，请在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="8498e-180">单击 "应用名称"，然后单击 "**更新**"。</span><span class="sxs-lookup"><span data-stu-id="8498e-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="8498e-181">执行此操作将替换现有应用，并且所有应用权限策略和应用设置策略都将对已更新的应用保持强制。</span><span class="sxs-lookup"><span data-stu-id="8498e-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="8498e-182">最终用户更新体验</span><span class="sxs-lookup"><span data-stu-id="8498e-182">End user update experience</span></span>

<span data-ttu-id="8498e-183">在大多数情况下，完成应用更新后，最终用户将自动显示新版本。</span><span class="sxs-lookup"><span data-stu-id="8498e-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="8498e-184">但是，对<a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 团队清单</a>有一些更新需要用户接受才能完成：</span><span class="sxs-lookup"><span data-stu-id="8498e-184">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="8498e-185">已添加或删除机器人</span><span class="sxs-lookup"><span data-stu-id="8498e-185">A bot was added or removed</span></span>
* <span data-ttu-id="8498e-186">现有 bot 的 "botId" 属性已更改</span><span class="sxs-lookup"><span data-stu-id="8498e-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="8498e-187">现有 bot 的 "isNotificationOnly" 属性已更改</span><span class="sxs-lookup"><span data-stu-id="8498e-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="8498e-188">Bot 的 "supportsFiles" 属性已更改</span><span class="sxs-lookup"><span data-stu-id="8498e-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="8498e-189">添加或删除了消息传递扩展</span><span class="sxs-lookup"><span data-stu-id="8498e-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="8498e-190">添加了新的连接器</span><span class="sxs-lookup"><span data-stu-id="8498e-190">A new connector was added</span></span>
* <span data-ttu-id="8498e-191">添加了新的静态选项卡</span><span class="sxs-lookup"><span data-stu-id="8498e-191">A new static tab was added</span></span>
* <span data-ttu-id="8498e-192">添加了新的 "可配置" 选项卡</span><span class="sxs-lookup"><span data-stu-id="8498e-192">A new configurable tab was added</span></span>
* <span data-ttu-id="8498e-193">"WebApplicationInfo" 中的属性已更改</span><span class="sxs-lookup"><span data-stu-id="8498e-193">Properties inside "webApplicationInfo" changed</span></span>

![应用列表的屏幕截图，显示新版本可用的应用](media/manage-your-custom-apps-update1.png)

![应用的升级选项的屏幕截图](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="8498e-196">相关主题</span><span class="sxs-lookup"><span data-stu-id="8498e-196">Related topics</span></span>

- [<span data-ttu-id="8498e-197">发布通过团队应用提交 API 提交的自定义应用</span><span class="sxs-lookup"><span data-stu-id="8498e-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="8498e-198">在 Microsoft 团队管理中心中管理你的应用</span><span class="sxs-lookup"><span data-stu-id="8498e-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="8498e-199">在 Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="8498e-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="8498e-200">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="8498e-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="8498e-201">在 Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="8498e-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
