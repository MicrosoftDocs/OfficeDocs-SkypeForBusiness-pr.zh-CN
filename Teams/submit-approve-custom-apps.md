---
title: 使用 Teams 应用提交 API 提交和批准自定义应用
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
description: 了解如何批准使用 Microsoft Teams 中的 Teams 应用提交 API 提交的自定义应用。
ms.openlocfilehash: bdd13dbe4db46110250ea380eebd0ea1d011a322
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824913"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="5f1bd-103">发布通过 Teams 应用提交 API 提交的自定义应用</span><span class="sxs-lookup"><span data-stu-id="5f1bd-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="5f1bd-104">概述</span><span class="sxs-lookup"><span data-stu-id="5f1bd-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="5f1bd-105">在你发布自定义 Teams 应用时，它可供组织的应用商店中的用户使用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="5f1bd-106">发布自定义应用的方法有两种，而根据获取应用的方式，具体取决于获取应用的方式。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="5f1bd-107">**本文重点介绍了开发人员**通过 Teams 应用提交 API 提交的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="5f1bd-108">当开发人员使用 .zip 格式向你发送应用包时，会使用上传自定义应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="5f1bd-109">若要了解有关该方法的详细信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">"通过上载应用包发布自定义应用</a>"。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-109">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span>
 
<span data-ttu-id="5f1bd-110">本文提供端到端指导，指导如何让 Teams 应用开发到部署到发现。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-110">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="5f1bd-111">你将概述 Teams 在应用生命周期内获得概述，简化了如何在组织的应用商店中开发、部署和管理自定义应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-111">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="5f1bd-112">我们将介绍生命周期的每个步骤，包括开发人员可如何使用 Teams 应用提交 API 将自定义应用直接提交到 Microsoft Teams 管理中心，以便你审查和批准，如何设置策略以管理组织中用户的应用以及用户在 Teams 中发现它们的方式。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-112">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![应用从开发到部署的概述](media/custom-app-lifecycle.png)

<span data-ttu-id="5f1bd-114">本指南侧重于 Teams 应用的一个方面，并适用于管理员和 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-114">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="5f1bd-115">有关开发 Teams 应用的信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams 开发人员文档</a>。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-115">For information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="5f1bd-116">开发</span><span class="sxs-lookup"><span data-stu-id="5f1bd-116">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="5f1bd-117">创建应用</span><span class="sxs-lookup"><span data-stu-id="5f1bd-117">Create the app</span></span>

<span data-ttu-id="5f1bd-118">Microsoft Teams 开发人员平台可让开发人员轻松集成你自己的应用和服务，从而提高工作效率、更快决策，并围现现有内容和工作流进行协作。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-118">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="5f1bd-119">Teams 平台上构建的应用是 Teams 客户端与你的服务和工作流之间的聚合，并将其直接放入协作平台的上下文中。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-119">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="5f1bd-120">有关详细信息，请转到 Teams <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">开发人员文档</a>。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-120">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="5f1bd-121">提交应用</span><span class="sxs-lookup"><span data-stu-id="5f1bd-121">Submit the app</span></span>

<span data-ttu-id="5f1bd-122">当应用准备好在生作环境中使用时，开发人员可以使用 Teams 应用提交 API 提交应用，可以从 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">图形 API、集</a>成的开发环境 (IDE) Visual Studio）或 Power 应用和 Power Virtual 代理等平台上提交应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-122">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="5f1bd-123">这样，可在 Microsoft Teams 管理中心的"管理 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">应用</a> "页面上访问该应用，而你和管理员可以在此查看和批准它。更改</span><span class="sxs-lookup"><span data-stu-id="5f1bd-123">Doing this makes the app available on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span> 

<span data-ttu-id="5f1bd-124">这些 Teams 应用提交 API <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">是在 Microsoft Graph</a>基上构建的，允许组织开发你选择的平台，并自动为 Teams 上的自定义应用提供提交到审批流程。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-124">The Teams App Submission API, <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="5f1bd-125">下面是此应用提交步骤在代码中的Visual Studio示例：</span><span class="sxs-lookup"><span data-stu-id="5f1bd-125">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![使用代码提交应用Visual Studio屏幕截图](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="5f1bd-127">请记住，这不会将应用发布到你的组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-127">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="5f1bd-128">此步骤会将应用提交到 Microsoft Teams 管理中心，在这里，你可以批准该应用以便发布到组织的应用商店。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-128">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id="5f1bd-129">有关使用图形 API 提交应用的详细信息，<a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">请参阅此处。</a></span><span class="sxs-lookup"><span data-stu-id="5f1bd-129">For more information about using the Graph API to submit apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">here</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="5f1bd-130">Validate</span><span class="sxs-lookup"><span data-stu-id="5f1bd-130">Validate</span></span>

<span data-ttu-id="5f1bd-131">在<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Microsoft</a> Teams 管理中心 (的"管理应用"页面的左侧导航**Teams apps**  >  **Manage apps**栏中，转到 Teams 应用管理) ，它将介绍你组织的所有 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-131">The <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="5f1bd-132">页面 **顶部的待** 定审批小组件可使你知道何时提交自定义应用以供审批。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-132">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="5f1bd-133">在表中，新提交的应用会自动**显示"已**提交 **"** 和"被阻止**状态\*\*\*\*"的发布状态**。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-133">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="5f1bd-134">你可以按 **降序对** "发布状态"列进行排序，以便快速找到应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-134">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="5f1bd-135">显示待处理请求和应用状态的"管理应用"页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="5f1bd-135">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="5f1bd-136">单击应用名称转到应用详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-136">Click the app name to go to the app details page.</span></span> <span data-ttu-id="5f1bd-137">在" **关** 于"选项卡上，您可以查看有关该应用的详细信息，包括说明、状态、子项目栏和应用 ID。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-137">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

![已提交应用的应用详细信息页面的屏幕截图](media/custom-app-lifecycle-app-details.png)

<span data-ttu-id="5f1bd-139">有关使用图形 API 检查发布状态的详细信息 **，**<a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">请参阅此处</a>。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-139">For more information about using the Graph API to check the **Publishing status**, see <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="5f1bd-140">发布</span><span class="sxs-lookup"><span data-stu-id="5f1bd-140">Publish</span></span>

<span data-ttu-id="5f1bd-141">当准备好向用户提供应用时，请发布应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-141">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="5f1bd-142">在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="5f1bd-143">单击应用名称转到应用详细信息页，然后在"发布 **状态"** 框中选择" **发布**"。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-143">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="5f1bd-144">在发布应用后，发布 **状态将** 更改为已 **发布状态** ， **状态会** 自动更改为 **"已允许**"。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-144">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="5f1bd-145">设置和管理</span><span class="sxs-lookup"><span data-stu-id="5f1bd-145">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="5f1bd-146">控制对应用的访问</span><span class="sxs-lookup"><span data-stu-id="5f1bd-146">Control access to the app</span></span>

<span data-ttu-id="5f1bd-147">默认情况下，组织中的所有用户都可以访问你组织的应用商店中的应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-147">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="5f1bd-148">若要限制和控制谁有权使用此应用，可以创建和分配应用许可策略。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-148">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="5f1bd-149">若要了解详细信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Teams 中的"管理应用权限策略</a>"。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-149">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="5f1bd-150">固定并安装可供用户发现的应用</span><span class="sxs-lookup"><span data-stu-id="5f1bd-150">Pin and install the app for users to discover</span></span>

<span data-ttu-id="5f1bd-151">默认情况下，用户可找到他们需要转到你组织的应用商店、浏览或搜索它所必要的应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-151">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="5f1bd-152">要使用户可以轻松地访问应用，你可以将应用固定到 Teams 中的应用栏。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-152">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="5f1bd-153">若要执行此操作，请创建应用设置策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-153">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="5f1bd-154">若要了解详细信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Teams 中的"管理应用设置策略</a>"。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-154">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="5f1bd-155">在审核日志 Teams 应用事件的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="5f1bd-155">Search the audit log for Teams app events</span></span>

<span data-ttu-id="5f1bd-156">你可以搜索审核日志以查看组织中的 Teams 应用活动。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-156">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="5f1bd-157">若要深入了解如何搜索 审核日志 并查看在 审核日志 中记录的 Teams 活动列表，请参阅 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">"在 Teams 审核日志中搜索事件</a>"。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-157">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="5f1bd-158">必须先在审核日志应用合规中心中打开 <a href="https://protection.office.com" target="_blank">审&审</a>。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-158">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="5f1bd-159">要了解详细信息， <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">请参阅审核日志搜索和关闭</a>。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-159">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="5f1bd-160">请记住，审计数据仅在打开审计时时提供。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-160">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="5f1bd-161">发现和接受</span><span class="sxs-lookup"><span data-stu-id="5f1bd-161">Discover and adopt</span></span>

<span data-ttu-id="5f1bd-162">对应用具有此权限的用户可以在组织的应用商店中找到它。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-162">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="5f1bd-163">转到" **应用 *"页面上为组织名称*** 构建，以查找组织的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-163">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="5f1bd-164">显示已发布应用的"应用"页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="5f1bd-164">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="5f1bd-165">如果创建并分配了应用安装策略，则会将应用固定到 Teams 中的应用栏，以便这些用户都可以轻松访问该策略。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-165">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="5f1bd-166">更新</span><span class="sxs-lookup"><span data-stu-id="5f1bd-166">Update</span></span>

<span data-ttu-id="5f1bd-167">若要更新应用，开发人员应该继续按照"开发"部分 [中的步骤](#develop) 操作。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-167">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="5f1bd-168">当开发人员向已发布的自定义应用提交更新时，你会在"管理 **应用"页面的"待** 定审批"小组件中 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">收到</a> 通知。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-168">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="5f1bd-169">在表格中 **，应用的**发布状态将设置为 **"更新"。**</span><span class="sxs-lookup"><span data-stu-id="5f1bd-169">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="5f1bd-170">显示待处理请求和应用状态的"管理应用"页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="5f1bd-170">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="5f1bd-171">若要查看并发布应用更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5f1bd-171">To review and publish an app update:</span></span>

1. <span data-ttu-id="5f1bd-172">在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-172">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="5f1bd-173">单击应用名称转到应用详细信息页，然后选择 **"更新"以** 查看更新详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-173">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![<span data-ttu-id="5f1bd-174">显示待处理请求和应用状态的"管理应用"页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="5f1bd-174">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="5f1bd-175">准备就绪后，选择" **发布"** 以发布更新。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-175">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="5f1bd-176">执行此操作会替换现有应用，更新版本号，并将 **"发布"状态更改为\*\*\*\*"已发布**"。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-176">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="5f1bd-177">已对更新的应用执行所有应用权限策略和应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-177">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="5f1bd-178">如果你拒绝更新，则会保持已发布的早期版本的应用。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-178">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="5f1bd-179">请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="5f1bd-179">Keep in mind the following:</span></span>

- <span data-ttu-id="5f1bd-180">批准应用后，任何人都可以提交应用更新。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-180">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="5f1bd-181">这意味着包括最初提交应用的开发人员）可以向应用提交更新。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-181">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="5f1bd-182">当开发人员提交应用并且请求挂起时，仅当同一开发人员才能向应用提交更新。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-182">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="5f1bd-183">其他开发人员只能在审批应用后提交更新。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-183">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="5f1bd-184">有关使用图形 API 更新应用的详细信息，请参阅 <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">此处</a>。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-184">For more information about using the Graph API to update apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="5f1bd-185">更新用户体验</span><span class="sxs-lookup"><span data-stu-id="5f1bd-185">Update experience for users</span></span>

<span data-ttu-id="5f1bd-186">在大多数情况下，发布应用更新后，会自动为用户显示新版本。</span><span class="sxs-lookup"><span data-stu-id="5f1bd-186">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="5f1bd-187">但是 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">，Microsoft Teams</a> 清单会有一些更新，要求用户接受才能完成：</span><span class="sxs-lookup"><span data-stu-id="5f1bd-187">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="5f1bd-188">已添加或删除自动程序</span><span class="sxs-lookup"><span data-stu-id="5f1bd-188">A bot was added or removed</span></span>
* <span data-ttu-id="5f1bd-189">已更改一个现有机器的 "botId" 属性</span><span class="sxs-lookup"><span data-stu-id="5f1bd-189">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="5f1bd-190">已更改一个现有机器的"isNotificationOnly"属性</span><span class="sxs-lookup"><span data-stu-id="5f1bd-190">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="5f1bd-191">已更改 bot 的"supportsFiles"属性</span><span class="sxs-lookup"><span data-stu-id="5f1bd-191">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="5f1bd-192">添加或删除了一个邮件扩展</span><span class="sxs-lookup"><span data-stu-id="5f1bd-192">A messaging extension was added or removed</span></span>
* <span data-ttu-id="5f1bd-193">已添加一条新连接线</span><span class="sxs-lookup"><span data-stu-id="5f1bd-193">A new connector was added</span></span>
* <span data-ttu-id="5f1bd-194">已添加新的"静态"选项卡</span><span class="sxs-lookup"><span data-stu-id="5f1bd-194">A new static tab was added</span></span>
* <span data-ttu-id="5f1bd-195">已添加新的可配置选项卡</span><span class="sxs-lookup"><span data-stu-id="5f1bd-195">A new configurable tab was added</span></span>
* <span data-ttu-id="5f1bd-196">已更改"webApplicationInfo"内的属性</span><span class="sxs-lookup"><span data-stu-id="5f1bd-196">Properties inside "webApplicationInfo" changed</span></span>

![显示有新版本可用的应用的屏幕截图](media/manage-your-custom-apps-update1.png)

![应用升级选项的屏幕截图](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="5f1bd-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="5f1bd-199">Related topics</span></span>

- [<span data-ttu-id="5f1bd-200">通过上载应用包发布自定义应用</span><span class="sxs-lookup"><span data-stu-id="5f1bd-200">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="5f1bd-201">在 Microsoft Teams 管理中心中管理应用</span><span class="sxs-lookup"><span data-stu-id="5f1bd-201">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="5f1bd-202">在 Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="5f1bd-202">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="5f1bd-203">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="5f1bd-203">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="5f1bd-204">在 Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="5f1bd-204">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="5f1bd-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">适用于 Teams 应用的 Microsoft Graph API</a></span><span class="sxs-lookup"><span data-stu-id="5f1bd-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Microsoft Graph API for Teams apps</a></span></span>
