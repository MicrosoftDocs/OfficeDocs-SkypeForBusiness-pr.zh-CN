---
title: Microsoft 团队实施升级概述
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 根据您当前的 Skype for Business 部署确定 Microsoft 团队的最佳升级途径。
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
ms.openlocfilehash: 0db2e752bb163f806c5dcba7aa56fc36bae7c2ef
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578355"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="a192b-103">实施升级概述</span><span class="sxs-lookup"><span data-stu-id="a192b-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="a192b-104">![升级旅程的阶段，重点介绍部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="a192b-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="a192b-105">本文是升级过程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="a192b-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="a192b-106">先决条件计划活动</span><span class="sxs-lookup"><span data-stu-id="a192b-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a192b-107">在继续升级实施之前，请确认您已阅读计划内容（从 [规划升级](upgrade-plan-journey.md) 开始），确保您已完成所有先决条件计划活动。</span><span class="sxs-lookup"><span data-stu-id="a192b-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="a192b-108">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="a192b-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="a192b-109">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="a192b-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="a192b-110">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="a192b-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="a192b-111">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="a192b-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="a192b-112">计划用户试点</span><span class="sxs-lookup"><span data-stu-id="a192b-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="a192b-113">准备好你的环境</span><span class="sxs-lookup"><span data-stu-id="a192b-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="a192b-114">准备好您的组织</span><span class="sxs-lookup"><span data-stu-id="a192b-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="a192b-115">选择升级起点</span><span class="sxs-lookup"><span data-stu-id="a192b-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="a192b-116">为团队执行升级所采取的步骤取决于 Skype for business 的当前部署：</span><span class="sxs-lookup"><span data-stu-id="a192b-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="a192b-117">根据当前环境，选择您的起始点：</span><span class="sxs-lookup"><span data-stu-id="a192b-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="a192b-118">**如果要从 skype For Business online 升级到团队**，请按照 [从 Skype For business Online 升级到团队](https://aka.ms/SkypeToTeams-UpgradeOnline)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a192b-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="a192b-119">**如果要从 Skype For business 本地环境升级**，则需要执行一些额外的步骤，以便在你的本地和联机环境之间设置连接，然后再将你的用户移动到团队。</span><span class="sxs-lookup"><span data-stu-id="a192b-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="a192b-120">有关详细信息，请参阅 [将本地 Skype for Business 升级到团队](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)。</span><span class="sxs-lookup"><span data-stu-id="a192b-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
