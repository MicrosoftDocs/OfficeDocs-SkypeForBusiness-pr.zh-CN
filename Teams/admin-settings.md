---
title: Microsoft Teams 中适用于应用的管理设置
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: 了解可用于管理组织中应用的策略和设置，Microsoft Teams。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f78069aea098b6318e49808245f5b17bd90509e0
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856051"
---
# <a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="64048-103">Microsoft Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="64048-103">Admin settings for apps in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="64048-104">应用为组织提供开箱即用的工具，以进一Teams。</span><span class="sxs-lookup"><span data-stu-id="64048-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="64048-105">这些应用结合了由 Microsoft 提供的选项卡、消息传送扩展、连接器和机器人的功能，这些功能由第三方构建，或者由组织中的开发人员提供。</span><span class="sxs-lookup"><span data-stu-id="64048-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="64048-106">在管理中心内为组织管理 **Teams** 应用。</span><span class="sxs-lookup"><span data-stu-id="64048-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="64048-107"> (请参阅使用 Teams 管理员角色管理[Teams](./using-admin-roles.md)以阅读有关获取管理员角色和权限的信息。) 例如，可以在组织级别允许或阻止应用，设置策略以控制可供 Teams 用户使用的应用，以及通过固定对用户最重要的应用来自定义 Teams。</span><span class="sxs-lookup"><span data-stu-id="64048-107">(See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="64048-108">我们正在不断改进应用体验，Teams添加特性和功能。</span><span class="sxs-lookup"><span data-stu-id="64048-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="64048-109">随着时间的推移，我们将构建其他应用管理功能，因此请返回查看有关应用策略最新信息。</span><span class="sxs-lookup"><span data-stu-id="64048-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="64048-110">管理应用</span><span class="sxs-lookup"><span data-stu-id="64048-110">Manage apps</span></span>

<span data-ttu-id="64048-111">使用 **"管理应用**"页查看和管理Teams应用程序目录中的所有应用。</span><span class="sxs-lookup"><span data-stu-id="64048-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="64048-112">可以在组织级别查看应用的状态和属性、在组织级别阻止或允许应用、将新的自定义应用上传到租户目录，以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="64048-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="64048-113">" **管理应用** "页面提供了租户目录中所有可用应用的视图，为你提供确定允许或阻止整个组织哪些应用时需要的信息。</span><span class="sxs-lookup"><span data-stu-id="64048-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="64048-114">然后，可以使用 [应用权限策略](#app-permission-policies)、 [应用设置策略](#app-setup-policies)和自定义应用策略 [和](#custom-app-policies-and-settings) 设置为组织中特定用户配置应用体验。</span><span class="sxs-lookup"><span data-stu-id="64048-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="64048-115">若要了解有关详细信息，请参阅[在 Teams 中管理应用](manage-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="64048-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="64048-116">应用权限策略</span><span class="sxs-lookup"><span data-stu-id="64048-116">App permission policies</span></span>

<span data-ttu-id="64048-117">使用应用权限策略，可以控制哪些应用可供组织的特定用户使用。</span><span class="sxs-lookup"><span data-stu-id="64048-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="64048-118">你可以允许或阻止 Microsoft、第三方和你的组织发布的所有应用或特定应用。</span><span class="sxs-lookup"><span data-stu-id="64048-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="64048-119">例如，可以使用应用权限策略来：</span><span class="sxs-lookup"><span data-stu-id="64048-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="64048-120">逐渐向特定用户推出新的第三方或自定义生成应用。</span><span class="sxs-lookup"><span data-stu-id="64048-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="64048-121">简化用户体验，尤其是当您开始在整个组织中Teams时。</span><span class="sxs-lookup"><span data-stu-id="64048-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="64048-122">若要了解有关详细信息，请转到在[中管理应用权限Teams。](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="64048-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="64048-123">应用设置策略</span><span class="sxs-lookup"><span data-stu-id="64048-123">App setup policies</span></span>

<span data-ttu-id="64048-124">应用设置策略允许为用户自定义应用体验。</span><span class="sxs-lookup"><span data-stu-id="64048-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="64048-125">在 Web 客户端、桌面客户端和移动Teams选择要固定到应用栏的应用及其显示顺序。</span><span class="sxs-lookup"><span data-stu-id="64048-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="64048-126">下面是一些如何使用应用设置策略的示例：</span><span class="sxs-lookup"><span data-stu-id="64048-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="64048-127">促进核心应用的认知和采用。</span><span class="sxs-lookup"><span data-stu-id="64048-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="64048-128">例如，为 HR 团队中的用户固定自定义招聘和才能管理应用。</span><span class="sxs-lookup"><span data-stu-id="64048-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="64048-129">选择性地固定Teams聊天、聊天和Teams等功能。</span><span class="sxs-lookup"><span data-stu-id="64048-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="64048-130">这样做有助于确保用户参与特定活动Teams。</span><span class="sxs-lookup"><span data-stu-id="64048-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="64048-131">若要了解有关详细信息，请查看在 应用中[管理应用Teams。](teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="64048-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="64048-132">自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="64048-132">Custom app policies and settings</span></span>

<span data-ttu-id="64048-133">Teams允许组织中开发人员生成、测试自定义应用，以及将自定义应用部署到其他用户。</span><span class="sxs-lookup"><span data-stu-id="64048-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="64048-134">可以通过将应用包Teams文件直接上传到团队.zip个人上下文中，将自定义应用添加到自定义应用。</span><span class="sxs-lookup"><span data-stu-id="64048-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="64048-135">可以使用应用设置策略来控制组织中哪些人可以上传自定义应用。</span><span class="sxs-lookup"><span data-stu-id="64048-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="64048-136">还可以设置组织范围的设置，以控制用户是否可以与特定的自定义应用交互。</span><span class="sxs-lookup"><span data-stu-id="64048-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="64048-137">若要了解有关详细信息，请转到管理应用中[的自定义应用策略Teams。](teams-custom-app-policies-and-settings.md)</span><span class="sxs-lookup"><span data-stu-id="64048-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>