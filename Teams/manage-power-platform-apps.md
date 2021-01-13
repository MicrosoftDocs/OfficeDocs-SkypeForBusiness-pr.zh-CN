---
title: 在 Microsoft Teams 管理中心管理 Microsoft Power Platform 应用
author: cichur
ms.author: v-cichur
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
description: 了解如何在 Microsoft Teams 管理中心管理对基于 Microsoft Power Platform 构建的自定义应用的访问权限。
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831292"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="93d42-103">在 Microsoft Teams 管理中心管理 Microsoft Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="93d42-103">Manage Microsoft Power Platform apps in the Microsoft Teams admin center</span></span>

## <a name="microsoft-power-platform-apps-in-teams"></a><span data-ttu-id="93d42-104">Teams 中的 Microsoft Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="93d42-104">Microsoft Power Platform apps in Teams</span></span>

<span data-ttu-id="93d42-105">本文概述了如何在 Microsoft Teams 管理中心管理 [Microsoft Power Platform](https://powerplatform.microsoft.com/) 应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-105">This article gives you an overview of how to manage [Microsoft Power Platform](https://powerplatform.microsoft.com/) apps in the Microsoft Teams admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="93d42-106">本文适用于组织中使用 Power Apps 或 Power Virtual Agents 的制造商创建的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-106">This article applies to custom apps created by makers in your organization using Power Apps or Power Virtual Agents.</span></span> <span data-ttu-id="93d42-107">这些自定义应用会自动添加到 Teams。</span><span class="sxs-lookup"><span data-stu-id="93d42-107">These custom apps are automatically added to Teams.</span></span> <span data-ttu-id="93d42-108">本文不适用于从"应用"页面安装或通过应用设置策略固定到 Teams 的 Power Apps 应用或 Power Virtual Agents 应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-108">This article doesn't apply to the Power Apps app or Power Virtual Agents app that are installed from the Apps page or pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="93d42-109">你可以像在"管理应用"页面上的其他任何应用一样[](manage-apps.md)使用应用权限策略和应用[](teams-app-permission-policies.md)设置策略来管理[这些应用](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="93d42-109">You manage those apps as you would for any other app on the [Manage apps](manage-apps.md) page, using [app permission policies](teams-app-permission-policies.md), and [app setup policies](teams-app-setup-policies.md).</span></span>

<span data-ttu-id="93d42-110">[Power Apps](https://powerapps.microsoft.com) 是一个低代码/无代码应用程序开发环境，您的组织中的制造商可以使用该环境构建连接到业务数据的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-110">[Power Apps](https://powerapps.microsoft.com) is a low-code/no-code application development environment that makers in your organization can use to build custom apps that connect to your business data.</span></span> <span data-ttu-id="93d42-111">[Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 是一个无代码机器人生成环境，制造商可以创建功能强大的机器人。</span><span class="sxs-lookup"><span data-stu-id="93d42-111">[Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) is a no-code bot building environment for makers to create powerful bots.</span></span> <span data-ttu-id="93d42-112">将 Microsoft Power Platform 应用集成到 Teams 中后，组织可以简化业务流程、更快速地响应不断变化的业务需求，从而推动更好的协作，并创建和共享自定义解决方案以提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="93d42-112">With the integration of Microsoft Power Platform apps into Teams, organizations can streamline business processes, respond to changing business needs more rapidly to drive greater collaboration, and create and share custom solutions to be more productive.</span></span>  

<span data-ttu-id="93d42-113">组织中制造商创建的 Microsoft Power Platform 应用会自动添加到 Teams。</span><span class="sxs-lookup"><span data-stu-id="93d42-113">Microsoft Power Platform apps created by makers in your organization are automatically added to Teams.</span></span> <span data-ttu-id="93d42-114">制造商可以使用 Power Apps 中的共享功能以及 [Power Virtual](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) Agents 中的共享功能来控制谁可以访问 [其应用](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)。</span><span class="sxs-lookup"><span data-stu-id="93d42-114">Makers can control who can access their app by using the [sharing feature in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) and the [sharing feature in Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/admin-share-bots).</span></span>

<span data-ttu-id="93d42-115">创建或共享 Microsoft Power Platform 应用时，用户可以通过进入"为同事构建的组织名称而构建 \*\*\*\*"，在"应用"页面上查看  >  **和安装该应用**。</span><span class="sxs-lookup"><span data-stu-id="93d42-115">When a Microsoft Power Platform app is created or shared, users can view and install it on the Apps page by going to **Built for *Your Organization Name*** > **Built by your colleagues**.</span></span> <span data-ttu-id="93d42-116"> (创建或共享应用后，可能需要几分钟时间，应用才能在此处显示。) </span><span class="sxs-lookup"><span data-stu-id="93d42-116">(It might take a few minutes after an app is created or shared for the app to appear here.)</span></span>

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text=""应用"页的屏幕截图，显示同事"构建"中列出的 Microsoft Power Platform 应用":::

<span data-ttu-id="93d42-118">如果应用满足以下条件之一，用户将看到同事构建的应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-118">A user will see an app in **Built by your colleagues** if the app meets one of the following conditions.</span></span>

|<span data-ttu-id="93d42-119">Power Apps</span><span class="sxs-lookup"><span data-stu-id="93d42-119">Power Apps</span></span> |<span data-ttu-id="93d42-120">Power Virtual Agents</span><span class="sxs-lookup"><span data-stu-id="93d42-120">Power Virtual Agents</span></span>  |
|---------|---------|
|<ul><li><span data-ttu-id="93d42-121">用户创建了应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-121">The user created the app.</span></span></li><li><span data-ttu-id="93d42-122">该应用已直接与用户共享。</span><span class="sxs-lookup"><span data-stu-id="93d42-122">The app was shared directly with the user.</span></span></li><li><span data-ttu-id="93d42-123">用户最近使用过该应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-123">The user recently used the app.</span></span> </li></ul>| <ul><li><span data-ttu-id="93d42-124">用户创建了机器人。</span><span class="sxs-lookup"><span data-stu-id="93d42-124">The user created the bot.</span></span></li><li><span data-ttu-id="93d42-125">机器人由用户所属团队拥有。</span><span class="sxs-lookup"><span data-stu-id="93d42-125">The bot is owned by a team the user is a member of.</span></span> </li></ul>        |

<span data-ttu-id="93d42-126">用户安装 Microsoft Power Platform 应用的方式与安装任何其他 Teams 应用相同。</span><span class="sxs-lookup"><span data-stu-id="93d42-126">Users install Microsoft Power Platform apps in the same way they install any other Teams app.</span></span> <span data-ttu-id="93d42-127">请记住，用户只能将应用安装到他们拥有权限的上下文中，例如，他们拥有的团队、他们参与的聊天或者他们的个人范围。</span><span class="sxs-lookup"><span data-stu-id="93d42-127">Keep in mind that users can only install  apps to the context to which they have permissions, for example, a team they own, a chat that they're a part of, or their personal scope.</span></span>

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="93d42-128">在 Microsoft Teams 管理中心管理对 Microsoft Power Platform 应用的访问权限</span><span class="sxs-lookup"><span data-stu-id="93d42-128">Manage access to Microsoft Power Platform apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="93d42-129">作为管理员，你可以控制 Microsoft Power Platform 应用是否列在同事在 Teams 的"应用"页面上的"构建"中。</span><span class="sxs-lookup"><span data-stu-id="93d42-129">As an admin, you can control whether Microsoft Power Platform apps are listed in **Built by your colleagues** on the Apps page in Teams.</span></span> <span data-ttu-id="93d42-130">可以统一阻止或允许 Power Apps 中创建的所有应用，或者"管理应用"页面上组织级别的 Power Virtual [](manage-apps.md) Agents 中创建的所有应用，或者针对使用应用权限策略的特定[用户创建的所有应用](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="93d42-130">You can collectively block or allow all apps created in Power Apps or all apps created in Power Virtual Agents at the org level on the [Manage apps](manage-apps.md) page or for specific users using [app permission policies](teams-app-permission-policies.md).</span></span>

<span data-ttu-id="93d42-131">组织的 **应用商店中的** 共享 **Power** Apps 和共享 Power Virtual Agent 应用表示该特定平台上创建的所有应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-131">The **Shared Power Apps** and **Shared Power Virtual Agent Apps** apps in your organization's app store represent all apps created on that particular platform.</span></span> <span data-ttu-id="93d42-132">如果在组织级别或特定用户中阻止了一个或两个这些应用，这些用户将看不到同事构建的这些平台的任何应用，并且无法将其安装在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="93d42-132">If you block one or both these apps at the org level or for specific users, those users can't see any apps from those platforms in **Built by your colleagues** and can't install them in Teams.</span></span>  

<span data-ttu-id="93d42-133">请记住，你可以控制对在 Power Apps 和 Power Virtual Agents 中创建的所有应用的访问，但不能允许或阻止单个应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-133">Keep in mind that you can control access to all apps created in Power Apps and Power Virtual Agents but you can't allow or block individual apps.</span></span> <span data-ttu-id="93d42-134">制造商决定谁可以从 Power Apps 和 Power Virtual Agents 内通过共享功能访问他们创建的应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-134">Makers decide who can access the apps they create through the sharing feature from within Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="93d42-135">如果制作者与用户共享他们在 Power Virtual Agents 中创建的应用，并且你阻止了该用户的 **共享 Power Virtual Agents** 应用，则用户将无法在 Teams 中查看或安装该平台的任何应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-135">If a maker shared an app they created in Power Virtual Agents with a user and you blocked **Shared Power Virtual Agents Apps** for that user, the user won't be able to see or install any apps from that platform in Teams.</span></span>

<span data-ttu-id="93d42-136">如果允许用户从 Power Apps 或 Power Virtual Agents 访问应用，然后阻止用户从一个或两个平台访问应用，则用户仍然可以访问和使用在阻止应用之前安装的 Microsoft Power Platforms 应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-136">If a user is allowed to access apps from Power Apps or Power Virtual Agents, and you then block the user from accessing apps from one or both these platforms, the user can still access and use Microsoft Power Platforms apps that they installed before you blocked the app or apps.</span></span> <span data-ttu-id="93d42-137">但是，用户无法再从同事构建的这些平台查看或 **安装任何应用**。</span><span class="sxs-lookup"><span data-stu-id="93d42-137">However, the user can no longer see or install any apps from those platforms in **Built by your colleagues**.</span></span>

> [!NOTE]
> <span data-ttu-id="93d42-138">"**管理应用"** 页面上的"允许与自定义应用组织范围内的 [](manage-apps.md)应用交互"设置适用于组织中的每个人，并控制他们是否可与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="93d42-138">The **Allow interaction with custom apps** org-wide app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can interact with custom apps.</span></span> <span data-ttu-id="93d42-139">组织范围的应用设置控制所有用户的行为，并覆盖分配给用户的其他任何应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="93d42-139">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="93d42-140">默认情况下，此设置已打开。</span><span class="sxs-lookup"><span data-stu-id="93d42-140">By default, this setting is turned on.</span></span> <span data-ttu-id="93d42-141">如果此设置已关闭，则您的组织中的用户无法查看或安装任何自定义应用，包括 Microsoft Power Platform 应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-141">If this setting is turned off, users in your organization can't see or install any custom apps, including Microsoft Power Platform apps.</span></span> <span data-ttu-id="93d42-142">若要了解有关详细信息，请参阅["管理组织范围内的应用设置"。](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="93d42-142">To learn  more, see [Manage org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a><span data-ttu-id="93d42-143">为组织允许或阻止 Microsoft Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="93d42-143">Allow or block Microsoft Power Platform apps for your organization</span></span>

<span data-ttu-id="93d42-144">默认情况下， **组织中所有 Teams** 用户都允许共享 Power Apps 和 **共享 Power Virtual Agent** 应用。</span><span class="sxs-lookup"><span data-stu-id="93d42-144">By default, **Shared Power Apps** and **Shared Power Virtual Agent Apps** are allowed for all Teams users in your organization.</span></span> <span data-ttu-id="93d42-145">可以在 Microsoft Teams 管理中心的"管理应用"[](manage-apps.md)页面上在组织级别阻止或允许他们。</span><span class="sxs-lookup"><span data-stu-id="93d42-145">You can block or allow them at the org level on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>  

1. <span data-ttu-id="93d42-146">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="93d42-146">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="93d42-147">只有全局管理员或 Teams 服务管理员才能访问页面。</span><span class="sxs-lookup"><span data-stu-id="93d42-147">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="93d42-148">在应用列表中，执行下列操作之一。</span><span class="sxs-lookup"><span data-stu-id="93d42-148">In the list of apps, do one of the following.</span></span>

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text=""管理应用"页面的屏幕截图，其中显示了共享的 Microsoft Power Platform 应用":::

    - <span data-ttu-id="93d42-150">若要阻止在 Power Apps 或 Power Virtual Agents 中为组织中所有用户创建的应用，请搜索"共享 **Power Apps"** 或"**共享 Power Virtual Agent** 应用"，将其选中，然后单击"**阻止"。**</span><span class="sxs-lookup"><span data-stu-id="93d42-150">To block apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="93d42-151">若要允许组织中所有用户在 Power Apps 或 Power Virtual Agents 中创建应用，请搜索"共享 **Power Apps"** 或"**共享 Power Virtual Agent** 应用"，将其选中，然后单击"允许 **"。**</span><span class="sxs-lookup"><span data-stu-id="93d42-151">To allow apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Allow**.</span></span>

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a><span data-ttu-id="93d42-152">允许或阻止特定用户的 Microsoft Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="93d42-152">Allow or block Microsoft Power Platform apps for specific users</span></span>

<span data-ttu-id="93d42-153">若要允许或阻止组织中特定用户访问在 Power Apps 或 Power Virtual Agents 中创建的应用，请创建并分配一个或多个自定义 [应用权限策略](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="93d42-153">To allow or block specific users in your organization from accessing apps created in Power Apps or Power Virtual Agents, create and assign one or more custom [app permission policies](teams-app-permission-policies.md).</span></span> 

<span data-ttu-id="93d42-154">例如，若要阻止特定用户访问在 Power Apps 中创建的应用，请创建自定义应用权限策略以阻止共享 **Power Apps，** 然后将该策略分配给这些用户。</span><span class="sxs-lookup"><span data-stu-id="93d42-154">For example, to block specific users from accessing apps created in Power Apps, create a custom app permission policy to block **Shared Power Apps**, and then assign the policy to those users.</span></span>

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="阻止共享 Power Apps 的示例自定义应用权限策略的屏幕截图":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a><span data-ttu-id="93d42-156">使用审核日志调查 Microsoft Power Platform 安装活动</span><span class="sxs-lookup"><span data-stu-id="93d42-156">Use audit logs to investigate Microsoft Power Platform installation activity</span></span>

<span data-ttu-id="93d42-157">可以使用 Teams 的审核日志调查用户从 Teams 中"应用"页的"由同事生成"部分安装 Microsoft Power Platform 应用的事件。</span><span class="sxs-lookup"><span data-stu-id="93d42-157">You can use audit logs for Teams to investigate events where users installed Microsoft Power Platform apps from the **Built by your colleagues** section of the Apps page in Teams.</span></span> <span data-ttu-id="93d42-158">为此，请审核日志 [](https://docs.microsoft.com/microsoftteams/audit-log-events)AppInstalled 操作 (用户或用户集的 **AppInstalled** 操作) 应用 Teams 事件列表。</span><span class="sxs-lookup"><span data-stu-id="93d42-158">To do this, [search the audit log](https://docs.microsoft.com/microsoftteams/audit-log-events) for the **Installed app** Teams event (under the **AppInstalled** operation) for a user or set of users.</span></span> <span data-ttu-id="93d42-159">若要查找同事从"生成"安装的应用，请查找给定记录详细信息 **中 AppDistributionMode** 属性中的 **TemplatedInstance** 值。</span><span class="sxs-lookup"><span data-stu-id="93d42-159">To find apps installed from **Built by your colleagues**, look for the **TemplatedInstance** value in the **AppDistributionMode** property in a given record's details.</span></span> 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 属性中 TemplatedInstance 值的屏幕截图":::

> [!NOTE]
> <span data-ttu-id="93d42-161">可以导出 CSV 格式的审核记录，以便更轻松地筛选。</span><span class="sxs-lookup"><span data-stu-id="93d42-161">You can export audit records in CSV format for easier filtering.</span></span>

## <a name="related-topics"></a><span data-ttu-id="93d42-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="93d42-162">Related topics</span></span>

- [<span data-ttu-id="93d42-163">在 Power Apps 中共享画布应用</span><span class="sxs-lookup"><span data-stu-id="93d42-163">Share a canvas app in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [<span data-ttu-id="93d42-164">与其他用户共享机器人</span><span class="sxs-lookup"><span data-stu-id="93d42-164">Share your bot with other users</span></span>](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [<span data-ttu-id="93d42-165">在 Microsoft Teams 管理中心管理应用</span><span class="sxs-lookup"><span data-stu-id="93d42-165">Manage apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="93d42-166">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="93d42-166">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="93d42-167">发布通过 Teams 应用提交 API 提交的自定义应用</span><span class="sxs-lookup"><span data-stu-id="93d42-167">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
