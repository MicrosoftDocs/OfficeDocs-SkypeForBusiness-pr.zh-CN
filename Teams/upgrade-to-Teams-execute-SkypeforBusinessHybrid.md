---
title: 将 Skype for business 混合部署升级到团队
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从 Skype for Business 混合部署将组织升级到 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2866ae5bdaf38c0269efda13beed98982a057a4d
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666034"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="6fe4d-103">从 Skype for Business 混合部署升级到团队</span><span class="sxs-lookup"><span data-stu-id="6fe4d-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="6fe4d-104">![升级旅程的阶段，重点介绍部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="6fe4d-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="6fe4d-105">本文是升级过程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="6fe4d-106">继续之前，请确认你已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="6fe4d-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="6fe4d-107">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="6fe4d-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="6fe4d-108">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="6fe4d-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="6fe4d-109">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="6fe4d-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="6fe4d-110">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="6fe4d-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="6fe4d-111">准备好你的环境</span><span class="sxs-lookup"><span data-stu-id="6fe4d-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="6fe4d-112">准备好您的组织</span><span class="sxs-lookup"><span data-stu-id="6fe4d-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="6fe4d-113">开展了一个试验</span><span class="sxs-lookup"><span data-stu-id="6fe4d-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="6fe4d-114">如果你已在本地部署 Skype for business 或 Microsoft Lync，并在与你的 Microsoft 365 或 Office 365 组织进行混合部署中配置它，并且你的组织希望通过使用多种共存模式（或多功能）升级到团队，请按照本文中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="6fe4d-115">对于升级旅程，你需要将用户移动到 Skype for business Online （如果他们尚未联机），然后为他们分配适当的共存和升级模式。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="6fe4d-116">步骤1：将用户移动到 Skype for business Online</span><span class="sxs-lookup"><span data-stu-id="6fe4d-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="6fe4d-117">此步骤适用于当前驻留在本地的用户。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="6fe4d-118">有关将这些用户移动到 Skype for business Online 的详细信息，请参阅[将用户从本地移动到 skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="6fe4d-119">步骤2：分配共存和升级模式</span><span class="sxs-lookup"><span data-stu-id="6fe4d-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="6fe4d-120">将用户移动到 Skype for Business Online 后，您可以根据组织选择的升级历程为他们分配适当的共存模式。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="6fe4d-121">有关详细信息，请参阅[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy：管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="6fe4d-122">使用 Skype for business Server 2019 和 Skype for Business Server 2015 的未来累积更新，你将能够执行步骤1（将用户移动到 Skype for business Online）和步骤2（将用户移至 "团队"），方法是执行单个步骤。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="6fe4d-123">在发布 Skype for Business Server 2019 后，将提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="6fe4d-124">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="6fe4d-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="6fe4d-125">如果你正在将 Skype for Business 混合部署转换为带有呼叫计划的电话系统，Microsoft 将成为您的公共交换电话网络（PSTN）提供商，并假设你已完成电话号码移植-将你的用户升级到团队会自动将入站 PSTN 呼叫转到团队。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="6fe4d-126">如果通话计划不可用或你打算使用现有的 PSTN 连接提供程序，则需要将你的企业语音部署（或使用现有本地部署或云连接器版本的混合语音部署）转换为 Microsoft Phone 系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="6fe4d-127">若要将用户升级到团队，请参阅[手机系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="6fe4d-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
