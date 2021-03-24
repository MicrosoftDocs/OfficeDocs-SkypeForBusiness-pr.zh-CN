---
title: 从 Skype for Business Online 升级到 Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从 Skype for Business Online 部署将组织升级到 Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65b00f8e56792164ed2aa0b8240d0d131a7bdbcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104008"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="54a87-103">从 Skype for Business Online 升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="54a87-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="54a87-104">![升级过程图，强调部署和实施](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="54a87-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="54a87-105">本文是升级旅程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="54a87-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="54a87-106">在继续之前，请确认已经完成了以下活动:</span><span class="sxs-lookup"><span data-stu-id="54a87-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="54a87-107">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="54a87-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="54a87-108">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="54a87-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="54a87-109">了解 Skype for Business 和 Teams 的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="54a87-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="54a87-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="54a87-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="54a87-111">准备环境</span><span class="sxs-lookup"><span data-stu-id="54a87-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="54a87-112">准备组织</span><span class="sxs-lookup"><span data-stu-id="54a87-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="54a87-113">开展试点</span><span class="sxs-lookup"><span data-stu-id="54a87-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="54a87-114">如果你已完全部署了 Skype for Business Online 并且想要将用户从 Skype for Business 升级到 Teams，请按照本文中的指导操作。</span><span class="sxs-lookup"><span data-stu-id="54a87-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="54a87-115">可以通过向用户分配适当的共存和升级模式，根据组织选择的升级过程，有选择地或全面升级用户。</span><span class="sxs-lookup"><span data-stu-id="54a87-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54a87-116">Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。</span><span class="sxs-lookup"><span data-stu-id="54a87-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="54a87-117">为了最大程度地实现权益并确保组织有适当的时间来实施升级，我们鼓励你立即开始 Microsoft Teams 之旅。</span><span class="sxs-lookup"><span data-stu-id="54a87-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="54a87-118">请记住，成功的升级符合技术和用户准备情况，因此，在导航到 Microsoft Teams 旅程时，请务必参考此处的指南。</span><span class="sxs-lookup"><span data-stu-id="54a87-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="54a87-119">分配共存和升级模式</span><span class="sxs-lookup"><span data-stu-id="54a87-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="54a87-120">可以通过分配 TeamsUpgradePolicy 的 UpgradeToTeams 实例（可以使用 Microsoft Teams 管理中心或 Skype for Business 远程 Windows PowerShell 会话执行）将用户升级到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="54a87-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="54a87-121">若要一步升级整个租户，可以按用户或租户范围执行此操作。</span><span class="sxs-lookup"><span data-stu-id="54a87-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="54a87-122">有关详细信息，请参阅 [设置共存和升级设置和](./setting-your-coexistence-and-upgrade-settings.md) [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="54a87-122">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="54a87-123">一次将所有用户升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="54a87-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="54a87-124">按照以下步骤一次将所有用户升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="54a87-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="54a87-125">步骤 1：将更改通知用户 (可选) </span><span class="sxs-lookup"><span data-stu-id="54a87-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="54a87-126">在 Microsoft Teams 管理中心中，选择 **"组织范围的设置**  >  **""Teams 升级"。**</span><span class="sxs-lookup"><span data-stu-id="54a87-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="54a87-127">在 **"共存模式"** 下，将"通知 Skype for Business 用户，可升级到 **Teams"切换** 为"**开"。**</span><span class="sxs-lookup"><span data-stu-id="54a87-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="54a87-128">步骤 2：为组织将共存模式设置为 TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="54a87-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="54a87-129">在 Microsoft Teams 管理中心中，选择 **"组织范围的设置"。**</span><span class="sxs-lookup"><span data-stu-id="54a87-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="54a87-130">从 **"共存模式** " **下拉列表中选择"仅** Teams 模式"。</span><span class="sxs-lookup"><span data-stu-id="54a87-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="54a87-131">分步升级用户</span><span class="sxs-lookup"><span data-stu-id="54a87-131">Upgrade users in stages</span></span>

<span data-ttu-id="54a87-132">如果要将用户逐渐升级到 TeamsOnly，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="54a87-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="54a87-133">步骤 1：确定要升级的用户组</span><span class="sxs-lookup"><span data-stu-id="54a87-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="54a87-134">通常，组织可能会选择在用户的成功波次中升级其组织。</span><span class="sxs-lookup"><span data-stu-id="54a87-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="54a87-135">首先需要识别这些用户，以便可以轻松在 Microsoft Teams 管理中心中搜索他们。</span><span class="sxs-lookup"><span data-stu-id="54a87-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="54a87-136">或者，可能需要使用 PowerShell 更有效地执行此操作。</span><span class="sxs-lookup"><span data-stu-id="54a87-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="54a87-137">确定给定升级波次的用户集后，继续执行剩余的步骤。</span><span class="sxs-lookup"><span data-stu-id="54a87-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="54a87-138">步骤 2：在当前升级波次中为用户设置通知 (可选) </span><span class="sxs-lookup"><span data-stu-id="54a87-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="54a87-139">如果使用 Microsoft Teams 管理中心，可以一次为最多 20 个用户配置 TeamsUpgradePolicy：</span><span class="sxs-lookup"><span data-stu-id="54a87-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="54a87-140">在 Microsoft Teams 管理中心中，选择"用户"，然后查找并多选最多 20 个应升级的用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="54a87-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="54a87-141">选择 **列表** 视图左上角的"编辑设置"。</span><span class="sxs-lookup"><span data-stu-id="54a87-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="54a87-142">在右侧 **"编辑设置"** 窗格中的 **"Teams 升级"** 下，将"通知 **Skype for Business** 用户"切换到"**开"。**</span><span class="sxs-lookup"><span data-stu-id="54a87-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="54a87-143">注意：如果共存模式的值是"使用组织范围的设置"，则看不到此开关，因此需要首先将这些用户的共存模式显式设置为组织的任何默认值。</span><span class="sxs-lookup"><span data-stu-id="54a87-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="54a87-144">或者，你可能会发现使用 PowerShell 一次为用户组启用通知会更容易。</span><span class="sxs-lookup"><span data-stu-id="54a87-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="54a87-145">步骤 3：将用户的共存模式设置为"仅 Teams"</span><span class="sxs-lookup"><span data-stu-id="54a87-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="54a87-146">如果已准备好升级当前波形中的用户以将 Teams 用作其唯一应用程序，请为用户设置"仅 Teams"共存模式。</span><span class="sxs-lookup"><span data-stu-id="54a87-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="54a87-147">如果使用 Microsoft Teams 管理中心，可以一次为最多 20 个用户配置 TeamsUpgradePolicy：</span><span class="sxs-lookup"><span data-stu-id="54a87-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="54a87-148">在 Microsoft Teams 管理中心中，选择" **用户"，** 然后选中最多 20 个用户复选框。</span><span class="sxs-lookup"><span data-stu-id="54a87-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="54a87-149">选择 **列表** 视图左上角的"编辑设置"。</span><span class="sxs-lookup"><span data-stu-id="54a87-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="54a87-150">在 **右侧"** 编辑设置"窗格中的 **"Teams** 升级"部分下，在下拉列表中将共存模式设置为" **仅** Teams"。</span><span class="sxs-lookup"><span data-stu-id="54a87-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="54a87-151">或者，你可能会发现使用 PowerShell 一次升级用户组更容易。</span><span class="sxs-lookup"><span data-stu-id="54a87-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="54a87-152">步骤 4：为连续的用户波形重复步骤 1-3</span><span class="sxs-lookup"><span data-stu-id="54a87-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="54a87-153">验证升级到"仅 Teams"模式并准备好进行扩展时，请重复上述步骤，将 TeamsOnly 应用到更多用户。</span><span class="sxs-lookup"><span data-stu-id="54a87-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="54a87-154">电话系统和 PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="54a87-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="54a87-155">在用户进入 TeamsOnly 模式后，支持 Teams 手机系统。</span><span class="sxs-lookup"><span data-stu-id="54a87-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="54a87-156"> (如果用户在群岛模式下，则电话系统仅支持 Skype for Business.) </span><span class="sxs-lookup"><span data-stu-id="54a87-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="54a87-157">PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="54a87-157">PSTN connectivity options</span></span>

<span data-ttu-id="54a87-158">在考虑使用 PSTN (公用电话) 时，从 Skype for Business Online 切换到 TeamsOnly 模式时，有两种可能的情况：</span><span class="sxs-lookup"><span data-stu-id="54a87-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="54a87-159">Skype for Business Online 中的用户，具有 Microsoft 呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="54a87-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="54a87-160">升级后，此用户将继续拥有 Microsoft 呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="54a87-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="54a87-161">这是最简单的方案，只需几个步骤。</span><span class="sxs-lookup"><span data-stu-id="54a87-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="54a87-162">有关详细信息，请参阅通过[Microsoft 呼叫计划从 Skype for Business Online。](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="54a87-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="54a87-163">Skype for Business Online 中的用户，通过本地 Skype for Business 或 Cloud Connector Edition 提供本地语音功能。</span><span class="sxs-lookup"><span data-stu-id="54a87-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="54a87-164">用户升级到 Teams 需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="54a87-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="54a87-165">有关详细信息，请参阅使用本地语音[从 Skype for Business Online。](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)</span><span class="sxs-lookup"><span data-stu-id="54a87-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>