---
title: 升级到 Microsoft 团队在线业务 Skype |部署
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 业务 online 从 Skype 升级到团队的注意事项
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc1334e019abadb030199518df15b0dde74dde52
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835332"
---
<span data-ttu-id="6b8b5-103">![升级旅程，重点强调部署阶段和实现阶段](media/upgrade-banner-deployment.png "升级旅程，重点强调部署阶段和实现阶段")</span><span class="sxs-lookup"><span data-stu-id="6b8b5-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="6b8b5-104">本文是您升级旅程的不同阶段提供部署和实施的一部分。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="6b8b5-105">在继续之前，确认您已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="6b8b5-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="6b8b5-106">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="6b8b5-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="6b8b5-107">定义您的项目范围</span><span class="sxs-lookup"><span data-stu-id="6b8b5-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="6b8b5-108">商业和团队理解共存和 Skype 的互操作性</span><span class="sxs-lookup"><span data-stu-id="6b8b5-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="6b8b5-109">选择您升级旅程</span><span class="sxs-lookup"><span data-stu-id="6b8b5-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="6b8b5-110">准备您的环境</span><span class="sxs-lookup"><span data-stu-id="6b8b5-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="6b8b5-111">准备您的组织</span><span class="sxs-lookup"><span data-stu-id="6b8b5-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="6b8b5-112">执行试验</span><span class="sxs-lookup"><span data-stu-id="6b8b5-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="6b8b5-113">从 Skype for Business Online 升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="6b8b5-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="6b8b5-114">如果具有完全部署 Skype online 业务，并且希望向工作组从 for Business 的 Skype 升级您的用户，请遵循本文中的指南。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="6b8b5-115">您可以有选择地升级用户或一体化、 基于升级历程的已选择您的组织，通过向用户分配适当的共存和升级的模式。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="6b8b5-116">分配的共存和升级模式</span><span class="sxs-lookup"><span data-stu-id="6b8b5-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="6b8b5-117">您可以通过分配 TeamsUpgradePolicy，可以执行的业务远程 Windows Powershell 会话中使用的 Microsoft 团队管理中心或 Skype 的 UpgradeToTeams 实例升级到 TeamsOnly 模式的用户。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="6b8b5-118">您可以这样做基于每个用户，或在租户范围内如果希望 ugprade 一个步骤中的整个租户。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="6b8b5-119">有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="6b8b5-120">一次升级到团队的所有用户</span><span class="sxs-lookup"><span data-stu-id="6b8b5-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="6b8b5-121">按照以下步骤一次将所有用户升级到团队。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="6b8b5-122">步骤 1： 通知用户的更改 （可选）</span><span class="sxs-lookup"><span data-stu-id="6b8b5-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="6b8b5-123">在 Microsoft 团队管理中心，选择**组织范围设置** > **团队升级**。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="6b8b5-124">**共存模式**下, 到**上**更改的**通知的 Skype 业务用户升级到团队是可用的**开关。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="6b8b5-125">步骤 2： 将共存模式设置为 TeamsOnly 组织</span><span class="sxs-lookup"><span data-stu-id="6b8b5-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="6b8b5-126">在 Microsoft 团队管理中心中，选择**组织范围的设置**。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="6b8b5-127">从**共存模式**下拉列表中选择**仅团队**模式。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="6b8b5-128">分阶段升级用户</span><span class="sxs-lookup"><span data-stu-id="6b8b5-128">Upgrade users in stages</span></span>

<span data-ttu-id="6b8b5-129">如果您想要在用户逐步升级到 TeamsOnly，请按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="6b8b5-130">步骤 1： 确定升级的用户组</span><span class="sxs-lookup"><span data-stu-id="6b8b5-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="6b8b5-131">通常组织可以选择升级成功随后在其组织的用户。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="6b8b5-132">您需要先确定这些用户，以便您可以方便地搜索联系人在管理中心中的 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6b8b5-133">此外，您可能想要使用 PowerShell 更有效地执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="6b8b5-134">一旦您确定的给定升级波形的用户数，继续执行其余步骤。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="6b8b5-135">步骤 2： 为用户的通知中设置当前 ugprade wave （可选）</span><span class="sxs-lookup"><span data-stu-id="6b8b5-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="6b8b5-136">如果使用的 Microsoft 团队管理中心，您可以同时为最多 20 个用户配置 TeamsUpgradePolicy:</span><span class="sxs-lookup"><span data-stu-id="6b8b5-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="6b8b5-137">在 Microsoft 团队管理中心中，选择**用户**和查找和多重选择应升级的最多 20 个用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="6b8b5-138">在列表视图的左上角中，选择**编辑设置**。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="6b8b5-139">在右侧，在**升级团队**、 下的**编辑设置**窗格中更改为**上**的**通知业务用户 Skype**交换机。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="6b8b5-140">注意： 如果共存模式的值为"使用组织范围设置"，您将不会看到此开关，因此您将需要首先为这些用户对任何默认值为组织显式设置的共存模式</span><span class="sxs-lookup"><span data-stu-id="6b8b5-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="6b8b5-141">此外，您会发现它更轻松地为用户同时使用 PowerShell 组启用通知。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="6b8b5-142">步骤 3： 为用户仅团队的共存模式</span><span class="sxs-lookup"><span data-stu-id="6b8b5-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="6b8b5-143">当您准备升级中的用户当前波形团队用作其唯一的应用程序时，为用户仅团队的共存模式。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="6b8b5-144">如果使用的 Microsoft 团队管理中心，您可以同时为最多 20 个用户配置 TeamsUpgradePolicy:</span><span class="sxs-lookup"><span data-stu-id="6b8b5-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="6b8b5-145">在 Microsoft 团队管理中心中，选择**用户**，然后选择最多 20 个用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="6b8b5-146">在列表视图的左上角中，选择**编辑设置**。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="6b8b5-147">在右侧，**团队升级**部分下的**编辑设置**窗格中将共存模式设置为**仅团队**下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="6b8b5-148">此外，您会发现它易于升级的用户同时使用 PowerShell 组。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="6b8b5-149">步骤 4： 为用户的连续随后重复步骤 1-3</span><span class="sxs-lookup"><span data-stu-id="6b8b5-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="6b8b5-150">根据您验证升级到团队仅模式，并且已准备好展开，重复前面的步骤将 TeamsOnly 应用于多个用户。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="6b8b5-151">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="6b8b5-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="6b8b5-152">如果您的业务 Online 部署的 Skype 包括电话系统与调用计划和 Microsoft 是您公用电话交换网 (pstn) 提供商，将用户升级到团队将自动转换到团队呼叫的入站的 PSTN。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="6b8b5-153">如果您的业务 Online 部署的 Skype 包括与云连接器 Edition 的电话系统，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="6b8b5-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
