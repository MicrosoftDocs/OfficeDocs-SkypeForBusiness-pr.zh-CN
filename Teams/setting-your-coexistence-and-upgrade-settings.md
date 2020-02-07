---
title: 设置共存和升级设置
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 本文将帮助你选择共存模式并设置其他共存设置。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0eee70dd27647e59a742f4155ba292b54684eaa
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837972"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="2e508-103">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="2e508-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="2e508-104">将 Skype for Business 用户升级为使用团队时，有多个选项可帮助你为你的用户设置无缝流程。</span><span class="sxs-lookup"><span data-stu-id="2e508-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="2e508-105">你可以选择同时为组织中的所有用户创建共存和升级设置，也可以为组织中的单个或一组用户更改设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="2e508-106">请注意，旧版本的 Skype for Business 客户端可能无法接受这些设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="2e508-107">有关 Skype for business 客户端版本的详细信息，请转到[skype for business 下载和更新页面](https://docs.microsoft.com/skypeforbusiness/software-updates)。</span><span class="sxs-lookup"><span data-stu-id="2e508-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="2e508-108">通过阅读[了解 Microsoft 团队和 skype for business 共存以及](teams-and-skypeforbusiness-coexistence-and-interoperability.md)[与 skype for](coexistence-chat-calls-presence.md)business 的互操作性或共存，你可以更好地了解可供你使用的模式类型。</span><span class="sxs-lookup"><span data-stu-id="2e508-108">You can get a better understanding of the types of modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="2e508-109">为组织中的所有用户设置升级选项</span><span class="sxs-lookup"><span data-stu-id="2e508-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="2e508-110">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="2e508-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2e508-111">在[Microsoft 团队管理中心](https://admin.teams.microsoft.com/)的左侧导航中，转到 "**组织范围的设置** > **团队升级**"。</span><span class="sxs-lookup"><span data-stu-id="2e508-111">In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), in the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="2e508-112">在 "**团队升级**" 页面上，进行以下更改（如果它们将适合你）。</span><span class="sxs-lookup"><span data-stu-id="2e508-112">At the top of the **Teams upgrade** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="2e508-113">设置**共存**模式。</span><span class="sxs-lookup"><span data-stu-id="2e508-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="2e508-114">**岛**-如果你希望用户能够同时使用 Skype for Business 和团队，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="2e508-115">**仅限 Skype for** business-如果你希望你的用户仅使用 Skype for business，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="2e508-116">**具有团队协作的 Skype For business** -如果你希望用户在使用团队协作（频道）的情况下使用 Skype for business，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-116">**Skype for Business with Teams collaboration** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
        - <span data-ttu-id="2e508-117">使用**团队协作和会议的 Skype For business** -如果您希望用户在使用工作组协作（频道）和团队会议时使用 Skype for business，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-117">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
        - <span data-ttu-id="2e508-118">**仅限团队**（在预览中对于某些组织）-如果希望用户仅使用团队，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-118">**Teams only** (in preview for some organizations) - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="2e508-119">请注意，即使采用此设置，用户仍然可以加入 Skype for Business 中托管的会议。</span><span class="sxs-lookup"><span data-stu-id="2e508-119">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="2e508-120">设置**可供团队升级的 Skype for business 用户的通知**。</span><span class="sxs-lookup"><span data-stu-id="2e508-120">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="2e508-121">如果启用此操作，它将通知 Skype for Business 用户即将升级到团队应用。</span><span class="sxs-lookup"><span data-stu-id="2e508-121">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="2e508-122">**为用户设置用于加入 Skype For business 会议的首选应用**。</span><span class="sxs-lookup"><span data-stu-id="2e508-122">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="2e508-123">此设置确定哪种应用用于加入 Skype for Business 会议，并且无论共存模式的价值如何都有效。</span><span class="sxs-lookup"><span data-stu-id="2e508-123">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="2e508-124">**Skype 会议应用**</span><span class="sxs-lookup"><span data-stu-id="2e508-124">**Skype Meetings app**</span></span>
      - <span data-ttu-id="2e508-125">**具有有限功能的 Skype for business**</span><span class="sxs-lookup"><span data-stu-id="2e508-125">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="2e508-126">设置是否**在 Skype for business 用户的后台下载团队应用**。</span><span class="sxs-lookup"><span data-stu-id="2e508-126">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="2e508-127">此设置将为运行 Windows 版 Skype for Business 的用户自动下载 "团队" 应用。</span><span class="sxs-lookup"><span data-stu-id="2e508-127">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="2e508-128">仅当用户的共存模式是 "仅限团队" 或 "在 Skype for Business 中启用了待升级通知" 时，才会接受此功能。</span><span class="sxs-lookup"><span data-stu-id="2e508-128">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="2e508-129">进行更改后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2e508-129">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="2e508-130">为组织中的单个用户设置升级选项</span><span class="sxs-lookup"><span data-stu-id="2e508-130">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="2e508-131">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="2e508-131">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2e508-132">在左侧导航中，转到 "**用户**"，然后从列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="2e508-132">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="2e508-133">在用户的 "**帐户**" 选项卡上的 "**团队升级**" 下，单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2e508-133">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="2e508-134">你可以设置**共存模式**。</span><span class="sxs-lookup"><span data-stu-id="2e508-134">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="2e508-135">从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="2e508-135">Choose from the following options:</span></span>
     - <span data-ttu-id="2e508-136">**使用组织范围的设置**-如果希望用户使用**组织范围**设置中的设置，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-136">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="2e508-137">**群岛**-如果您希望用户能够使用 Skype for Business 和团队，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-137">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="2e508-138">**仅限 Skype** for business-如果希望用户使用 Skype for business，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-138">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span>
     - <span data-ttu-id="2e508-139">**具有团队协作的 Skype For business** -如果你希望用户除了使用团队协作（频道），还希望使用 Skype for business，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-139">**Skype for Business with Teams collaboration** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
      - <span data-ttu-id="2e508-140">**使用团队协作和会议的 Skype For business** -如果你希望用户在使用工作组协作（频道）和团队会议时使用 Skype for business，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-140">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
     - <span data-ttu-id="2e508-141">**仅限团队**-如果你希望用户仅使用团队，请使用此设置。</span><span class="sxs-lookup"><span data-stu-id="2e508-141">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="2e508-142">用户仍将能够加入 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="2e508-142">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="2e508-143">如果你选择除 "**使用组织范围外的设置**" 之外的任何**共存模式**，你可以选择在用户的 Skype for business 应用中启用通知，即将推出升级到团队的应用。</span><span class="sxs-lookup"><span data-stu-id="2e508-143">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="2e508-144">你可以通过打开 "**通知 Skype for business 用户**" 选项为用户启用此通知。</span><span class="sxs-lookup"><span data-stu-id="2e508-144">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="2e508-145">进行更改后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2e508-145">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="2e508-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="2e508-146">Related topics</span></span>
[<span data-ttu-id="2e508-147">规划旅程</span><span class="sxs-lookup"><span data-stu-id="2e508-147">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="2e508-148">了解 Skype for business 和团队的共存和升级旅程</span><span class="sxs-lookup"><span data-stu-id="2e508-148">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="2e508-149">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="2e508-149">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
