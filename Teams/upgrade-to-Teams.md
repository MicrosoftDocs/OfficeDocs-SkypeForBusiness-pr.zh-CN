---
title: 有关实现升级到 Microsoft Teams 的概述
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 根据当前部署确定Microsoft Teams升级路径Skype for Business路径。
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
ms.openlocfilehash: 1774b8bebc1330e69a611e64d4f0a8e01f05febb
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282369"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="33716-103">实现升级的概述</span><span class="sxs-lookup"><span data-stu-id="33716-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="33716-104">![升级旅程的阶段，着重强调部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="33716-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="33716-105">本文是升级旅程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="33716-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="33716-106">先决条件规划活动</span><span class="sxs-lookup"><span data-stu-id="33716-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33716-107">在继续升级实施之前，请确认已阅读从计划升级开始的计划内容，以确保[](upgrade-plan-journey.md)已完成所有先决条件规划活动。</span><span class="sxs-lookup"><span data-stu-id="33716-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="33716-108">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="33716-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="33716-109">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="33716-109">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="33716-110">了解两者共存Skype for Business互操作性Teams</span><span class="sxs-lookup"><span data-stu-id="33716-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="33716-111">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="33716-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="33716-112">计划的用户试点</span><span class="sxs-lookup"><span data-stu-id="33716-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="33716-113">准备环境</span><span class="sxs-lookup"><span data-stu-id="33716-113">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="33716-114">准备组织</span><span class="sxs-lookup"><span data-stu-id="33716-114">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="33716-115">选择升级起点</span><span class="sxs-lookup"><span data-stu-id="33716-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="33716-116">执行升级以升级到 Teams的步骤取决于当前部署Skype for Business：</span><span class="sxs-lookup"><span data-stu-id="33716-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="33716-117">根据当前环境，选择起点：</span><span class="sxs-lookup"><span data-stu-id="33716-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="33716-118">**如果要从 Skype for Business Online** 升级到 Teams，请按照从 [Skype for Business Online 升级到 Teams。](./upgrade-to-teams-execute-skypeforbusinessonline.md)</span><span class="sxs-lookup"><span data-stu-id="33716-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span></span>

-  <span data-ttu-id="33716-119">如果要 **从** Skype for Business 本地环境升级，则需要执行一些额外步骤，在本地和联机环境之间设置连接，然后再将用户移动到 Teams。</span><span class="sxs-lookup"><span data-stu-id="33716-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="33716-120">有关详细信息，请参阅将[Skype for Business升级到 Teams。](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)</span><span class="sxs-lookup"><span data-stu-id="33716-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]