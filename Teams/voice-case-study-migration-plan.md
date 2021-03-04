---
title: Teams 语音 Contoso 案例研究
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
description: 适用于多语言公司的 Teams 语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93f6d0877537a740dc867b44c3c4deb9bebb8441
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421287"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="92957-103">Contoso 案例研究：团队升级计划</span><span class="sxs-lookup"><span data-stu-id="92957-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="92957-104">在决定从 Skype for Business 迁移到 Teams 时，Contoso 希望为最终用户提供简单的过渡体验。</span><span class="sxs-lookup"><span data-stu-id="92957-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="92957-105">他们决定不将所有人同时切换到 Teams，而是决定设置混合连接，并使用重叠功能方法将用户移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="92957-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="92957-106">这允许 Teams 和本地 Skype for Business 中的用户共享状态和进行通信。</span><span class="sxs-lookup"><span data-stu-id="92957-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="92957-107">当用户进入手机系统的试点时，他们已移至 Teams Only 模式。</span><span class="sxs-lookup"><span data-stu-id="92957-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="92957-108">若要了解有关升级、方法和模式的基本概念，Contoso 请阅读以下文章：</span><span class="sxs-lookup"><span data-stu-id="92957-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="92957-109">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="92957-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="92957-110">适用于 IT 管理员的升级策略</span><span class="sxs-lookup"><span data-stu-id="92957-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- [<span data-ttu-id="92957-111">迁移和互操作性指南</span><span class="sxs-lookup"><span data-stu-id="92957-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="92957-112">Contoso 还参加 Ignite 2019 会话，设计从 [Skype for Business](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)到 Teams 的路径。</span><span class="sxs-lookup"><span data-stu-id="92957-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="92957-113">Contoso 已了解：</span><span class="sxs-lookup"><span data-stu-id="92957-113">Contoso learned about:</span></span>

- <span data-ttu-id="92957-114">基本概念，例如互操作性、联合和升级行为</span><span class="sxs-lookup"><span data-stu-id="92957-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="92957-115">基于 TeamsUpgradePolicy 的共存模式和管理</span><span class="sxs-lookup"><span data-stu-id="92957-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="92957-116">最终用户体验：</span><span class="sxs-lookup"><span data-stu-id="92957-116">End user experience for:</span></span> 

  - <span data-ttu-id="92957-117">聊天和通话</span><span class="sxs-lookup"><span data-stu-id="92957-117">Chat and Calling</span></span> 

  - <span data-ttu-id="92957-118">会议安排</span><span class="sxs-lookup"><span data-stu-id="92957-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="92957-119">Teams 客户端中协作功能的可用性</span><span class="sxs-lookup"><span data-stu-id="92957-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="92957-120">若要计划和配置混合连接，第一步是将其本地环境迁移到云，Contoso 阅读"规划混合连接"[](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)和"[配置混合](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)连接"，了解如何：</span><span class="sxs-lookup"><span data-stu-id="92957-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="92957-121">将其本地环境服务配置为与 Office 365 联合。</span><span class="sxs-lookup"><span data-stu-id="92957-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="92957-122">将其本地环境配置为信任 Office 365，并启用 Office 365 的共享 SIP 地址空间</span><span class="sxs-lookup"><span data-stu-id="92957-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="92957-123">在 Office 365 租户中启用共享 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="92957-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="92957-124">在技术试运行期间使用群岛模式。</span><span class="sxs-lookup"><span data-stu-id="92957-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="92957-125">为用户启用电话系统后，将用户切换到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="92957-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="92957-126">通话计划和直接路由需要 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="92957-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
