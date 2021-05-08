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
description: 了解如何为直接Location-Based启用路由，包括为用户、网络站点、网关配置和调用策略启用路由。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d43d650384dd538ff481ac9625c15b9a9f420d95
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120573"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="9df8e-103">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="9df8e-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="9df8e-104">在按照本文中的步骤操作之前，请确保已阅读规划直接路由的[](location-based-routing-plan.md)Location-Based 路由，并已完成配置路由的网络设置中的[Location-Based步骤](location-based-routing-configure-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="9df8e-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="9df8e-105">本文介绍如何为直接路由Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="9df8e-106">部署电话系统路由并设置网络区域、站点和子网后，即可启用 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="9df8e-107">若要完成本文中的步骤，需要熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9df8e-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="9df8e-108">有关详细信息，请参阅[PowerShell Teams概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9df8e-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="9df8e-109">必须针对以下Location-Based启用路由：</span><span class="sxs-lookup"><span data-stu-id="9df8e-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="9df8e-110">用户</span><span class="sxs-lookup"><span data-stu-id="9df8e-110">Users</span></span>
- <span data-ttu-id="9df8e-111">网络站点</span><span class="sxs-lookup"><span data-stu-id="9df8e-111">Network sites</span></span>
- <span data-ttu-id="9df8e-112">网关配置</span><span class="sxs-lookup"><span data-stu-id="9df8e-112">Gateway configurations</span></span>
- <span data-ttu-id="9df8e-113">通话策略</span><span class="sxs-lookup"><span data-stu-id="9df8e-113">Calling policies</span></span>

<span data-ttu-id="9df8e-114">可以使用 Microsoft [团队管理中心或](#using-the-microsoft-teams-admin-center) [PowerShel](#using-powershell)l 启用Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9df8e-115">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="9df8e-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="9df8e-116">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="9df8e-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="9df8e-117">创建语音路由策略并将 PSTN 使用情况分配给该策略。</span><span class="sxs-lookup"><span data-stu-id="9df8e-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="9df8e-118">将 PSTN 使用情况分配给策略时，请确保执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="9df8e-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="9df8e-119">使用与使用站点本地 PSTN 网关的语音路由关联的 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="9df8e-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="9df8e-120">使用与使用 PSTN 网关的语音路由相关联的 PSTN 使用情况，该网关位于Location-Based不需要路由限制的区域。</span><span class="sxs-lookup"><span data-stu-id="9df8e-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="9df8e-121">将语音路由策略分配给需要强制实施路由限制的用户。</span><span class="sxs-lookup"><span data-stu-id="9df8e-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="9df8e-122">若要详细了解如何创建语音路由策略并将其分配给用户，请参阅在 Microsoft Teams 中管理[语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9df8e-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="9df8e-123">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="9df8e-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="9df8e-124">为Location-Based实施路由限制的站点启用路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="9df8e-125">为此，请在 Microsoft Teams 管理中心的左侧导航中，转到"位置""网络拓扑"，选择一个网络站点，单击"编辑"，然后打开"基于位置的路由  >  **"。** </span><span class="sxs-lookup"><span data-stu-id="9df8e-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="9df8e-126">有关详细信息，请参阅 [管理网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="9df8e-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="9df8e-127">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="9df8e-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="9df8e-128">启用Location-Based路由到将呼叫路由到 PSTN 的 PSTN 网关的网关，并关联网关所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="9df8e-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="9df8e-129">在左侧导航中，转到 **"语音**  >  **直接路由"，** 然后单击 **"SDC"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9df8e-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="9df8e-130">选择 SBC，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="9df8e-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="9df8e-131">在 **"基于位置的路由和媒体优化"下**，启用 **"启用基于位置的路由"。**</span><span class="sxs-lookup"><span data-stu-id="9df8e-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="9df8e-132">指定网关站点 ID，然后设置绕过模式。</span><span class="sxs-lookup"><span data-stu-id="9df8e-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="9df8e-133">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="9df8e-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="9df8e-134">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="9df8e-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="9df8e-135">若要Location-Based用户强制使用呼叫路由，请设置用户的呼叫策略以防止 PSTN 收费绕过。</span><span class="sxs-lookup"><span data-stu-id="9df8e-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="9df8e-136">为此，请打开呼叫 **策略中的** "防止绕过收费"设置。</span><span class="sxs-lookup"><span data-stu-id="9df8e-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="9df8e-137">若要了解有关详细信息，请参阅[在 Teams 中调用策略](teams-calling-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="9df8e-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="9df8e-138">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9df8e-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="9df8e-139">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="9df8e-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="9df8e-140">使用 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet 设置 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="9df8e-140">Use the [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="9df8e-141">对于多个用法，请用逗号分隔每个用法。</span><span class="sxs-lookup"><span data-stu-id="9df8e-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="9df8e-142">例如：</span><span class="sxs-lookup"><span data-stu-id="9df8e-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="9df8e-143">使用 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 创建语音路由策略，将用户与相应的 PSTN 使用情况关联。</span><span class="sxs-lookup"><span data-stu-id="9df8e-143">Use the [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="9df8e-144">将 PSTN 使用情况分配到语音路由策略时，请确保执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="9df8e-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="9df8e-145">使用与使用站点本地 PSTN 网关的语音路由关联的 PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="9df8e-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="9df8e-146">使用与使用 PSTN 网关的语音路由相关联的 PSTN 使用情况，该网关位于Location-Based不需要路由限制的区域。</span><span class="sxs-lookup"><span data-stu-id="9df8e-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="9df8e-147">本示例将创建两个新的语音路由策略，并为其分配 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="9df8e-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="9df8e-148">下表显示了本示例中定义的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="9df8e-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="9df8e-149">语音路由策略 1</span><span class="sxs-lookup"><span data-stu-id="9df8e-149">Voice routing policy 1</span></span>|<span data-ttu-id="9df8e-150">语音路由策略 2</span><span class="sxs-lookup"><span data-stu-id="9df8e-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="9df8e-151">联机语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="9df8e-151">Online voice policy ID</span></span>   |<span data-ttu-id="9df8e-152">印地语在线语音路由策略</span><span class="sxs-lookup"><span data-stu-id="9df8e-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="9df8e-153">海得拉巴在线语音路由策略</span><span class="sxs-lookup"><span data-stu-id="9df8e-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="9df8e-154">联机 PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="9df8e-154">Online PSTN usages</span></span>  |<span data-ttu-id="9df8e-155">长距离</span><span class="sxs-lookup"><span data-stu-id="9df8e-155">Long Distance</span></span>  |<span data-ttu-id="9df8e-156">长距离、本地、内部</span><span class="sxs-lookup"><span data-stu-id="9df8e-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="9df8e-157">使用 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 将联机语音路由策略关联到需要强制实施路由限制的用户。</span><span class="sxs-lookup"><span data-stu-id="9df8e-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="9df8e-158">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="9df8e-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="9df8e-159">使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet 启用 Location-Based 路由并将语音路由策略关联到需要强制实施路由限制的网络站点。</span><span class="sxs-lookup"><span data-stu-id="9df8e-159">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="9df8e-160">此示例中，我们为Location-Based和海得拉巴站点启用路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="9df8e-161">下表显示了本示例中为 Location-Based路由启用的站点。</span><span class="sxs-lookup"><span data-stu-id="9df8e-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="9df8e-162">网站 1 (里尼) </span><span class="sxs-lookup"><span data-stu-id="9df8e-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="9df8e-163">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="9df8e-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="9df8e-164">站点名称</span><span class="sxs-lookup"><span data-stu-id="9df8e-164">Site name</span></span>    |<span data-ttu-id="9df8e-165">网站 1 (里尼) </span><span class="sxs-lookup"><span data-stu-id="9df8e-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="9df8e-166">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="9df8e-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="9df8e-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="9df8e-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="9df8e-168">True</span><span class="sxs-lookup"><span data-stu-id="9df8e-168">True</span></span>    |<span data-ttu-id="9df8e-169">True</span><span class="sxs-lookup"><span data-stu-id="9df8e-169">True</span></span>    |
    |<span data-ttu-id="9df8e-170">子网</span><span class="sxs-lookup"><span data-stu-id="9df8e-170">Subnets</span></span>     |<span data-ttu-id="9df8e-171">子网 1 (里尼) </span><span class="sxs-lookup"><span data-stu-id="9df8e-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="9df8e-172">Hyderabad (子网 2) </span><span class="sxs-lookup"><span data-stu-id="9df8e-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="9df8e-173">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="9df8e-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="9df8e-174">使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet 为每个网关或网络站点创建网关配置。</span><span class="sxs-lookup"><span data-stu-id="9df8e-174">Use the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="9df8e-175">如果多个网关与一个系统 (例如网关或 PBX) ，请修改每个网关以启用Location-Based限制。</span><span class="sxs-lookup"><span data-stu-id="9df8e-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="9df8e-176">本示例为每个网关创建一个网关配置。</span><span class="sxs-lookup"><span data-stu-id="9df8e-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="9df8e-177">有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="9df8e-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="9df8e-178">使用 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet 为需要强制实施路由Location-Based网关启用路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-178">Use the [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="9df8e-179">启用Location-Based路由到将呼叫路由到 PSTN 的 PSTN 网关的网关，并关联网关所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="9df8e-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="9df8e-180">本示例为与Location-Based和海得拉巴站点中的 PSTN 网关关联的每个网关启用路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="9df8e-181">不要为Location-Based PSTN 路由呼叫的网关启用路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="9df8e-182">但是，仍必须将网关关联到系统所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="9df8e-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="9df8e-183">这是因为对于Location-Based通过此网关连接的终结点的 PSTN 呼叫，需要强制实施路由限制。</span><span class="sxs-lookup"><span data-stu-id="9df8e-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="9df8e-184">此示例中，Location-Based和海得拉巴站点中与 PBX 系统关联的每个网关未启用路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="9df8e-185">为Location-Based启用路由</span><span class="sxs-lookup"><span data-stu-id="9df8e-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="9df8e-186">若要为Location-Based用户强制实施语音路由，请设置用户的语音策略，以防止 PTSN 收费绕过。</span><span class="sxs-lookup"><span data-stu-id="9df8e-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="9df8e-187">使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet Location-Based PSTN 收费绕过来启用自动路由。</span><span class="sxs-lookup"><span data-stu-id="9df8e-187">Use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="9df8e-188">本示例阻止用户 1 的呼叫策略绕过 PSTN 收费。</span><span class="sxs-lookup"><span data-stu-id="9df8e-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="9df8e-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="9df8e-189">Related topics</span></span>

- [<span data-ttu-id="9df8e-190">云语音功能的网络设置Teams</span><span class="sxs-lookup"><span data-stu-id="9df8e-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)