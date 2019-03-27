---
title: 为直接路由启用基于位置的路由
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
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68b239d00e67d942f80a259facb87c80ddf2a55
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886029"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="480f4-103">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="480f4-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="480f4-104">在按照本文中的步骤之前，请确保您已阅读[Plan Location-Based 路由直接路由](location-based-routing-plan.md)并完成[配置的基于位置的路由的网络设置](location-based-routing-configure-network-settings.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="480f4-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="480f4-105">本文介绍如何启用基于位置的路由，以便直接路由。</span><span class="sxs-lookup"><span data-stu-id="480f4-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="480f4-106">在部署电话系统直接路由，并设置网络区域、 网站和子网后，您已准备好启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="480f4-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="480f4-107">若要完成本文中的步骤，您将需要一些熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="480f4-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="480f4-108">若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="480f4-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="480f4-109">您必须启用以下基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="480f4-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="480f4-110">用户</span><span class="sxs-lookup"><span data-stu-id="480f4-110">Users</span></span>
- <span data-ttu-id="480f4-111">网络站点</span><span class="sxs-lookup"><span data-stu-id="480f4-111">Network sites</span></span>
- <span data-ttu-id="480f4-112">网关配置</span><span class="sxs-lookup"><span data-stu-id="480f4-112">Gateway configurations</span></span>
- <span data-ttu-id="480f4-113">调用策略</span><span class="sxs-lookup"><span data-stu-id="480f4-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="480f4-114">启用的用户的基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="480f4-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="480f4-115">使用[组 CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet 可设置 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="480f4-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="480f4-116">使用多个实例，用逗号分隔每个使用率。</span><span class="sxs-lookup"><span data-stu-id="480f4-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="480f4-117">例如：</span><span class="sxs-lookup"><span data-stu-id="480f4-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="480f4-118">[新建 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 用于创建语音路由策略，以将用户与相应的 PSTN 用法相关联。</span><span class="sxs-lookup"><span data-stu-id="480f4-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="480f4-119">当您将 PSTN 用法分配语音路由策略时时，请确保您执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="480f4-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="480f4-120">使用对网站使用本地 PSTN 网关的语音路由相关联的 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="480f4-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="480f4-121">使用与使用 PSTN 网关位于其中不需要基于位置的路由限制区域中的语音路由相关联的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="480f4-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="480f4-122">本示例中，我们将创建两个新的语音路由策略和 PSTN 用法分配给它们。</span><span class="sxs-lookup"><span data-stu-id="480f4-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="480f4-123">下表显示了在此示例中定义的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="480f4-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="480f4-124">语音路由策略 1</span><span class="sxs-lookup"><span data-stu-id="480f4-124">Voice routing policy 1</span></span>|<span data-ttu-id="480f4-125">语音路由策略 2</span><span class="sxs-lookup"><span data-stu-id="480f4-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="480f4-126">Online 语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="480f4-126">Online voice policy ID</span></span>   |<span data-ttu-id="480f4-127">德里联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="480f4-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="480f4-128">海德拉巴联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="480f4-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="480f4-129">联机 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="480f4-129">Online PSTN usages</span></span>  |<span data-ttu-id="480f4-130">长途电话</span><span class="sxs-lookup"><span data-stu-id="480f4-130">Long Distance</span></span>  |<span data-ttu-id="480f4-131">Long Distance，Local，内部</span><span class="sxs-lookup"><span data-stu-id="480f4-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="480f4-132">使用[授予 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 可以将用户需要路由限制以强制实施联机语音路由策略相关联。</span><span class="sxs-lookup"><span data-stu-id="480f4-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="480f4-133">启用基于位置的路由的网络站点</span><span class="sxs-lookup"><span data-stu-id="480f4-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="480f4-134">[设置 CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet 用于启用基于位置的路由，并将语音路由策略给您需要强制执行路由限制的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="480f4-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="480f4-135">本示例中，我们启用德里网站和海德拉巴站点基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="480f4-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="480f4-136">下表显示了在此示例基于位置的路由启用的网站。</span><span class="sxs-lookup"><span data-stu-id="480f4-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="480f4-137">站点 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="480f4-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="480f4-138">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="480f4-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="480f4-139">站点名称</span><span class="sxs-lookup"><span data-stu-id="480f4-139">Site name</span></span>    |<span data-ttu-id="480f4-140">站点 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="480f4-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="480f4-141">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="480f4-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="480f4-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="480f4-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="480f4-143">True</span><span class="sxs-lookup"><span data-stu-id="480f4-143">True</span></span>    |<span data-ttu-id="480f4-144">True</span><span class="sxs-lookup"><span data-stu-id="480f4-144">True</span></span>    |
    |<span data-ttu-id="480f4-145">子网</span><span class="sxs-lookup"><span data-stu-id="480f4-145">Subnets</span></span>     |<span data-ttu-id="480f4-146">子网 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="480f4-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="480f4-147">子网 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="480f4-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="480f4-148">启用基于位置的网关的路由</span><span class="sxs-lookup"><span data-stu-id="480f4-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="480f4-149">[新建 CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet 用于创建网关配置为每个网关或网络站点。</span><span class="sxs-lookup"><span data-stu-id="480f4-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="480f4-150">如果多个网关相关联 （例如，网关或 PBX） 系统，修改每个网关，若要启用基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="480f4-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="480f4-151">本示例中，我们将创建一个网关配置，每个网关。</span><span class="sxs-lookup"><span data-stu-id="480f4-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="480f4-152">有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="480f4-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="480f4-153">[设置 CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet 用于启用基于位置的路由需要强制执行路由限制您网关。</span><span class="sxs-lookup"><span data-stu-id="480f4-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="480f4-154">启用基于位置的路由到网关将呼叫路由到 PSTN 网关的呼叫路由到 PSTN，并将网关所在的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="480f4-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="480f4-155">本示例中，我们启用基于位置的每个网关关联到德里和海德拉巴站点中的 PSTN 网关的路由。</span><span class="sxs-lookup"><span data-stu-id="480f4-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="480f4-156">不启用基于位置的不将呼叫路由至 PSTN 网关的路由。</span><span class="sxs-lookup"><span data-stu-id="480f4-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="480f4-157">但是，您仍需要将的网关的系统所在的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="480f4-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="480f4-158">这是因为需要达到通过此网关连接的终结点的 PSTN 呼叫的强制实施基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="480f4-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="480f4-159">本示例中，基于位置的路由到 PBX 系统的德里和海德拉巴站点中具有关联的每个网关未启用。</span><span class="sxs-lookup"><span data-stu-id="480f4-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="480f4-160">连接到系统不将呼叫路由至 PSTN (例如，PBX) 的终结点将作为团队启用的用户的基于位置的路由的终结点具有类似的限制。</span><span class="sxs-lookup"><span data-stu-id="480f4-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="480f4-161">这意味着这些用户可以发起和接收呼叫与团队用户无论用户的位置。</span><span class="sxs-lookup"><span data-stu-id="480f4-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="480f4-162">此外可以发起和接收呼叫与其他系统不将呼叫路由至 PSTN 网络 （例如，连接到不同 PBX 终结点） 无论系统已关联的网络站点。</span><span class="sxs-lookup"><span data-stu-id="480f4-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="480f4-163">所有入站的呼叫、 出站呼叫、 呼叫转接和涉及 PSTN 终结点的呼叫转接将采用基于位置的路由执行进行。</span><span class="sxs-lookup"><span data-stu-id="480f4-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="480f4-164">这些呼叫必须使用仅 PSTN 网关定义为本地到这些系统。</span><span class="sxs-lookup"><span data-stu-id="480f4-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="480f4-165">下表显示的四个网关的网关配置在两个不同的网络站点： 两个连接到 PSTN 网关和两个连接到 PBX 系统。</span><span class="sxs-lookup"><span data-stu-id="480f4-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="480f4-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="480f4-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="480f4-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="480f4-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="480f4-168">PstnGateway:Gateway 1 DEL 网关</span><span class="sxs-lookup"><span data-stu-id="480f4-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="480f4-169">True</span><span class="sxs-lookup"><span data-stu-id="480f4-169">True</span></span>     |   <span data-ttu-id="480f4-170">站点 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="480f4-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="480f4-171">PstnGateway:Gateway 2 HYD 网关</span><span class="sxs-lookup"><span data-stu-id="480f4-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="480f4-172">True</span><span class="sxs-lookup"><span data-stu-id="480f4-172">True</span></span>      |      <span data-ttu-id="480f4-173">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="480f4-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="480f4-174">PstnGateway:Gateway 3 DEL PBX</span><span class="sxs-lookup"><span data-stu-id="480f4-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="480f4-175">False</span><span class="sxs-lookup"><span data-stu-id="480f4-175">False</span></span>     |     <span data-ttu-id="480f4-176">站点 1 （德里）</span><span class="sxs-lookup"><span data-stu-id="480f4-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="480f4-177">PstnGateway:Gateway 4 HYD PBX</span><span class="sxs-lookup"><span data-stu-id="480f4-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="480f4-178">False</span><span class="sxs-lookup"><span data-stu-id="480f4-178">False</span></span>     |    <span data-ttu-id="480f4-179">站点 2 （海德拉巴）</span><span class="sxs-lookup"><span data-stu-id="480f4-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="480f4-180">启用基于位置的路由调用策略</span><span class="sxs-lookup"><span data-stu-id="480f4-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="480f4-181">若要强制执行的特定用户的基于位置的路由，用户的语音策略，可防止 PTSN 收费电话设置，绕过。</span><span class="sxs-lookup"><span data-stu-id="480f4-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="480f4-182">[授予 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet 用于启用基于位置的路由通过防止 PSTN 收费绕过。</span><span class="sxs-lookup"><span data-stu-id="480f4-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="480f4-183">本示例中，我们将禁止 PSTN 收费绕过为 User1 的调用策略。</span><span class="sxs-lookup"><span data-stu-id="480f4-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="480f4-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="480f4-184">Related topics</span></span>
- [<span data-ttu-id="480f4-185">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="480f4-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="480f4-186">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="480f4-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="480f4-187">基于位置的路由术语</span><span class="sxs-lookup"><span data-stu-id="480f4-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
