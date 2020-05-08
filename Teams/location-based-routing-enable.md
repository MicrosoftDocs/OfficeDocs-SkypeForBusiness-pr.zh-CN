---
title: 为直接路由启用基于位置的路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何为直接路由启用基于位置的路由，包括为用户、网络站点、网关配置和呼叫策略启用它。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69f2ee37e63f83d6fc1d19ea733ff44ad23e7011
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158989"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="0b9b2-103">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0b9b2-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="0b9b2-104">在按照本文中的步骤操作之前，请确保已阅读[基于计划位置的路由以进行直接路由](location-based-routing-plan.md)，并完成了为[基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="0b9b2-105">本文介绍如何为直接路由启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="0b9b2-106">部署手机系统直接路由和设置网络区域、网站和子网后，您就可以启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="0b9b2-107">若要完成本文中的步骤，你需要熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="0b9b2-108">若要了解详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="0b9b2-109">您必须启用以下各项的基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="0b9b2-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="0b9b2-110">用户</span><span class="sxs-lookup"><span data-stu-id="0b9b2-110">Users</span></span>
- <span data-ttu-id="0b9b2-111">网络站点</span><span class="sxs-lookup"><span data-stu-id="0b9b2-111">Network sites</span></span>
- <span data-ttu-id="0b9b2-112">网关配置</span><span class="sxs-lookup"><span data-stu-id="0b9b2-112">Gateway configurations</span></span>
- <span data-ttu-id="0b9b2-113">通话政策</span><span class="sxs-lookup"><span data-stu-id="0b9b2-113">Calling policies</span></span>

<span data-ttu-id="0b9b2-114">你可以使用[Microsoft Team 管理中心](#using-the-microsoft-teams-admin-center)或[PowerShel](#using-powershell)l 启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0b9b2-115">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="0b9b2-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="0b9b2-116">为用户启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0b9b2-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="0b9b2-117">创建语音路由策略，并为策略分配 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="0b9b2-118">将 PSTN 使用分配给策略时，请确保执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="0b9b2-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="0b9b2-119">使用与在本地使用该站点的 PSTN 网关的语音路由相关联的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="0b9b2-120">使用与使用不需要基于位置的路由限制的区域中的 PSTN 网关相关的语音路由的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="0b9b2-121">将 "语音路由策略" 分配给需要强制使用路由限制的用户。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="0b9b2-122">若要了解有关如何创建语音路由策略并将其分配给用户的详细信息，请参阅[管理 Microsoft 团队中的语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="0b9b2-123">为网络站点启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0b9b2-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="0b9b2-124">为需要强制实施路由限制的网站启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="0b9b2-125">若要执行此操作，请在 Microsoft 团队管理中心的左侧导航中，转到 "**位置** > **网络拓扑**"，选择一个网络网站，单击 "**编辑**"，然后打开 "**基于位置的路由**"。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="0b9b2-126">若要了解详细信息，请参阅[管理你的网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="0b9b2-127">启用网关的基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0b9b2-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="0b9b2-128">支持将呼叫路由到将呼叫路由到 PSTN 的 PSTN 网关的基于位置的路由，并关联网关所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="0b9b2-129">在左侧导航中，转到 "**语音** > **直接路由**"，然后单击 " **SBCs** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="0b9b2-130">选择 SBC，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="0b9b2-131">在 "**基于位置的路由和媒体优化**" 下，打开 "**启用基于位置的路由**"。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="0b9b2-132">指定网关站点 ID，然后设置绕过模式。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="0b9b2-133">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="0b9b2-134">为呼叫策略启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0b9b2-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="0b9b2-135">若要为特定用户强制执行基于位置的路由，请设置用户的呼叫策略以防止 PSTN 免绕过。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="0b9b2-136">若要执行此操作，请在呼叫策略中启用 "**阻止收费跳过**" 设置。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="0b9b2-137">若要了解详细信息，请参阅[在团队中调用策略](teams-calling-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="0b9b2-138">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b9b2-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="0b9b2-139">为用户启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0b9b2-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="0b9b2-140">使用[CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) CMDLET 设置 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="0b9b2-141">对于多种用途，用逗号分隔每个用法。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="0b9b2-142">例如：</span><span class="sxs-lookup"><span data-stu-id="0b9b2-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="0b9b2-143">使用[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 创建语音路由策略，以将用户与适当的 PSTN 用法关联起来。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="0b9b2-144">将 PSTN 使用分配给语音路由策略时，请确保执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="0b9b2-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="0b9b2-145">使用与使用网站本地的 PSTN 网关的语音路由相关联的 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="0b9b2-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="0b9b2-146">使用与使用不需要基于位置的路由限制的区域中的 PSTN 网关相关的语音路由的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="0b9b2-147">在此示例中，我们将创建两个新的语音路由策略，并向其分配 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="0b9b2-148">下表显示了本示例中定义的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="0b9b2-149">语音路由策略1</span><span class="sxs-lookup"><span data-stu-id="0b9b2-149">Voice routing policy 1</span></span>|<span data-ttu-id="0b9b2-150">语音路由策略2</span><span class="sxs-lookup"><span data-stu-id="0b9b2-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="0b9b2-151">在线语音政策 ID</span><span class="sxs-lookup"><span data-stu-id="0b9b2-151">Online voice policy ID</span></span>   |<span data-ttu-id="0b9b2-152">新德里 online 语音路由策略</span><span class="sxs-lookup"><span data-stu-id="0b9b2-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="0b9b2-153">Hyderabad online 语音路由策略</span><span class="sxs-lookup"><span data-stu-id="0b9b2-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="0b9b2-154">联机 PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="0b9b2-154">Online PSTN usages</span></span>  |<span data-ttu-id="0b9b2-155">长途</span><span class="sxs-lookup"><span data-stu-id="0b9b2-155">Long Distance</span></span>  |<span data-ttu-id="0b9b2-156">长途、本地、内部</span><span class="sxs-lookup"><span data-stu-id="0b9b2-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="0b9b2-157">使用[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet 将联机语音路由策略与需要执行路由限制的用户相关联。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="0b9b2-158">为网络站点启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0b9b2-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="0b9b2-159">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) Cmdlet 启用基于位置的路由，并将语音路由策略与你的网络站点进行关联，以强制执行路由限制。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="0b9b2-160">在此示例中，我们为新德里网站和 Hyderabad 网站启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="0b9b2-161">下表显示了在此示例中为基于位置的路由启用的网站。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="0b9b2-162">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="0b9b2-163">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="0b9b2-164">站点名称</span><span class="sxs-lookup"><span data-stu-id="0b9b2-164">Site name</span></span>    |<span data-ttu-id="0b9b2-165">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="0b9b2-166">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="0b9b2-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="0b9b2-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="0b9b2-168">True</span><span class="sxs-lookup"><span data-stu-id="0b9b2-168">True</span></span>    |<span data-ttu-id="0b9b2-169">True</span><span class="sxs-lookup"><span data-stu-id="0b9b2-169">True</span></span>    |
    |<span data-ttu-id="0b9b2-170">子网</span><span class="sxs-lookup"><span data-stu-id="0b9b2-170">Subnets</span></span>     |<span data-ttu-id="0b9b2-171">子网1（新德里）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="0b9b2-172">子网2（Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="0b9b2-173">启用网关的基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0b9b2-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="0b9b2-174">使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet 为每个网关或网络网站创建网关配置。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="0b9b2-175">如果多个网关与系统（例如网关或 PBX）相关联，请修改每个网关以启用基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="0b9b2-176">在此示例中，我们为每个网关创建一个网关配置。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="0b9b2-177">有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="0b9b2-178">使用[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet 为你的网关启用需要强制使用路由限制的基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="0b9b2-179">支持将呼叫路由到将呼叫路由到 PSTN 的 PSTN 网关的基于位置的路由，并关联网关所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="0b9b2-180">在此示例中，我们为与新德里和 Hyderabad 网站中的 PSTN 网关相关联的每个网关启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="0b9b2-181">不要为不将调用路由到 PSTN 的网关启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="0b9b2-182">但是，您仍然必须将网关与系统所在的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="0b9b2-183">这是因为基于位置的路由限制需要强制实施 PSTN 呼叫，从而达到通过此网关连接的终结点。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="0b9b2-184">在此示例中，没有为与新德里和 Hyderabad 网站中的 PBX 系统相关联的每个网关启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="0b9b2-185">连接到不路由到 PSTN 的系统的终结点（例如，PBX）将具有类似于为基于位置的路由启用的团队用户的终结点的限制。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-185">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="0b9b2-186">这意味着，无论用户的位置如何，这些用户都可以与团队用户进行呼叫和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-186">This means that these users can place and receive calls to and from Teams users regardless of the user's location.</span></span> <span data-ttu-id="0b9b2-187">他们还可以在不将呼叫路由到 PSTN 网络的其他系统（例如，连接到其他 PBX 的终结点）的情况下与其他系统进行呼叫和接收呼叫，而不管与系统关联的网络站点。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-187">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="0b9b2-188">所有入站呼叫、出站呼叫、呼叫转移以及涉及 PSTN 终结点的呼叫转移将受到基于位置的路由 enforcements。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-188">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="0b9b2-189">这些调用必须仅使用定义为此类系统本地的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-189">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="0b9b2-190">下表显示两个不同网络站点中的四个网关的网关配置：两个连接到 PSTN 网关的两个网关和连接到 PBX 系统的两个。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-190">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="0b9b2-191">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="0b9b2-191">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="0b9b2-192">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="0b9b2-192">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="0b9b2-193">PstnGateway：网关 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="0b9b2-193">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="0b9b2-194">True</span><span class="sxs-lookup"><span data-stu-id="0b9b2-194">True</span></span>     |   <span data-ttu-id="0b9b2-195">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-195">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="0b9b2-196">PstnGateway：网关 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="0b9b2-196">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="0b9b2-197">True</span><span class="sxs-lookup"><span data-stu-id="0b9b2-197">True</span></span>      |      <span data-ttu-id="0b9b2-198">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-198">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="0b9b2-199">PstnGateway：网关 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="0b9b2-199">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="0b9b2-200">False</span><span class="sxs-lookup"><span data-stu-id="0b9b2-200">False</span></span>     |     <span data-ttu-id="0b9b2-201">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-201">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="0b9b2-202">PstnGateway：网关 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="0b9b2-202">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="0b9b2-203">False</span><span class="sxs-lookup"><span data-stu-id="0b9b2-203">False</span></span>     |    <span data-ttu-id="0b9b2-204">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="0b9b2-204">Site 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="0b9b2-205">为呼叫策略启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0b9b2-205">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="0b9b2-206">若要为特定用户强制执行基于位置的路由，请设置用户的语音策略，以防止 PTSN 收费旁路。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-206">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="0b9b2-207">通过阻止 PSTN 免绕过，使用[CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Cmdlet 启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-207">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="0b9b2-208">在此示例中，我们将阻止 PSTN 免绕过 User1's 呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="0b9b2-208">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="0b9b2-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="0b9b2-209">Related topics</span></span>

- [<span data-ttu-id="0b9b2-210">团队中云语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="0b9b2-210">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
