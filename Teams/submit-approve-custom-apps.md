---
title: 使用 Teams 应用提交 API 提交和审批自定义应用
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
description: 了解如何批准使用 Microsoft Teams 中的应用提交 API Teams提交的自定义Microsoft Teams。
ms.openlocfilehash: e544fdc12e17fc8917a2d3b9ce01dfc5985261de
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337789"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="47eab-103">发布通过应用提交 API Teams提交的自定义应用</span><span class="sxs-lookup"><span data-stu-id="47eab-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="47eab-104">概述</span><span class="sxs-lookup"><span data-stu-id="47eab-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="47eab-105">当你发布自定义Teams应用时，该应用可供组织应用商店中的用户使用。</span><span class="sxs-lookup"><span data-stu-id="47eab-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="47eab-106">有两种方法可发布自定义应用，使用方式取决于获取应用的方式。</span><span class="sxs-lookup"><span data-stu-id="47eab-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="47eab-107">**本文重点介绍如何批准** 和发布开发人员通过应用提交 API 提交的Teams应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="47eab-108">当开发人员以其他格式将应用包发送给你时，会使用另一种方法.zip应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="47eab-109">若要详细了解该方法，请参阅通过上传应用包 <a href="/microsoftteams/upload-custom-apps" target="_blank">发布自定义应用</a>。</span><span class="sxs-lookup"><span data-stu-id="47eab-109">To learn more about that method, see <a href="/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span> <span data-ttu-id="47eab-110">审批应用小组件在租户中GCC可用。</span><span class="sxs-lookup"><span data-stu-id="47eab-110">The approve app widget isn't available in GCC tenants.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="47eab-111">此方法当前不适用于GCC环境。</span><span class="sxs-lookup"><span data-stu-id="47eab-111">This method is not currently available for GCC environments.</span></span> <span data-ttu-id="47eab-112">必须使用上传 *自定义应用方法* 。</span><span class="sxs-lookup"><span data-stu-id="47eab-112">You must use the *uploading a custom app* method.</span></span>

<span data-ttu-id="47eab-113">本文提供端到端指导，指导如何将 Teams应用从开发到部署到发现。</span><span class="sxs-lookup"><span data-stu-id="47eab-113">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="47eab-114">你将获得跨应用生命周期Teams连接体验的概述，以简化在组织的应用商店中开发、部署和管理自定义应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-114">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="47eab-115">我们将介绍生命周期的每个步骤，包括开发人员如何使用 Teams 应用提交 API 将自定义应用直接提交到 Microsoft Teams 管理中心，以便你审阅和批准、如何设置策略以管理组织中用户的应用，以及用户如何在 Teams 中发现它们。</span><span class="sxs-lookup"><span data-stu-id="47eab-115">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![从开发到部署的应用概述](media/custom-app-lifecycle.png)

<span data-ttu-id="47eab-117">本指南重点介绍应用Teams面向管理员和 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="47eab-117">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="47eab-118">有关开发应用Teams，请参阅开发人员<a href="/microsoftteams/platform" target="_blank">Teams文档</a>。</span><span class="sxs-lookup"><span data-stu-id="47eab-118">For information about developing Teams apps, see the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="47eab-119">开发</span><span class="sxs-lookup"><span data-stu-id="47eab-119">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="47eab-120">创建应用</span><span class="sxs-lookup"><span data-stu-id="47eab-120">Create the app</span></span>

<span data-ttu-id="47eab-121">开发人员Microsoft Teams平台，开发人员可以轻松集成自己的应用和服务，以提高工作效率、更快地做出决策，以及围绕现有内容和工作流创建协作。</span><span class="sxs-lookup"><span data-stu-id="47eab-121">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="47eab-122">基于 Teams 平台构建的应用是 Teams 客户端与服务和工作流之间的桥梁，可将它们直接带到协作平台的上下文中。</span><span class="sxs-lookup"><span data-stu-id="47eab-122">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="47eab-123">有关详细信息，请转到开发人员Teams<a href="/microsoftteams/platform" target="_blank">文档</a>。</span><span class="sxs-lookup"><span data-stu-id="47eab-123">For more information, go to the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="47eab-124">提交应用</span><span class="sxs-lookup"><span data-stu-id="47eab-124">Submit the app</span></span>

<span data-ttu-id="47eab-125">当应用准备好在生产环境中使用时，开发人员可以使用 Teams 应用提交 API 提交应用，该应用可以从<a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API、</a>集成开发环境 (IDE) （如 Visual Studio Code）或平台（如 Power Apps 和 Power Virtual Agents）调用。</span><span class="sxs-lookup"><span data-stu-id="47eab-125">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="47eab-126">这样，应用就可以在 Microsoft Teams<a href="/microsoftteams/manage-apps" target="_blank"></a>管理中心的"管理应用"页面上使用，你（管理员）可以在其中查看和批准它。</span><span class="sxs-lookup"><span data-stu-id="47eab-126">Doing this makes the app available on the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span>

<span data-ttu-id="47eab-127">基于<a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph</a>的 Teams 应用提交 API 允许组织在自己选择的平台上进行开发，并自动完成 Teams 上的自定义应用的提交审批过程。</span><span class="sxs-lookup"><span data-stu-id="47eab-127">The Teams App Submission API, <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="47eab-128">下面是此应用提交步骤在应用中的外观Visual Studio Code：</span><span class="sxs-lookup"><span data-stu-id="47eab-128">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![在应用程序中提交Visual Studio Code](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="47eab-130&quot;>请记住，这不会将应用发布到组织的应用商店。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;47eab-130&quot;>Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id=&quot;47eab-131&quot;>此步骤将应用提交到Microsoft Teams管理中心，可以在其中批准该应用发布到组织的应用商店。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;47eab-131&quot;>This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id=&quot;47eab-132&quot;>有关使用 Graph API 提交应用的信息，请参阅<a href=&quot;/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&quot; target=&quot;_blank&quot;>此处</a>。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;47eab-132&quot;>For more information about using the Graph API to submit apps, see <a href=&quot;/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&quot; target=&quot;_blank&quot;>here</a>.</span></span>

## <a name=&quot;validate&quot;></a><span data-ttu-id=&quot;47eab-133&quot;>验证</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;47eab-133&quot;>Validate</span></span>

<span data-ttu-id=&quot;47eab-134&quot;>左侧<a href=&quot;/microsoftteams/manage-apps&quot; target=&quot;_blank&quot;>导航</a>栏中Microsoft Teams管理中心 (&quot;管理应用&quot;页，转到&quot;Teams 应用&quot;&quot;管理应用  >  ") ，查看组织的所有 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-134">The <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="47eab-135">页面 **顶部的** "挂起审批"小组件可让你了解何时提交自定义应用进行审批。</span><span class="sxs-lookup"><span data-stu-id="47eab-135">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="47eab-136">在表中，新提交的应用会自动显示"已提交"和"**已** 阻止 **状态"的发布状态**。</span><span class="sxs-lookup"><span data-stu-id="47eab-136">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="47eab-137">你可以按降 **序对"发布状态** "列进行排序以快速查找应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-137">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="47eab-138">发布状态</span><span class="sxs-lookup"><span data-stu-id="47eab-138">publishing status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="47eab-139">单击应用名称转到应用详细信息页。</span><span class="sxs-lookup"><span data-stu-id="47eab-139">Click the app name to go to the app details page.</span></span> <span data-ttu-id="47eab-140">在 **"关于** "选项卡上，可以查看有关应用的详细信息，包括说明、状态、提交者以及应用 ID。</span><span class="sxs-lookup"><span data-stu-id="47eab-140">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

![已提交应用的应用详细信息页面](media/custom-app-lifecycle-app-details.png)

<span data-ttu-id="47eab-142">有关使用 Graph API 检查发布 **状态的信息**，请参阅 <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">此处</a>。</span><span class="sxs-lookup"><span data-stu-id="47eab-142">For more information about using the Graph API to check the **Publishing status**, see <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="47eab-143">发布</span><span class="sxs-lookup"><span data-stu-id="47eab-143">Publish</span></span>

<span data-ttu-id="47eab-144">当你准备好使应用可供用户使用时，请发布该应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-144">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="47eab-145">在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="47eab-145">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="47eab-146">单击应用名称转到应用详细信息页，然后在 **"发布状态**"框中，选择"发布 **"。**</span><span class="sxs-lookup"><span data-stu-id="47eab-146">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="47eab-147">发布应用后，"发布状态 **"将更改** 为"已发布 **"，"\*\*\*\*状态"** 会自动更改为"允许 **"。**</span><span class="sxs-lookup"><span data-stu-id="47eab-147">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="47eab-148">设置和管理</span><span class="sxs-lookup"><span data-stu-id="47eab-148">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="47eab-149">控制对应用的访问</span><span class="sxs-lookup"><span data-stu-id="47eab-149">Control access to the app</span></span>

<span data-ttu-id="47eab-150">默认情况下，组织中的所有用户都可以访问组织应用商店中的应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-150">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="47eab-151">若要限制和控制谁有权使用应用，可以创建并分配应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="47eab-151">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="47eab-152">要了解详细信息，请参阅<a href="/microsoftteams/teams-app-permission-policies" target="_blank">在 Teams 中管理应用权限策略</a>。</span><span class="sxs-lookup"><span data-stu-id="47eab-152">To learn more, see <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="47eab-153">固定并安装应用供用户发现</span><span class="sxs-lookup"><span data-stu-id="47eab-153">Pin and install the app for users to discover</span></span>

<span data-ttu-id="47eab-154">默认情况下，用户若要查找应用，必须转到组织的应用商店并浏览或搜索该应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-154">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="47eab-155">为了方便用户访问该应用，你可以将应用固定到应用中的Teams。</span><span class="sxs-lookup"><span data-stu-id="47eab-155">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="47eab-156">为此，请创建应用设置策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="47eab-156">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="47eab-157">要了解详细信息，请参阅<a href="/microsoftteams/teams-app-setup-policies" target="_blank">在 Teams 中管理应用设置策略</a>。</span><span class="sxs-lookup"><span data-stu-id="47eab-157">To learn more, see <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="47eab-158">在审核日志搜索Teams事件</span><span class="sxs-lookup"><span data-stu-id="47eab-158">Search the audit log for Teams app events</span></span>

<span data-ttu-id="47eab-159">可以搜索审核日志以查看Teams应用活动。</span><span class="sxs-lookup"><span data-stu-id="47eab-159">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="47eab-160">若要详细了解如何搜索 审核日志 并查看 审核日志 中记录的 Teams 活动的列表，请参阅在 Teams 中搜索 审核日志<a href="/microsoftteams/audit-log-events" target="_blank">事件。</a></span><span class="sxs-lookup"><span data-stu-id="47eab-160">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="47eab-161">在搜索审核日志之前，你必须先在<a href="https://protection.office.com" target="_blank">安全与合规中心</a>中启用审核。</span><span class="sxs-lookup"><span data-stu-id="47eab-161">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="47eab-162">有关详细信息，请参阅<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">启用或禁用审核日志搜索</a>。</span><span class="sxs-lookup"><span data-stu-id="47eab-162">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="47eab-163">请记住，审核数据仅在你启用审核的那一刻才可用。</span><span class="sxs-lookup"><span data-stu-id="47eab-163">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="47eab-164">发现和采用</span><span class="sxs-lookup"><span data-stu-id="47eab-164">Discover and adopt</span></span>

<span data-ttu-id="47eab-165">对应用具有权限的用户可以在组织的应用商店中查找该应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-165">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="47eab-166">转到 **"应用 *"页上*** 的"为组织名称构建"，查找组织的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="47eab-166">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="47eab-167">显示已发布应用的应用页面</span><span class="sxs-lookup"><span data-stu-id="47eab-167">Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="47eab-168">如果创建并分配了应用设置策略，该应用将固定到 Teams 中的应用栏，以便分配了该策略的用户轻松访问。</span><span class="sxs-lookup"><span data-stu-id="47eab-168">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="47eab-169">更新</span><span class="sxs-lookup"><span data-stu-id="47eab-169">Update</span></span>

<span data-ttu-id="47eab-170">若要更新应用，开发人员应继续按照开发部分中 [的步骤](#develop) 操作。</span><span class="sxs-lookup"><span data-stu-id="47eab-170">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="47eab-171">当开发人员将更新提交到已发布的自定义应用时，您将在"管理应用"页面的"挂起审批"小组件<a href="/microsoftteams/manage-apps" target="_blank">中</a>收到通知。</span><span class="sxs-lookup"><span data-stu-id="47eab-171">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="47eab-172">在表中，**应用的发布** 状态将设置为"已 **提交更新"。**</span><span class="sxs-lookup"><span data-stu-id="47eab-172">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="47eab-173">显示挂起的请求和应用状态的"管理应用"页</span><span class="sxs-lookup"><span data-stu-id="47eab-173">Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="47eab-174">查看和发布应用更新：</span><span class="sxs-lookup"><span data-stu-id="47eab-174">To review and publish an app update:</span></span>

1. <span data-ttu-id="47eab-175">在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="47eab-175">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="47eab-176">单击应用名称转到应用详细信息页，然后选择"可用更新"查看更新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="47eab-176">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![应用详细信息页面](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="47eab-178">准备就绪后，选择" **发布** "以发布更新。</span><span class="sxs-lookup"><span data-stu-id="47eab-178">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="47eab-179">执行此操作会替换现有应用，更新版本号，将"**发布状态"更改为**"已发布 **"。**</span><span class="sxs-lookup"><span data-stu-id="47eab-179">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="47eab-180">对于更新的应用，所有应用权限策略和应用设置策略仍然强制实施。</span><span class="sxs-lookup"><span data-stu-id="47eab-180">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="47eab-181">如果你拒绝更新，则应用的早期版本将保持发布状态。</span><span class="sxs-lookup"><span data-stu-id="47eab-181">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="47eab-182">请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="47eab-182">Keep in mind the following:</span></span>

- <span data-ttu-id="47eab-183">应用获得批准后，任何用户都可以向应用提交更新。</span><span class="sxs-lookup"><span data-stu-id="47eab-183">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="47eab-184">这意味着其他开发人员（包括最初提交该应用的开发人员）可以提交应用更新。</span><span class="sxs-lookup"><span data-stu-id="47eab-184">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="47eab-185">当开发人员提交应用并且请求挂起时，只有该开发人员才能向应用提交更新。</span><span class="sxs-lookup"><span data-stu-id="47eab-185">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="47eab-186">其他开发人员只能在应用获得批准后提交更新。</span><span class="sxs-lookup"><span data-stu-id="47eab-186">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="47eab-187">有关使用 Graph API 更新应用的信息，请参阅<a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">此处</a>。</span><span class="sxs-lookup"><span data-stu-id="47eab-187">For more information about using the Graph API to update apps, see <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

## <a name="related-topics"></a><span data-ttu-id="47eab-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="47eab-188">Related topics</span></span>

- [<span data-ttu-id="47eab-189">通过上传应用包发布自定义应用</span><span class="sxs-lookup"><span data-stu-id="47eab-189">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="47eab-190">在管理中心内Microsoft Teams应用</span><span class="sxs-lookup"><span data-stu-id="47eab-190">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="47eab-191">在 Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="47eab-191">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="47eab-192">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="47eab-192">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="47eab-193">在 Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="47eab-193">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="47eab-194"><a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">适用于 Graph 应用的 Microsoft Teams API</a></span><span class="sxs-lookup"><span data-stu-id="47eab-194"><a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Microsoft Graph API for Teams apps</a></span></span>