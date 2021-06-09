---
title: 在管理中心内管理 microsoft Power Platform Microsoft Teams应用
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
description: 了解如何在管理中心内管理对基于 Microsoft Power Platform 的自定义Microsoft Teams的访问权限。
ms.openlocfilehash: 03940d402bd2259287e1e69f844e6560424f15e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096156"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8823c-103">在管理中心内管理 microsoft Power Platform Microsoft Teams应用</span><span class="sxs-lookup"><span data-stu-id="8823c-103">Manage Microsoft Power Platform apps in the Microsoft Teams admin center</span></span>

## <a name="microsoft-power-platform-apps-in-teams"></a><span data-ttu-id="8823c-104">Teams 中的 Microsoft Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="8823c-104">Microsoft Power Platform apps in Teams</span></span>

<span data-ttu-id="8823c-105">本文概述了如何在管理中心内管理 Microsoft [Power Platform](https://powerplatform.microsoft.com/) Microsoft Teams应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-105">This article gives you an overview of how to manage [Microsoft Power Platform](https://powerplatform.microsoft.com/) apps in the Microsoft Teams admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="8823c-106">本文适用于组织中制造商使用自定义应用或Power Apps Power Virtual Agents。</span><span class="sxs-lookup"><span data-stu-id="8823c-106">This article applies to custom apps created by makers in your organization using Power Apps or Power Virtual Agents.</span></span> <span data-ttu-id="8823c-107">这些自定义应用会自动添加到Teams。</span><span class="sxs-lookup"><span data-stu-id="8823c-107">These custom apps are automatically added to Teams.</span></span> <span data-ttu-id="8823c-108">本文不适用于应用Power Apps应用Power Virtual Agents通过应用设置策略固定到Teams的应用或应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-108">This article doesn't apply to the Power Apps app or Power Virtual Agents app that are installed from the Apps page or pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="8823c-109">你可以像管理应用页面上任何其他应用一样，使用应用权限[](manage-apps.md)策略[和应用](teams-app-permission-policies.md)设置策略来管理[这些应用](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8823c-109">You manage those apps as you would for any other app on the [Manage apps](manage-apps.md) page, using [app permission policies](teams-app-permission-policies.md), and [app setup policies](teams-app-setup-policies.md).</span></span>

<span data-ttu-id="8823c-110">[Power Apps](https://powerapps.microsoft.com)是一个低代码/无代码的应用程序开发环境，您的组织中的制造商可以使用该环境构建连接到业务数据的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-110">[Power Apps](https://powerapps.microsoft.com) is a low-code/no-code application development environment that makers in your organization can use to build custom apps that connect to your business data.</span></span> <span data-ttu-id="8823c-111">[Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents)是一个无代码机器人生成环境，制造商可以创建功能强大的机器人。</span><span class="sxs-lookup"><span data-stu-id="8823c-111">[Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) is a no-code bot building environment for makers to create powerful bots.</span></span> <span data-ttu-id="8823c-112">将 Microsoft Power Platform 应用集成到 Teams 后，组织可以简化业务流程、更快速地响应不断变化的业务需求，从而推动更好的协作，并创建和共享自定义解决方案以提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="8823c-112">With the integration of Microsoft Power Platform apps into Teams, organizations can streamline business processes, respond to changing business needs more rapidly to drive greater collaboration, and create and share custom solutions to be more productive.</span></span>  

<span data-ttu-id="8823c-113">由您组织中制造商创建的 Microsoft Power Platform 应用将自动添加到Teams。</span><span class="sxs-lookup"><span data-stu-id="8823c-113">Microsoft Power Platform apps created by makers in your organization are automatically added to Teams.</span></span> <span data-ttu-id="8823c-114">制作者可以通过使用应用中的共享功能以及 Power Apps[](/powerapps/maker/canvas-apps/share-app)中的共享功能来控制[谁](/power-virtual-agents/admin-share-bots)可以访问Power Virtual Agents。</span><span class="sxs-lookup"><span data-stu-id="8823c-114">Makers can control who can access their app by using the [sharing feature in Power Apps](/powerapps/maker/canvas-apps/share-app) and the [sharing feature in Power Virtual Agents](/power-virtual-agents/admin-share-bots).</span></span>

<span data-ttu-id="8823c-115">创建或共享 Microsoft Power Platform 应用后，用户可以在"应用"页面上查看并安装该应用，\*\*\*\* 其方式为"为同事构建的组织名称  >  **生成"。**</span><span class="sxs-lookup"><span data-stu-id="8823c-115">When a Microsoft Power Platform app is created or shared, users can view and install it on the Apps page by going to **Built for *Your Organization Name*** > **Built by your colleagues**.</span></span> <span data-ttu-id="8823c-116"> (创建或共享应用后，可能需要几分钟时间，应用才能在此处显示。) </span><span class="sxs-lookup"><span data-stu-id="8823c-116">(It might take a few minutes after an app is created or shared for the app to appear here.)</span></span>

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="应用页的屏幕截图，显示由同事构建中列出的 Microsoft Power Platform 应用":::

<span data-ttu-id="8823c-118">如果应用满足 **以下条件之** 一，用户将看到同事生成的应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-118">A user will see an app in **Built by your colleagues** if the app meets one of the following conditions.</span></span>

|<span data-ttu-id="8823c-119">Power Apps</span><span class="sxs-lookup"><span data-stu-id="8823c-119">Power Apps</span></span> |<span data-ttu-id="8823c-120">Power Virtual Agents</span><span class="sxs-lookup"><span data-stu-id="8823c-120">Power Virtual Agents</span></span>  |
|---------|---------|
|<ul><li><span data-ttu-id="8823c-121">用户创建了应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-121">The user created the app.</span></span></li><li><span data-ttu-id="8823c-122">该应用已直接与用户共享。</span><span class="sxs-lookup"><span data-stu-id="8823c-122">The app was shared directly with the user.</span></span></li><li><span data-ttu-id="8823c-123">用户最近使用过该应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-123">The user recently used the app.</span></span> </li></ul>| <ul><li><span data-ttu-id="8823c-124">用户创建了机器人。</span><span class="sxs-lookup"><span data-stu-id="8823c-124">The user created the bot.</span></span></li><li><span data-ttu-id="8823c-125">机器人由用户所属团队拥有。</span><span class="sxs-lookup"><span data-stu-id="8823c-125">The bot is owned by a team the user is a member of.</span></span> </li></ul>        |

<span data-ttu-id="8823c-126">用户安装 Microsoft Power Platform 应用的方式与安装任何其他 Teams相同。</span><span class="sxs-lookup"><span data-stu-id="8823c-126">Users install Microsoft Power Platform apps in the same way they install any other Teams app.</span></span> <span data-ttu-id="8823c-127">请记住，用户只能将应用安装到他们拥有权限的上下文中，例如，他们拥有的团队、他们参与的聊天或者他们的个人范围。</span><span class="sxs-lookup"><span data-stu-id="8823c-127">Keep in mind that users can only install  apps to the context to which they have permissions, for example, a team they own, a chat that they're a part of, or their personal scope.</span></span>

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8823c-128">在管理中心内管理对 Microsoft Power Platform Microsoft Teams的访问权限</span><span class="sxs-lookup"><span data-stu-id="8823c-128">Manage access to Microsoft Power Platform apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="8823c-129">作为管理员，你可以控制 Microsoft Power Platform 应用是否列在同事在"应用"页面的"构建"Teams。</span><span class="sxs-lookup"><span data-stu-id="8823c-129">As an admin, you can control whether Microsoft Power Platform apps are listed in **Built by your colleagues** on the Apps page in Teams.</span></span> <span data-ttu-id="8823c-130">你可以共同阻止或允许在 Power Apps 中创建的所有应用，或者允许所有在 Power Virtual Agents 中创建的应用在"管理应用"页面的[](manage-apps.md)组织级别创建，或者允许特定用户使用应用权限[策略 创建的所有应用](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8823c-130">You can collectively block or allow all apps created in Power Apps or all apps created in Power Virtual Agents at the org level on the [Manage apps](manage-apps.md) page or for specific users using [app permission policies](teams-app-permission-policies.md).</span></span>

<span data-ttu-id="8823c-131">组织的 **Power Apps** 中的共享应用和 **共享 Power Virtual Agent** 应用表示该特定平台上创建的所有应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-131">The **Shared Power Apps** and **Shared Power Virtual Agent Apps** apps in your organization's app store represent all apps created on that particular platform.</span></span> <span data-ttu-id="8823c-132">如果在组织级别或特定用户中阻止了一个或两个这些应用，这些用户无法从同事构建的这些平台看到任何应用，并且无法将它们安装在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="8823c-132">If you block one or both these apps at the org level or for specific users, those users can't see any apps from those platforms in **Built by your colleagues** and can't install them in Teams.</span></span>  

<span data-ttu-id="8823c-133">请记住，你可以控制对在 Power Apps 和 Power Virtual Agents 中创建的所有应用的访问，但不能允许或阻止单个应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-133">Keep in mind that you can control access to all apps created in Power Apps and Power Virtual Agents but you can't allow or block individual apps.</span></span> <span data-ttu-id="8823c-134">制作者决定谁可以通过共享功能从游戏和游戏内访问Power Apps Power Virtual Agents。</span><span class="sxs-lookup"><span data-stu-id="8823c-134">Makers decide who can access the apps they create through the sharing feature from within Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="8823c-135">如果制作者与Power Virtual Agents共享了他们在 Power Virtual Agents 中创建的应用，并且你阻止了该用户的共享 **Power Virtual Agents** 应用，则用户将无法在 Teams 中查看或安装来自该平台的任何应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-135">If a maker shared an app they created in Power Virtual Agents with a user and you blocked **Shared Power Virtual Agents Apps** for that user, the user won't be able to see or install any apps from that platform in Teams.</span></span>

<span data-ttu-id="8823c-136">如果允许用户从 Power Apps 或 Power Virtual Agents 访问应用，然后阻止用户从一个或两个平台访问应用，则在您阻止应用或应用之前，该用户仍可以访问和使用他们安装的 Microsoft Power Platforms 应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-136">If a user is allowed to access apps from Power Apps or Power Virtual Agents, and you then block the user from accessing apps from one or both these platforms, the user can still access and use Microsoft Power Platforms apps that they installed before you blocked the app or apps.</span></span> <span data-ttu-id="8823c-137">但是，用户不再可以在同事构建的 中查看或安装这些 **平台的任何应用**。</span><span class="sxs-lookup"><span data-stu-id="8823c-137">However, the user can no longer see or install any apps from those platforms in **Built by your colleagues**.</span></span>

> [!NOTE]
> <span data-ttu-id="8823c-138">"**管理应用**"页上的"允许与自定义应用与组织 [](manage-apps.md)范围的自定义应用交互"设置适用于组织中的每个人，并控制他们是否可与自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="8823c-138">The **Allow interaction with custom apps** org-wide app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can interact with custom apps.</span></span> <span data-ttu-id="8823c-139">组织范围的应用设置可控制所有用户的行为，并且可覆盖分配给用户的任何其他应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="8823c-139">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="8823c-140">默认情况下，此设置已启动。</span><span class="sxs-lookup"><span data-stu-id="8823c-140">By default, this setting is turned on.</span></span> <span data-ttu-id="8823c-141">如果此设置已关闭，则您的组织中的用户无法查看或安装任何自定义应用，包括 Microsoft Power Platform 应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-141">If this setting is turned off, users in your organization can't see or install any custom apps, including Microsoft Power Platform apps.</span></span> <span data-ttu-id="8823c-142">有关详细信息，请参阅 [管理组织范围内的应用设置](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="8823c-142">To learn  more, see [Manage org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a><span data-ttu-id="8823c-143">为组织允许或阻止 Microsoft Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="8823c-143">Allow or block Microsoft Power Platform apps for your organization</span></span>

<span data-ttu-id="8823c-144">默认情况下，**组织中Power Apps\*\*\*\*共享应用程序和共享 Power Virtual Agent** 应用Teams共享 Power Virtual Agent 应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-144">By default, **Shared Power Apps** and **Shared Power Virtual Agent Apps** are allowed for all Teams users in your organization.</span></span> <span data-ttu-id="8823c-145">可以在管理中心的"管理应用"页面上在组织级别阻止[](manage-apps.md)Microsoft Teams应用。</span><span class="sxs-lookup"><span data-stu-id="8823c-145">You can block or allow them at the org level on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>  

1. <span data-ttu-id="8823c-146">在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="8823c-146">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="8823c-147">只有全局管理员或Teams才能访问页面。</span><span class="sxs-lookup"><span data-stu-id="8823c-147">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="8823c-148">在应用列表中，执行下列操作之一。</span><span class="sxs-lookup"><span data-stu-id="8823c-148">In the list of apps, do one of the following.</span></span>

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="管理应用页面的屏幕截图，显示共享的 Microsoft Power Platform 应用":::

    - <span data-ttu-id="8823c-150">若要阻止在 Power Apps 或 Power Virtual Agents 中创建的应用，请搜索"共享 Power Apps"或"**共享 Power Virtual Agent** 应用 **"，** 将其选中，然后单击"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="8823c-150">To block apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="8823c-151">若要允许在 Power Apps 或 Power Virtual Agents 中创建应用，请搜索"共享 Power Apps"或 **"共享 Power Virtual Agent** 应用 **"，** 将其选中，然后单击"允许 **"。**</span><span class="sxs-lookup"><span data-stu-id="8823c-151">To allow apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Allow**.</span></span>

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a><span data-ttu-id="8823c-152">允许或阻止特定用户的 Microsoft Power Platform 应用</span><span class="sxs-lookup"><span data-stu-id="8823c-152">Allow or block Microsoft Power Platform apps for specific users</span></span>

<span data-ttu-id="8823c-153">若要允许或阻止组织中特定用户访问在 Power Apps 或 Power Virtual Agents 中创建的应用，请创建并分配一个或多个自定义[应用权限策略](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8823c-153">To allow or block specific users in your organization from accessing apps created in Power Apps or Power Virtual Agents, create and assign one or more custom [app permission policies](teams-app-permission-policies.md).</span></span> 

<span data-ttu-id="8823c-154">例如，若要阻止特定用户访问 Power Apps 中创建的应用，请创建自定义应用权限策略来阻止共享 Power Apps **，然后将** 策略分配给这些用户。</span><span class="sxs-lookup"><span data-stu-id="8823c-154">For example, to block specific users from accessing apps created in Power Apps, create a custom app permission policy to block **Shared Power Apps**, and then assign the policy to those users.</span></span>

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="阻止了共享应用的自定义应用权限策略Power Apps屏幕截图":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a><span data-ttu-id="8823c-156">使用审核日志调查 Microsoft Power Platform 安装活动</span><span class="sxs-lookup"><span data-stu-id="8823c-156">Use audit logs to investigate Microsoft Power Platform installation activity</span></span>

<span data-ttu-id="8823c-157">可以使用适用于 Teams 的审核日志，以调查用户从"应用"页的"同事生成"部分安装 Microsoft Power Platform Teams。</span><span class="sxs-lookup"><span data-stu-id="8823c-157">You can use audit logs for Teams to investigate events where users installed Microsoft Power Platform apps from the **Built by your colleagues** section of the Apps page in Teams.</span></span> <span data-ttu-id="8823c-158">为此，在"AppInstalled 审核日志 **Teams"** 下 (用户或一组用户的"已安装应用") "事件"。 [](./audit-log-events.md)</span><span class="sxs-lookup"><span data-stu-id="8823c-158">To do this, [search the audit log](./audit-log-events.md) for the **Installed app** Teams event (under the **AppInstalled** operation) for a user or set of users.</span></span> <span data-ttu-id="8823c-159">若要查找从同事 **生成安装的应用**，请查找给定记录详细信息 **中 AppDistributionMode** 属性中的 **TemplatedInstance** 值。</span><span class="sxs-lookup"><span data-stu-id="8823c-159">To find apps installed from **Built by your colleagues**, look for the **TemplatedInstance** value in the **AppDistributionMode** property in a given record's details.</span></span> 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 属性中 TemplatedInstance 值的屏幕截图":::

> [!NOTE]
> <span data-ttu-id="8823c-161">可以导出 CSV 格式的审核记录，以便更轻松地筛选。</span><span class="sxs-lookup"><span data-stu-id="8823c-161">You can export audit records in CSV format for easier filtering.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8823c-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="8823c-162">Related topics</span></span>

- [<span data-ttu-id="8823c-163">在应用中共享画布Power Apps</span><span class="sxs-lookup"><span data-stu-id="8823c-163">Share a canvas app in Power Apps</span></span>](/powerapps/maker/canvas-apps/share-app)
- [<span data-ttu-id="8823c-164">与其他用户共享机器人</span><span class="sxs-lookup"><span data-stu-id="8823c-164">Share your bot with other users</span></span>](/power-virtual-agents/admin-share-bots)
- [<span data-ttu-id="8823c-165">在管理中心Microsoft Teams应用</span><span class="sxs-lookup"><span data-stu-id="8823c-165">Manage apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="8823c-166">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="8823c-166">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="8823c-167">发布通过应用提交 API Teams提交的自定义应用</span><span class="sxs-lookup"><span data-stu-id="8823c-167">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)