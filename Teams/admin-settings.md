---
title: "Microsoft Teams 中适用于应用的管理设置 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何在 Microsoft Teams 中允许和启用应用，包括侧向加载外部应用。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 3e385c1a9a3175d4aaef6ea0eb52d6278c538d94
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2017
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="e532c-103">Microsoft Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="e532c-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="e532c-104">在本节中，我们提到了选项卡、连接器和聊天机器人或这些功能的任意组合（由单个第三方服务以应用形式提供）。</span><span class="sxs-lookup"><span data-stu-id="e532c-104">In this section, we refer to tabs, connectors, and bots, or any combination of these capabilities, provided by a single third-party service as Apps.</span></span> <span data-ttu-id="e532c-105">可以在 Office 365 管理门户中配置管理策略来控制允许哪些外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="e532c-105">There are Admin policies that can be configured in the Office 365 Admin Portal to control which external third-party apps are allowed.</span></span> <span data-ttu-id="e532c-106">通过这些策略可以指定允许和不允许哪些应用、新的外部应用行为以及是否允许侧向加载应用。</span><span class="sxs-lookup"><span data-stu-id="e532c-106">These policies let you specify which apps are allowed and disallowed, new external App behavior, as well as whether side-loading apps is allowed.</span></span>

<span data-ttu-id="e532c-107">**在 Microsoft Teams 中允许外部应用**</span><span class="sxs-lookup"><span data-stu-id="e532c-107">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="e532c-108">默认情况下，启用“在 Microsoft Teams 中允许外部应用”，并选中所有应用。</span><span class="sxs-lookup"><span data-stu-id="e532c-108">By default, allow external apps in Microsoft Teams is enabled with all apps selected.</span></span> <span data-ttu-id="e532c-109">将此策略设置为**“关闭”**后，则禁用所有外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="e532c-109">When turning this policy to **“Off”**, then all external third-party apps are disabled.</span></span> <span data-ttu-id="e532c-110">你可以进行更加精细的控制，先启用允许外部应用，然后单个取消选中你要禁用的特定应用。</span><span class="sxs-lookup"><span data-stu-id="e532c-110">You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="e532c-111">**默认启用新的外部应用**</span><span class="sxs-lookup"><span data-stu-id="e532c-111">**Enable new external apps by default**</span></span>

<span data-ttu-id="e532c-112">每当新应用提交到 Teams 应用目录时，此开关控制此租户中的用户是否可以使用这些应用。</span><span class="sxs-lookup"><span data-stu-id="e532c-112">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant.</span></span> <span data-ttu-id="e532c-113">默认情况下，此策略设置为**“开启”**，表示允许用户在应用添加到 Teams 的应用目录时即可访问这些应用。</span><span class="sxs-lookup"><span data-stu-id="e532c-113">By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog.</span></span> <span data-ttu-id="e532c-114">如果你更希望先验证应用，再允许在 Teams 中使用它们，则将此策略设置为**“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="e532c-114">If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.**</span></span> <span data-ttu-id="e532c-115">请注意，如果将此策略设置为**“关闭”**，你应该定期评估新加的应用，以确保你的用户能够从应用的最新创新和增加内容中获益。</span><span class="sxs-lookup"><span data-stu-id="e532c-115">Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="e532c-116">**允许侧向加载外部应用**</span><span class="sxs-lookup"><span data-stu-id="e532c-116">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="e532c-117">仅获得权限的 Team 所有者或成员可以向 Microsoft Teams 中侧向加载应用。</span><span class="sxs-lookup"><span data-stu-id="e532c-117">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams.</span></span> <span data-ttu-id="e532c-118">向 Microsoft Teams 中侧向加载应用的一些优势如下：</span><span class="sxs-lookup"><span data-stu-id="e532c-118">Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="e532c-119">能够在向 Microsoft 提交应用之前对其进行测试</span><span class="sxs-lookup"><span data-stu-id="e532c-119">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="e532c-120">直接向贵组织中的用户提供应用，而无需向 Office 应用商店提交应用</span><span class="sxs-lookup"><span data-stu-id="e532c-120">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="e532c-121">要详细了解如何向 Microsoft Teams 中侧向加载应用，请参阅：[在团队中侧向加载应用](https://go.microsoft.com/fwlink/?linkid=854631)。</span><span class="sxs-lookup"><span data-stu-id="e532c-121">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![Microsoft Teams 设置的“应用”部分屏幕截图。](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
