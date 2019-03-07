---
title: 升级到 Microsoft 团队业务混合部署的 Skype |PSTN
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 从业务混合部署的 Skype 升级到团队的注意事项。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e27e36a26115acf23536edb896066d6bc78daa4e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464809"
---
<span data-ttu-id="7bf3c-103">![升级旅程，重点强调部署阶段和实现阶段](media/upgrade-banner-deployment.png "升级旅程，重点强调部署阶段和实现阶段")</span><span class="sxs-lookup"><span data-stu-id="7bf3c-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="7bf3c-104">本文是您升级旅程的不同阶段提供部署和实施的一部分。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="7bf3c-105">在继续之前，确认您已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="7bf3c-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="7bf3c-106">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="7bf3c-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="7bf3c-107">定义您的项目范围</span><span class="sxs-lookup"><span data-stu-id="7bf3c-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="7bf3c-108">商业和团队理解共存和 Skype 的互操作性</span><span class="sxs-lookup"><span data-stu-id="7bf3c-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="7bf3c-109">选择您升级旅程</span><span class="sxs-lookup"><span data-stu-id="7bf3c-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="7bf3c-110">准备您的环境</span><span class="sxs-lookup"><span data-stu-id="7bf3c-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="7bf3c-111">准备您的组织</span><span class="sxs-lookup"><span data-stu-id="7bf3c-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="7bf3c-112">执行试验</span><span class="sxs-lookup"><span data-stu-id="7bf3c-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="7bf3c-113">从业务混合部署的 Skype 升级到团队</span><span class="sxs-lookup"><span data-stu-id="7bf3c-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="7bf3c-114">请遵循本文中的指南，如果您已经部署了 for Business 的 Skype 或 Microsoft Lync 的本地和其配置为与 Office 365 租户，混合部署中，您的组织希望在升级到团队也有选择地 — 通过使用多个共存模式 — 或一体化。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="7bf3c-115">对于任一升级旅程，您需要将用户移动到 Skype 业务 online （如果它们不已联机驻留），然后将其分配适当的共存和升级的模式。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="7bf3c-116">步骤 1： 将用户移动到业务 online Skype</span><span class="sxs-lookup"><span data-stu-id="7bf3c-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="7bf3c-117">此步骤应用于当前驻留在内部部署的用户。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="7bf3c-118">有关业务 online 将这些用户移动到 Skype 的详细信息，请参阅[移动用户从本地-到业务 online Skype](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="7bf3c-119">步骤 2： 分配共存并升级模式</span><span class="sxs-lookup"><span data-stu-id="7bf3c-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="7bf3c-120">您已为业务 Online 到 Skype 移动用户后，您可以将其分配基于您的组织已选择升级旅程的相应共存模式。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="7bf3c-121">有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="7bf3c-122">与业务服务器 2019年和未来的业务服务器 2015 Skype 的累积更新的 Skype，您将能够单步执行 （将用户移动到 Skype 业务 online） 的步骤 1 和步骤 2 （向工作组的升级用户）。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="7bf3c-123">发布的业务服务器 2019 Skype 之后，将提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="7bf3c-124">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="7bf3c-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="7bf3c-125">如果您正在转换到与调用计划的电话系统的业务混合部署您 Skype 和 Microsoft 将您的公用电话交换网 (pstn) 提供商 — 和假定您已完成电话号码移植 — 升级到您的用户团队，将自动转换为入站的 PSTN 呼叫到团队。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="7bf3c-126">如果调用计划不可用或您打算使用您现有的 PSTN 连接的提供程序，您需要转换企业语音部署，或使用您现有的混合语音部署本地部署或云连接器 Edition — 到Microsoft 电话系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="7bf3c-127">若要向工作组升级您的用户，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="7bf3c-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
