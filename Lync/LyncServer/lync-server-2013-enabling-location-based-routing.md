---
title: Lync Server 2013：启用基于位置的路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="a5dd8-102">在 Lync Server 2013 中启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="a5dd8-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5dd8-103">_**主题上次修改时间：** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="a5dd8-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="a5dd8-104">部署企业语音并定义网络区域、网站和子网后，您可以启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="a5dd8-105">必须为以下企业语音元素启用基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="a5dd8-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="a5dd8-106">网络站点</span><span class="sxs-lookup"><span data-stu-id="a5dd8-106">Network sites</span></span>

  - <span data-ttu-id="a5dd8-107">中继配置</span><span class="sxs-lookup"><span data-stu-id="a5dd8-107">Trunk configurations</span></span>

  - <span data-ttu-id="a5dd8-108">语音策略</span><span class="sxs-lookup"><span data-stu-id="a5dd8-108">Voice policies</span></span>

  - <span data-ttu-id="a5dd8-109">路由配置</span><span class="sxs-lookup"><span data-stu-id="a5dd8-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="a5dd8-110">启用到网络站点的基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="a5dd8-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="a5dd8-111">部署企业语音和配置的网络站点后，即可配置基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="a5dd8-112">首先，创建一个语音路由策略，将网络站点与适当的 PSTN 使用情况关联起来。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="a5dd8-113">将 PSTN 使用分配给语音路由策略时，请确保仅使用与在不需要基于位置的路由限制的区域中使用站点或 PSTN 网关的 pstn 网关相关的 PSTN 使用。使用 Lync Server Windows PowerShell 命令、"新建-CsVoiceRoutingPolicy" 或 "Lync Server 控制面板" 创建语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="a5dd8-114">有关更多信息，请参阅 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="a5dd8-115">对于此示例，下表和 Windows PowerShell 命令演示了这种情况下定义的两个语音路由策略及其关联的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="a5dd8-116">只有特定于基于位置的路由的设置才会包含在表中，以便进行图解。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="a5dd8-117">语音路由策略1</span><span class="sxs-lookup"><span data-stu-id="a5dd8-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="a5dd8-118">语音路由策略2</span><span class="sxs-lookup"><span data-stu-id="a5dd8-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5dd8-119">语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="a5dd8-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-120">新德里语音路由策略</span><span class="sxs-lookup"><span data-stu-id="a5dd8-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-121">Hyderabad 语音路由策略</span><span class="sxs-lookup"><span data-stu-id="a5dd8-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5dd8-122">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="a5dd8-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-123">新德里使用，PBX Del 用法，PBX Hyd 用法</span><span class="sxs-lookup"><span data-stu-id="a5dd8-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-124">Hyderabad 使用，PBX Hyd 使用，PBX Del 使用</span><span class="sxs-lookup"><span data-stu-id="a5dd8-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="a5dd8-125">接下来，为适用的网络网站配置基于位置的路由，并将你的语音路由策略关联到它们。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="a5dd8-126">使用 Lync Server Windows PowerShell 命令 CsNetworkSite，可启用基于位置的路由，并将语音路由策略与您的网络站点进行关联，这些站点必须实施路由限制。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="a5dd8-127">在此示例中，下表介绍了使用 Lync Server Windows PowerShell 在此方案中定义的两个不同网络站点、新德里和 Hyderabad 的基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="a5dd8-128">只有特定于基于位置的路由的设置才会包含在表中，以便进行图解。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="a5dd8-129">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="a5dd8-130">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5dd8-131">站点名称</span><span class="sxs-lookup"><span data-stu-id="a5dd8-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-132">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-133">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5dd8-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="a5dd8-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-135">True</span><span class="sxs-lookup"><span data-stu-id="a5dd8-135">True</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-136">True</span><span class="sxs-lookup"><span data-stu-id="a5dd8-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5dd8-137">语音路由策略</span><span class="sxs-lookup"><span data-stu-id="a5dd8-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-138">新德里语音路由策略</span><span class="sxs-lookup"><span data-stu-id="a5dd8-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-139">Hyderabad 语音路由策略</span><span class="sxs-lookup"><span data-stu-id="a5dd8-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5dd8-140">子网</span><span class="sxs-lookup"><span data-stu-id="a5dd8-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-141">子网1（新德里）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-142">子网2（Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="a5dd8-143">支持基于位置的路由到中继</span><span class="sxs-lookup"><span data-stu-id="a5dd8-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="a5dd8-144">在可以为基于位置的路由启用中继配置之前，你需要为每个主干或每个网络站点创建中继配置。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="a5dd8-145">使用 Lync Server Windows PowerShell 命令 New-cstrunkconfiguration 创建中继配置。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="a5dd8-146">如果多个中继与给定系统（即网关或 PBX）相关联，则必须修改每个中继配置以启用基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="a5dd8-147">有关详细信息，请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="a5dd8-148">对于此示例，以下 Windows PowerShell 命令演示了为此方案中定义的部署中的每个主干创建一个 trunk 配置。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="a5dd8-149">每个干线配置了中继配置后，您可以使用 Lync Server Windows PowerShell 命令 New-cstrunkconfiguration，以便为必须强制执行路由限制的中继启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="a5dd8-150">启用到中继的基于位置的路由，将呼叫路由到将呼叫路由到 PSTN 的 PSTN 网关，并关联网关所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="a5dd8-151">有关详细信息，请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="a5dd8-152">在此示例中，为与新德里和 Hyderabad 中的 PSTN 网关相关联的每个干线启用基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="a5dd8-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="a5dd8-153">不要为不将呼叫路由到 PSTN 的中继启用基于位置的路由;但是，你仍然必须将主干与系统所在的网络站点相关联，因为需要针对通过此主干连接的终结点强制执行 PSTN 调用的基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="a5dd8-154">对于此示例，对于与新德里和 Hyderabad 中的 PBX 系统相关联的每个主干，不启用基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="a5dd8-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="a5dd8-155">连接到不将调用路由到 PSTN （即 PBX）的系统的终结点将具有与启用基于位置的路由的用户的 Lync 终结点类似的限制。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="a5dd8-156">这意味着，无论用户的位置如何，这些用户都可以将呼叫放入和接收 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="a5dd8-157">他们还可以将接收呼叫与其他系统进行呼叫，而不是将呼叫路由到 PSTN 网络（即连接到其他 PBX 的终结点），无论与系统关联的网络站点。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="a5dd8-158">涉及 PSTN 终结点的所有入站呼叫、出站呼叫、呼叫转移和呼叫转接将受到基于位置的路由 enforcements。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="a5dd8-159">此类通话只能使用定义为此类系统本地的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="a5dd8-160">下表说明了两个不同网络站点中四个中继的干线配置：两个连接到 PSTN 网关的两个连接和连接到 PBX 系统的两个。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5dd8-161">名称</span><span class="sxs-lookup"><span data-stu-id="a5dd8-161">Name</span></span></th>
<th><span data-ttu-id="a5dd8-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="a5dd8-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="a5dd8-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="a5dd8-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5dd8-164">PstnGateway：干线 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="a5dd8-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-165">True</span><span class="sxs-lookup"><span data-stu-id="a5dd8-165">True</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-166">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5dd8-167">PstnGateway：主干 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="a5dd8-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-168">True</span><span class="sxs-lookup"><span data-stu-id="a5dd8-168">True</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-169">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5dd8-170">PstnGateway：干线 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="a5dd8-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-171">False</span><span class="sxs-lookup"><span data-stu-id="a5dd8-171">False</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-172">站点1（新德里）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5dd8-173">PstnGateway：干线 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="a5dd8-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-174">False</span><span class="sxs-lookup"><span data-stu-id="a5dd8-174">False</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-175">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="a5dd8-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="a5dd8-176">支持基于位置的路由到语音策略</span><span class="sxs-lookup"><span data-stu-id="a5dd8-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="a5dd8-177">若要强制将基于位置的路由到特定用户，请将这些用户的语音策略配置为阻止 PSTN 免绕过。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="a5dd8-178">使用 Lync Server Windows PowerShell 命令 CsVoicePolicy 创建新的语音策略或设置 CsVoicePolicy （如果使用现有策略），以通过阻止 PSTN 免绕过来启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="a5dd8-179">有关详细信息，请参阅[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="a5dd8-180">在此示例中，下表和 Windows PowerShell 命令演示了如何为本方案中定义的 Hyderabad 语音策略启用 PSTN 免绕过保护。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="a5dd8-181">只有特定于基于位置的路由的设置才会包含在表中，以便进行图解。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="a5dd8-182">语音策略1</span><span class="sxs-lookup"><span data-stu-id="a5dd8-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="a5dd8-183">语音政策2</span><span class="sxs-lookup"><span data-stu-id="a5dd8-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5dd8-184">语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="a5dd8-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-185">新德里语音政策</span><span class="sxs-lookup"><span data-stu-id="a5dd8-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-186">Hyderabad 语音政策</span><span class="sxs-lookup"><span data-stu-id="a5dd8-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5dd8-187">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="a5dd8-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-188">新德里使用，PBX Del 用法，PBX Hyd 用法</span><span class="sxs-lookup"><span data-stu-id="a5dd8-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-189">Hyderabad 使用，PBX Hyd 使用，PBX Del 使用</span><span class="sxs-lookup"><span data-stu-id="a5dd8-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5dd8-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="a5dd8-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-191">True</span><span class="sxs-lookup"><span data-stu-id="a5dd8-191">True</span></span></p></td>
<td><p><span data-ttu-id="a5dd8-192">True</span><span class="sxs-lookup"><span data-stu-id="a5dd8-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="a5dd8-193">在路由配置中启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="a5dd8-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="a5dd8-194">最后，全局启用到路由配置的基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="a5dd8-195">使用 Lync Server Windows PowerShell 命令 CsRoutingConfiguration，以启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="a5dd8-196">有关详细信息，请参阅[设置 CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5dd8-197">基于位置的路由必须通过全局配置启用时，将仅针对本文档中指定的网站、用户和中继强制执行要应用的规则集。</span><span class="sxs-lookup"><span data-stu-id="a5dd8-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5dd8-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5dd8-198">See Also</span></span>


[<span data-ttu-id="a5dd8-199">在 Lync Server 2013 中配置基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="a5dd8-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

