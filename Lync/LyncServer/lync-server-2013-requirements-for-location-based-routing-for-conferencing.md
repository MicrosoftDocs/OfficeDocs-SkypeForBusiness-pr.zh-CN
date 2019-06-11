---
title: 'Lync Server 2013: 适用于会议的基于位置的路由的要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 925b71497012d7e6ed9c19042a079a7b30630c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="08dfb-102">Lync Server 2013 中基于位置的会议路由的要求</span><span class="sxs-lookup"><span data-stu-id="08dfb-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08dfb-103">_**主题上次修改时间:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="08dfb-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="08dfb-104">以下是安装和配置基于位置的路由会议应用程序所需的要求:</span><span class="sxs-lookup"><span data-stu-id="08dfb-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="08dfb-105">Lync Server 2013 累积更新2必须部署在拓扑中的所有服务器或池上。</span><span class="sxs-lookup"><span data-stu-id="08dfb-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08dfb-106">如果拓扑中的 Lync 服务器或池未安装 Lync Server 2013 累积更新2或更高版本, 则不能保证对 Lync 会议的基于位置的路由的强制。</span><span class="sxs-lookup"><span data-stu-id="08dfb-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="08dfb-107">Lync Server 2013 基于位置的路由是基于位置的路由会议应用程序的先决条件。</span><span class="sxs-lookup"><span data-stu-id="08dfb-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="08dfb-108">有关配置 Lync Server 2013 基于位置的路由的详细信息, 请参阅[配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="08dfb-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="08dfb-109">基于位置的路由会议应用程序的要求与 Lync Server 2013 基于位置的路由的要求相同。</span><span class="sxs-lookup"><span data-stu-id="08dfb-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="08dfb-110">有关详细信息, 请参阅[规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="08dfb-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="08dfb-111">支持的服务器</span><span class="sxs-lookup"><span data-stu-id="08dfb-111">Supported Servers</span></span>

<span data-ttu-id="08dfb-112">基于位置的路由会议应用程序要求在拓扑中的所有前端池和标准版服务器上部署 Lync Server 2013 累积更新2。</span><span class="sxs-lookup"><span data-stu-id="08dfb-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="08dfb-113">如果您的拓扑中的某些 Lync 服务器上未安装 Lync Server 2013 累积更新 2, 基于位置的路由限制不能在 Lync 会议和咨询式呼叫转移上完全强制实施。</span><span class="sxs-lookup"><span data-stu-id="08dfb-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="08dfb-114">下表标识了支持基于位置的路由的服务器角色和版本的组合。</span><span class="sxs-lookup"><span data-stu-id="08dfb-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08dfb-115">前端池版本</span><span class="sxs-lookup"><span data-stu-id="08dfb-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="08dfb-116">中介服务器版本</span><span class="sxs-lookup"><span data-stu-id="08dfb-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="08dfb-117">支持</span><span class="sxs-lookup"><span data-stu-id="08dfb-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dfb-118">Lync Server 2013 累积更新 2</span><span class="sxs-lookup"><span data-stu-id="08dfb-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="08dfb-119">Lync Server 2013 累积更新 2</span><span class="sxs-lookup"><span data-stu-id="08dfb-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="08dfb-120">是</span><span class="sxs-lookup"><span data-stu-id="08dfb-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08dfb-121">Lync Server 2013 累积更新 2</span><span class="sxs-lookup"><span data-stu-id="08dfb-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="08dfb-122">Lync Server 2013 累积更新 1</span><span class="sxs-lookup"><span data-stu-id="08dfb-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="08dfb-123">否</span><span class="sxs-lookup"><span data-stu-id="08dfb-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dfb-124">Lync Server 2013 累积更新 2</span><span class="sxs-lookup"><span data-stu-id="08dfb-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="08dfb-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="08dfb-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="08dfb-126">否</span><span class="sxs-lookup"><span data-stu-id="08dfb-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08dfb-127">Lync Server 2013 累积更新 2</span><span class="sxs-lookup"><span data-stu-id="08dfb-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="08dfb-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="08dfb-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="08dfb-129">否</span><span class="sxs-lookup"><span data-stu-id="08dfb-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dfb-130">Lync Server 2013 累积更新 1</span><span class="sxs-lookup"><span data-stu-id="08dfb-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="08dfb-131">任意</span><span class="sxs-lookup"><span data-stu-id="08dfb-131">Any</span></span></p></td>
<td><p><span data-ttu-id="08dfb-132">否</span><span class="sxs-lookup"><span data-stu-id="08dfb-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08dfb-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="08dfb-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="08dfb-134">任意</span><span class="sxs-lookup"><span data-stu-id="08dfb-134">Any</span></span></p></td>
<td><p><span data-ttu-id="08dfb-135">否</span><span class="sxs-lookup"><span data-stu-id="08dfb-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dfb-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="08dfb-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="08dfb-137">任意</span><span class="sxs-lookup"><span data-stu-id="08dfb-137">Any</span></span></p></td>
<td><p><span data-ttu-id="08dfb-138">否</span><span class="sxs-lookup"><span data-stu-id="08dfb-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="08dfb-139">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="08dfb-139">Supported Clients</span></span>

<span data-ttu-id="08dfb-140">支持 Lync 会议基于位置路由的 Lync 客户端是支持 Lync Server 2013 基于位置的路由的相同客户。</span><span class="sxs-lookup"><span data-stu-id="08dfb-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="08dfb-141">有关详细信息, 请参阅[客户端和服务器支持以获取基于位置的路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="08dfb-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="08dfb-142">咨询式呼叫转移的中介服务器要求</span><span class="sxs-lookup"><span data-stu-id="08dfb-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="08dfb-143">基于位置的路由会议应用程序需要部署独立的中介服务器, 以便在咨询式呼叫转移上强制使用基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="08dfb-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="08dfb-144">若要强制执行基于位置的咨询呼叫转移路由, 中介服务器只能与需要基于位置的路由的网络区域中的一个中介服务器对等 (如 PBX、SIP 网关等) 相关联。</span><span class="sxs-lookup"><span data-stu-id="08dfb-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="08dfb-145">如果在同一网络区域中部署其他中介服务器对等, 则中介服务器必须与不同的中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="08dfb-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="08dfb-146">此要求的详细信息如下:</span><span class="sxs-lookup"><span data-stu-id="08dfb-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="08dfb-147">每台多个中介服务器对等的单中介服务器当通过将多个 SIP 中继配置为多个对等 (即 Pbx 和网关) 的中介服务器将咨询呼叫转移路由到中介服务器对等如果通过某些 SIP 中继允许咨询呼叫转接, 但禁止通过其他 SIP 中继, 则呼叫转接被阻止, 以防止 PSTN 长途电话旁路。</span><span class="sxs-lookup"><span data-stu-id="08dfb-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="08dfb-148">例如, 在单个中介服务器处理 PSTN 网关中介服务器对等和 PBX 中介服务器对等的情况下, 将看到以下行为:</span><span class="sxs-lookup"><span data-stu-id="08dfb-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="08dfb-149">当来自给定网站 (即站点 1) 的 Lync 用户尝试通过顾问式转移将具有 PSTN 终结点的呼叫转移到其他网站 (即 site 2) 中的 Lync 用户时, 将禁止呼叫阻止 PSTN 免绕过。</span><span class="sxs-lookup"><span data-stu-id="08dfb-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="08dfb-150">当来自给定网站 (即站点 1) 的 Lync 用户尝试将同一站点 (站点 1) 中的 PBX 终结点与 Lync 用户 (即 site 2) 转移到来自另一个网站 (即 site 2) 的 Lync 用户时, 即使不是在潜在的 PSTN tol 中, 也将禁止呼叫。l 忽略。</span><span class="sxs-lookup"><span data-stu-id="08dfb-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="08dfb-151">每个中介服务器对等单独的中介服务器</span><span class="sxs-lookup"><span data-stu-id="08dfb-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="08dfb-152">当向中介服务器对等进行定向传输时, 将根据中介服务器提供服务的单个中介服务器对来评估咨询转移。</span><span class="sxs-lookup"><span data-stu-id="08dfb-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="08dfb-153">无论其他 Mediations 服务器在不同的中介服务器中提供服务, 该呼叫都将在 PSTN 免绕过的可能性内被禁止或允许使用。</span><span class="sxs-lookup"><span data-stu-id="08dfb-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="08dfb-154">例如, 在单独的中介服务器处理 PSTN 网关中介服务器对等和 PBX 中介服务器对等的情况下, 将看到以下行为:</span><span class="sxs-lookup"><span data-stu-id="08dfb-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="08dfb-155">当来自给定网站 (即站点 1) 的 Lync 用户尝试通过顾问式转移将具有 PSTN 终结点的呼叫转移到其他网站 (即 site 2) 中的 Lync 用户时, 将禁止呼叫阻止 PSTN 免绕过。</span><span class="sxs-lookup"><span data-stu-id="08dfb-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="08dfb-156">当来自给定网站 (即站点 1) 的 Lync 用户尝试将同一站点 (站点 1) 中的 PBX 终结点与 Lync 用户 (即 site 2) 从咨询转移转移到其他网站 (即 site 2) 上的 lync 用户时, 将允许进行呼叫, 因为它不会在潜在的 PSTN 免绕过&.</span><span class="sxs-lookup"><span data-stu-id="08dfb-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="08dfb-157">基于位置的路由会议应用程序不支持的功能</span><span class="sxs-lookup"><span data-stu-id="08dfb-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="08dfb-158">基于位置的路由会议应用程序不支持以下功能:</span><span class="sxs-lookup"><span data-stu-id="08dfb-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="08dfb-159">电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="08dfb-159">Dial-in conferencing.</span></span> <span data-ttu-id="08dfb-160">不能为电话拨入式会议强制使用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="08dfb-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="08dfb-161">对给定会议的任何拨入请求不会受到基于位置的路由限制, 即使会议组织者是启用了基于位置的路由的 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="08dfb-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="08dfb-162">建议在需要强制实施基于位置的路由限制的区域中设置会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="08dfb-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

