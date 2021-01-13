---
title: 将 Skype for Business 混合部署升级到 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从 Skype for Business 混合部署将组织升级到 Microsoft Teams。
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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802342"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="a48f9-103">从 Skype for Business 混合部署升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="a48f9-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="a48f9-104">![升级过程阶段，侧重于部署和实施阶段](media/upgrade-banner-deployment.png "升级过程阶段，侧重于部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="a48f9-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="a48f9-105">本文是升级旅程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="a48f9-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="a48f9-106">在继续之前，请确认已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="a48f9-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="a48f9-107">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="a48f9-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="a48f9-108">定义项目范围</span><span class="sxs-lookup"><span data-stu-id="a48f9-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="a48f9-109">了解 Skype for Business 和 Teams 的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="a48f9-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="a48f9-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="a48f9-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="a48f9-111">准备好环境</span><span class="sxs-lookup"><span data-stu-id="a48f9-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="a48f9-112">为组织做好准备</span><span class="sxs-lookup"><span data-stu-id="a48f9-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="a48f9-113">开展试点</span><span class="sxs-lookup"><span data-stu-id="a48f9-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="a48f9-114">如果你已在本地部署 Skype for Business 或 Microsoft Lync，并且已与 Microsoft 365 或 Office 365 组织在混合部署中配置了 Skype for Business 或 Microsoft Lync，并且你的组织希望选择性地升级到 Teams，或者使用多种共存模式或一切功能进行升级，请遵循本文中的指导。</span><span class="sxs-lookup"><span data-stu-id="a48f9-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="a48f9-115">对于任一升级过程，你都需要将用户移动到 Skype for Business Online (如果他们还没有在线家庭) 然后为其分配适当的共存和升级模式。</span><span class="sxs-lookup"><span data-stu-id="a48f9-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="a48f9-116">步骤 1：将用户移动到 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a48f9-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="a48f9-117">此步骤适用于当前位于本地的用户。</span><span class="sxs-lookup"><span data-stu-id="a48f9-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="a48f9-118">有关将这些用户移动到 Skype for Business Online 的信息，请参阅"将用户从本地移动到[Skype for Business Online"。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="a48f9-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="a48f9-119">步骤 2：分配共存和升级模式</span><span class="sxs-lookup"><span data-stu-id="a48f9-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="a48f9-120">将用户移动到 Skype for Business Online 后，你可以根据组织选择的升级旅程为其分配适当的共存模式。</span><span class="sxs-lookup"><span data-stu-id="a48f9-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="a48f9-121">有关详细信息，请参阅["设置共存和](https://aka.ms/SkypeToTeams-SetCoexistence)升级设置"和["TeamsUpgradePolicy：管理迁移和共存"。](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="a48f9-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a48f9-122">使用 Skype for Business Server 2019 和 Skype for Business Server 2015 的未来累积更新，你将能够执行步骤 1 (将用户移动到 Skype for Business Online) ，并且步骤 2 (通过单个步骤将用户升级到 Teams) 。</span><span class="sxs-lookup"><span data-stu-id="a48f9-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="a48f9-123">发布 Skype for Business Server 2019 后，将提供更多信息。</span><span class="sxs-lookup"><span data-stu-id="a48f9-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="a48f9-124">手机系统和 Teams 升级</span><span class="sxs-lookup"><span data-stu-id="a48f9-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="a48f9-125">如果你正在使用通话计划将 Skype for Business 混合部署转换到电话系统，并且 Microsoft 将成为你的公共电话交换网 (PSTN) 提供商，并且假设你已完成电话号码转网，将你的用户升级到 Teams 将自动将入站 PSTN 呼叫转换到 Teams。</span><span class="sxs-lookup"><span data-stu-id="a48f9-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="a48f9-126">如果呼叫计划不可用，或者你计划使用现有的 PSTN 连接提供商，则需要将企业语音部署（或使用现有本地部署或 Cloud Connector Edition 的混合语音部署）转换为 Microsoft Phone 系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="a48f9-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="a48f9-127">若要将用户升级到 Teams，请参阅电话系统直接 [路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="a48f9-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
