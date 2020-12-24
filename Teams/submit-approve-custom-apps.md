---
title: 使用 Teams 应用提交 API 提交和批准自定义应用
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
description: 了解如何批准使用 Microsoft Teams 中的 Teams 应用提交 API 提交的自定义应用。
ms.openlocfilehash: 5b6c8512943527a82b3477579e535bcc151331c0
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731090"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="df2c9-103">发布通过 Teams 应用提交 API 提交的自定义应用</span><span class="sxs-lookup"><span data-stu-id="df2c9-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="df2c9-104">概述</span><span class="sxs-lookup"><span data-stu-id="df2c9-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="df2c9-105">发布自定义 Teams 应用时，该应用可供组织应用商店中的用户使用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="df2c9-106">有两种方法可以发布自定义应用，使用方式取决于获取应用的方式。</span><span class="sxs-lookup"><span data-stu-id="df2c9-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="df2c9-107">**本文重点介绍如何批准和发布** 开发人员通过 Teams 应用提交 API 提交的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="df2c9-108">当开发人员以 .zip 格式发送给你应用包时，会使用上传自定义应用的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="df2c9-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="df2c9-109">若要详细了解该方法，请参阅"通过<a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">上传应用包发布自定义应用"。</a></span><span class="sxs-lookup"><span data-stu-id="df2c9-109">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span>

<span data-ttu-id="df2c9-110">本文提供有关如何将 Teams 应用从开发到部署到发现的端到端指南。</span><span class="sxs-lookup"><span data-stu-id="df2c9-110">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="df2c9-111">你将大致了解 Teams 在应用生命周期中提供的连接体验，以简化在组织的应用商店中开发、部署和管理自定义应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-111">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="df2c9-112">我们将介绍生命周期的每个步骤，包括开发人员如何使用 Teams 应用提交 API 将自定义应用直接提交到 Microsoft Teams 管理中心供你查看和批准、如何设置策略来管理组织中用户的应用，以及用户如何在 Teams 中发现它们。</span><span class="sxs-lookup"><span data-stu-id="df2c9-112">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![从开发到部署的应用的概述](media/custom-app-lifecycle.png)

<span data-ttu-id="df2c9-114">本指南重点介绍应用的 Teams 方面，面向管理员和 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="df2c9-114">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="df2c9-115">有关开发 Teams 应用的信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams 开发人员文档</a>。</span><span class="sxs-lookup"><span data-stu-id="df2c9-115">For information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="df2c9-116">开发</span><span class="sxs-lookup"><span data-stu-id="df2c9-116">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="df2c9-117">创建应用</span><span class="sxs-lookup"><span data-stu-id="df2c9-117">Create the app</span></span>

<span data-ttu-id="df2c9-118">使用 Microsoft Teams 开发人员平台，开发人员可以轻松集成自己的应用和服务，以提高工作效率、更快地做出决策，以及围绕现有内容和工作流创建协作。</span><span class="sxs-lookup"><span data-stu-id="df2c9-118">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="df2c9-119">基于 Teams 平台构建的应用是 Teams 客户端与服务和工作流之间的桥梁，可将它们直接引入协作平台的上下文中。</span><span class="sxs-lookup"><span data-stu-id="df2c9-119">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="df2c9-120">有关详细信息，请转到 Teams 开发人员 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">文档</a>。</span><span class="sxs-lookup"><span data-stu-id="df2c9-120">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="df2c9-121">提交应用</span><span class="sxs-lookup"><span data-stu-id="df2c9-121">Submit the app</span></span>

<span data-ttu-id="df2c9-122">当应用准备好在生产环境中使用时，开发人员可以使用 Teams 应用提交 <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">API（可以从图形 API、</a>集成开发环境 (IDE) （如 Visual Studio Code）或平台（如 Power Apps 和 Power Virtual Agents）调用该应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-122">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="df2c9-123">这样，应用就可以在 Microsoft <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a> Teams 管理中心的"管理应用"页面上使用，你（管理员）可以在其中查看和批准该应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-123">Doing this makes the app available on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span>

<span data-ttu-id="df2c9-124">构建在 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph</a>上的 Teams 应用提交 API 允许组织在选择的平台上进行开发，并自动执行 Teams 上自定义应用的提交到审批过程。</span><span class="sxs-lookup"><span data-stu-id="df2c9-124">The Teams App Submission API, <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="df2c9-125">下面是此应用提交步骤在应用代码中的外观Visual Studio示例：</span><span class="sxs-lookup"><span data-stu-id="df2c9-125">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![在 Visual Studio Code 中提交应用](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="df2c9-127">请记住，这不会将应用发布到组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="df2c9-127">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="df2c9-128">此步骤将应用提交到 Microsoft Teams 管理中心，可在其中批准该应用发布到组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="df2c9-128">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id="df2c9-129">有关使用图形 API 提交应用的信息，请参阅 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">此处</a>。</span><span class="sxs-lookup"><span data-stu-id="df2c9-129">For more information about using the Graph API to submit apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">here</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="df2c9-130">验证</span><span class="sxs-lookup"><span data-stu-id="df2c9-130">Validate</span></span>

<span data-ttu-id="df2c9-131">Microsoft <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a> Teams 管理中心中的"管理应用" (左侧导航栏中，转到 **"管理** 应用") ，查看组织的所有  >  Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-131">The <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="df2c9-132">页面 **顶部的** "待定审批"小组件可让你了解何时提交自定义应用进行审批。</span><span class="sxs-lookup"><span data-stu-id="df2c9-132">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="df2c9-133">在表中，新提交的应用会自动显示"已提交"和"已 **阻止状态\*\*\*\*"的发布状态**。</span><span class="sxs-lookup"><span data-stu-id="df2c9-133">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="df2c9-134">你可以按降 **序对"发布** 状态"列进行排序以快速找到该应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-134">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="df2c9-135">发布状态</span><span class="sxs-lookup"><span data-stu-id="df2c9-135">publishing status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="df2c9-136">单击应用名称转到应用详细信息页。</span><span class="sxs-lookup"><span data-stu-id="df2c9-136">Click the app name to go to the app details page.</span></span> <span data-ttu-id="df2c9-137">在 **"关于** "选项卡上，可以查看有关应用的详细信息，包括说明、状态、提交者以及应用 ID。</span><span class="sxs-lookup"><span data-stu-id="df2c9-137">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

<span data-ttu-id="df2c9-138">已提交应用的 ！应用详细信息页] (媒体/custom-app-lifecycle-app-details.png) </span><span class="sxs-lookup"><span data-stu-id="df2c9-138">!app details page for a submitted app](media/custom-app-lifecycle-app-details.png)</span></span>

<span data-ttu-id="df2c9-139">有关使用图形 API 检查发布 **状态的信息**，请参阅 <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">此处</a>。</span><span class="sxs-lookup"><span data-stu-id="df2c9-139">For more information about using the Graph API to check the **Publishing status**, see <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="df2c9-140">发布</span><span class="sxs-lookup"><span data-stu-id="df2c9-140">Publish</span></span>

<span data-ttu-id="df2c9-141">当你准备好使应用可供用户使用时，请发布该应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-141">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="df2c9-142">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="df2c9-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="df2c9-143">单击应用名称转到应用详细信息页，然后在"发布状态"框中选择"发布 **"。**</span><span class="sxs-lookup"><span data-stu-id="df2c9-143">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="df2c9-144">发布应用后，"发布"**状态将更改** 为 **"** 已发布"，"**状态"会自动** 更改为"允许 **"。**</span><span class="sxs-lookup"><span data-stu-id="df2c9-144">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="df2c9-145">设置和管理</span><span class="sxs-lookup"><span data-stu-id="df2c9-145">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="df2c9-146">控制对应用的访问</span><span class="sxs-lookup"><span data-stu-id="df2c9-146">Control access to the app</span></span>

<span data-ttu-id="df2c9-147">默认情况下，组织中的所有用户都可以访问组织应用商店中的应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-147">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="df2c9-148">若要限制和控制谁有权使用应用，可以创建并分配应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="df2c9-148">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="df2c9-149">若要了解有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">"在 Teams 中管理应用权限策略"。</a></span><span class="sxs-lookup"><span data-stu-id="df2c9-149">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="df2c9-150">固定并安装应用供用户发现</span><span class="sxs-lookup"><span data-stu-id="df2c9-150">Pin and install the app for users to discover</span></span>

<span data-ttu-id="df2c9-151">默认情况下，用户若要查找应用，必须转到组织的应用商店并浏览或搜索该应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-151">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="df2c9-152">为了方便用户访问该应用，你可以将应用固定到 Teams 中的应用栏。</span><span class="sxs-lookup"><span data-stu-id="df2c9-152">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="df2c9-153">为此，请创建应用设置策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="df2c9-153">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="df2c9-154">若要了解有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">"在 Teams 中管理应用设置策略"。</a></span><span class="sxs-lookup"><span data-stu-id="df2c9-154">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="df2c9-155">在审核日志搜索 Teams 应用事件</span><span class="sxs-lookup"><span data-stu-id="df2c9-155">Search the audit log for Teams app events</span></span>

<span data-ttu-id="df2c9-156">可以搜索应用审核日志查看组织中 Teams 应用活动。</span><span class="sxs-lookup"><span data-stu-id="df2c9-156">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="df2c9-157">若要详细了解如何搜索 审核日志并查看记录在 审核日志 中的 Teams 活动列表，请参阅"在 审核日志 中搜索 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">活动</a>。</span><span class="sxs-lookup"><span data-stu-id="df2c9-157">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="df2c9-158">在搜索安全中心审核日志，首先必须打开安全中心& <a href="https://protection.office.com" target="_blank">审核</a>。</span><span class="sxs-lookup"><span data-stu-id="df2c9-158">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="df2c9-159">若要了解有关详细信息，请参阅 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">审核日志打开或关闭搜索</a>。</span><span class="sxs-lookup"><span data-stu-id="df2c9-159">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="df2c9-160">请记住，只有启用审核时，审核数据才可用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-160">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="df2c9-161">发现和采用</span><span class="sxs-lookup"><span data-stu-id="df2c9-161">Discover and adopt</span></span>

<span data-ttu-id="df2c9-162">对应用具有权限的用户可以在组织的应用商店中查找它。</span><span class="sxs-lookup"><span data-stu-id="df2c9-162">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="df2c9-163">转到 **"应用 *"页上*** 的"为组织名称构建"，查找组织的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="df2c9-163">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="df2c9-164">显示已发布应用的应用页面</span><span class="sxs-lookup"><span data-stu-id="df2c9-164">Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="df2c9-165">如果创建并分配了应用设置策略，该应用将固定到 Teams 中的应用栏，以便分配有该策略的用户轻松访问。</span><span class="sxs-lookup"><span data-stu-id="df2c9-165">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="df2c9-166">更新</span><span class="sxs-lookup"><span data-stu-id="df2c9-166">Update</span></span>

<span data-ttu-id="df2c9-167">若要更新应用，开发人员应继续按照"开发"部分中 [的步骤](#develop) 操作。</span><span class="sxs-lookup"><span data-stu-id="df2c9-167">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="df2c9-168">当开发人员将更新提交到已发布的自定义应用时，您将在"管理应用"页面的"待定 **审批** " <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">小组件中收到通知</a> 。</span><span class="sxs-lookup"><span data-stu-id="df2c9-168">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="df2c9-169">在表中，**应用的发布** 状态将设置为 **"已提交更新"。**</span><span class="sxs-lookup"><span data-stu-id="df2c9-169">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="df2c9-170">显示挂起的请求和应用状态的"管理应用"页</span><span class="sxs-lookup"><span data-stu-id="df2c9-170">Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="df2c9-171">查看和发布应用更新：</span><span class="sxs-lookup"><span data-stu-id="df2c9-171">To review and publish an app update:</span></span>

1. <span data-ttu-id="df2c9-172">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="df2c9-172">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="df2c9-173">单击应用名称转到应用详细信息页，然后选择"可用更新"查看更新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="df2c9-173">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![应用详细信息页](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="df2c9-175">准备就绪后，选择" **发布** "以发布更新。</span><span class="sxs-lookup"><span data-stu-id="df2c9-175">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="df2c9-176">执行此操作会替换现有应用、更新版本号，以及将 **发布状态更改** 为 **"已发布"。**</span><span class="sxs-lookup"><span data-stu-id="df2c9-176">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="df2c9-177">对于更新的应用，所有应用权限策略和应用设置策略仍强制实施。</span><span class="sxs-lookup"><span data-stu-id="df2c9-177">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="df2c9-178">如果你拒绝更新，则应用的早期版本将保持已发布状态。</span><span class="sxs-lookup"><span data-stu-id="df2c9-178">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="df2c9-179">请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="df2c9-179">Keep in mind the following:</span></span>

- <span data-ttu-id="df2c9-180">应用获得批准后，任何一个都可以向应用提交更新。</span><span class="sxs-lookup"><span data-stu-id="df2c9-180">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="df2c9-181">这意味着其他开发人员（包括最初提交该应用的开发人员）可以提交应用更新。</span><span class="sxs-lookup"><span data-stu-id="df2c9-181">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="df2c9-182">当开发人员提交应用并且请求挂起时，只有该开发人员才能向应用提交更新。</span><span class="sxs-lookup"><span data-stu-id="df2c9-182">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="df2c9-183">其他开发人员只能在应用获得批准后提交更新。</span><span class="sxs-lookup"><span data-stu-id="df2c9-183">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="df2c9-184">有关使用图形 API 更新应用的信息，请参阅 <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">此处</a>。</span><span class="sxs-lookup"><span data-stu-id="df2c9-184">For more information about using the Graph API to update apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="df2c9-185">用户的更新体验</span><span class="sxs-lookup"><span data-stu-id="df2c9-185">Update experience for users</span></span>

<span data-ttu-id="df2c9-186">在大多数情况下，发布应用更新后，新版本会自动显示给用户。</span><span class="sxs-lookup"><span data-stu-id="df2c9-186">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="df2c9-187">但是，Microsoft <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Teams</a> 清单的一些更新需要用户验收才能完成：</span><span class="sxs-lookup"><span data-stu-id="df2c9-187">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="df2c9-188">添加或删除了机器人</span><span class="sxs-lookup"><span data-stu-id="df2c9-188">A bot was added or removed</span></span>
* <span data-ttu-id="df2c9-189">现有机器人的"botId"属性已更改</span><span class="sxs-lookup"><span data-stu-id="df2c9-189">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="df2c9-190">现有机器人的"isNotificationOnly"属性已更改</span><span class="sxs-lookup"><span data-stu-id="df2c9-190">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="df2c9-191">机器人的"supportsFiles"属性已更改</span><span class="sxs-lookup"><span data-stu-id="df2c9-191">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="df2c9-192">添加或删除了消息传送扩展</span><span class="sxs-lookup"><span data-stu-id="df2c9-192">A messaging extension was added or removed</span></span>
* <span data-ttu-id="df2c9-193">添加了一个新连接器</span><span class="sxs-lookup"><span data-stu-id="df2c9-193">A new connector was added</span></span>
* <span data-ttu-id="df2c9-194">添加了新的静态选项卡</span><span class="sxs-lookup"><span data-stu-id="df2c9-194">A new static tab was added</span></span>
* <span data-ttu-id="df2c9-195">添加了新的"可配置"选项卡</span><span class="sxs-lookup"><span data-stu-id="df2c9-195">A new configurable tab was added</span></span>
* <span data-ttu-id="df2c9-196">"webApplicationInfo"中的属性已更改</span><span class="sxs-lookup"><span data-stu-id="df2c9-196">Properties inside "webApplicationInfo" changed</span></span>

![可用的新版本](media/manage-your-custom-apps-update1.png)

![应用的升级选项](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="df2c9-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="df2c9-199">Related topics</span></span>

- [<span data-ttu-id="df2c9-200">通过上传应用包发布自定义应用</span><span class="sxs-lookup"><span data-stu-id="df2c9-200">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="df2c9-201">在 Microsoft Teams 管理中心管理应用</span><span class="sxs-lookup"><span data-stu-id="df2c9-201">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="df2c9-202">在 Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="df2c9-202">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="df2c9-203">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="df2c9-203">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="df2c9-204">在 Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="df2c9-204">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="df2c9-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Microsoft Graph API for Teams 应用</a></span><span class="sxs-lookup"><span data-stu-id="df2c9-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Microsoft Graph API for Teams apps</a></span></span>
