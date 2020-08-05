---
title: 使用团队应用提交 API 提交和批准自定义应用
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
description: 了解如何使用 Microsoft 团队中的团队应用提交 API 批准已提交的自定义应用。
ms.openlocfilehash: 6efb6a6c1541b7ea7e252b132c0ea891560bbdb6
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552598"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="bb8eb-103">发布通过团队应用提交 API 提交的自定义应用</span><span class="sxs-lookup"><span data-stu-id="bb8eb-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="bb8eb-104">概述</span><span class="sxs-lookup"><span data-stu-id="bb8eb-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="bb8eb-105">发布自定义团队应用时，用户可在组织的应用商店中使用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="bb8eb-106">发布自定义应用的方法有两种，使用方式取决于你获取该应用的方式。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="bb8eb-107">**本文重点介绍如何批准和发布开发人员通过团队应用提交 API 提交的自定义应用**。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="bb8eb-108">当开发人员以 .zip 格式发送应用包时，将使用另一种方法，即上载自定义应用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="bb8eb-109">若要了解有关该方法的详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">通过上载应用包发布自定义应用</a>。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-109">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span>
 
<span data-ttu-id="bb8eb-110">本文提供了有关如何将你的团队应用从开发转到部署到发现的端到端指南。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-110">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="bb8eb-111">你将大致了解团队在应用生命周期中提供的连接体验，以简化如何在组织的应用商店中开发、部署和管理自定义应用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-111">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="bb8eb-112">我们将介绍生命周期的每个步骤，包括开发人员如何使用团队应用提交 API 将自定义应用直接提交到 Microsoft 团队管理中心供你查看和批准，如何设置策略以管理你组织中的用户的应用，以及你的用户如何在团队中发现这些应用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-112">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![从开发到部署概述应用](media/custom-app-lifecycle.png)

<span data-ttu-id="bb8eb-114">本指南重点介绍应用的团队方面，并面向管理员和 IT 专业人士。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-114">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="bb8eb-115">有关开发团队应用的信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">团队开发人员文档</a>。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-115">For information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="bb8eb-116">开发</span><span class="sxs-lookup"><span data-stu-id="bb8eb-116">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="bb8eb-117">创建应用</span><span class="sxs-lookup"><span data-stu-id="bb8eb-117">Create the app</span></span>

<span data-ttu-id="bb8eb-118">Microsoft 团队开发人员平台使开发人员可以轻松地集成你自己的应用和服务，以提高工作效率、更快地做出决策以及围绕现有内容和工作流创建协作。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-118">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="bb8eb-119">在团队平台上构建的应用是团队客户端和你的服务和工作流之间的桥梁，可直接将它们引入协作平台的上下文中。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-119">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="bb8eb-120">有关详细信息，请转到<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">团队开发人员文档</a>。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-120">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="bb8eb-121">提交应用</span><span class="sxs-lookup"><span data-stu-id="bb8eb-121">Submit the app</span></span>

<span data-ttu-id="bb8eb-122">当应用准备好在生产中使用时，开发人员可以使用团队应用提交 API 提交应用，该 API 可以从 Graph API 中调用，集成开发环境 (IDE) （如 Visual Studio 代码）或诸如 Power App 和 Power Virtual Agent 之类的平台。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-122">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from Graph API, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="bb8eb-123">执行此操作将使应用在 Microsoft 团队管理中心的 "<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理应用</a>" 页面上可用，你的管理员可以在其中查看和批准该应用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-123">Doing this makes the app available on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span> 

<span data-ttu-id="bb8eb-124">在 Microsoft Graph 上构建的团队应用提交 API 允许你的组织在你选择的平台上进行开发，并为团队中的自定义应用自动执行提交到审批流程。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-124">The Teams App Submission API, built on Microsoft Graph, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="bb8eb-125">下面是此应用提交步骤在 Visual Studio 代码中的外观示例：</span><span class="sxs-lookup"><span data-stu-id="bb8eb-125">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![在 Visual Studio 代码中提交应用的屏幕截图](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="bb8eb-127">请记住，这并不会将应用发布到你的组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-127">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="bb8eb-128">此步骤将应用提交到 Microsoft 团队管理中心，你可以在其中批准将其发布到你的组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-128">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

## <a name="validate"></a><span data-ttu-id="bb8eb-129">复核</span><span class="sxs-lookup"><span data-stu-id="bb8eb-129">Validate</span></span>

<span data-ttu-id="bb8eb-130">Microsoft 团队管理中心 (中的 "<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理应用</a>" 页面在左侧导航中，转到 "**团队应用**  >  **管理应用**") ，为你的组织提供所有团队应用的视图。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-130">The <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="bb8eb-131">页面顶部的 "**待定审批**" 小组件可让你知道何时提交自定义应用以供审批。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-131">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="bb8eb-132">在表格中，新提交的应用会自动显示已提交**状态**的 "已**提交**" 和 "已**阻止**"**状态**。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-132">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="bb8eb-133">可以按降序对 "**发布状态**" 列进行排序，以便快速找到该应用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-133">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="bb8eb-134">"管理应用" 页面的屏幕截图，显示挂起的请求和应用状态</span><span class="sxs-lookup"><span data-stu-id="bb8eb-134">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="bb8eb-135">单击应用名称以转到 "应用详细信息" 页面。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-135">Click the app name to go to the app details page.</span></span> <span data-ttu-id="bb8eb-136">在 "**关于**" 选项卡上，您可以查看有关应用的详细信息，包括说明、状态、提交者和应用 ID。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-136">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

![已提交应用的应用程序详细信息页面的屏幕截图](media/custom-app-lifecycle-app-details.png)

## <a name="publish"></a><span data-ttu-id="bb8eb-138">发布</span><span class="sxs-lookup"><span data-stu-id="bb8eb-138">Publish</span></span>

<span data-ttu-id="bb8eb-139">当你准备好使应用可供用户使用时，请发布应用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-139">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="bb8eb-140">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-140">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="bb8eb-141">单击应用名称转到 "应用程序详细信息" 页，然后在 "**发布状态**" 框中，选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-141">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="bb8eb-142">发布应用后，**发布状态**将更改为 "**已发布**"，"**状态**" 将自动更改为 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-142">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="bb8eb-143">设置和管理</span><span class="sxs-lookup"><span data-stu-id="bb8eb-143">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="bb8eb-144">控制对应用的访问</span><span class="sxs-lookup"><span data-stu-id="bb8eb-144">Control access to the app</span></span>

<span data-ttu-id="bb8eb-145">默认情况下，组织中的所有用户都可以访问组织的应用商店中的应用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-145">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="bb8eb-146">若要限制和控制谁有权使用该应用程序，你可以创建并分配应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-146">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="bb8eb-147">若要了解详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">管理团队中的应用权限策略</a>。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-147">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="bb8eb-148">固定并安装应用以供用户发现</span><span class="sxs-lookup"><span data-stu-id="bb8eb-148">Pin and install the app for users to discover</span></span>

<span data-ttu-id="bb8eb-149">默认情况下，用户可以使用该应用程序找到你的组织的应用商店所需的应用，然后浏览或搜索它。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-149">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="bb8eb-150">若要使用户可以轻松访问应用，可以将应用固定到团队中的应用栏。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-150">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="bb8eb-151">若要执行此操作，请创建应用设置策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-151">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="bb8eb-152">若要了解详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">管理团队中的应用设置策略</a>。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-152">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="bb8eb-153">探索和采纳</span><span class="sxs-lookup"><span data-stu-id="bb8eb-153">Discover and adopt</span></span>

<span data-ttu-id="bb8eb-154">具有应用权限的用户可以在你的组织的应用商店中找到它。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-154">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="bb8eb-155">转到 "应用" 页面上的 "为\***你的组织名称\*生成**" 以查找你的组织的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-155">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="bb8eb-156">显示已发布应用的 "应用" 页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="bb8eb-156">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="bb8eb-157">如果你创建并分配了应用设置策略，应用将固定到团队中的应用栏，以便为分配了该策略的用户轻松访问。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-157">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="bb8eb-158">更新</span><span class="sxs-lookup"><span data-stu-id="bb8eb-158">Update</span></span>

<span data-ttu-id="bb8eb-159">若要更新应用，开发人员应继续按照 "[开发](#develop)" 部分中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-159">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="bb8eb-160">当开发人员向已发布的自定义应用程序提交更新时，将在 "<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理应用程序</a>" 页面的 "**挂起审批**" 小组件中收到通知。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-160">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="bb8eb-161">在表中，应用的**发布状态**将设置为 "已**提交更新**"。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-161">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="bb8eb-162">"管理应用" 页面的屏幕截图，显示挂起的请求和应用状态</span><span class="sxs-lookup"><span data-stu-id="bb8eb-162">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="bb8eb-163">要查看和发布应用更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bb8eb-163">To review and publish an app update:</span></span>

1. <span data-ttu-id="bb8eb-164">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-164">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="bb8eb-165">单击应用名称转到 "应用详细信息" 页面，然后选择 "**更新可用**" 以查看更新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-165">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![<span data-ttu-id="bb8eb-166">"管理应用" 页面的屏幕截图，显示挂起的请求和应用状态</span><span class="sxs-lookup"><span data-stu-id="bb8eb-166">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="bb8eb-167">准备就绪后，选择 "**发布**" 以发布更新。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-167">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="bb8eb-168">执行此操作将替换现有应用、更新版本号，并将**发布状态**更改为 "**已发布**"。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-168">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="bb8eb-169">所有应用权限策略和应用设置策略对于更新的应用均保持强制实施。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-169">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="bb8eb-170">如果拒绝更新，则早期版本的应用仍将发布。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-170">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="bb8eb-171">请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="bb8eb-171">Keep in mind the following:</span></span>

- <span data-ttu-id="bb8eb-172">当应用获得批准后，任何人都可以向应用提交更新。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-172">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="bb8eb-173">这意味着其他开发人员（包括最初提交该应用的开发人员）可以提交对该应用的更新。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-173">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="bb8eb-174">当开发人员提交应用且请求处于挂起状态时，仅该开发人员可以向该应用提交更新。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-174">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="bb8eb-175">其他开发人员只能在应用获得批准后提交更新。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-175">Other developers can submit an update only after the app is approved.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="bb8eb-176">用户更新体验</span><span class="sxs-lookup"><span data-stu-id="bb8eb-176">Update experience for users</span></span>

<span data-ttu-id="bb8eb-177">在大多数情况下，发布应用更新后，将自动为用户显示新版本。</span><span class="sxs-lookup"><span data-stu-id="bb8eb-177">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="bb8eb-178">但是，对<a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 团队清单</a>有一些更新需要用户接受才能完成：</span><span class="sxs-lookup"><span data-stu-id="bb8eb-178">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="bb8eb-179">已添加或删除机器人</span><span class="sxs-lookup"><span data-stu-id="bb8eb-179">A bot was added or removed</span></span>
* <span data-ttu-id="bb8eb-180">现有 bot 的 "botId" 属性已更改</span><span class="sxs-lookup"><span data-stu-id="bb8eb-180">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="bb8eb-181">现有 bot 的 "isNotificationOnly" 属性已更改</span><span class="sxs-lookup"><span data-stu-id="bb8eb-181">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="bb8eb-182">Bot 的 "supportsFiles" 属性已更改</span><span class="sxs-lookup"><span data-stu-id="bb8eb-182">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="bb8eb-183">添加或删除了消息传递扩展</span><span class="sxs-lookup"><span data-stu-id="bb8eb-183">A messaging extension was added or removed</span></span>
* <span data-ttu-id="bb8eb-184">添加了新的连接器</span><span class="sxs-lookup"><span data-stu-id="bb8eb-184">A new connector was added</span></span>
* <span data-ttu-id="bb8eb-185">添加了新的静态选项卡</span><span class="sxs-lookup"><span data-stu-id="bb8eb-185">A new static tab was added</span></span>
* <span data-ttu-id="bb8eb-186">添加了新的 "可配置" 选项卡</span><span class="sxs-lookup"><span data-stu-id="bb8eb-186">A new configurable tab was added</span></span>
* <span data-ttu-id="bb8eb-187">"WebApplicationInfo" 中的属性已更改</span><span class="sxs-lookup"><span data-stu-id="bb8eb-187">Properties inside "webApplicationInfo" changed</span></span>

![显示新版本可用的应用的屏幕截图](media/manage-your-custom-apps-update1.png)

![应用的升级选项的屏幕截图](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="bb8eb-190">相关主题</span><span class="sxs-lookup"><span data-stu-id="bb8eb-190">Related topics</span></span>

- [<span data-ttu-id="bb8eb-191">通过上载应用包发布自定义应用</span><span class="sxs-lookup"><span data-stu-id="bb8eb-191">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="bb8eb-192">在 Microsoft 团队管理中心中管理你的应用</span><span class="sxs-lookup"><span data-stu-id="bb8eb-192">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="bb8eb-193">在 Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="bb8eb-193">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="bb8eb-194">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="bb8eb-194">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="bb8eb-195">在 Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="bb8eb-195">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
