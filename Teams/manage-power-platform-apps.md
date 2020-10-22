---
title: 在 Microsoft 团队管理中心中管理 Power Platform 应用
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
description: 了解如何在 Microsoft 团队管理中心中管理对 Power Platform 应用的访问权限。
ms.openlocfilehash: 687d8df929150cdc38795a13ba06687ed7e42b2b
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650955"
---
# <a name="manage-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="87e43-103">在 Microsoft 团队管理中心中管理 Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="87e43-103">Manage Power Platform apps in the Microsoft Teams admin center</span></span>

## <a name="power-platform-apps-in-teams"></a><span data-ttu-id="87e43-104">团队中的 Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="87e43-104">Power Platform apps in Teams</span></span>

<span data-ttu-id="87e43-105">本文概述了如何管理添加到 Microsoft 团队管理中心中的团队的 [Power Platform](https://powerplatform.microsoft.com/) 应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-105">This article gives you an overview of how to manage [Power Platform](https://powerplatform.microsoft.com/) apps added to Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="87e43-106">[Power Apps](https://powerapps.microsoft.com) 是低代码/无代码应用程序开发环境，你的组织中的开发者可以使用它来生成连接到你的业务数据的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-106">[Power Apps](https://powerapps.microsoft.com) is a low-code/no-code application development environment that makers in your organization can use to build custom apps that connect to your business data.</span></span> <span data-ttu-id="87e43-107">[Power Virtual agent](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 是一个无代码 bot 构建环境，用于创建功能强大的 bot。</span><span class="sxs-lookup"><span data-stu-id="87e43-107">[Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) is a no-code bot building environment for makers to create powerful bots.</span></span> <span data-ttu-id="87e43-108">通过将 Power Platform 应用集成到团队中，组织可以优化业务流程、更快地响应不断变化的业务需求，以提高协作能力，并创建和共享自定义解决方案以提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="87e43-108">With the integration of Power Platform apps into Teams, organizations can streamline business processes, respond to changing business needs more rapidly to drive greater collaboration, and create and share custom solutions to be more productive.</span></span>  

<span data-ttu-id="87e43-109">由你的组织中的由决策者创建的 Power Platform 应用将自动添加到团队。</span><span class="sxs-lookup"><span data-stu-id="87e43-109">Power Platform apps created by makers in your organization are automatically added to Teams.</span></span> <span data-ttu-id="87e43-110">通过使用 power [Apps 中的共享功能](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) 和 [power Virtual agent 中的共享功能](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)，制造商可以控制哪些人可以访问其应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-110">Makers can control who can access their app by using the [sharing feature in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) and the [sharing feature in Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/admin-share-bots).</span></span>

<span data-ttu-id="87e43-111">当创建或共享 Power Platform 应用时，用户可以通过面向你的同事构建的***组织名称***，在 "应用" 页面上查看和安装该应用  >  **Built by your colleagues**。</span><span class="sxs-lookup"><span data-stu-id="87e43-111">When a Power Platform app is created or shared, users can view and install it on the Apps page by going to **Built for *Your Organization Name*** > **Built by your colleagues**.</span></span> <span data-ttu-id="87e43-112"> (在创建或共享应用后，可能需要几分钟的时间才能在此处显示。 ) </span><span class="sxs-lookup"><span data-stu-id="87e43-112">(It might take a few minutes after an app is created or shared for the app to appear here.)</span></span>

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text=""应用程序" 页面的屏幕截图，显示由同事构建的 Power Platform 应用":::

<span data-ttu-id="87e43-114">如果应用满足以下条件之一，用户将看到 **由同事构建** 的 Power Platform 应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-114">A user will see a Power Platform app in **Built by your colleagues** if the app meets one of the following conditions.</span></span>

|<span data-ttu-id="87e43-115">Power Apps</span><span class="sxs-lookup"><span data-stu-id="87e43-115">Power Apps</span></span> |<span data-ttu-id="87e43-116">Power Virtual Agent</span><span class="sxs-lookup"><span data-stu-id="87e43-116">Power Virtual Agents</span></span>  |
|---------|---------|
|<ul><li><span data-ttu-id="87e43-117">用户创建了该应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-117">The user created the app.</span></span></li><li><span data-ttu-id="87e43-118">该应用直接与用户共享。</span><span class="sxs-lookup"><span data-stu-id="87e43-118">The app was shared directly with the user.</span></span></li><li><span data-ttu-id="87e43-119">用户最近使用过该应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-119">The user recently used the app.</span></span> </li></ul>| <ul><li><span data-ttu-id="87e43-120">用户创建了机器人。</span><span class="sxs-lookup"><span data-stu-id="87e43-120">The user created the bot.</span></span></li><li><span data-ttu-id="87e43-121">机器人由用户所属的团队拥有。</span><span class="sxs-lookup"><span data-stu-id="87e43-121">The bot is owned by a team the user is a member of.</span></span> </li></ul>        |

<span data-ttu-id="87e43-122">用户安装 Power Platform 应用的方式与安装任何其他团队应用的方式相同。</span><span class="sxs-lookup"><span data-stu-id="87e43-122">Users install Power Platform apps in the same way they install any other Teams app.</span></span> <span data-ttu-id="87e43-123">请记住，用户只能将应用安装到他们拥有权限的上下文中，例如，团队拥有的团队、其所属的聊天或其个人范围。</span><span class="sxs-lookup"><span data-stu-id="87e43-123">Keep in mind that users can only install  apps to the context to which they have permissions, for example, a team they own, a chat that they're a part of, or their personal scope.</span></span>

## <a name="manage-access-to-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="87e43-124">在 Microsoft 团队管理中心中管理对 Power Platform 应用的访问</span><span class="sxs-lookup"><span data-stu-id="87e43-124">Manage access to Power Platform apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="87e43-125">作为管理员，你可以控制 Power Platform 应用是否在团队中的 "应用" 页面上的 **同事构建** 中列出。</span><span class="sxs-lookup"><span data-stu-id="87e43-125">As an admin, you can control whether Power Platform apps are listed in **Built by your colleagues** on the Apps page in Teams.</span></span> <span data-ttu-id="87e43-126">你可以在 "管理应用" 页面上的 "管理应用" 页面上的 "管理应用" 页面上的 "管理应用" 页面上的 "管理应用[app permission policies](teams-app-permission-policies.md)" 页面或特定用户的 "[管理应用](manage-apps.md)" 页面上创建的所有应用中，</span><span class="sxs-lookup"><span data-stu-id="87e43-126">You can collectively block or allow all apps created in Power Apps or all apps created in Power Virtual Agents at the org level on the [Manage apps](manage-apps.md) page or for specific users using [app permission policies](teams-app-permission-policies.md).</span></span>

<span data-ttu-id="87e43-127">你组织的应用商店中的 **共享 Power Apps** 和 **Shared Power Virtual Agent 应用** 应用代表在该特定平台上创建的所有应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-127">The **Shared Power Apps** and **Shared Power Virtual Agent Apps** apps in your organization's app store represent all apps created on that particular platform.</span></span> <span data-ttu-id="87e43-128">如果在组织级别或针对特定用户阻止其中一个或两个应用，这些用户将无法看到 **由同事构建** 的平台中的任何应用，并且无法在团队中安装它们。</span><span class="sxs-lookup"><span data-stu-id="87e43-128">If you block one or both these apps at the org level or for specific users, those users can't see any apps from those platforms in **Built by your colleagues** and can't install them in Teams.</span></span>  

<span data-ttu-id="87e43-129">请记住，你可以控制对在 Power Apps 和 Power Virtual Agent 中创建的所有应用的访问权限，但不能允许或阻止单个应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-129">Keep in mind that you can control access to all apps created in Power Apps and Power Virtual Agents but you can't allow or block individual apps.</span></span> <span data-ttu-id="87e43-130">通过 "Power Apps" 和 "Power Virtual Agent" 中的 "共享" 功能，制造商决定哪些人可以访问他们创建的应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-130">Makers decide who can access the apps they create through the sharing feature from within Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="87e43-131">如果某个 maker 在与用户的 Power Virtual 代理中创建了一个应用，并且已阻止该用户的 **共享 Power Virtual Agent 应用** ，则该用户将无法在团队中看到或安装该平台中的任何应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-131">If a maker shared an app they created in Power Virtual Agents with a user and you blocked **Shared Power Virtual Agents Apps** for that user, the user won't be able to see or install any apps from that platform in Teams.</span></span>

<span data-ttu-id="87e43-132">如果允许用户从 Power Apps 或 Power Virtual Agent 访问应用，然后阻止用户从这两个平台之一访问应用，则用户仍可以访问和使用在阻止应用或应用之前安装的 Power 平台应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-132">If a user is allowed to access apps from Power Apps or Power Virtual Agents, and you then block the user from accessing apps from one or both these platforms, the user can still access and use the Power Platforms apps that they installed before you blocked the app or apps.</span></span> <span data-ttu-id="87e43-133">但是，用户无法再查看或安装 **由你的同事构建**的平台中的任何应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-133">However, the user can no longer see or install any apps from those platforms in **Built by your colleagues**.</span></span>

> [!NOTE]
> <span data-ttu-id="87e43-134">"[管理应用](manage-apps.md)" 页面上的 "**允许与自定义应用进行交互**" 组织范围的应用设置适用于组织中的所有人，并控制他们是否可以与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="87e43-134">The **Allow interaction with custom apps** org-wide app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can interact with custom apps.</span></span> <span data-ttu-id="87e43-135">组织范围内的应用设置控制所有用户的行为，并替代分配给用户的任何其他应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="87e43-135">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="87e43-136">默认情况下，此设置处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="87e43-136">By default, this setting is turned on.</span></span> <span data-ttu-id="87e43-137">如果关闭此设置，则你的组织中的用户无法查看或安装任何自定义应用，包括 Power Platform 应用。</span><span class="sxs-lookup"><span data-stu-id="87e43-137">If this setting is turned off, users in your organization can't see or install any custom apps, including Power Platform apps.</span></span> <span data-ttu-id="87e43-138">若要了解详细信息，请参阅 [管理组织范围内的应用设置](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="87e43-138">To learn  more, see [Manage org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

### <a name="allow-or-block-power-platform-apps-for-your-organization"></a><span data-ttu-id="87e43-139">为你的组织允许或阻止 Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="87e43-139">Allow or block Power Platform apps for your organization</span></span>

<span data-ttu-id="87e43-140">默认情况下，你的组织中的所有团队用户都可以使用 **共享的 Power 应用** 和 **共享 Power Virtual Agent 应用** 。</span><span class="sxs-lookup"><span data-stu-id="87e43-140">By default, **Shared Power Apps** and **Shared Power Virtual Agent Apps** are allowed for all Teams users in your organization.</span></span> <span data-ttu-id="87e43-141">你可以在 "Microsoft 团队管理中心" 的 " [管理应用](manage-apps.md) " 页面上的 "组织" 级别阻止或允许他们。</span><span class="sxs-lookup"><span data-stu-id="87e43-141">You can block or allow them at the org level on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>  

1. <span data-ttu-id="87e43-142">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="87e43-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="87e43-143">您必须是全局管理员或团队服务管理员才能访问该页面。</span><span class="sxs-lookup"><span data-stu-id="87e43-143">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="87e43-144">在应用列表中，执行下列操作之一。</span><span class="sxs-lookup"><span data-stu-id="87e43-144">In the list of apps, do one of the following.</span></span>

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text=""管理应用" 页面的屏幕截图，显示共享的 Power Platform 应用":::

    - <span data-ttu-id="87e43-146">若要阻止在你的组织中的所有用户的 Power Apps 或 Power Virtual 代理中创建的应用，请搜索 **共享的 Power apps** 或 **Shared Power virtual Agent 应用**，将其选中，然后单击 " **阻止**"。</span><span class="sxs-lookup"><span data-stu-id="87e43-146">To block apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="87e43-147">若要为组织中的所有用户允许在 Power Apps 或 Power Virtual Agent 中创建的应用，请搜索 " **共享 Power apps** " 或 " **共享 Power virtual Agent 应用**"，选择它，然后单击 " **允许**"。</span><span class="sxs-lookup"><span data-stu-id="87e43-147">To allow apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Allow**.</span></span>

### <a name="allow-or-block-power-platform-apps-for-specific-users"></a><span data-ttu-id="87e43-148">针对特定用户允许或阻止 Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="87e43-148">Allow or block Power Platform apps for specific users</span></span>

<span data-ttu-id="87e43-149">若要允许或阻止组织中的特定用户访问在 Power Apps 或 Power Virtual Agent 中创建的应用，请创建并分配一个或多个自定义 [应用权限策略](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="87e43-149">To allow or block specific users in your organization from accessing apps created in Power Apps or Power Virtual Agents, create and assign one or more custom [app permission policies](teams-app-permission-policies.md).</span></span> 

<span data-ttu-id="87e43-150">例如，若要阻止特定用户访问在 Power Apps 中创建的应用，请创建一个自定义应用权限策略来阻止 **共享的 Power 应用**，然后为这些用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="87e43-150">For example, to block specific users from accessing apps created in Power Apps, create a custom app permission policy to block **Shared Power Apps**, and then assign the policy to those users.</span></span>

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="已阻止共享 Power 应用的示例自定义应用权限策略的屏幕截图":::

### <a name="use-audit-logs-to-investigate-power-platform-installation-activity"></a><span data-ttu-id="87e43-152">使用审核日志检查 Power Platform 安装活动</span><span class="sxs-lookup"><span data-stu-id="87e43-152">Use audit logs to investigate Power Platform installation activity</span></span>

<span data-ttu-id="87e43-153">你可以使用团队的审核日志来调查用户从团队中的 "应用" 页面的 " **由你的同事构建** 的" 部分中安装了 Power Platform 应用的事件。</span><span class="sxs-lookup"><span data-stu-id="87e43-153">You can use audit logs for Teams to investigate events where users installed Power Platform apps from the **Built by your colleagues** section of the Apps page in Teams.</span></span> <span data-ttu-id="87e43-154">若要执行此操作，请在**AppInstalled**操作) 下为用户或用户组搜索**已安装应用**团队事件 (的[审核日志](https://docs.microsoft.com/microsoftteams/audit-log-events)。</span><span class="sxs-lookup"><span data-stu-id="87e43-154">To do this, [search the audit log](https://docs.microsoft.com/microsoftteams/audit-log-events) for the **Installed app** Teams event (under the **AppInstalled** operation) for a user or set of users.</span></span> <span data-ttu-id="87e43-155">若要查找**由你的同事自构建**的应用，请在给定记录的详细信息的**AppDistributionMode**属性中查找**TemplatedInstance**值。</span><span class="sxs-lookup"><span data-stu-id="87e43-155">To find apps installed from **Built by your colleagues**, look for the **TemplatedInstance** value in the **AppDistributionMode** property in a given record's details.</span></span> 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 属性中的 TemplatedInstance 值的屏幕截图":::

> [!NOTE]
> <span data-ttu-id="87e43-157">你可以以 CSV 格式导出审核记录，以便更轻松地进行筛选。</span><span class="sxs-lookup"><span data-stu-id="87e43-157">You can export audit records in CSV format for easier filtering.</span></span>

## <a name="related-topics"></a><span data-ttu-id="87e43-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="87e43-158">Related topics</span></span>

- [<span data-ttu-id="87e43-159">在 Power Apps 中共享画布应用</span><span class="sxs-lookup"><span data-stu-id="87e43-159">Share a canvas app in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [<span data-ttu-id="87e43-160">与其他用户共享机器人</span><span class="sxs-lookup"><span data-stu-id="87e43-160">Share your bot with other users</span></span>](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [<span data-ttu-id="87e43-161">管理 Microsoft 团队管理中心中的应用</span><span class="sxs-lookup"><span data-stu-id="87e43-161">Manage apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="87e43-162">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="87e43-162">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="87e43-163">发布通过团队应用提交 API 提交的自定义应用</span><span class="sxs-lookup"><span data-stu-id="87e43-163">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
