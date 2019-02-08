---
title: 启用基于位置的路由直接路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 了解如何启用基于位置的路由，以便直接路由。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8437eba299cb42415d224017ca7d0e888fffa684
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "29771005"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="c7ddc-103">启用基于位置的路由直接路由</span><span class="sxs-lookup"><span data-stu-id="c7ddc-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="c7ddc-104">在按照本文中的步骤之前，请确保您已阅读[Plan Location-Based 路由直接路由](location-based-routing-plan.md)并完成[配置的基于位置的路由的网络设置](location-based-routing-configure-network-settings.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="c7ddc-105">本文介绍如何启用基于位置的路由，以便直接路由。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="c7ddc-106">在部署电话系统直接路由，并设置网络区域、 网站和子网后，您已准备好启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="c7ddc-107">若要完成本文中的步骤，您将需要一些熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="c7ddc-108">若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="c7ddc-109">您必须启用以下基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="c7ddc-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="c7ddc-110">用户</span><span class="sxs-lookup"><span data-stu-id="c7ddc-110">Users</span></span>
- <span data-ttu-id="c7ddc-111">网络站点</span><span class="sxs-lookup"><span data-stu-id="c7ddc-111">Network sites</span></span>
- <span data-ttu-id="c7ddc-112">网关配置</span><span class="sxs-lookup"><span data-stu-id="c7ddc-112">Gateway configurations</span></span>
- <span data-ttu-id="c7ddc-113">调用策略</span><span class="sxs-lookup"><span data-stu-id="c7ddc-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="c7ddc-114">启用的用户的基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="c7ddc-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="c7ddc-115">使用``Set-CsOnlinePstnUsages``cmdlet 设置 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-115">Use the ``Set-CsOnlinePstnUsages`` cmdlet to set PSTN usages.</span></span> <span data-ttu-id="c7ddc-116">使用多个实例，用逗号分隔每个使用率。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="c7ddc-117">例如：</span><span class="sxs-lookup"><span data-stu-id="c7ddc-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="c7ddc-118">使用``New-CsOnlineVoiceRoutingPolicy``cmdlet 以创建语音路由策略，以将用户与相应的 PSTN 用法相关联。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-118">Use the ``New-CsOnlineVoiceRoutingPolicy`` cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="c7ddc-119">当您将 PSTN 用法分配语音路由策略时时，请确保您执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="c7ddc-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="c7ddc-120">使用对网站使用本地 PSTN 网关的语音路由相关联的 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="c7ddc-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="c7ddc-121">使用与使用 PSTN 网关位于其中不需要基于位置的路由限制区域中的语音路由相关联的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="c7ddc-122">本示例中，我们将创建两个新的语音路由策略和 PSTN 用法分配给它们。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="c7ddc-123">下表显示了在此示例中定义的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="c7ddc-124">语音路由策略 1</span><span class="sxs-lookup"><span data-stu-id="c7ddc-124">Voice routing policy 1</span></span>|<span data-ttu-id="c7ddc-125">语音路由策略 2</span><span class="sxs-lookup"><span data-stu-id="c7ddc-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="c7ddc-126">语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="c7ddc-126">Voice policy ID</span></span>   |<span data-ttu-id="c7ddc-127">德里语音路由策略</span><span class="sxs-lookup"><span data-stu-id="c7ddc-127">Delhi voice routing policy</span></span>   |<span data-ttu-id="c7ddc-128">海德拉巴语音路由策略</span><span class="sxs-lookup"><span data-stu-id="c7ddc-128">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="c7ddc-129">联机 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="c7ddc-129">Online PSTN usages</span></span>  |<span data-ttu-id="c7ddc-130">长途电话</span><span class="sxs-lookup"><span data-stu-id="c7ddc-130">Long Distance</span></span>  |<span data-ttu-id="c7ddc-131">Long Distance，Local，内部</span><span class="sxs-lookup"><span data-stu-id="c7ddc-131">Long Distance, Local, Internal</span></span>  |

    <span data-ttu-id="c7ddc-132">有关详细信息，请参阅[新建 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-132">For more information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>
3. <span data-ttu-id="c7ddc-133">使用``Grant-CsOnlineVoiceRoutingPolicy``cmdlet 将联机语音路由到用户需要路由限制以强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-133">Use the ``Grant-CsOnlineVoiceRoutingPolicy`` cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="c7ddc-134">启用基于位置的路由的网络站点</span><span class="sxs-lookup"><span data-stu-id="c7ddc-134">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="c7ddc-135">使用``Set-CsTenantNetworkSite``cmdlet 启用基于位置的路由和关联的语音路由策略给您需要强制执行路由限制的网络站点。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-135">Use the ``Set-CsTenantNetworkSite`` cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -OnlineVoiceRoutingPolicy <voice routing policy ID> 
    ```

    <span data-ttu-id="c7ddc-136">本示例中，我们启用德里网站和海德拉巴站点基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-136">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "DelhiVoiceRoutingPolicy" 
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "HyderabadVoiceRoutingPolicy" 
    ```
    <span data-ttu-id="c7ddc-137">下表显示了在此示例基于位置的路由启用的网站。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-137">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="c7ddc-138">站点 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="c7ddc-138">Site 1 (Delhi)</span></span>  |<span data-ttu-id="c7ddc-139">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="c7ddc-139">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="c7ddc-140">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="c7ddc-140">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="c7ddc-141">True</span><span class="sxs-lookup"><span data-stu-id="c7ddc-141">True</span></span>    |<span data-ttu-id="c7ddc-142">True</span><span class="sxs-lookup"><span data-stu-id="c7ddc-142">True</span></span>    |
    |<span data-ttu-id="c7ddc-143">语音路由策略</span><span class="sxs-lookup"><span data-stu-id="c7ddc-143">Voice routing policy</span></span>    | <span data-ttu-id="c7ddc-144">德里语音路由策略</span><span class="sxs-lookup"><span data-stu-id="c7ddc-144">Delhi voice routing policy</span></span>       |<span data-ttu-id="c7ddc-145">海德拉巴语音路由策略</span><span class="sxs-lookup"><span data-stu-id="c7ddc-145">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="c7ddc-146">子网</span><span class="sxs-lookup"><span data-stu-id="c7ddc-146">Subnets</span></span>     |<span data-ttu-id="c7ddc-147">子网 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="c7ddc-147">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="c7ddc-148">子网 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="c7ddc-148">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="c7ddc-149">启用基于位置的网关的路由</span><span class="sxs-lookup"><span data-stu-id="c7ddc-149">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="c7ddc-150">使用``New-CsOnlinePstnGateway``cmdlet 以创建网关配置为每个网关或网络站点。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-150">Use the ``New-CsOnlinePstnGateway`` cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="c7ddc-151">如果多个网关相关联 （例如，网关或 PBX） 系统，修改每个网关，若要启用基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-151">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="c7ddc-152">本示例中，我们将创建一个网关配置，每个网关。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-152">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="c7ddc-153">有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-153">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="c7ddc-154">使用``Set-CSOnlinePSTNGateway``cmdlet 来启用基于位置的路由需要强制执行路由限制您网关。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-154">Use the ``Set-CSOnlinePSTNGateway`` cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="c7ddc-155">启用基于位置的路由到网关将呼叫路由到 PSTN 网关的呼叫路由到 PSTN，并将网关所在的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-155">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="c7ddc-156">本示例中，我们启用基于位置的每个网关关联到德里和海德拉巴站点中的 PSTN 网关的路由。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-156">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="c7ddc-157">不启用基于位置的不将呼叫路由至 PSTN 网关的路由。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-157">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="c7ddc-158">但是，您仍需要将的网关的系统所在的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-158">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="c7ddc-159">这是因为需要达到通过此网关连接的终结点的 PSTN 呼叫的强制实施基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-159">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="c7ddc-160">本示例中，基于位置的路由到 PBX 系统的德里和海德拉巴站点中具有关联的每个网关未启用。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-160">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="c7ddc-161">连接到系统不将呼叫路由至 PSTN (例如，PBX) 的终结点将作为团队启用的用户的基于位置的路由的终结点具有类似的限制。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-161">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="c7ddc-162">这意味着这些用户可以发起和接收呼叫与团队用户无论用户的位置。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-162">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="c7ddc-163">此外可以发起和接收呼叫与其他系统不将呼叫路由至 PSTN 网络 （例如，连接到不同 PBX 终结点） 无论系统已关联的网络站点。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-163">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="c7ddc-164">所有入站的呼叫、 出站呼叫、 呼叫转接和涉及 PSTN 终结点的呼叫转接将采用基于位置的路由执行进行。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-164">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="c7ddc-165">这些呼叫必须使用仅 PSTN 网关定义为本地到这些系统。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-165">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="c7ddc-166">下表显示的四个网关的网关配置在两个不同的网络站点： 两个连接到 PSTN 网关和两个连接到 PBX 系统。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-166">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="c7ddc-167">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="c7ddc-167">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="c7ddc-168">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="c7ddc-168">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="c7ddc-169">PstnGateway:Gateway 1 DEL 网关</span><span class="sxs-lookup"><span data-stu-id="c7ddc-169">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="c7ddc-170">True</span><span class="sxs-lookup"><span data-stu-id="c7ddc-170">True</span></span>     |   <span data-ttu-id="c7ddc-171">站点 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="c7ddc-171">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="c7ddc-172">PstnGateway:Gateway 2 HYD 网关</span><span class="sxs-lookup"><span data-stu-id="c7ddc-172">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="c7ddc-173">True</span><span class="sxs-lookup"><span data-stu-id="c7ddc-173">True</span></span>      |      <span data-ttu-id="c7ddc-174">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="c7ddc-174">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="c7ddc-175">PstnGateway:Gateway 3 DEL PBX</span><span class="sxs-lookup"><span data-stu-id="c7ddc-175">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="c7ddc-176">True</span><span class="sxs-lookup"><span data-stu-id="c7ddc-176">True</span></span>     |     <span data-ttu-id="c7ddc-177">站点 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="c7ddc-177">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="c7ddc-178">PstnGateway:Gateway 4 HYD PBX</span><span class="sxs-lookup"><span data-stu-id="c7ddc-178">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="c7ddc-179">True</span><span class="sxs-lookup"><span data-stu-id="c7ddc-179">True</span></span>     |    <span data-ttu-id="c7ddc-180">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="c7ddc-180">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="c7ddc-181">启用基于位置的路由调用策略</span><span class="sxs-lookup"><span data-stu-id="c7ddc-181">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="c7ddc-182">若要强制执行的特定用户的基于位置的路由，用户的语音策略，可防止 PTSN 收费电话设置，绕过。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-182">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="c7ddc-183">使用``Grant-TeamsCallingPolicy``cmdlet 来启用基于位置的路由通过防止 PSTN 收费绕过。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-183">Use the ``Grant-TeamsCallingPolicy`` cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-TeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="c7ddc-184">本示例中，我们将禁止 PSTN 收费绕过为 User1 的调用策略。</span><span class="sxs-lookup"><span data-stu-id="c7ddc-184">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-TeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="c7ddc-185">相关主题</span><span class="sxs-lookup"><span data-stu-id="c7ddc-185">Related topics</span></span>
- [<span data-ttu-id="c7ddc-186">规划基于位置的路由直接路由</span><span class="sxs-lookup"><span data-stu-id="c7ddc-186">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="c7ddc-187">配置基于位置的路由的网络设置</span><span class="sxs-lookup"><span data-stu-id="c7ddc-187">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="c7ddc-188">基于位置的路由术语</span><span class="sxs-lookup"><span data-stu-id="c7ddc-188">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
