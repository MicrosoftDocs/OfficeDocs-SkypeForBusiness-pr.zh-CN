---
title: Lync Server 2013：会议的基于位置的路由要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a5e97ed5e762b35489eac0b69fbfcad45a8e822
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="8380d-102">Lync Server 2013 中对会议的基于位置的路由的要求</span><span class="sxs-lookup"><span data-stu-id="8380d-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8380d-103">_**上次修改的主题：** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="8380d-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="8380d-104">以下是安装和配置基于位置的路由会议应用程序所需的要求：</span><span class="sxs-lookup"><span data-stu-id="8380d-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="8380d-105">Lync Server 2013 累积更新2必须部署在拓扑中的所有服务器或池上。</span><span class="sxs-lookup"><span data-stu-id="8380d-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8380d-106">如果拓扑中的 Lync server 或池未安装 Lync Server 2013 累积更新2或更高版本，则不能保证 Lync 会议的基于位置的路由的强制执行。</span><span class="sxs-lookup"><span data-stu-id="8380d-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="8380d-107">Lync Server 2013 基于位置的路由是基于位置的路由会议应用程序的预备项。</span><span class="sxs-lookup"><span data-stu-id="8380d-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="8380d-108">有关配置 Lync Server 2013 基于位置的路由的详细信息，请参阅[配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="8380d-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="8380d-109">基于位置的路由会议应用程序的要求与 Lync Server 2013 基于位置的路由的要求相同。</span><span class="sxs-lookup"><span data-stu-id="8380d-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="8380d-110">有关详细信息，请参阅[规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="8380d-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="8380d-111">支持的服务器</span><span class="sxs-lookup"><span data-stu-id="8380d-111">Supported Servers</span></span>

<span data-ttu-id="8380d-112">基于位置的路由会议应用程序要求在拓扑中的所有前端池和 Standard Edition 服务器上部署 Lync Server 2013 累积更新2。</span><span class="sxs-lookup"><span data-stu-id="8380d-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="8380d-113">如果您的拓扑中的某些 Lync 服务器上未安装 Lync Server 2013 累积更新2，则不能在 Lync 会议和咨询呼叫转移上完全强制实施基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="8380d-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="8380d-114">下表标识了支持基于位置的路由的服务器角色和版本的组合。</span><span class="sxs-lookup"><span data-stu-id="8380d-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8380d-115">前端池版本</span><span class="sxs-lookup"><span data-stu-id="8380d-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="8380d-116">中介服务器版本</span><span class="sxs-lookup"><span data-stu-id="8380d-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="8380d-117">支持</span><span class="sxs-lookup"><span data-stu-id="8380d-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8380d-118">Lync Server 2013 累积更新2</span><span class="sxs-lookup"><span data-stu-id="8380d-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="8380d-119">Lync Server 2013 累积更新2</span><span class="sxs-lookup"><span data-stu-id="8380d-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="8380d-120">是</span><span class="sxs-lookup"><span data-stu-id="8380d-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8380d-121">Lync Server 2013 累积更新2</span><span class="sxs-lookup"><span data-stu-id="8380d-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="8380d-122">Lync Server 2013 累积更新1</span><span class="sxs-lookup"><span data-stu-id="8380d-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="8380d-123">否</span><span class="sxs-lookup"><span data-stu-id="8380d-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8380d-124">Lync Server 2013 累积更新2</span><span class="sxs-lookup"><span data-stu-id="8380d-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="8380d-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8380d-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="8380d-126">否</span><span class="sxs-lookup"><span data-stu-id="8380d-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8380d-127">Lync Server 2013 累积更新2</span><span class="sxs-lookup"><span data-stu-id="8380d-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="8380d-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8380d-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="8380d-129">否</span><span class="sxs-lookup"><span data-stu-id="8380d-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8380d-130">Lync Server 2013 累积更新1</span><span class="sxs-lookup"><span data-stu-id="8380d-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="8380d-131">任意</span><span class="sxs-lookup"><span data-stu-id="8380d-131">Any</span></span></p></td>
<td><p><span data-ttu-id="8380d-132">否</span><span class="sxs-lookup"><span data-stu-id="8380d-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8380d-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8380d-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="8380d-134">任意</span><span class="sxs-lookup"><span data-stu-id="8380d-134">Any</span></span></p></td>
<td><p><span data-ttu-id="8380d-135">否</span><span class="sxs-lookup"><span data-stu-id="8380d-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8380d-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8380d-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="8380d-137">任意</span><span class="sxs-lookup"><span data-stu-id="8380d-137">Any</span></span></p></td>
<td><p><span data-ttu-id="8380d-138">否</span><span class="sxs-lookup"><span data-stu-id="8380d-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="8380d-139">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="8380d-139">Supported Clients</span></span>

<span data-ttu-id="8380d-140">支持 Lync 会议的基于位置的路由的 Lync 客户端是支持 Lync Server 2013 基于位置的路由的相同客户端。</span><span class="sxs-lookup"><span data-stu-id="8380d-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="8380d-141">有关详细信息，请参阅[客户端和服务器支持以获取基于位置的路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="8380d-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="8380d-142">咨询呼叫转移的中介服务器要求</span><span class="sxs-lookup"><span data-stu-id="8380d-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="8380d-143">基于位置的路由会议应用程序需要部署独立中介服务器，以便在咨询呼叫转移上强制实施基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="8380d-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="8380d-144">若要强制实施咨询呼叫转移的基于位置的路由，中介服务器必须仅与需要基于位置的路由的网络区域中的一个中介服务器对等方（即 PBX、SIP 网关等）相关联。</span><span class="sxs-lookup"><span data-stu-id="8380d-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="8380d-145">如果在同一网络区域中部署其他中介服务器对等方，则必须将中介服务器对等方与不同的中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="8380d-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="8380d-146">此要求的详细说明如下：</span><span class="sxs-lookup"><span data-stu-id="8380d-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="8380d-147">每台中介服务器对等台中介服务器：当通过配置了多个 SIP 中继的中介服务器将咨询呼叫转移路由到中介服务器对等方（即 Pbx 和网关）时，咨询如果允许通过某些 SIP 中继进行咨询呼叫转接，但不允许通过其他 SIP 中继，则呼叫转接被阻止，以防止 PSTN 收费旁路。</span><span class="sxs-lookup"><span data-stu-id="8380d-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="8380d-148">例如，在单个中介服务器为 PSTN 网关中介服务器对等方和 PBX 中介服务器对等方提供服务时，将会看到以下行为：</span><span class="sxs-lookup"><span data-stu-id="8380d-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="8380d-149">当来自给定站点（即站点1）的 Lync 用户尝试通过咨询转移转移从其他站点（即 site 2）将带有 PSTN 终结点的呼叫转移到 Lync 用户时，将不允许该呼叫阻止 PSTN 收费旁路。</span><span class="sxs-lookup"><span data-stu-id="8380d-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="8380d-150">当来自给定站点（即站点1）的 Lync 用户尝试将同一站点（站点1）中 PBX 终结点的呼叫转移到来自不同站点（即 site 2）的 Lync 用户时，即使该呼叫不会出现在潜在 PSTN tol 中，也不会允许该呼叫。l 绕过。</span><span class="sxs-lookup"><span data-stu-id="8380d-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="8380d-151">每个中介服务器对等的单独中介服务器</span><span class="sxs-lookup"><span data-stu-id="8380d-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="8380d-152">在面向中介服务器的对等客户端进行咨询转移时，将根据中介服务器提供服务的单个中介服务器对来评估咨询转移。</span><span class="sxs-lookup"><span data-stu-id="8380d-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="8380d-153">根据不同中介服务器提供服务中的所有其他 Mediations 服务器等方，此呼叫将因其在 PSTN 收费旁路中的潜在情况而不允许或允许出现。</span><span class="sxs-lookup"><span data-stu-id="8380d-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="8380d-154">例如，在单独的中介服务器为 PSTN 网关中介服务器对等方和 PBX 中介服务器对等方提供服务时，将会看到以下行为：</span><span class="sxs-lookup"><span data-stu-id="8380d-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="8380d-155">当来自给定站点（即站点1）的 Lync 用户尝试通过咨询转移转移从其他站点（即 site 2）将带有 PSTN 终结点的呼叫转移到 Lync 用户时，将不允许该呼叫阻止 PSTN 收费旁路。</span><span class="sxs-lookup"><span data-stu-id="8380d-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="8380d-156">当来自给定站点（即站点1）的 Lync 用户尝试从另一个站点（站点1）中的 PBX 终结点将呼叫转移到其他站点（即 site 2）上的 Lync 用户时，将允许该呼叫，因为它不会在潜在的 PSTN 收费旁路中产生。ing.</span><span class="sxs-lookup"><span data-stu-id="8380d-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="8380d-157">基于位置的路由会议应用程序不支持的功能</span><span class="sxs-lookup"><span data-stu-id="8380d-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="8380d-158">基于位置的路由会议应用程序不支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="8380d-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="8380d-159">电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="8380d-159">Dial-in conferencing.</span></span> <span data-ttu-id="8380d-160">无法为电话拨入式会议强制实施基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="8380d-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="8380d-161">对给定会议的任何拨入请求不会受到基于位置的路由的限制，即使会议组织者是启用了基于位置的路由的 Lync 用户也是如此。</span><span class="sxs-lookup"><span data-stu-id="8380d-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="8380d-162">建议不要在需要强制实施基于位置的路由限制的区域中设置会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="8380d-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

