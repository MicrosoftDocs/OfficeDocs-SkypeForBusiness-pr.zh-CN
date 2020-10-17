---
title: Lync Server 2013：启用 Location-Based 路由
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
ms.openlocfilehash: 1ab22ffdfc47f390671f2bf66ea76dd734aaa128
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500969"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="1896c-102">在 Lync Server 2013 中启用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="1896c-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1896c-103">_**上次修改的主题：** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="1896c-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="1896c-104">部署企业语音并定义网络区域、站点和子网之后，您可以启用 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="1896c-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="1896c-105">必须为以下 Enterprise Voice 元素启用 Location-Based 路由：</span><span class="sxs-lookup"><span data-stu-id="1896c-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="1896c-106">网络站点</span><span class="sxs-lookup"><span data-stu-id="1896c-106">Network sites</span></span>

  - <span data-ttu-id="1896c-107">中继配置</span><span class="sxs-lookup"><span data-stu-id="1896c-107">Trunk configurations</span></span>

  - <span data-ttu-id="1896c-108">语音策略</span><span class="sxs-lookup"><span data-stu-id="1896c-108">Voice policies</span></span>

  - <span data-ttu-id="1896c-109">路由配置</span><span class="sxs-lookup"><span data-stu-id="1896c-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="1896c-110">启用到网络站点的 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="1896c-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="1896c-111">部署企业语音和配置的网络站点后，即可配置 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="1896c-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="1896c-112">首先，创建语音路由策略以将网络站点与适当的 PSTN 用法关联起来。</span><span class="sxs-lookup"><span data-stu-id="1896c-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="1896c-113">为语音路由策略分配 PSTN 用法时，请确保仅使用与使用站点的 PSTN 网关或 PSTN 网关（位于不需要 Location-Based 路由限制的区域）的语音路由相关联的 PSTN 用法。使用 Lync Server Windows PowerShell 命令 "Grant-csvoiceroutingpolicy" 或 "Lync Server 控制面板" 创建语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="1896c-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="1896c-114">有关详细信息，请参阅 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)。</span><span class="sxs-lookup"><span data-stu-id="1896c-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="1896c-115">对于此示例，下表和 Windows PowerShell 命令说明了在此方案中定义的两种语音路由策略及其关联 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="1896c-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="1896c-116">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="1896c-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="1896c-117">语音路由策略1</span><span class="sxs-lookup"><span data-stu-id="1896c-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="1896c-118">语音路由策略2</span><span class="sxs-lookup"><span data-stu-id="1896c-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1896c-119">语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="1896c-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="1896c-120">新德里语音路由策略</span><span class="sxs-lookup"><span data-stu-id="1896c-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="1896c-121">Hyderabad 语音路由策略</span><span class="sxs-lookup"><span data-stu-id="1896c-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1896c-122">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="1896c-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="1896c-123">新德里使用，PBX Del 用法，PBX Hyd 用法</span><span class="sxs-lookup"><span data-stu-id="1896c-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="1896c-124">Hyderabad 用法，PBX Hyd usage，PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="1896c-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="1896c-125">接下来，为相应的网络站点配置 Location-Based 路由，并将您的语音路由策略关联到它们。</span><span class="sxs-lookup"><span data-stu-id="1896c-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="1896c-126">使用 Lync Server Windows PowerShell 命令 CsNetworkSite，启用 Location-Based 路由，并将语音路由策略与必须强制实施路由限制的网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="1896c-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="1896c-127">在此示例中，下表说明了使用 Lync Server Windows PowerShell 在此方案中定义的两个不同网络站点（Hyderabad 和）的 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="1896c-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="1896c-128">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="1896c-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="1896c-129">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="1896c-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="1896c-130">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="1896c-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1896c-131">网站名称</span><span class="sxs-lookup"><span data-stu-id="1896c-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="1896c-132">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="1896c-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="1896c-133">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="1896c-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1896c-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="1896c-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="1896c-135">True</span><span class="sxs-lookup"><span data-stu-id="1896c-135">True</span></span></p></td>
<td><p><span data-ttu-id="1896c-136">True</span><span class="sxs-lookup"><span data-stu-id="1896c-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1896c-137">语音路由策略</span><span class="sxs-lookup"><span data-stu-id="1896c-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="1896c-138">新德里语音路由策略</span><span class="sxs-lookup"><span data-stu-id="1896c-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="1896c-139">Hyderabad 语音路由策略</span><span class="sxs-lookup"><span data-stu-id="1896c-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1896c-140">子网</span><span class="sxs-lookup"><span data-stu-id="1896c-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="1896c-141">Subnet 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="1896c-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="1896c-142">Subnet 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="1896c-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="1896c-143">启用到中继的 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="1896c-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="1896c-144">在可以为 Location-Based 路由启用中继配置之前，您需要为每个中继或每个网络站点创建中继配置。</span><span class="sxs-lookup"><span data-stu-id="1896c-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="1896c-145">使用 Lync Server Windows PowerShell 命令 Remove-cstrunkconfiguration，创建中继配置。</span><span class="sxs-lookup"><span data-stu-id="1896c-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="1896c-146">如果多个中继与给定系统相关联 (即 Gateway 或 PBX) ，则必须修改每个中继配置，以启用 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="1896c-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="1896c-147">有关详细信息，请参阅 [remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="1896c-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="1896c-148">对于此示例，以下 Windows PowerShell 命令说明了如何为此方案中定义的部署中的每个中继创建一个中继配置。</span><span class="sxs-lookup"><span data-stu-id="1896c-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="1896c-149">一旦每个中继配置了中继配置，您就可以使用 Lync Server Windows PowerShell 命令 Remove-cstrunkconfiguration，以启用到必须强制执行路由限制的中继的 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="1896c-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="1896c-150">Location-Based 启用到中继的路由，将呼叫路由到将呼叫路由到 PSTN 网关的 PSTN 网关，并将该网关所在的网络站点关联起来。</span><span class="sxs-lookup"><span data-stu-id="1896c-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="1896c-151">有关详细信息，请参阅 [remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="1896c-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="1896c-152">在此示例中，将为与在新德里和 Hyderabad 中的 PSTN 网关关联的每个中继启用 Location-Based 路由：</span><span class="sxs-lookup"><span data-stu-id="1896c-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="1896c-153">请勿为不将呼叫路由到 PSTN 的中继启用 Location-Based 路由;但是，仍必须将中继与系统所在的网络站点相关联，以便在到达通过此中继连接的终结点的 PSTN 呼叫时，需要强制实施 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="1896c-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="1896c-154">对于此示例，对于与在新德里和 Hyderabad 中的 PBX 系统相关联的每个中继，不启用 Location-Based 路由：</span><span class="sxs-lookup"><span data-stu-id="1896c-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="1896c-155">连接到不将呼叫路由到 PSTN 的系统的终结点 (即 PBX) 的限制与启用了 Location-Based 路由的用户的 Lync 终结点的类似限制。</span><span class="sxs-lookup"><span data-stu-id="1896c-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="1896c-156">这意味着，无论用户的位置如何，这些用户都将能够在 Lync 用户处呼叫和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="1896c-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="1896c-157">他们还可以在不将呼叫路由到 PSTN (网络的其他系统（即连接到不同) PBX 的终结点，无论与系统关联的网络站点）之间进行接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="1896c-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="1896c-158">涉及 PSTN 终结点的所有入站呼叫、出站呼叫、呼叫转移和呼叫转接将受 Location-Based 路由之后。</span><span class="sxs-lookup"><span data-stu-id="1896c-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="1896c-159">此类呼叫必须仅使用定义为此类系统的本地的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="1896c-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="1896c-160">下表说明了两个不同网络站点中四个中继的中继配置：两个连接到 PSTN 网关的两个网络站点，以及两个连接到 PBX 系统的站点。</span><span class="sxs-lookup"><span data-stu-id="1896c-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1896c-161">名称</span><span class="sxs-lookup"><span data-stu-id="1896c-161">Name</span></span></th>
<th><span data-ttu-id="1896c-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="1896c-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="1896c-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="1896c-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1896c-164">为 pstngateway：中继 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="1896c-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="1896c-165">True</span><span class="sxs-lookup"><span data-stu-id="1896c-165">True</span></span></p></td>
<td><p><span data-ttu-id="1896c-166">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="1896c-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1896c-167">为 pstngateway： Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="1896c-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="1896c-168">True</span><span class="sxs-lookup"><span data-stu-id="1896c-168">True</span></span></p></td>
<td><p><span data-ttu-id="1896c-169">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="1896c-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1896c-170">为 pstngateway： Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="1896c-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="1896c-171">False</span><span class="sxs-lookup"><span data-stu-id="1896c-171">False</span></span></p></td>
<td><p><span data-ttu-id="1896c-172">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="1896c-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1896c-173">为 pstngateway： Trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="1896c-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="1896c-174">False</span><span class="sxs-lookup"><span data-stu-id="1896c-174">False</span></span></p></td>
<td><p><span data-ttu-id="1896c-175">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="1896c-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="1896c-176">启用 Location-Based 路由到语音策略</span><span class="sxs-lookup"><span data-stu-id="1896c-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="1896c-177">若要强制 Location-Based 路由到特定用户，请将这些用户的语音策略配置为阻止 PSTN 收费旁路。</span><span class="sxs-lookup"><span data-stu-id="1896c-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="1896c-178">使用 Lync Server Windows PowerShell 命令 Set-csvoicepolicy，创建新的语音策略或 Set-csvoicepolicy （如果使用现有策略），通过防止 PSTN 收费旁路来启用 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="1896c-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="1896c-179">有关详细信息，请参阅 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)。</span><span class="sxs-lookup"><span data-stu-id="1896c-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="1896c-180">对于此示例，下表和 Windows PowerShell 命令说明了如何防止对此方案中定义的新德里和 Hyderabad 语音策略禁止 PSTN 收费旁路。</span><span class="sxs-lookup"><span data-stu-id="1896c-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="1896c-181">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="1896c-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="1896c-182">语音策略1</span><span class="sxs-lookup"><span data-stu-id="1896c-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="1896c-183">语音策略2</span><span class="sxs-lookup"><span data-stu-id="1896c-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1896c-184">语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="1896c-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="1896c-185">新德里语音策略</span><span class="sxs-lookup"><span data-stu-id="1896c-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="1896c-186">Hyderabad 语音策略</span><span class="sxs-lookup"><span data-stu-id="1896c-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1896c-187">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="1896c-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="1896c-188">新德里使用，PBX Del 用法，PBX Hyd 用法</span><span class="sxs-lookup"><span data-stu-id="1896c-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="1896c-189">Hyderabad 用法，PBX Hyd usage，PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="1896c-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1896c-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="1896c-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="1896c-191">True</span><span class="sxs-lookup"><span data-stu-id="1896c-191">True</span></span></p></td>
<td><p><span data-ttu-id="1896c-192">True</span><span class="sxs-lookup"><span data-stu-id="1896c-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="1896c-193">在路由配置中启用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="1896c-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="1896c-194">最后，全局启用 Location-Based 路由到您的路由配置。</span><span class="sxs-lookup"><span data-stu-id="1896c-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="1896c-195">使用 Lync Server Windows PowerShell 命令 CsRoutingConfiguration，启用 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="1896c-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="1896c-196">有关详细信息，请参阅 [CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="1896c-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1896c-197">虽然必须通过全局配置启用 Location-Based 路由，但只会对要应用的一组规则强制实施此文档中为其配置的网站、用户和中继。</span><span class="sxs-lookup"><span data-stu-id="1896c-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1896c-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1896c-198">See Also</span></span>


[<span data-ttu-id="1896c-199">在 Lync Server 2013 中配置 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="1896c-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

