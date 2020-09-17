---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 075960ef47f5d708a72cabc8e3c492786c2a5112
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940630"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="902ff-103">为 IT 管理员升级到团队时的 PSTN 注意事项 &mdash;</span><span class="sxs-lookup"><span data-stu-id="902ff-103">PSTN considerations when upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="902ff-104">本文介绍升级到团队时 (PSTN) 注意事项的公共交换电话网络。</span><span class="sxs-lookup"><span data-stu-id="902ff-104">This article describes Public Switched Telephone Network (PSTN) considerations when upgrading to Teams.</span></span> <span data-ttu-id="902ff-105">本文是针对 IT 管理员介绍升级概念和实现的第六个。</span><span class="sxs-lookup"><span data-stu-id="902ff-105">This article is the sixth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="902ff-106">概述</span><span class="sxs-lookup"><span data-stu-id="902ff-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="902ff-107">升级方法</span><span class="sxs-lookup"><span data-stu-id="902ff-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="902ff-108">用于管理升级的工具</span><span class="sxs-lookup"><span data-stu-id="902ff-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="902ff-109">具有 Skype for business 内部部署的组织的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="902ff-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="902ff-110">实现升级</span><span class="sxs-lookup"><span data-stu-id="902ff-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- <span data-ttu-id="902ff-111">**公共交换电话网络 (PSTN) 注意事项** (本文) </span><span class="sxs-lookup"><span data-stu-id="902ff-111">**Public Switched Telephone Network (PSTN) considerations** (this article)</span></span>

<span data-ttu-id="902ff-112">此外，以下文章介绍了重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="902ff-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="902ff-113">团队和 Skype for business 的共存</span><span class="sxs-lookup"><span data-stu-id="902ff-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="902ff-114">共存模式-参考</span><span class="sxs-lookup"><span data-stu-id="902ff-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="902ff-115">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="902ff-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > <span data-ttu-id="902ff-116">仅当用户处于 TeamsOnly 模式时，才支持将电话系统与团队配合使用。</span><span class="sxs-lookup"><span data-stu-id="902ff-116">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span>  <span data-ttu-id="902ff-117">如果用户处于 "孤岛" 模式，则只有 Skype for Business 才支持电话系统。</span><span class="sxs-lookup"><span data-stu-id="902ff-117">If the user is in Islands mode, Phone System is only supported with Skype for Business.</span></span> 


## <a name="pstn-calling-scenarios"></a><span data-ttu-id="902ff-118">PSTN 呼叫方案</span><span class="sxs-lookup"><span data-stu-id="902ff-118">PSTN calling scenarios</span></span>

<span data-ttu-id="902ff-119">移动到 TeamsOnly 模式时，有四种可能的通话方案：</span><span class="sxs-lookup"><span data-stu-id="902ff-119">There are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="902ff-120">[Skype For Business Online 中使用 Microsoft 通话计划的用户](#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="902ff-120">[A user in Skype for Business Online, with a Microsoft Calling Plan](#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="902ff-121">升级后，此用户将继续拥有 Microsoft 通话计划。</span><span class="sxs-lookup"><span data-stu-id="902ff-121">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span>

- <span data-ttu-id="902ff-122">[Skype for Business Online 中的用户，](#from-skype-for-business-online-with-on-premises-voice) 通过 skype for business 本地或云连接器版本使用本地语音功能。</span><span class="sxs-lookup"><span data-stu-id="902ff-122">[A user in Skype for Business Online, with on-premises voice functionality](#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="902ff-123">用户对团队的升级需要与用户迁移以直接路由，以确保 TeamsOnly 用户具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="902ff-123">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="902ff-124">[使用企业语音的 Skype For business online 中的用户](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，这些用户将移动到联机状态并保持本地 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="902ff-124">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity.</span></span>  <span data-ttu-id="902ff-125">将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并通过将用户迁移到直接路由来协调该用户。</span><span class="sxs-lookup"><span data-stu-id="902ff-125">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="902ff-126">[使用企业语音的 Skype For business online 中的用户](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，这些用户将移动到联机并使用 Microsoft 通话计划。</span><span class="sxs-lookup"><span data-stu-id="902ff-126">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan.</span></span>  <span data-ttu-id="902ff-127">将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并使用) 该用户电话号码的端口与 Microsoft 通话计划或 B 进行协调，) 从可用区域分配新的订户号码。</span><span class="sxs-lookup"><span data-stu-id="902ff-127">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="902ff-128">本文仅提供高级别概述。</span><span class="sxs-lookup"><span data-stu-id="902ff-128">This article provides a high-level overview only.</span></span> <span data-ttu-id="902ff-129">有关详细信息，请参阅 [电话系统直接路由](direct-routing-landing-page.md) 和 [通话计划](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="902ff-129">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md) and [Calling Plans](calling-plan-landing-page.md).</span></span> 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a><span data-ttu-id="902ff-130">通过 Microsoft 通话计划从 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="902ff-130">From Skype for Business Online with Microsoft Calling Plans</span></span> 

<span data-ttu-id="902ff-131">这是涉及语音的最简单的升级方案。</span><span class="sxs-lookup"><span data-stu-id="902ff-131">This is the simplest upgrade scenario involving voice.</span></span> 

1. <span data-ttu-id="902ff-132">请确保已为用户分配了团队许可证。</span><span class="sxs-lookup"><span data-stu-id="902ff-132">Make sure users have been assigned a Teams license.</span></span> <span data-ttu-id="902ff-133">默认情况下，当你分配 Microsoft 365 或 Office 365 许可证时，团队已启用，因此除非你以前禁用了团队许可证，否则不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="902ff-133">By default, when you assign a Microsoft 365 or Office 365 license, Teams is enabled, so unless you previously disabled the Teams license, no action should be necessary.</span></span>

2.  <span data-ttu-id="902ff-134">如果用户已有一个包含电话号码的 Microsoft 通话计划，则唯一所需的更改是在 TeamsUpgradePolicy 中分配用户 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="902ff-134">If users already have a Microsoft Calling Plan with a phone number, the only required change is to assign the user TeamsOnly mode in TeamsUpgradePolicy.</span></span>  <span data-ttu-id="902ff-135">在分配 TeamsOnly 模式之前，传入的 PSTN 呼叫将位于用户的 Skype for Business 客户端中。</span><span class="sxs-lookup"><span data-stu-id="902ff-135">Prior to assigning TeamsOnly mode, incoming PSTN calls will land in the user’s Skype for Business client.</span></span> <span data-ttu-id="902ff-136">升级到 TeamsOnly 模式后，传入的 PSTN 呼叫将位于用户的团队客户端。</span><span class="sxs-lookup"><span data-stu-id="902ff-136">After the upgrade to TeamsOnly mode, incoming PSTN calls will land in the user’s Teams client.</span></span>  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a><span data-ttu-id="902ff-137">通过 Skype for Business Online 与本地语音</span><span class="sxs-lookup"><span data-stu-id="902ff-137">From Skype for Business Online with on-premises voice</span></span>

<span data-ttu-id="902ff-138">在此方案中，用户已在 Skype for business Online 中，但其 PSTN 连接在本地，使用混合模式或云连接器版本中的 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="902ff-138">In this scenario, the user is already in Skype for Business Online, but their PSTN connectivity is on-premises, either using Skype for Business Server in hybrid mode or Cloud Connector Edition.</span></span> <span data-ttu-id="902ff-139">通过 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着可以直接路由，其中 PSTN 中继通过本地会话边界控制器 (SBC) 直接连接到云中的直接路由服务。</span><span class="sxs-lookup"><span data-stu-id="902ff-139">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing, in which PSTN trunks connect directly to the Direct Routing service in the cloud, via your on-premises Session Border Controller (SBC).</span></span>

<span data-ttu-id="902ff-140">下面列出了基本步骤。</span><span class="sxs-lookup"><span data-stu-id="902ff-140">The basic steps are listed below.</span></span>  <span data-ttu-id="902ff-141">步骤1-4 按建议的顺序列出，但可以按任意顺序完成。</span><span class="sxs-lookup"><span data-stu-id="902ff-141">Steps 1-4 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="902ff-142">关键是，所有这些都应在步骤5之前完成。</span><span class="sxs-lookup"><span data-stu-id="902ff-142">The key is that all of these should be completed before Step 5.</span></span>

1. <span data-ttu-id="902ff-143">如果你要将租户范围内的策略设置为 Skype for Business 模式之一，请确保通过显式分配任何现有的 grandfather 用户，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="902ff-143">If you are setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather any existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="902ff-144">为直接路由配置租户。</span><span class="sxs-lookup"><span data-stu-id="902ff-144">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="902ff-145">请参阅 [直接路由的每租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="902ff-145">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

3. <span data-ttu-id="902ff-146">如果需要，请为这些用户配置各种团队策略 (例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。</span><span class="sxs-lookup"><span data-stu-id="902ff-146">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="902ff-147">可以随时执行此操作，但如果你希望确保用户在升级时具有正确的配置，最好在将用户升级到 TeamsOnly 模式之前执行此操作。</span><span class="sxs-lookup"><span data-stu-id="902ff-147">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly mode.</span></span>

4. <span data-ttu-id="902ff-148">准备选择要进行语音迁移的用户：</span><span class="sxs-lookup"><span data-stu-id="902ff-148">Prepare select users for voice migration:</span></span> 
   - <span data-ttu-id="902ff-149">如有必要，请分配 "团队" 许可证。</span><span class="sxs-lookup"><span data-stu-id="902ff-149">If necessary, assign the Teams license.</span></span>  <span data-ttu-id="902ff-150">假设用户在本地语音的 Skype for business Online 中已起作用，则用户已经拥有 Skype for business 计划2和 Microsoft Phone 系统。</span><span class="sxs-lookup"><span data-stu-id="902ff-150">Assuming the user is already functional in Skype for Business Online on-premises voice, the user already has Skype for Business Plan 2 as well as Microsoft Phone System.</span></span> <span data-ttu-id="902ff-151">让这些计划保持启用状态，包括 Skype for Business Online 计划2许可证。</span><span class="sxs-lookup"><span data-stu-id="902ff-151">Leave both those plans enabled, including the Skype for Business Online Plan 2 license.</span></span>  
   - <span data-ttu-id="902ff-152">分配所需的 OnlineVoiceRoutingPolicy。</span><span class="sxs-lookup"><span data-stu-id="902ff-152">Assign the desired OnlineVoiceRoutingPolicy.</span></span> 

5. <span data-ttu-id="902ff-153">升级用户：这些步骤应协调。</span><span class="sxs-lookup"><span data-stu-id="902ff-153">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="902ff-154">在 Microsoft 365 或 Office 365 中，将用户升级到 TeamsOnly 模式 (授予 CsTeamsUpgradePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="902ff-154">In Microsoft 365 or Office 365, upgrade the user to TeamsOnly mode (Grant-CsTeamsUpgradePolicy).</span></span>
   - <span data-ttu-id="902ff-155">在 SBC 上，将语音路由配置为通过将呼叫发送到直接路由（而不是本地中介服务器）来启用传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="902ff-155">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span>


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a><span data-ttu-id="902ff-156">从具有企业语音的本地 Skype for Business 服务器到直接路由</span><span class="sxs-lookup"><span data-stu-id="902ff-156">From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing</span></span>

<span data-ttu-id="902ff-157">在此方案中，用户仍托管在本地 Skype for business 中，并且其 PSTN 连接也位于本地。</span><span class="sxs-lookup"><span data-stu-id="902ff-157">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="902ff-158">通过 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着为直接路由，然后将用户移动到云。</span><span class="sxs-lookup"><span data-stu-id="902ff-158">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing and then moving the user to the cloud.</span></span> 
 
<span data-ttu-id="902ff-159">下面列出了基本步骤。</span><span class="sxs-lookup"><span data-stu-id="902ff-159">The basic steps are listed below.</span></span>  <span data-ttu-id="902ff-160">步骤1-5 按建议的顺序列出，但可以按任意顺序完成。</span><span class="sxs-lookup"><span data-stu-id="902ff-160">Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="902ff-161">关键是，所有这些都应在步骤6之前完成。</span><span class="sxs-lookup"><span data-stu-id="902ff-161">The key is that all of these should be completed before Step 6.</span></span>

1. <span data-ttu-id="902ff-162">如果你要将租户范围内的策略设置为 Skype for Business 模式之一，请确保将现有的 grandfather 用户显式分配给其孤岛模式（如前面所述）。</span><span class="sxs-lookup"><span data-stu-id="902ff-162">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="902ff-163">如果尚未执行此操作，请 [为 Skype for business 混合配置组织](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="902ff-163">If you haven’t already done so, [configure the organization for Skype for Business hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span>

3. <span data-ttu-id="902ff-164">为直接路由配置租户。</span><span class="sxs-lookup"><span data-stu-id="902ff-164">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="902ff-165">请参阅 [直接路由的每租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="902ff-165">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

4. <span data-ttu-id="902ff-166">如果需要，为这些用户配置各种团队策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。</span><span class="sxs-lookup"><span data-stu-id="902ff-166">If desired, configure various Teams policies for these users (e.g. TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="902ff-167">可以随时执行此操作，但如果你希望确保用户在升级时具有正确的配置，最好在将用户升级到 TeamsOnly 之前执行此操作。</span><span class="sxs-lookup"><span data-stu-id="902ff-167">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span>

5. <span data-ttu-id="902ff-168">如有必要，请分配 Microsoft 365 或 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="902ff-168">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span>  <span data-ttu-id="902ff-169">用户应同时拥有团队和 Skype for business Online 计划2以及电话系统。</span><span class="sxs-lookup"><span data-stu-id="902ff-169">The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="902ff-170">如果 "Skype for Business Online 计划 2" 已禁用，请重新启用它。</span><span class="sxs-lookup"><span data-stu-id="902ff-170">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

6. <span data-ttu-id="902ff-171">升级用户：这些步骤应协调。</span><span class="sxs-lookup"><span data-stu-id="902ff-171">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="902ff-172">使用本地 Skype for Business 工具，通过-MoveToTeams 开关运行 Move-csuser。</span><span class="sxs-lookup"><span data-stu-id="902ff-172">Using the on-premises Skype for Business tools, run Move-CsUser with -MoveToTeams switch.</span></span> <span data-ttu-id="902ff-173">如果你使用的 Skype for Business Server 版本不支持-MoveToTeams 开关，请先运行 Move Move-csuser，然后在租户远程 PowerShell 或团队管理控制台中分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="902ff-173">If you are using a version of Skype for Business Server that does not support the -MoveToTeams switch, first run Move-CsUser and then assign TeamsOnly mode in tenant remote PowerShell or Teams Admin Console.</span></span>

   - <span data-ttu-id="902ff-174">在 SBC 上，将语音路由配置为通过将呼叫发送到直接路由（而不是本地中介服务器）来启用传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="902ff-174">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span> 

   - <span data-ttu-id="902ff-175">在 Microsoft 365 或 Office 365 中：分配相关的 OnlineVoiceRoutingPolicy 以启用传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="902ff-175">In Microsoft 365 or Office 365: Assign the relevant OnlineVoiceRoutingPolicy to enable outgoing calls.</span></span> 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a><span data-ttu-id="902ff-176">从具有企业语音的本地 Skype for Business 服务器到 Microsoft 通话计划</span><span class="sxs-lookup"><span data-stu-id="902ff-176">From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan</span></span>

<span data-ttu-id="902ff-177">在此方案中，用户仍托管在本地 Skype for business 中，并且其 PSTN 连接也位于本地。</span><span class="sxs-lookup"><span data-stu-id="902ff-177">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="902ff-178">通过 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着将用户移动到云，并将其编号从旧运营商移植到 Microsoft 通话计划，或为用户分配一个新号码。</span><span class="sxs-lookup"><span data-stu-id="902ff-178">Migrating these users to TeamsOnly mode with PSTN functionality means moving the user to the cloud and either porting their number from the old carrier to a Microsoft Calling plan or assigning the user a new number.</span></span> 

<span data-ttu-id="902ff-179">下面列出了基本步骤。</span><span class="sxs-lookup"><span data-stu-id="902ff-179">The basic steps are listed below.</span></span><span data-ttu-id="902ff-180">步骤1-5 按建议的顺序列出，但可以按任意顺序完成。</span><span class="sxs-lookup"><span data-stu-id="902ff-180">  Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="902ff-181">关键是，所有这些都应在步骤6之前完成。</span><span class="sxs-lookup"><span data-stu-id="902ff-181">The key is that all of these should be completed before Step 6.</span></span> 

1. <span data-ttu-id="902ff-182">如果你要将租户范围内的策略设置为 Skype for Business 模式之一，请确保将现有的 grandfather 用户显式分配给其孤岛模式（如前面所述）。</span><span class="sxs-lookup"><span data-stu-id="902ff-182">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span> 

2. <span data-ttu-id="902ff-183">如果尚未执行此操作，请 [为 Skype for business 混合配置组织](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="902ff-183">If you haven’t already done so, [configure the organization for Skype for Business hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span> 

3. <span data-ttu-id="902ff-184">如果需要，请为这些用户配置各种团队策略 (例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。</span><span class="sxs-lookup"><span data-stu-id="902ff-184">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="902ff-185">可以随时执行此操作，但如果你希望确保用户在升级时具有正确的配置，最好在将用户升级到 TeamsOnly 之前执行此操作。</span><span class="sxs-lookup"><span data-stu-id="902ff-185">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span> 

4. <span data-ttu-id="902ff-186">如有必要，请分配 Microsoft 365 或 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="902ff-186">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span><span data-ttu-id="902ff-187">用户应同时拥有团队和 Skype for business Online 计划2以及电话系统。</span><span class="sxs-lookup"><span data-stu-id="902ff-187">  The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="902ff-188">如果 "Skype for Business Online 计划 2" 已禁用，请重新启用它。</span><span class="sxs-lookup"><span data-stu-id="902ff-188">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

5. <span data-ttu-id="902ff-189">为您的用户获取电话号码。</span><span class="sxs-lookup"><span data-stu-id="902ff-189">Get phone numbers for your users.</span></span> <span data-ttu-id="902ff-190"> (有关详细信息，请参阅 [管理你的组织的电话号码](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。 ) </span><span class="sxs-lookup"><span data-stu-id="902ff-190">(For details see [Manage phone numbers for your organization](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)</span></span>

   - <span data-ttu-id="902ff-191">如果您将重新使用这些号码，请向您的运营商提交一个移植请求。</span><span class="sxs-lookup"><span data-stu-id="902ff-191">If you will be re-using the numbers, submit a porting request to your carrier.</span></span>  
   - <span data-ttu-id="902ff-192">或者，您可以直接从 Microsoft 获取新号码。</span><span class="sxs-lookup"><span data-stu-id="902ff-192">Alternatively, you can acquire new numbers directly from Microsoft.</span></span> 

6. <span data-ttu-id="902ff-193">升级用户，如果需要，请分配 LineUri。</span><span class="sxs-lookup"><span data-stu-id="902ff-193">Upgrade the user and if needed assign LineUri.</span></span> <span data-ttu-id="902ff-194">使用本地 Skype for Business 工具，通过-MoveToTeams 开关运行 Move-csuser。</span><span class="sxs-lookup"><span data-stu-id="902ff-194">Using the on-premises Skype for Business tools, run Move-CsUser with the -MoveToTeams switch.</span></span>  

    - <span data-ttu-id="902ff-195">如果你要将数字移植到 Microsoft，你应该将此操作的计时协调为在端口出现时发生。</span><span class="sxs-lookup"><span data-stu-id="902ff-195">If you are porting numbers to Microsoft, you should coordinate the timing of this operation to occur when the port occurs.</span></span> 

    - <span data-ttu-id="902ff-196">如果您使用的是 Microsoft 的新号码，您需要为用户更改 LineUri。</span><span class="sxs-lookup"><span data-stu-id="902ff-196">If you are using new numbers from Microsoft, you’ll need to change the LineUri for the user.</span></span> <span data-ttu-id="902ff-197">必须在用户使用 Set-CsOnlineVoiceUser 进行联机移动后执行此操作。</span><span class="sxs-lookup"><span data-stu-id="902ff-197">This must be done after the user is moved online using Set-CsOnlineVoiceUser.</span></span>  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a><span data-ttu-id="902ff-198">直接路由的每租户配置摘要</span><span class="sxs-lookup"><span data-stu-id="902ff-198">Summary of per-tenant configuration of Direct Routing</span></span> 

1. <span data-ttu-id="902ff-199">通过查看 [此列表](direct-routing-border-controllers.md)，确保由直接路由支持 (SBC) 的会话边界控制器。</span><span class="sxs-lookup"><span data-stu-id="902ff-199">Ensure that your Session Border Controller (SBC) is supported with Direct Routing by reviewing [this list](direct-routing-border-controllers.md).</span></span> <span data-ttu-id="902ff-200">您还必须确保拥有正确版本的固件。</span><span class="sxs-lookup"><span data-stu-id="902ff-200">You must also ensure that you have correct version of firmware.</span></span>  

2. <span data-ttu-id="902ff-201">将本地 SBC 与团队直接路由服务配对。</span><span class="sxs-lookup"><span data-stu-id="902ff-201">Pair your on-premises SBC with the Teams Direct Routing service.</span></span> <span data-ttu-id="902ff-202">有关详细信息，请参阅将 [SBC 与电话系统的直接路由服务配对](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="902ff-202">For details, see [Pair the SBC to the Direct Routing service of Phone System](direct-routing-configure.md).</span></span> 

3. <span data-ttu-id="902ff-203">此配置实质上是本地配置的镜像。</span><span class="sxs-lookup"><span data-stu-id="902ff-203">This configuration is essentially a mirror of the on-premises configuration.</span></span> <span data-ttu-id="902ff-204">联机配置包括：</span><span class="sxs-lookup"><span data-stu-id="902ff-204">The online configuration consists of:</span></span> 
   - <span data-ttu-id="902ff-205">OnlineVoiceRoutingPolicy (基于本地 VoiceRoutingPolicy，如果从 Skype for business Online 迁移用户，并且基于 VoicePolicy 将用户从企业语音) 迁移到本地，则基于。</span><span class="sxs-lookup"><span data-stu-id="902ff-205">OnlineVoiceRoutingPolicy (based on the on-premises VoiceRoutingPolicy if migrating users from Skype for Business   Online, and based on VoicePolicy if migrating users from on-premises with Enterprise Voice).</span></span>
   - <span data-ttu-id="902ff-206">OnlinePSTNUsage 对象 (基于本地 PSTN 使用) 。</span><span class="sxs-lookup"><span data-stu-id="902ff-206">OnlinePSTNUsage objects (based on on-premises PSTN usage).</span></span> 
   - <span data-ttu-id="902ff-207">OnlineVoiceRoute (基于本地 VoiceRoute) 的对象。</span><span class="sxs-lookup"><span data-stu-id="902ff-207">OnlineVoiceRoute objects (based on-premises VoiceRoute).</span></span> 

<span data-ttu-id="902ff-208">有关详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="902ff-208">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a><span data-ttu-id="902ff-209">迁移期间管理 EnterpriseVoiceEnabled 属性</span><span class="sxs-lookup"><span data-stu-id="902ff-209">Manage EnterpriseVoiceEnabled property during migration</span></span> 

<span data-ttu-id="902ff-210">无论使用直接路由还是 Microsoft 呼叫计划，用户都必须在 Azure AD 中具有 EnterpriseVoiceEnabled = true，用户才能拥有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="902ff-210">Whether using Direct Routing or a Microsoft Calling plan, a user must have EnterpriseVoiceEnabled=true in Azure AD for the user to have PSTN functionality.</span></span>  <span data-ttu-id="902ff-211">EnterpriseVoiceEnabled ( "EV-enabled" ) 是一个 (在本地目录和云中都不存在的策略) 的属性。</span><span class="sxs-lookup"><span data-stu-id="902ff-211">EnterpriseVoiceEnabled (“EV-enabled”) is a property (not a policy) that exists in both an on-premises directory and in the cloud.</span></span> <span data-ttu-id="902ff-212">云中的值是团队的重要事项。</span><span class="sxs-lookup"><span data-stu-id="902ff-212">The value in the cloud is what matters for Teams.</span></span>  <span data-ttu-id="902ff-213">如何将 EV 启用的确切逻辑设置为 true 取决于以下方案：</span><span class="sxs-lookup"><span data-stu-id="902ff-213">The exact logic for how EV-enabled gets set to true depends on the following scenario:</span></span> 

- <span data-ttu-id="902ff-214">如果用户在本地 Skype for Business 服务器中启用了 EV，并且在将用户移动到云之前使用 Move-Move-csuser 为用户分配了电话系统许可证，则在线用户将预配为 "启用 EV"。</span><span class="sxs-lookup"><span data-stu-id="902ff-214">If the user is EV-enabled in on-premises Skype for Business Server and a Phone System license is assigned to the user prior to moving the user to the cloud with Move-CsUser, the online user will be provisioned with EV-enabled=true.</span></span> 

- <span data-ttu-id="902ff-215">如果现有的 TeamsOnly 或 Skype for business Online 用户分配有电话系统许可证，则默认情况下，启用 EV 不会设置为 true。</span><span class="sxs-lookup"><span data-stu-id="902ff-215">If an existing TeamsOnly or Skype for Business Online user is assigned a Phone System license, EV-enabled is not set to true by default.</span></span>  <span data-ttu-id="902ff-216">如果在分配电话系统许可证之前将本地用户移到云，也会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="902ff-216">This also is the case if an on-premises user is moved to the cloud prior to assigning the Phone System license.</span></span> <span data-ttu-id="902ff-217">在任何一种情况下，管理员都必须指定以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="902ff-217">In either case, the admin must specify the following cmdlet:</span></span> 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a><span data-ttu-id="902ff-218">相关链接</span><span class="sxs-lookup"><span data-stu-id="902ff-218">Related links</span></span>

[<span data-ttu-id="902ff-219">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="902ff-219">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="902ff-220">配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="902ff-220">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="902ff-221">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="902ff-221">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="902ff-222">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="902ff-222">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="902ff-223">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="902ff-223">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="902ff-224">使用会议迁移服务 (MMS) </span><span class="sxs-lookup"><span data-stu-id="902ff-224">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

