---
title: 团队语音 Contoso 个案研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785956"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="c5549-103">Contoso 案例研究：团队升级计划</span><span class="sxs-lookup"><span data-stu-id="c5549-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="c5549-104">在决定从 Skype for Business 迁移到团队时，Contoso 希望为最终用户提供轻松的过渡体验。</span><span class="sxs-lookup"><span data-stu-id="c5549-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="c5549-105">他们不会同时将每个人切换到团队，而是决定设置混合连接，并使用重叠的功能方法将用户移动到团队。</span><span class="sxs-lookup"><span data-stu-id="c5549-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="c5549-106">这允许团队和 Skype for business 中的用户共享联机状态和通信。</span><span class="sxs-lookup"><span data-stu-id="c5549-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="c5549-107">当用户输入手机系统的试点时，它们将被移动到 "仅限团队" 模式。</span><span class="sxs-lookup"><span data-stu-id="c5549-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="c5549-108">若要了解有关升级、方法和模式的基本概念，Contoso 阅读以下文章：</span><span class="sxs-lookup"><span data-stu-id="c5549-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="c5549-109">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="c5549-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="c5549-110">从 Skype for Business 升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="c5549-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="c5549-111">迁移和互操作性指南</span><span class="sxs-lookup"><span data-stu-id="c5549-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="c5549-112">Contoso 还参与了 Ignite 2019 会话[来设计您从 Skype For business 到团队的路径](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="c5549-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="c5549-113">Contoso 已了解：</span><span class="sxs-lookup"><span data-stu-id="c5549-113">Contoso learned about:</span></span>

- <span data-ttu-id="c5549-114">互操作性、联合身份验证和升级行为等基本概念</span><span class="sxs-lookup"><span data-stu-id="c5549-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="c5549-115">基于 TeamsUpgradePolicy 的共存模式和管理</span><span class="sxs-lookup"><span data-stu-id="c5549-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="c5549-116">最终用户体验：</span><span class="sxs-lookup"><span data-stu-id="c5549-116">End user experience for:</span></span> 

  - <span data-ttu-id="c5549-117">聊天和通话</span><span class="sxs-lookup"><span data-stu-id="c5549-117">Chat and Calling</span></span> 

  - <span data-ttu-id="c5549-118">会议计划</span><span class="sxs-lookup"><span data-stu-id="c5549-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="c5549-119">团队客户端中的协作功能的可用性</span><span class="sxs-lookup"><span data-stu-id="c5549-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="c5549-120">若要计划和配置混合连接，第一步是将其本地环境移动到云、Contoso 读取[计划混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)和[配置混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)，以了解如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c5549-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="c5549-121">将其本地环境服务配置为与 Office 365 联盟。</span><span class="sxs-lookup"><span data-stu-id="c5549-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="c5549-122">将其本地环境配置为信任 Office 365 并启用 Office 365 的共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="c5549-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="c5549-123">在其 Office 365 租户中启用共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="c5549-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="c5549-124">在技术试验期间使用孤岛模式。</span><span class="sxs-lookup"><span data-stu-id="c5549-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="c5549-125">用户启用电话系统后，将用户切换到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="c5549-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="c5549-126">TeamsOnly 模式是通话计划和直接路由所必需的。</span><span class="sxs-lookup"><span data-stu-id="c5549-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
