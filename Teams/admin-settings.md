---
title: Microsoft Teams 中适用于应用的管理设置
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: 了解可用于管理 Microsoft 团队中的组织应用的策略和设置。
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ae1776cf57368ea0f18cb6b0e46e5a11dffe447
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45228898"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="5ac75-103">Microsoft Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="5ac75-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="5ac75-104">应用为你的组织提供现成的工具，以充分利用团队。</span><span class="sxs-lookup"><span data-stu-id="5ac75-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="5ac75-105">这些应用结合由 Microsoft （由第三方构建）或您的组织中的开发人员提供的选项卡、消息扩展、连接器和 bot 的功能。</span><span class="sxs-lookup"><span data-stu-id="5ac75-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="5ac75-106">在管理中心的**团队应用**中管理组织的应用。</span><span class="sxs-lookup"><span data-stu-id="5ac75-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="5ac75-107">（请参阅[使用团队管理员角色管理团队](https://docs.microsoft.com/microsoftteams/using-admin-roles)以阅读有关获取管理员角色和权限的信息。）例如，你可以在组织级别允许或阻止应用，设置用于控制团队用户可用的应用的策略，并通过固定对你的用户最重要的应用自定义团队。</span><span class="sxs-lookup"><span data-stu-id="5ac75-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="5ac75-108">我们正在不断改进团队中的应用体验，并添加功能和功能。</span><span class="sxs-lookup"><span data-stu-id="5ac75-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="5ac75-109">随着时间的推移，我们将构建其他应用管理功能，请查看有关应用策略的最新信息。</span><span class="sxs-lookup"><span data-stu-id="5ac75-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="5ac75-110">管理应用程序</span><span class="sxs-lookup"><span data-stu-id="5ac75-110">Manage apps</span></span>

<span data-ttu-id="5ac75-111">使用 "**管理应用**" 页面查看和管理组织的应用程序目录中的所有团队应用。</span><span class="sxs-lookup"><span data-stu-id="5ac75-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="5ac75-112">你可以查看应用的组织级别状态和属性、阻止或允许应用组织级别的应用、将新的自定义应用上载到租户目录以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="5ac75-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="5ac75-113">"**管理应用**" 页面为你提供租户目录中所有可用应用的视图，为你提供了确定要在组织中允许或阻止哪些应用的信息。</span><span class="sxs-lookup"><span data-stu-id="5ac75-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="5ac75-114">然后，你可以使用[应用权限策略](#app-permission-policies)、[应用设置策略](#app-setup-policies)和[自定义应用策略和设置](#custom-app-policies-and-settings)来为你的组织中的特定用户配置应用体验。</span><span class="sxs-lookup"><span data-stu-id="5ac75-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="5ac75-115">若要了解详细信息，请参阅[管理团队中的应用](manage-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="5ac75-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="5ac75-116">应用权限策略</span><span class="sxs-lookup"><span data-stu-id="5ac75-116">App permission policies</span></span>

<span data-ttu-id="5ac75-117">使用应用权限策略，你可以控制你的组织中的特定用户可以使用哪些应用。</span><span class="sxs-lookup"><span data-stu-id="5ac75-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="5ac75-118">你可以允许或阻止由 Microsoft、第三方和你的组织发布的所有应用或特定应用。</span><span class="sxs-lookup"><span data-stu-id="5ac75-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="5ac75-119">例如，你可以使用应用权限策略执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5ac75-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="5ac75-120">向特定用户逐步推出新的第三方或自定义生成的应用。</span><span class="sxs-lookup"><span data-stu-id="5ac75-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="5ac75-121">简化用户体验，尤其是当您开始在整个组织中推出团队时。</span><span class="sxs-lookup"><span data-stu-id="5ac75-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="5ac75-122">若要了解详细信息，请转到[管理团队中的应用权限策略](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5ac75-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="5ac75-123">应用设置策略</span><span class="sxs-lookup"><span data-stu-id="5ac75-123">App setup policies</span></span>

<span data-ttu-id="5ac75-124">应用设置策略允许你为你的用户自定义应用体验。</span><span class="sxs-lookup"><span data-stu-id="5ac75-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="5ac75-125">选择要固定到团队客户端中的应用栏的应用，以及这些应用在 web、桌面和移动客户端上的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="5ac75-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="5ac75-126">下面是有关如何使用应用设置策略的一些示例：</span><span class="sxs-lookup"><span data-stu-id="5ac75-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="5ac75-127">促进核心应用的认识和采纳。</span><span class="sxs-lookup"><span data-stu-id="5ac75-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="5ac75-128">例如，将自定义招聘和人才管理应用固定到 HR 团队的用户。</span><span class="sxs-lookup"><span data-stu-id="5ac75-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="5ac75-129">有选择地固定核心团队功能，如聊天、团队和通话。</span><span class="sxs-lookup"><span data-stu-id="5ac75-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="5ac75-130">这样做有助于确保用户参与团队中的特定活动。</span><span class="sxs-lookup"><span data-stu-id="5ac75-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="5ac75-131">若要了解详细信息，请参阅[管理团队中的应用设置策略](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5ac75-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="5ac75-132">自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="5ac75-132">Custom app policies and settings</span></span>

<span data-ttu-id="5ac75-133">团队允许组织中的开发人员生成、测试并将自定义应用部署到其他用户。</span><span class="sxs-lookup"><span data-stu-id="5ac75-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="5ac75-134">通过直接将 .zip 文件中的应用包上载到团队或个人上下文中，可以将自定义应用添加到团队。</span><span class="sxs-lookup"><span data-stu-id="5ac75-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="5ac75-135">你可以使用应用设置策略控制你的组织中可以上载自定义应用的人员。</span><span class="sxs-lookup"><span data-stu-id="5ac75-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="5ac75-136">你还可以设置组织范围的设置，以控制用户是否可以与特定的自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="5ac75-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="5ac75-137">若要了解详细信息，请转到[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5ac75-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
