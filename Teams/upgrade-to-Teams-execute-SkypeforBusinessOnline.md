---
title: 将 Skype for Business Online 升级到 Microsoft 团队 |部署
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 从 Skype for Business Online 升级到团队的注意事项
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03eda4a90cc90eed38e6a1f6bb6ff6751291ffc1
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706622"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="122a1-103">从 Skype for Business Online 升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="122a1-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="122a1-104">![升级旅行图，强调部署和实现](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="122a1-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="122a1-105">本文是升级过程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="122a1-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="122a1-106">继续之前，请确认你已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="122a1-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="122a1-107">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="122a1-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="122a1-108">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="122a1-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="122a1-109">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="122a1-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="122a1-110">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="122a1-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="122a1-111">准备好你的环境</span><span class="sxs-lookup"><span data-stu-id="122a1-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="122a1-112">准备好您的组织</span><span class="sxs-lookup"><span data-stu-id="122a1-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="122a1-113">开展了一个试验</span><span class="sxs-lookup"><span data-stu-id="122a1-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="122a1-114">如果已部署了完全部署的 Skype for business Online，并且想要将用户从 Skype for Business 升级到团队，请按照本文中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="122a1-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="122a1-115">通过为用户分配适当的共存和升级模式，你可以有选择地或从你的组织选择的升级历程升级用户。</span><span class="sxs-lookup"><span data-stu-id="122a1-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="122a1-116">Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。</span><span class="sxs-lookup"><span data-stu-id="122a1-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="122a1-117">为了最大程度地实现收益并确保你的组织有适当的时间实施升级，我们鼓励你立即开始迁移到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="122a1-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="122a1-118">请记住，成功升级会使技术和用户准备相一致，因此，在您向 Microsoft 团队导航旅行时，请务必利用本指南。</span><span class="sxs-lookup"><span data-stu-id="122a1-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="122a1-119">分配共存和升级模式</span><span class="sxs-lookup"><span data-stu-id="122a1-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="122a1-120">你可以通过分配 TeamsUpgradePolicy 的 UpgradeToTeams 实例将你的用户升级到 TeamsOnly 模式，这可以通过使用 Microsoft 团队管理中心或 Skype for business 远程 Windows Powershell 会话来执行。</span><span class="sxs-lookup"><span data-stu-id="122a1-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="122a1-121">你可以基于每个用户执行此操作，也可以在租户范围内执行此操作，前提是要在一个步骤中升级整个租户。</span><span class="sxs-lookup"><span data-stu-id="122a1-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="122a1-122">有关详细信息，请参阅[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy：管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="122a1-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="122a1-123">一次将所有用户升级到团队</span><span class="sxs-lookup"><span data-stu-id="122a1-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="122a1-124">请按照以下步骤一次将所有用户升级到团队。</span><span class="sxs-lookup"><span data-stu-id="122a1-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="122a1-125">步骤1：将更改通知给用户（可选）</span><span class="sxs-lookup"><span data-stu-id="122a1-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="122a1-126">在 "Microsoft 团队管理中心" 中，选择 "**组织范围设置** > **团队升级**"。</span><span class="sxs-lookup"><span data-stu-id="122a1-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="122a1-127">在 "**共存模式**" 下，更改 "**通知 Skype for business" 用户是否有升级到团队的功能**切换到 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="122a1-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="122a1-128">步骤2：将组织的共存模式设置为 TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="122a1-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="122a1-129">在 "Microsoft 团队管理中心" 中，选择 "**组织范围的设置**"。</span><span class="sxs-lookup"><span data-stu-id="122a1-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="122a1-130">从 "**共存模式**" 下拉列表中选择 "**仅团队**模式"。</span><span class="sxs-lookup"><span data-stu-id="122a1-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="122a1-131">分阶段升级用户</span><span class="sxs-lookup"><span data-stu-id="122a1-131">Upgrade users in stages</span></span>

<span data-ttu-id="122a1-132">如果想要将用户逐步升级到 TeamsOnly，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="122a1-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="122a1-133">步骤1：确定要升级的用户组</span><span class="sxs-lookup"><span data-stu-id="122a1-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="122a1-134">组织通常可以选择在用户成功的用户的成功波上升级其组织。</span><span class="sxs-lookup"><span data-stu-id="122a1-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="122a1-135">你将首先确定这些用户，以便可以在 Microsoft 团队管理中心轻松搜索它们。</span><span class="sxs-lookup"><span data-stu-id="122a1-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="122a1-136">或者，你可能希望使用 PowerShell 更高效地执行此操作。</span><span class="sxs-lookup"><span data-stu-id="122a1-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="122a1-137">一旦确定了给定升级 wave 的用户集，请继续执行剩余步骤。</span><span class="sxs-lookup"><span data-stu-id="122a1-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="122a1-138">步骤2：为当前升级浪潮中的用户设置通知（可选）</span><span class="sxs-lookup"><span data-stu-id="122a1-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="122a1-139">如果使用的是 Microsoft 团队管理中心，则可以同时为多达20个用户配置 TeamsUpgradePolicy：</span><span class="sxs-lookup"><span data-stu-id="122a1-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="122a1-140">在 Microsoft 团队管理中心，选择 "**用户**"，然后找到多达20个应升级的用户的复选框，然后多选。</span><span class="sxs-lookup"><span data-stu-id="122a1-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="122a1-141">选择 listview 左上角的 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="122a1-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="122a1-142">在右侧的 "**编辑设置**" 窗格中，在 "**团队升级**" 下，"更改**通知 Skype for Business 用户**" 切换到 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="122a1-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="122a1-143">注意：如果 "共存" 模式的值为 "使用组织范围的设置"，你将看不到此开关，因此你需要首先将这些用户的共存模式显式设置为组织的默认值。</span><span class="sxs-lookup"><span data-stu-id="122a1-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="122a1-144">或者，你可能会发现使用 PowerShell 一次性为用户组启用通知更容易。</span><span class="sxs-lookup"><span data-stu-id="122a1-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="122a1-145">步骤3：将用户的共存模式设置为 "仅限团队"</span><span class="sxs-lookup"><span data-stu-id="122a1-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="122a1-146">准备好升级当前浪潮中的用户以使用团队作为其唯一的应用程序时，将用户的共存模式设置为 "仅限团队"。</span><span class="sxs-lookup"><span data-stu-id="122a1-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="122a1-147">如果使用的是 Microsoft 团队管理中心，则可以同时为多达20个用户配置 TeamsUpgradePolicy：</span><span class="sxs-lookup"><span data-stu-id="122a1-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="122a1-148">在 Microsoft 团队管理中心，选择 "**用户**"，然后选择最多20个用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="122a1-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="122a1-149">选择 listview 左上角的 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="122a1-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="122a1-150">在右侧的 "**编辑设置**" 窗格中，在 "**团队升级**" 部分中，在下拉列表中将 "共存模式" 设置为 "**仅限团队团队**"。</span><span class="sxs-lookup"><span data-stu-id="122a1-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="122a1-151">或者，你可能会发现使用 PowerShell 一次性升级用户组更容易。</span><span class="sxs-lookup"><span data-stu-id="122a1-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="122a1-152">步骤4：对连续的用户波形重复步骤1-3</span><span class="sxs-lookup"><span data-stu-id="122a1-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="122a1-153">当你验证升级到 "仅团队" 模式并准备好进行扩展时，请重复前面的步骤以将 TeamsOnly 应用于更多用户。</span><span class="sxs-lookup"><span data-stu-id="122a1-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="122a1-154">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="122a1-154">Phone System and Teams upgrade</span></span>

<span data-ttu-id="122a1-155">如果您的 Skype for Business Online 部署包括带有呼叫计划的电话系统，并且 Microsoft 是您的公共交换电话网络（PSTN）提供商，则将用户升级到团队会自动将入站 PSTN 呼叫转到团队。</span><span class="sxs-lookup"><span data-stu-id="122a1-155">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="122a1-156">如果您的 Skype for Business Online 部署包括带有云连接器版本的电话系统，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="122a1-156">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
