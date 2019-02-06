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
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 668e44b66b08b16a04e730c43dbbe02a9edea4fe
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754628"
---
<span data-ttu-id="e3115-103">![升级旅程，重点强调部署阶段和实现阶段](media/upgrade-banner-deployment.png "升级旅程，重点强调部署阶段和实现阶段")</span><span class="sxs-lookup"><span data-stu-id="e3115-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e3115-104">本文是您升级旅程的不同阶段提供部署和实施的一部分。</span><span class="sxs-lookup"><span data-stu-id="e3115-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e3115-105">在继续之前，确认您已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="e3115-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="e3115-106">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="e3115-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e3115-107">定义您的项目范围</span><span class="sxs-lookup"><span data-stu-id="e3115-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="e3115-108">商业和团队理解共存和 Skype 的互操作性</span><span class="sxs-lookup"><span data-stu-id="e3115-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="e3115-109">选择您升级旅程</span><span class="sxs-lookup"><span data-stu-id="e3115-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="e3115-110">准备您的环境</span><span class="sxs-lookup"><span data-stu-id="e3115-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="e3115-111">准备您的组织</span><span class="sxs-lookup"><span data-stu-id="e3115-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="e3115-112">执行试验</span><span class="sxs-lookup"><span data-stu-id="e3115-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="e3115-113">从联机业务的 Skype 升级到团队</span><span class="sxs-lookup"><span data-stu-id="e3115-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="e3115-114">如果具有完全部署 Skype online 业务，并且希望向工作组从 for Business 的 Skype 升级您的用户，请遵循本文中的指南。</span><span class="sxs-lookup"><span data-stu-id="e3115-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="e3115-115">您可以有选择地升级用户或一体化、 基于升级历程的已选择您的组织，通过向用户分配适当的共存和升级的模式。</span><span class="sxs-lookup"><span data-stu-id="e3115-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="e3115-116">分配的共存和升级模式</span><span class="sxs-lookup"><span data-stu-id="e3115-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="e3115-117">您可以通过分配 TeamsUpgradePolicy，可以执行的业务远程 Windows Powershell 会话中使用的 Microsoft 团队管理中心或 Skype 的 TeamsOnly 模式升级团队用户。</span><span class="sxs-lookup"><span data-stu-id="e3115-117">You can upgrade your users by Teams by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="e3115-118">有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="e3115-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="e3115-119">一次升级到团队的所有用户</span><span class="sxs-lookup"><span data-stu-id="e3115-119">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="e3115-120">按照以下步骤一次将所有用户升级到团队。</span><span class="sxs-lookup"><span data-stu-id="e3115-120">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change"></a><span data-ttu-id="e3115-121">步骤 1： 通知用户的更改</span><span class="sxs-lookup"><span data-stu-id="e3115-121">Step 1: Notify the users of the change</span></span>

1. <span data-ttu-id="e3115-122">在 Microsoft 团队管理中心，选择**组织范围设置** > **团队升级**。</span><span class="sxs-lookup"><span data-stu-id="e3115-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="e3115-123">**共存模式**下, 到**上**更改的**通知的 Skype 业务用户升级到团队是可用的**开关。</span><span class="sxs-lookup"><span data-stu-id="e3115-123">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a><span data-ttu-id="e3115-124">步骤 2： 为用户设置的共存模式</span><span class="sxs-lookup"><span data-stu-id="e3115-124">Step 2: Set the coexistence mode for the users</span></span>

1. <span data-ttu-id="e3115-125">在 Microsoft 团队管理中心中，选择**组织范围的设置**。</span><span class="sxs-lookup"><span data-stu-id="e3115-125">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="e3115-126">从**共存模式**下拉列表中选择**仅团队**模式。</span><span class="sxs-lookup"><span data-stu-id="e3115-126">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="e3115-127">分阶段升级用户</span><span class="sxs-lookup"><span data-stu-id="e3115-127">Upgrade users in stages</span></span>

<span data-ttu-id="e3115-128">如果您想要为团队中逐步升级您的用户，请按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e3115-128">Follow these steps if you want to gradually upgrade your users to Teams.</span></span>

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a><span data-ttu-id="e3115-129">步骤 1： 创建您升级的用户群体</span><span class="sxs-lookup"><span data-stu-id="e3115-129">Step 1: Create your user cohorts for the upgrade</span></span>

<span data-ttu-id="e3115-130">用户群体是将同时移至仅团队模式的用户的组。</span><span class="sxs-lookup"><span data-stu-id="e3115-130">User cohorts are groups of users who will be moved to Teams Only mode at the same time.</span></span>

<span data-ttu-id="e3115-131">创建您的用户群体 （将链接添加到用户选择页）</span><span class="sxs-lookup"><span data-stu-id="e3115-131">To create your user cohorts (Add link to user selection page)</span></span>

### <a name="step-2-set-the-user-mode-to-islands"></a><span data-ttu-id="e3115-132">步骤 2： 将用户模式下设置为群岛</span><span class="sxs-lookup"><span data-stu-id="e3115-132">Step 2: Set the user mode to Islands</span></span>

1. <span data-ttu-id="e3115-133">在 Microsoft 团队管理中心中，选择**用户**，然后选择用户群体。</span><span class="sxs-lookup"><span data-stu-id="e3115-133">In the Microsoft Teams admin center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="e3115-134">**升级团队**、 旁边选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="e3115-134">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="e3115-135">在**工作组升级**窗格的**共存模式**下，从下拉列表中选择**群岛**。</span><span class="sxs-lookup"><span data-stu-id="e3115-135">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Islands** from the drop-down list.</span></span>

### <a name="step-3-set-notification-for-the-user-optional"></a><span data-ttu-id="e3115-136">步骤 3： 为用户的通知 （可选）</span><span class="sxs-lookup"><span data-stu-id="e3115-136">Step 3: Set notification for the user (optional)</span></span>

1. <span data-ttu-id="e3115-137">在 Microsoft 团队管理中心中，选择**用户**，然后选择用户群体。</span><span class="sxs-lookup"><span data-stu-id="e3115-137">In the Microsoft Teams admin center, select **Users**, and select a user cohort.</span></span>
2. <span data-ttu-id="e3115-138">**升级团队**、 旁边选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="e3115-138">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="e3115-139">在**工作组升级**窗格的**共存模式**下，更改为**上**的**通知业务用户 Skype**开关。</span><span class="sxs-lookup"><span data-stu-id="e3115-139">In the **Teams Upgrade** pane, under **Coexistence mode**, change **Notify the Skype for Business user** switch to **On**.</span></span>

### <a name="step-4-set-the-user-mode-to-teams-only"></a><span data-ttu-id="e3115-140">步骤 4： 将用户模式下设置为仅团队</span><span class="sxs-lookup"><span data-stu-id="e3115-140">Step 4: Set the user mode to Teams Only</span></span>

<span data-ttu-id="e3115-141">当您准备升级团队用作其唯一的应用程序的用户时，为团队仅用户的共存模式。</span><span class="sxs-lookup"><span data-stu-id="e3115-141">When you are ready to upgrade the users to use Teams as their only application, set the Coexistence mode for the user to Teams Only.</span></span>

1. <span data-ttu-id="e3115-142">在 Microsoft 团队管理中心中，选择**用户**，然后选择用户群体。</span><span class="sxs-lookup"><span data-stu-id="e3115-142">In the Microsoft Teams admin center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="e3115-143">**升级团队**、 旁边选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="e3115-143">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="e3115-144">在**工作组升级**窗格的**共存模式**下，从下拉列表中选择**仅团队**。</span><span class="sxs-lookup"><span data-stu-id="e3115-144">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Teams Only** from the drop-down list.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e3115-145">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="e3115-145">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e3115-146">如果您的业务 Online 部署的 Skype 包括电话系统与调用计划和 Microsoft 是您公用电话交换网 (pstn) 提供商，将用户升级到团队将自动转换到团队呼叫的入站的 PSTN。</span><span class="sxs-lookup"><span data-stu-id="e3115-146">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="e3115-147">如果您的业务 Online 部署的 Skype 包括与云连接器 Edition 的电话系统，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="e3115-147">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>