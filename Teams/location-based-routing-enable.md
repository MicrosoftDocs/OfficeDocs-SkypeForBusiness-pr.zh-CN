---
title: 为直接路由启用基于位置的路由
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何为直接路由Location-Based路由，包括为用户、网络站点、网关配置和调用策略启用它。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe9600a1ddc530b1dbbcb6c061021c9d4cd9d537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822912"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="45b1a-103">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="45b1a-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="45b1a-104">在按照本文中的步骤操作之前，请确保已阅读"直接路由Location-Based[](location-based-routing-plan.md)计划"，并完成了"为直接路由配置网络设置Location-Based[步骤](location-based-routing-configure-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="45b1a-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="45b1a-105">本文介绍如何为直接路由Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="45b1a-106">部署电话系统直接路由并设置网络区域、站点和子网后，即可启用Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="45b1a-107">若要完成本文中的步骤，需要熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="45b1a-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="45b1a-108">若要了解有关详细信息，请参阅 [Teams PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="45b1a-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="45b1a-109">必须启用以下Location-Based路由：</span><span class="sxs-lookup"><span data-stu-id="45b1a-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="45b1a-110">用户</span><span class="sxs-lookup"><span data-stu-id="45b1a-110">Users</span></span>
- <span data-ttu-id="45b1a-111">网络站点</span><span class="sxs-lookup"><span data-stu-id="45b1a-111">Network sites</span></span>
- <span data-ttu-id="45b1a-112">网关配置</span><span class="sxs-lookup"><span data-stu-id="45b1a-112">Gateway configurations</span></span>
- <span data-ttu-id="45b1a-113">通话策略</span><span class="sxs-lookup"><span data-stu-id="45b1a-113">Calling policies</span></span>

<span data-ttu-id="45b1a-114">可以使用 Microsoft [团队管理中心或](#using-the-microsoft-teams-admin-center) [PowerShel](#using-powershell)l 来启用Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="45b1a-115">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="45b1a-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="45b1a-116">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="45b1a-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="45b1a-117">创建语音路由策略，并将 PSTN 使用情况分配到该策略。</span><span class="sxs-lookup"><span data-stu-id="45b1a-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="45b1a-118">将 PSTN 使用情况分配给策略时，请确保执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="45b1a-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="45b1a-119">使用与使用站点本地 PSTN 网关的语音路由关联的 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="45b1a-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="45b1a-120">使用与使用 PSTN 网关（位于不需要路由Location-Based区域）的语音路由关联的 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="45b1a-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="45b1a-121">将语音路由策略分配给需要强制实施路由限制的用户。</span><span class="sxs-lookup"><span data-stu-id="45b1a-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="45b1a-122">若要详细了解如何创建语音路由策略并将其分配给用户，请参阅"在 Microsoft Teams 中管理[语音路由策略"。](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="45b1a-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="45b1a-123">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="45b1a-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="45b1a-124">为Location-Based实施路由限制的站点启用路由路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="45b1a-125">为此，请在 Microsoft Teams 管理中心的左侧导航栏中，转到"位置网络拓扑"，选择网络站点，单击"编辑"，然后打开基于位置的  >  **路由**。 </span><span class="sxs-lookup"><span data-stu-id="45b1a-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="45b1a-126">若要了解有关详细信息，请参阅["管理网络拓扑"。](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="45b1a-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="45b1a-127">为Location-Based启用网关路由</span><span class="sxs-lookup"><span data-stu-id="45b1a-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="45b1a-128">启用Location-Based路由到将呼叫路由到 PSTN 的 PSTN 网关的网关，并关联网关所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="45b1a-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="45b1a-129">在左侧导航栏中，转到 **"语音**  >  **直接路由**"，然后单击 **"SDC"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="45b1a-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="45b1a-130">选择 SBC，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="45b1a-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="45b1a-131">在 **"基于位置的路由和媒体优化**"下，启用 **"启用基于位置的路由"。**</span><span class="sxs-lookup"><span data-stu-id="45b1a-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="45b1a-132">指定网关站点 ID，然后设置绕过模式。</span><span class="sxs-lookup"><span data-stu-id="45b1a-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="45b1a-133">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="45b1a-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="45b1a-134">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="45b1a-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="45b1a-135">若要为Location-Based强制路由，请设置用户的呼叫策略以防止 PSTN 收费绕过。</span><span class="sxs-lookup"><span data-stu-id="45b1a-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="45b1a-136">为此，请打开呼叫策略 **中的** "防止免验证通行费"设置。</span><span class="sxs-lookup"><span data-stu-id="45b1a-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="45b1a-137">若要了解有关详细信息，请参阅 Teams [中的调用策略](teams-calling-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="45b1a-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="45b1a-138">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="45b1a-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="45b1a-139">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="45b1a-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="45b1a-140">使用 [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet 设置 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="45b1a-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="45b1a-141">对于多个用法，请用逗号分隔每个用法。</span><span class="sxs-lookup"><span data-stu-id="45b1a-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="45b1a-142">例如：</span><span class="sxs-lookup"><span data-stu-id="45b1a-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="45b1a-143">使用 [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 创建语音路由策略，将用户与相应的 PSTN 使用情况关联。</span><span class="sxs-lookup"><span data-stu-id="45b1a-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="45b1a-144">将 PSTN 使用情况分配给语音路由策略时，请确保执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="45b1a-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="45b1a-145">使用与使用站点本地 PSTN 网关的语音路由关联的 PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="45b1a-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="45b1a-146">使用与使用 PSTN 网关（位于不需要路由Location-Based区域）的语音路由关联的 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="45b1a-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="45b1a-147">本示例创建两个新的语音路由策略，并为其分配 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="45b1a-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="45b1a-148">下表显示了本示例中定义的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="45b1a-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="45b1a-149">语音路由策略 1</span><span class="sxs-lookup"><span data-stu-id="45b1a-149">Voice routing policy 1</span></span>|<span data-ttu-id="45b1a-150">语音路由策略 2</span><span class="sxs-lookup"><span data-stu-id="45b1a-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="45b1a-151">联机语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="45b1a-151">Online voice policy ID</span></span>   |<span data-ttu-id="45b1a-152">用户在线语音路由策略</span><span class="sxs-lookup"><span data-stu-id="45b1a-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="45b1a-153">海得拉巴在线语音路由策略</span><span class="sxs-lookup"><span data-stu-id="45b1a-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="45b1a-154">联机 PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="45b1a-154">Online PSTN usages</span></span>  |<span data-ttu-id="45b1a-155">长距离</span><span class="sxs-lookup"><span data-stu-id="45b1a-155">Long Distance</span></span>  |<span data-ttu-id="45b1a-156">长距离、本地、内部</span><span class="sxs-lookup"><span data-stu-id="45b1a-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="45b1a-157">使用 [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 将联机语音路由策略关联到需要强制实施路由限制的用户。</span><span class="sxs-lookup"><span data-stu-id="45b1a-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="45b1a-158">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="45b1a-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="45b1a-159">使用 [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet 启用Location-Based路由并将语音路由策略关联到需要强制实施路由限制的网络站点。</span><span class="sxs-lookup"><span data-stu-id="45b1a-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="45b1a-160">此示例中，我们为Location-Based和海得拉巴站点启用路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="45b1a-161">下表显示了本示例中为Location-Based路由启用的站点。</span><span class="sxs-lookup"><span data-stu-id="45b1a-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="45b1a-162">站点 1 (西) </span><span class="sxs-lookup"><span data-stu-id="45b1a-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="45b1a-163">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="45b1a-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="45b1a-164">站点名称</span><span class="sxs-lookup"><span data-stu-id="45b1a-164">Site name</span></span>    |<span data-ttu-id="45b1a-165">站点 1 (西) </span><span class="sxs-lookup"><span data-stu-id="45b1a-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="45b1a-166">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="45b1a-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="45b1a-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="45b1a-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="45b1a-168">True</span><span class="sxs-lookup"><span data-stu-id="45b1a-168">True</span></span>    |<span data-ttu-id="45b1a-169">True</span><span class="sxs-lookup"><span data-stu-id="45b1a-169">True</span></span>    |
    |<span data-ttu-id="45b1a-170">子网</span><span class="sxs-lookup"><span data-stu-id="45b1a-170">Subnets</span></span>     |<span data-ttu-id="45b1a-171">子网 1 (卡西) </span><span class="sxs-lookup"><span data-stu-id="45b1a-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="45b1a-172">Hyderabad (子网 2) </span><span class="sxs-lookup"><span data-stu-id="45b1a-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="45b1a-173">为Location-Based启用网关路由</span><span class="sxs-lookup"><span data-stu-id="45b1a-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="45b1a-174">使用 [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet 为每个网关或网络站点创建网关配置。</span><span class="sxs-lookup"><span data-stu-id="45b1a-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="45b1a-175">如果多个网关与一个系统 (例如网关或 PBX) ，请修改每个网关以启用Location-Based限制。</span><span class="sxs-lookup"><span data-stu-id="45b1a-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="45b1a-176">本示例为每个网关创建一个网关配置。</span><span class="sxs-lookup"><span data-stu-id="45b1a-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="45b1a-177">有关详细信息，请参阅"配置[直接路由"。](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="45b1a-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="45b1a-178">使用 [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet Location-Based网关启用需要强制实施路由限制的路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="45b1a-179">启用Location-Based路由到将呼叫路由到 PSTN 的 PSTN 网关的网关，并关联网关所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="45b1a-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="45b1a-180">本示例为与 Location-Based Hyderabad 站点中的 PSTN 网关关联的每个网关启用网关路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="45b1a-181">不要为Location-Based PSTN 路由呼叫的网关启用路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="45b1a-182">但是，仍必须将网关关联到系统所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="45b1a-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="45b1a-183">这是因为对于Location-Based通过此网关连接的终结点的 PSTN 呼叫，需要强制实施路由限制。</span><span class="sxs-lookup"><span data-stu-id="45b1a-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="45b1a-184">本示例未Location-Based与用户和海得拉巴站点中的 PBX 系统关联的每个网关启用路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="45b1a-185">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="45b1a-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="45b1a-186">若要为Location-Based用户强制实施语音路由，请设置用户的语音策略以防止 PTSN 通行费绕过。</span><span class="sxs-lookup"><span data-stu-id="45b1a-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="45b1a-187">使用 [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet Location-Based PSTN 通行费绕过来启用自动路由。</span><span class="sxs-lookup"><span data-stu-id="45b1a-187">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="45b1a-188">本示例阻止用户 1 的呼叫策略绕过 PSTN 收费。</span><span class="sxs-lookup"><span data-stu-id="45b1a-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="45b1a-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="45b1a-189">Related topics</span></span>

- [<span data-ttu-id="45b1a-190">Teams 中云语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="45b1a-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
