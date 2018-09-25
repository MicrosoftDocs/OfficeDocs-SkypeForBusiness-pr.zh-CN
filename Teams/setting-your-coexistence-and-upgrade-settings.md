---
title: 设置您的共存和升级设置
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: bjwhalen
search.appverid: MET150
description: 本文将帮助您选择的共存模式和设置其他共存。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a83382ff46e5a698e3755f2c1d2d859dddd65f0
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013198"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="cbbfc-103">设置您的共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="cbbfc-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="cbbfc-104">升级您的业务用户来使用团队 Skype 时, 有几个选项可帮助您让您的用户的无缝过程。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-104">When you are upgrading your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="cbbfc-105">您可以选择使共存和升级的同时，组织中的用户的所有设置，或您可以为一个或一组用户设置更改您的组织中。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="cbbfc-106">请注意，旧版本的 Skype 业务客户端无法服从这些设置。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span>

<span data-ttu-id="cbbfc-107">分配用户级别的设置优先于组织范围级别设置。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-107">Settings assigned at a user level take precedence over settings applied at the org-wide level.</span></span> <span data-ttu-id="cbbfc-108">您可以获得更好地了解通过阅读[了解共存和升级的业务和团队的 Skype 旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)可供您的模式的类型。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-108">You can get a better understanding of the types of modes that are available to you by reading [Understand coexistence and upgrade journey for Skype for Business and Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="setting-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="cbbfc-109">设置为在组织中的所有用户的的升级选项</span><span class="sxs-lookup"><span data-stu-id="cbbfc-109">Setting upgrade options for all users in your organization</span></span>

<span data-ttu-id="cbbfc-110">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="cbbfc-110">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="cbbfc-111">在左侧导航窗格中，转到**组织范围的设置** > **团队升级**。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-111">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="cbbfc-112">在**工作组升级页**页的顶部，进行以下更改，如果他们将为您的工作。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-112">At the top of the **Teams upgrade page** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="cbbfc-113">将**共存**模式设置。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="cbbfc-114">**群岛**-使用此设置，如果您希望用户能够同时使用这两个 Skype 业务和团队。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="cbbfc-115">**Skype for Business 仅**-使用此设置，如果您希望仅对用户 for Business 使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="cbbfc-116">仅团队**团队仅**-使用此设置，如果您希望用户使用。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-116">**Teams only** - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="cbbfc-117">请注意，即使使用此设置，用户仍可以加入 Skype for Business 中托管的会议。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-117">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="cbbfc-118">设置**通知的业务用户可用于升级团队的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-118">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="cbbfc-119">如果您关闭此功能，它将告知业务用户的 Skype 他们会很快将升级到团队应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-119">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="cbbfc-120">设置**首选应用程序的用户可以加入 Skype 业务会议**。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-120">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="cbbfc-121">此设置确定哪个应用程序用于业务会议加入 Skype，采用无论共存模式的值。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-121">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="cbbfc-122">**Skype 会议应用程序**</span><span class="sxs-lookup"><span data-stu-id="cbbfc-122">**Skype Meetings app**</span></span>
      - <span data-ttu-id="cbbfc-123">**Skype for Business 使用有限的功能**</span><span class="sxs-lookup"><span data-stu-id="cbbfc-123">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="cbbfc-124">设置为**下载适用于业务用户的 Skype 的背景中的团队应用程序**。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-124">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="cbbfc-125">此设置以无提示方式下载 Windows 上运行 for Business 的 Skype 用户团队相关应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-125">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="cbbfc-126">它被有效只有当用户的共存模式为仅团队或 Skype for Business 中启用的挂起升级通知。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-126">It is honored only if coexistence mode for the user is Teams Only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="cbbfc-127">进行更改后，请单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-127">Click **Save** after you make your changes.</span></span>

## <a name="setting-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="cbbfc-128">设置您的组织中的单个用户的升级选项</span><span class="sxs-lookup"><span data-stu-id="cbbfc-128">Setting upgrade options for a single user in your organization</span></span>

<span data-ttu-id="cbbfc-129">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="cbbfc-129">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="cbbfc-130">在左侧导航窗格中，转到**用户**，，然后从列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-130">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="cbbfc-131">在用户，在**升级团队**、 下的**帐户**选项卡上单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-131">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
- <span data-ttu-id="cbbfc-132">您可以设置**共存模式**。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-132">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="cbbfc-133">选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="cbbfc-133">Choose from the following options:</span></span>
    - <span data-ttu-id="cbbfc-134">**使用组织范围的设置**-使用此设置，如果您希望用户使用**组织范围**的设置中的设置。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-134">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
    - <span data-ttu-id="cbbfc-135">**群岛**-使用此设置，如果您希望用户能够使用这两个 Skype 业务和团队。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-135">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
    - <span data-ttu-id="cbbfc-136">**Skype for Business 仅**-使用此设置，如果您希望用户 for Business 使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-136">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span> 
    - <span data-ttu-id="cbbfc-137">仅团队**团队仅**-使用此设置，如果您希望用户使用。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-137">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="cbbfc-138">用户仍可以加入 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-138">The user will still be able to join Skype for Business meetings.</span></span>
3. <span data-ttu-id="cbbfc-139">如果您选择任何**共存模式**以外**使用组织范围的设置**，必须启用中用户的 Skype 的通知的业务应用程序升级到团队即将提供的选项。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-139">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="cbbfc-140">您可以通过打开**Notify 业务用户 Skype**选项启用此通知用户。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-140">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
4. <span data-ttu-id="cbbfc-141">进行更改后，请单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="cbbfc-141">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="cbbfc-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="cbbfc-142">Related topics</span></span>
[<span data-ttu-id="cbbfc-143">规划迁移</span><span class="sxs-lookup"><span data-stu-id="cbbfc-143">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="cbbfc-144">了解共存和升级的 Skype 旅程，业务和团队</span><span class="sxs-lookup"><span data-stu-id="cbbfc-144">Understand coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="cbbfc-145">使用团队一起 Skype for Business 的组织的迁移和互操作性指南</span><span class="sxs-lookup"><span data-stu-id="cbbfc-145">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)
