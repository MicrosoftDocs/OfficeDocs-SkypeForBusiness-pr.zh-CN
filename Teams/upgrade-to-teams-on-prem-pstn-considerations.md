---
title: 从服务器升级到 pstN Teams PSTN Skype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams 的语音注意事项
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9a454b3c23074a1ab7a750e8d282e9a562257eb
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282349"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a><span data-ttu-id="72767-103">从本地Teams升级到 Skype for Business PSTN 注意事项</span><span class="sxs-lookup"><span data-stu-id="72767-103">PSTN considerations for upgrading to Teams from Skype for Business on-premises</span></span>

<span data-ttu-id="72767-104">本文介绍 PSTN (电话交换) 时需要考虑的Teams。</span><span class="sxs-lookup"><span data-stu-id="72767-104">This article describes Public Switched Telephone Network (PSTN) considerations when upgrading to Teams.</span></span>

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="72767-105">此外，以下文章介绍重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="72767-105">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="72767-106">Teams 和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="72767-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="72767-107">共存模式 - 参考</span><span class="sxs-lookup"><span data-stu-id="72767-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="72767-108">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="72767-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - <span data-ttu-id="72767-109">仅在电话系统 TeamsOnly Teams，才支持将 Teams 与应用一起使用。</span><span class="sxs-lookup"><span data-stu-id="72767-109">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span>  <span data-ttu-id="72767-110">如果用户在群岛模式下，电话系统仅支持Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="72767-110">If the user is in Islands mode, Phone System is only supported with Skype for Business.</span></span> 
 > - <span data-ttu-id="72767-111">系统不会迁移来自 Skype for Business 的任何呼叫转发、团队呼叫组和委派设置，需要重新重新创建Teams。</span><span class="sxs-lookup"><span data-stu-id="72767-111">Any call forwarding, team-call group, and delegation settings from Skype for Business are not migrated and will need to be re-recreated for Teams.</span></span>
 > - <span data-ttu-id="72767-112">有关云语音Microsoft Teams的一般概述，并帮助确定哪个 Microsoft 语音解决方案适合你的组织，请参阅规划你的Teams[解决方案](cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="72767-112">For a general overview of Microsoft Teams cloud voice features, and help deciding which Microsoft voice solution is right for your organization, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>


## <a name="pstn-calling-scenarios"></a><span data-ttu-id="72767-113">PSTN 呼叫方案</span><span class="sxs-lookup"><span data-stu-id="72767-113">PSTN calling scenarios</span></span>

<span data-ttu-id="72767-114">迁移到 TeamsOnly 模式时，有四种可能的调用方案：</span><span class="sxs-lookup"><span data-stu-id="72767-114">There are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="72767-115">[具有 Microsoft 呼叫Skype for Business的 Skype for Business Online 中的用户](#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="72767-115">[A user in Skype for Business Online, with a Microsoft Calling Plan](#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="72767-116">升级后，此用户将继续拥有 Microsoft 呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="72767-116">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span>

- <span data-ttu-id="72767-117">[使用 Skype for Business Online](#from-skype-for-business-online-with-on-premises-voice)的用户，通过本地或云连接器Skype for Business本地语音功能。</span><span class="sxs-lookup"><span data-stu-id="72767-117">[A user in Skype for Business Online, with on-premises voice functionality](#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="72767-118">用户升级到 Teams需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="72767-118">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="72767-119">[在本地使用 Skype for Business 的用户企业语音，](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)该用户将移动到联机并保留本地 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="72767-119">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity.</span></span>  <span data-ttu-id="72767-120">将该用户迁移到 Teams需要将用户的本地 Skype for Business 帐户移动到云，并协调该移动，同时将用户迁移到直接路由。</span><span class="sxs-lookup"><span data-stu-id="72767-120">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="72767-121">[在本地使用 Skype for Business 的用户企业语音，](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)该用户将移动到联机状态，使用 Microsoft 呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="72767-121">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan.</span></span>  <span data-ttu-id="72767-122">将该用户迁移到 Teams 需要将用户的本地 Skype for Business 帐户移动到云，并将该帐户与 A) 用户电话号码的端口转移到 Microsoft 呼叫计划或 B) 从可用区域分配新的订阅者号码协调。</span><span class="sxs-lookup"><span data-stu-id="72767-122">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="72767-123">本文仅提供高级概述。</span><span class="sxs-lookup"><span data-stu-id="72767-123">This article provides a high-level overview only.</span></span> <span data-ttu-id="72767-124">有关详细信息，请参阅直接电话系统[和](direct-routing-landing-page.md)[呼叫计划](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="72767-124">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md) and [Calling Plans](calling-plan-landing-page.md).</span></span> 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a><span data-ttu-id="72767-125">从 Skype for Business Online 与 Microsoft 呼叫计划</span><span class="sxs-lookup"><span data-stu-id="72767-125">From Skype for Business Online with Microsoft Calling Plans</span></span> 

<span data-ttu-id="72767-126">这是涉及语音的最简单升级方案。</span><span class="sxs-lookup"><span data-stu-id="72767-126">This is the simplest upgrade scenario involving voice.</span></span> 

1. <span data-ttu-id="72767-127">确保为用户分配了一个Teams许可证。</span><span class="sxs-lookup"><span data-stu-id="72767-127">Make sure users have been assigned a Teams license.</span></span> <span data-ttu-id="72767-128">默认情况下，分配 Microsoft 365 或 Office 365 许可证时，Teams启用，因此，除非以前禁用了 Teams 许可证，否则不需要任何操作。</span><span class="sxs-lookup"><span data-stu-id="72767-128">By default, when you assign a Microsoft 365 or Office 365 license, Teams is enabled, so unless you previously disabled the Teams license, no action should be necessary.</span></span>

2.  <span data-ttu-id="72767-129">如果用户已经有一个包含电话号码的 Microsoft 呼叫计划，则只需在 TeamsUpgradePolicy 中分配用户 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="72767-129">If users already have a Microsoft Calling Plan with a phone number, the only required change is to assign the user TeamsOnly mode in TeamsUpgradePolicy.</span></span>  <span data-ttu-id="72767-130">在分配 TeamsOnly 模式之前，传入的 PSTN 呼叫将进入用户Skype for Business客户端。</span><span class="sxs-lookup"><span data-stu-id="72767-130">Prior to assigning TeamsOnly mode, incoming PSTN calls will land in the user’s Skype for Business client.</span></span> <span data-ttu-id="72767-131">升级到 TeamsOnly 模式后，传入的 PSTN 呼叫将进入用户Teams客户端。</span><span class="sxs-lookup"><span data-stu-id="72767-131">After the upgrade to TeamsOnly mode, incoming PSTN calls will land in the user’s Teams client.</span></span>  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a><span data-ttu-id="72767-132">使用Skype for Business语音从 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="72767-132">From Skype for Business Online with on-premises voice</span></span>

<span data-ttu-id="72767-133">在此方案中，用户已使用 Skype for Business Online，但其 PSTN 连接是本地的，使用混合Skype for Business Server云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="72767-133">In this scenario, the user is already in Skype for Business Online, but their PSTN connectivity is on-premises, either using Skype for Business Server in hybrid mode or Cloud Connector Edition.</span></span> <span data-ttu-id="72767-134">使用 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着支持直接路由，其中 PSTN 中继通过本地会话边界控制器 (SBC) 直接连接到云中的直接路由服务。</span><span class="sxs-lookup"><span data-stu-id="72767-134">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing, in which PSTN trunks connect directly to the Direct Routing service in the cloud, via your on-premises Session Border Controller (SBC).</span></span>

<span data-ttu-id="72767-135">下面列出了基本步骤。</span><span class="sxs-lookup"><span data-stu-id="72767-135">The basic steps are listed below.</span></span>  <span data-ttu-id="72767-136">步骤 1-4 在建议的顺序中列出，但可以按任何顺序完成。</span><span class="sxs-lookup"><span data-stu-id="72767-136">Steps 1-4 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="72767-137">关键是，所有这些操作都应在步骤 5 之前完成。</span><span class="sxs-lookup"><span data-stu-id="72767-137">The key is that all of these should be completed before Step 5.</span></span>

1. <span data-ttu-id="72767-138">如果要将租户范围策略设置为其中一种Skype for Business模式，请确保通过显式分配任何现有群岛用户来委派他们，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="72767-138">If you are setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather any existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="72767-139">为租户配置直接路由。</span><span class="sxs-lookup"><span data-stu-id="72767-139">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="72767-140">请参阅 [Direct Routing 的按租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="72767-140">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

3. <span data-ttu-id="72767-141">如果需要，请为这些Teams配置各种策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。</span><span class="sxs-lookup"><span data-stu-id="72767-141">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="72767-142">这随时都可以完成，但是，如果你想要确保在用户升级时具有正确的配置，最好在用户升级到 TeamsOnly 模式之前这样做。</span><span class="sxs-lookup"><span data-stu-id="72767-142">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly mode.</span></span>

4. <span data-ttu-id="72767-143">为语音迁移准备选择用户：</span><span class="sxs-lookup"><span data-stu-id="72767-143">Prepare select users for voice migration:</span></span> 
   - <span data-ttu-id="72767-144">如有必要，请分配Teams许可证。</span><span class="sxs-lookup"><span data-stu-id="72767-144">If necessary, assign the Teams license.</span></span>  <span data-ttu-id="72767-145">假设用户已在 Skype for Business Online 本地语音中正常运行，则用户已有Skype for Business计划 2 和Microsoft 电话系统。</span><span class="sxs-lookup"><span data-stu-id="72767-145">Assuming the user is already functional in Skype for Business Online on-premises voice, the user already has Skype for Business Plan 2 as well as Microsoft Phone System.</span></span> <span data-ttu-id="72767-146">让这两个计划保持启用状态，Skype for Business Online 计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="72767-146">Leave both those plans enabled, including the Skype for Business Online Plan 2 license.</span></span>  
   - <span data-ttu-id="72767-147">分配所需的 OnlineVoiceRoutingPolicy。</span><span class="sxs-lookup"><span data-stu-id="72767-147">Assign the desired OnlineVoiceRoutingPolicy.</span></span> 

5. <span data-ttu-id="72767-148">升级用户：这些步骤应进行协调。</span><span class="sxs-lookup"><span data-stu-id="72767-148">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="72767-149">在 Microsoft 365 或 Office 365 中，使用 Grant-CsTeamsUpgradePolicy (将用户升级到 TeamsOnly) 。</span><span class="sxs-lookup"><span data-stu-id="72767-149">In Microsoft 365 or Office 365, upgrade the user to TeamsOnly mode (Grant-CsTeamsUpgradePolicy).</span></span>
   - <span data-ttu-id="72767-150">在 SBC 上，将语音路由配置为通过向直接路由而不是本地中介服务器发送呼叫来启用传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="72767-150">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span>


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a><span data-ttu-id="72767-151">从Skype for Business Server到本地，使用 企业语音，到直接路由</span><span class="sxs-lookup"><span data-stu-id="72767-151">From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing</span></span>

<span data-ttu-id="72767-152">在此方案中，用户仍位于本地Skype for Business，其 PSTN 连接也在本地。</span><span class="sxs-lookup"><span data-stu-id="72767-152">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="72767-153">使用 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着启用直接路由，然后将用户移动到云。</span><span class="sxs-lookup"><span data-stu-id="72767-153">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing and then moving the user to the cloud.</span></span> 
 
<span data-ttu-id="72767-154">下面列出了基本步骤。</span><span class="sxs-lookup"><span data-stu-id="72767-154">The basic steps are listed below.</span></span>  <span data-ttu-id="72767-155">步骤 1-5 在建议的顺序中列出，但可以按任何顺序完成。</span><span class="sxs-lookup"><span data-stu-id="72767-155">Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="72767-156">关键是应在步骤 6 之前完成所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="72767-156">The key is that all of these should be completed before Step 6.</span></span>

1. <span data-ttu-id="72767-157">如果要将租户范围策略设置为其中一种 Skype for Business 模式，请确保按前面所述显式分配现有群岛用户来配置这些用户。</span><span class="sxs-lookup"><span data-stu-id="72767-157">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="72767-158">如果尚未这样做，请为组织配置Skype for Business[混合 。](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="72767-158">If you haven’t already done so, [configure the organization for Skype for Business hybrid](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span>

3. <span data-ttu-id="72767-159">为租户配置直接路由。</span><span class="sxs-lookup"><span data-stu-id="72767-159">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="72767-160">请参阅 [Direct Routing 的按租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="72767-160">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

4. <span data-ttu-id="72767-161">如果需要，请为这些Teams配置各种策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。</span><span class="sxs-lookup"><span data-stu-id="72767-161">If desired, configure various Teams policies for these users (e.g. TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="72767-162">这可随时完成，但如果希望确保用户在升级时具有正确的配置，最好是在用户升级到 TeamsOnly 之前这样做。</span><span class="sxs-lookup"><span data-stu-id="72767-162">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span>

5. <span data-ttu-id="72767-163">如有必要，Microsoft 365或Office 365许可证。</span><span class="sxs-lookup"><span data-stu-id="72767-163">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span>  <span data-ttu-id="72767-164">用户应同时拥有 Teams 和 Skype for Business Online 计划 2 以及 电话系统。</span><span class="sxs-lookup"><span data-stu-id="72767-164">The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="72767-165">如果Skype for Business计划 2，请重新启用它。</span><span class="sxs-lookup"><span data-stu-id="72767-165">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

6. <span data-ttu-id="72767-166">升级用户：这些步骤应进行协调。</span><span class="sxs-lookup"><span data-stu-id="72767-166">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="72767-167">使用本地部署Skype for Business，使用 -MoveToTeams Move-CsUser运行脚本。</span><span class="sxs-lookup"><span data-stu-id="72767-167">Using the on-premises Skype for Business tools, run Move-CsUser with -MoveToTeams switch.</span></span> <span data-ttu-id="72767-168">如果使用不支持 -MoveToTeams 开关的 Skype for Business Server 版本，请首先运行 Move-CsUser，然后在租户远程 PowerShell 或 Teams 管理控制台中分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="72767-168">If you are using a version of Skype for Business Server that does not support the -MoveToTeams switch, first run Move-CsUser and then assign TeamsOnly mode in tenant remote PowerShell or Teams Admin Console.</span></span>

   - <span data-ttu-id="72767-169">在 SBC 上，将语音路由配置为通过向直接路由而不是本地中介服务器发送呼叫来启用传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="72767-169">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span> 

   - <span data-ttu-id="72767-170">在Microsoft 365或Office 365：分配相关的 OnlineVoiceRoutingPolicy 以启用传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="72767-170">In Microsoft 365 or Office 365: Assign the relevant OnlineVoiceRoutingPolicy to enable outgoing calls.</span></span> 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a><span data-ttu-id="72767-171">从Skype for Business Server本地，使用 企业语音，到 Microsoft 呼叫计划</span><span class="sxs-lookup"><span data-stu-id="72767-171">From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan</span></span>

<span data-ttu-id="72767-172">在此方案中，用户仍位于本地Skype for Business，其 PSTN 连接也在本地。</span><span class="sxs-lookup"><span data-stu-id="72767-172">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="72767-173">使用 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着将用户移动到云，或者将其号码从旧运营商移植到 Microsoft 呼叫计划或为用户分配新号码。</span><span class="sxs-lookup"><span data-stu-id="72767-173">Migrating these users to TeamsOnly mode with PSTN functionality means moving the user to the cloud and either porting their number from the old carrier to a Microsoft Calling plan or assigning the user a new number.</span></span> 

<span data-ttu-id="72767-174">下面列出了基本步骤。</span><span class="sxs-lookup"><span data-stu-id="72767-174">The basic steps are listed below.</span></span><span data-ttu-id="72767-175">步骤 1-5 在建议的顺序中列出，但可以按任何顺序完成。</span><span class="sxs-lookup"><span data-stu-id="72767-175">  Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="72767-176">关键是应在步骤 6 之前完成所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="72767-176">The key is that all of these should be completed before Step 6.</span></span> 

1. <span data-ttu-id="72767-177">如果要将租户范围策略设置为其中一种 Skype for Business 模式，请确保按前面所述显式分配现有群岛用户来配置这些用户。</span><span class="sxs-lookup"><span data-stu-id="72767-177">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span> 

2. <span data-ttu-id="72767-178">如果尚未这样做，请为组织配置Skype for Business[混合 。](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="72767-178">If you haven’t already done so, [configure the organization for Skype for Business hybrid](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span> 

3. <span data-ttu-id="72767-179">如果需要，请为这些Teams配置各种策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。</span><span class="sxs-lookup"><span data-stu-id="72767-179">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="72767-180">这可随时完成，但如果希望确保用户在升级时具有正确的配置，最好是在用户升级到 TeamsOnly 之前这样做。</span><span class="sxs-lookup"><span data-stu-id="72767-180">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span> 

4. <span data-ttu-id="72767-181">如有必要，Microsoft 365或Office 365许可证。</span><span class="sxs-lookup"><span data-stu-id="72767-181">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span><span data-ttu-id="72767-182">用户应同时拥有 Teams 和 Skype for Business Online 计划 2 以及 电话系统。</span><span class="sxs-lookup"><span data-stu-id="72767-182">  The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="72767-183">如果Skype for Business计划 2，请重新启用它。</span><span class="sxs-lookup"><span data-stu-id="72767-183">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

5. <span data-ttu-id="72767-184">获取用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="72767-184">Get phone numbers for your users.</span></span> <span data-ttu-id="72767-185"> (有关详细信息，请参阅 [管理](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)组织的电话号码 .) </span><span class="sxs-lookup"><span data-stu-id="72767-185">(For details see [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).)</span></span>

   - <span data-ttu-id="72767-186">如果要重新使用号码，请向运营商提交移植请求。</span><span class="sxs-lookup"><span data-stu-id="72767-186">If you will be re-using the numbers, submit a porting request to your carrier.</span></span>  
   - <span data-ttu-id="72767-187">或者，可以直接从 Microsoft 获取新号码。</span><span class="sxs-lookup"><span data-stu-id="72767-187">Alternatively, you can acquire new numbers directly from Microsoft.</span></span> 

6. <span data-ttu-id="72767-188">升级用户，并根据需要分配 LineUri。</span><span class="sxs-lookup"><span data-stu-id="72767-188">Upgrade the user and if needed assign LineUri.</span></span> <span data-ttu-id="72767-189">使用本地 Skype for Business 工具，使用 Move-CsUser -MoveToTeams 开关运行脚本。</span><span class="sxs-lookup"><span data-stu-id="72767-189">Using the on-premises Skype for Business tools, run Move-CsUser with the -MoveToTeams switch.</span></span>  

    - <span data-ttu-id="72767-190">如果要将号码移植到 Microsoft，应协调发生端口时此操作的计时。</span><span class="sxs-lookup"><span data-stu-id="72767-190">If you are porting numbers to Microsoft, you should coordinate the timing of this operation to occur when the port occurs.</span></span> 

    - <span data-ttu-id="72767-191">如果使用来自 Microsoft 的新号码，则需要更改用户的 LineUri。</span><span class="sxs-lookup"><span data-stu-id="72767-191">If you are using new numbers from Microsoft, you’ll need to change the LineUri for the user.</span></span> <span data-ttu-id="72767-192">必须使用 Set-CsOnlineVoiceUser 将用户联机移动后完成此操作。</span><span class="sxs-lookup"><span data-stu-id="72767-192">This must be done after the user is moved online using Set-CsOnlineVoiceUser.</span></span>  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a><span data-ttu-id="72767-193">直接路由的按租户配置摘要</span><span class="sxs-lookup"><span data-stu-id="72767-193">Summary of per-tenant configuration of Direct Routing</span></span> 

1. <span data-ttu-id="72767-194">查看此列表，确保直接路由 (SBC) 的会话边界 [控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="72767-194">Ensure that your Session Border Controller (SBC) is supported with Direct Routing by reviewing [this list](direct-routing-border-controllers.md).</span></span> <span data-ttu-id="72767-195">此外，必须确保固件版本正确。</span><span class="sxs-lookup"><span data-stu-id="72767-195">You must also ensure that you have correct version of firmware.</span></span>  

2. <span data-ttu-id="72767-196">将本地 SBC 与 Teams直接路由服务配对。</span><span class="sxs-lookup"><span data-stu-id="72767-196">Pair your on-premises SBC with the Teams Direct Routing service.</span></span> <span data-ttu-id="72767-197">有关详细信息，请参阅将 SBC 与 电话系统[的直接路由服务](direct-routing-configure.md)配对。</span><span class="sxs-lookup"><span data-stu-id="72767-197">For details, see [Pair the SBC to the Direct Routing service of Phone System](direct-routing-configure.md).</span></span> 

3. <span data-ttu-id="72767-198">此配置实质上是本地配置的镜像。</span><span class="sxs-lookup"><span data-stu-id="72767-198">This configuration is essentially a mirror of the on-premises configuration.</span></span> <span data-ttu-id="72767-199">联机配置包括：</span><span class="sxs-lookup"><span data-stu-id="72767-199">The online configuration consists of:</span></span> 
   - <span data-ttu-id="72767-200">如果从 Skype for Business Online 迁移用户，则 OnlineVoiceRoutingPolicy (基于本地 VoiceRoutingPolicy;如果使用 企业语音) 从本地迁移用户，则基于 VoicePolicy。</span><span class="sxs-lookup"><span data-stu-id="72767-200">OnlineVoiceRoutingPolicy (based on the on-premises VoiceRoutingPolicy if migrating users from Skype for Business   Online, and based on VoicePolicy if migrating users from on-premises with Enterprise Voice).</span></span>
   - <span data-ttu-id="72767-201">OnlinePSTNUsage 对象 (本地 PSTN 使用情况) 。</span><span class="sxs-lookup"><span data-stu-id="72767-201">OnlinePSTNUsage objects (based on on-premises PSTN usage).</span></span> 
   - <span data-ttu-id="72767-202">OnlineVoiceRoute 对象 (本地 VoiceRoute) 。</span><span class="sxs-lookup"><span data-stu-id="72767-202">OnlineVoiceRoute objects (based on-premises VoiceRoute).</span></span> 

<span data-ttu-id="72767-203">有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="72767-203">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a><span data-ttu-id="72767-204">在迁移期间管理 EnterpriseVoiceEnabled 属性</span><span class="sxs-lookup"><span data-stu-id="72767-204">Manage EnterpriseVoiceEnabled property during migration</span></span> 

<span data-ttu-id="72767-205">无论使用直接路由还是 Microsoft 呼叫计划，用户都必须在 Azure AD 中拥有 EnterpriseVoiceEnabled=true，用户必须具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="72767-205">Whether using Direct Routing or a Microsoft Calling plan, a user must have EnterpriseVoiceEnabled=true in Azure AD for the user to have PSTN functionality.</span></span>  <span data-ttu-id="72767-206">EnterpriseVoiceEnabled ("已启用 EV") 是一个属性 (，而不是存在于本地目录和云中的策略) 。</span><span class="sxs-lookup"><span data-stu-id="72767-206">EnterpriseVoiceEnabled (“EV-enabled”) is a property (not a policy) that exists in both an on-premises directory and in the cloud.</span></span> <span data-ttu-id="72767-207">云中的值对于云Teams。</span><span class="sxs-lookup"><span data-stu-id="72767-207">The value in the cloud is what matters for Teams.</span></span>  <span data-ttu-id="72767-208">启用 EV 的方式设置为 true 的确切逻辑取决于以下方案：</span><span class="sxs-lookup"><span data-stu-id="72767-208">The exact logic for how EV-enabled gets set to true depends on the following scenario:</span></span> 

- <span data-ttu-id="72767-209">如果用户在本地 Skype for Business Server 中启用了 EV，并且使用 Move-CsUser 将用户移动到云之前，向用户分配了 电话系统 许可证，则联机用户将预配 EV-enabled=true。</span><span class="sxs-lookup"><span data-stu-id="72767-209">If the user is EV-enabled in on-premises Skype for Business Server and a Phone System license is assigned to the user prior to moving the user to the cloud with Move-CsUser, the online user will be provisioned with EV-enabled=true.</span></span> 

- <span data-ttu-id="72767-210">如果为现有 TeamsOnly 或 Skype for Business Online 用户分配了 电话系统 许可证，则启用 EV 的 默认设置为 true。</span><span class="sxs-lookup"><span data-stu-id="72767-210">If an existing TeamsOnly or Skype for Business Online user is assigned a Phone System license, EV-enabled is not set to true by default.</span></span>  <span data-ttu-id="72767-211">如果在分配本地用户许可证之前将本地用户移到云中，电话系统这种情况。</span><span class="sxs-lookup"><span data-stu-id="72767-211">This also is the case if an on-premises user is moved to the cloud prior to assigning the Phone System license.</span></span> <span data-ttu-id="72767-212">在任一情况下，管理员必须指定以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="72767-212">In either case, the admin must specify the following cmdlet:</span></span> 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a><span data-ttu-id="72767-213">相关链接</span><span class="sxs-lookup"><span data-stu-id="72767-213">Related links</span></span>

[<span data-ttu-id="72767-214">规划Teams语音解决方案</span><span class="sxs-lookup"><span data-stu-id="72767-214">Plan your Teams voice solution</span></span>](cloud-voice-landing-page.md)

[<span data-ttu-id="72767-215">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="72767-215">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="72767-216">配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="72767-216">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="72767-217">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="72767-217">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="72767-218">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="72767-218">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="72767-219">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="72767-219">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="72767-220">使用会议迁移服务 (MMS)</span><span class="sxs-lookup"><span data-stu-id="72767-220">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)