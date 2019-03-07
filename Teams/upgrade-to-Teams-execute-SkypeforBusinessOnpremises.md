---
title: 为业务内部部署到的 Microsoft 团队升级 Skype |部署 |Lync
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 为业务本地部署从 Skype 升级到团队的注意事项。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78c69b8fb54a430269e63836ef430d63270841f8
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464745"
---
<span data-ttu-id="078e1-103">![升级旅程，重点强调部署阶段和实现阶段](media/upgrade-banner-deployment.png "升级旅程，重点强调部署阶段和实现阶段")</span><span class="sxs-lookup"><span data-stu-id="078e1-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="078e1-104">本文是您升级旅程的不同阶段提供部署和实施的一部分。</span><span class="sxs-lookup"><span data-stu-id="078e1-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="078e1-105">在继续之前，确认您已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="078e1-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="078e1-106">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="078e1-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="078e1-107">定义您的项目范围</span><span class="sxs-lookup"><span data-stu-id="078e1-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="078e1-108">商业和团队理解共存和 Skype 的互操作性</span><span class="sxs-lookup"><span data-stu-id="078e1-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="078e1-109">选择您升级旅程</span><span class="sxs-lookup"><span data-stu-id="078e1-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="078e1-110">准备您的环境</span><span class="sxs-lookup"><span data-stu-id="078e1-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="078e1-111">准备您的组织</span><span class="sxs-lookup"><span data-stu-id="078e1-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="078e1-112">执行试验</span><span class="sxs-lookup"><span data-stu-id="078e1-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="078e1-113">从业务在本地部署 Skype 升级到团队</span><span class="sxs-lookup"><span data-stu-id="078e1-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="078e1-114">请遵循本文中的指南，如果您已经部署了 for Business 的 Skype 或 Microsoft Lync 本地和贵组织希望如何升级到团队也有选择地 — 通过使用多个共存模式 — 或一体化。</span><span class="sxs-lookup"><span data-stu-id="078e1-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="078e1-115">第一步是设置混合连接性与 Office 365 租户，然后您将用户移至 Skype 业务 online 和将其分配适当的共存和升级模式。</span><span class="sxs-lookup"><span data-stu-id="078e1-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="078e1-116">步骤 1： 部署混合连接性</span><span class="sxs-lookup"><span data-stu-id="078e1-116">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="078e1-117">将用户升级到团队的主要先决条件是部署混合连接性。</span><span class="sxs-lookup"><span data-stu-id="078e1-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="078e1-118">这样做可能会为您现有的 Skype 业务或 Lync 部署新的外部连接或只使用 Office 365 租户配置混合关系。</span><span class="sxs-lookup"><span data-stu-id="078e1-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span>

<span data-ttu-id="078e1-119">详细信息，请参阅[Deploy Skype 业务服务器和 Skype 业务 online 之间的混合连接性](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="078e1-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="078e1-120">步骤 2： 将用户移动到业务 online Skype</span><span class="sxs-lookup"><span data-stu-id="078e1-120">Step 2: Move users to Skype for Business Online</span></span>

<span data-ttu-id="078e1-121">在您完成混合安装程序后，将用户移至 Skype 中，为业务 Online。</span><span class="sxs-lookup"><span data-stu-id="078e1-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span>

<span data-ttu-id="078e1-122">有关详细信息，请参阅[移动用户从本地到业务 online Skype](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="078e1-122">For more information, see [Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span></span>

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="078e1-123">步骤 3： 分配共存并升级模式</span><span class="sxs-lookup"><span data-stu-id="078e1-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="078e1-124">您已为业务 Online 到 Skype 移动用户后，您可以将其分配基于您的组织已选择升级旅程的相应共存模式。</span><span class="sxs-lookup"><span data-stu-id="078e1-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="078e1-125">有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="078e1-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="078e1-126">与业务服务器 2019年和未来的业务服务器 2015 Skype 的累积更新的 Skype，您将能够单步执行 （将用户移动到 Skype 业务 online） 的步骤 2 和步骤 3 （向工作组的升级用户）。</span><span class="sxs-lookup"><span data-stu-id="078e1-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="078e1-127">发布的业务服务器 2019 Skype 之后，将提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="078e1-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="078e1-128">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="078e1-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="078e1-129">如果您正在转换您从企业语音的业务的本地部署到与调用计划的电话系统的 Skype 和 Microsoft 将您的公用电话交换网 (pstn) 提供商 — 和假定您已完成的电话号码移植 — 将用户升级到团队将自动转换为团队的入站的 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="078e1-129">If you’re transitioning your Skype for Business on-premises deployment from enterprise voice to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="078e1-130">如果调用计划不可用，则需要转换为 Microsoft 电话系统直接路由企业语音部署。</span><span class="sxs-lookup"><span data-stu-id="078e1-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="078e1-131">若要向工作组升级您的用户，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="078e1-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>