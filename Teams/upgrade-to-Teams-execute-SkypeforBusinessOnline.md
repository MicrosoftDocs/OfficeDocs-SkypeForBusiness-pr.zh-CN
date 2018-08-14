---
title: 从联机业务的 Skype 升级到团队的 Microsoft 团队
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 业务 online 从 Skype 升级到团队的注意事项
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c910a9a206f93b56e5768498fa9e036132b9c368
ms.sourcegitcommit: b45077dd1b5d366fa9a30698aa66ed4b13264eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "21148151"
---
<span data-ttu-id="bd3bc-103">![升级旅程，重点强调部署阶段和实现阶段](media/upgrade-banner-deployment.png "升级旅程，重点强调部署阶段和实现阶段")</span><span class="sxs-lookup"><span data-stu-id="bd3bc-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="bd3bc-104">本文是您升级旅程的不同阶段提供部署和实施的一部分。</span><span class="sxs-lookup"><span data-stu-id="bd3bc-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="bd3bc-105">在继续之前，确认您已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="bd3bc-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="bd3bc-106">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="bd3bc-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="bd3bc-107">定义您的项目范围</span><span class="sxs-lookup"><span data-stu-id="bd3bc-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="bd3bc-108">商业和团队理解共存和 Skype 的互操作性</span><span class="sxs-lookup"><span data-stu-id="bd3bc-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="bd3bc-109">选择您升级旅程</span><span class="sxs-lookup"><span data-stu-id="bd3bc-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="bd3bc-110">准备您的环境</span><span class="sxs-lookup"><span data-stu-id="bd3bc-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="bd3bc-111">准备您的组织</span><span class="sxs-lookup"><span data-stu-id="bd3bc-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="bd3bc-112">执行试验</span><span class="sxs-lookup"><span data-stu-id="bd3bc-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="bd3bc-113">从联机业务的 Skype 升级到团队</span><span class="sxs-lookup"><span data-stu-id="bd3bc-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="bd3bc-114">如果具有完全部署 Skype online 业务，并且希望向工作组从 for Business 的 Skype 升级您的用户，请遵循本文中的指南。</span><span class="sxs-lookup"><span data-stu-id="bd3bc-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="bd3bc-115">您可以有选择地升级用户或一体化、 基于升级历程的已选择您的组织，通过向用户分配适当的共存和升级的模式。</span><span class="sxs-lookup"><span data-stu-id="bd3bc-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="bd3bc-116">分配的共存和升级模式</span><span class="sxs-lookup"><span data-stu-id="bd3bc-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="bd3bc-117">升级到团队可以通过分配 TeamsUpgradePolicy，可以使用的 Microsoft 团队 Skype Business Admin Center 或 Skype 业务远程 Windows Powershell 会话执行的 TeamsOnly 模式来实现。</span><span class="sxs-lookup"><span data-stu-id="bd3bc-117">Upgrading to Teams can be accomplished by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using Microsoft Teams & Skype for Business Admin Center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="bd3bc-118">有关详细信息，请参阅[设置您共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy： 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="bd3bc-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="bd3bc-119">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="bd3bc-119">Phone System and Teams upgrade</span></span>

<span data-ttu-id="bd3bc-120">如果您的业务 Online 部署的 Skype 包括电话系统与调用计划和 Microsoft 是您公用电话交换网 (pstn) 提供商，将用户升级到团队将自动转换到团队呼叫的入站的 PSTN。</span><span class="sxs-lookup"><span data-stu-id="bd3bc-120">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="bd3bc-121">如果您的业务 Online 部署的 Skype 包括与云连接器 Edition 的电话系统，请参阅[电话系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="bd3bc-121">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>