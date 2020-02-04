---
title: Lync Server 2013：选择拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="955e7-102">在 Lync Server 2013 中选择拓扑</span><span class="sxs-lookup"><span data-stu-id="955e7-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="955e7-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="955e7-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="955e7-104">选择拓扑时，可以使用以下受支持的拓扑选项之一：</span><span class="sxs-lookup"><span data-stu-id="955e7-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="955e7-105">除非另有说明，否则，如果你有 Microsoft Lync Server 2010 的体验，你将在此处发现指南，这主要是未更改的。</span><span class="sxs-lookup"><span data-stu-id="955e7-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="955e7-106">Lync Server 2013 中使用专用 IP 地址和 NAT 的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="955e7-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="955e7-107">Lync Server 2013 中使用公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="955e7-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="955e7-108">Lync Server 2013 中的扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="955e7-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="955e7-109">Lync Server 2013 中的扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="955e7-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="955e7-110">Lync Server 2013 中使用硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="955e7-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="955e7-111">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="955e7-111">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="955e7-112">您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="955e7-112">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="955e7-113">下表总结了支持的 Microsoft Lync Server 2013 拓扑的可用功能。</span><span class="sxs-lookup"><span data-stu-id="955e7-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="955e7-114">列标题指示给定的边缘配置选项可用的功能。</span><span class="sxs-lookup"><span data-stu-id="955e7-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="955e7-115">使用缩放的边缘（DNS 负载平衡）选项作为示例，你可以看到它支持高可用性，可以使用无法路由的专用 IP 地址（带有 NAT），也可以使用分配给 Edge 外部接口的可路由的公共 IP 地址，从而降低成本，因为不需要硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="955e7-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="955e7-116">DNS 负载平衡支持的边缘故障切换方案是 Lync 到 Lync 的点到点会话、Lync 会议会话、Lync 到 PSTN 会话和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="955e7-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="955e7-117">对于远程用户 Exchange 统一消息（UM）（在 Exchange 2010 SP1 之前）、公共即时消息（IM）连接和与运行 Office 通信的服务器之间的联盟，不能受益的边缘故障切换方案服务.</span><span class="sxs-lookup"><span data-stu-id="955e7-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="955e7-118">边缘服务器拓扑选项摘要</span><span class="sxs-lookup"><span data-stu-id="955e7-118">Summary of Edge Server Topology Options</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="955e7-119">拓扑</span><span class="sxs-lookup"><span data-stu-id="955e7-119">Topology</span></span></th>
<th><span data-ttu-id="955e7-120">高可用性</span><span class="sxs-lookup"><span data-stu-id="955e7-120">High availability</span></span></th>
<th><span data-ttu-id="955e7-121">边缘池中的外部边缘服务器所需的其他 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="955e7-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="955e7-122">Lync 至 Lync 会话的边缘故障转移</span><span class="sxs-lookup"><span data-stu-id="955e7-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="955e7-123">Lync to Lync EUM/PIC/OCS 联合身份验证会话的边缘故障转移</span><span class="sxs-lookup"><span data-stu-id="955e7-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="955e7-124">使用 NAT 的单个边缘</span><span class="sxs-lookup"><span data-stu-id="955e7-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="955e7-125">否</span><span class="sxs-lookup"><span data-stu-id="955e7-125">No</span></span></p></td>
<td><p><span data-ttu-id="955e7-126">否</span><span class="sxs-lookup"><span data-stu-id="955e7-126">No</span></span></p></td>
<td><p><span data-ttu-id="955e7-127">否</span><span class="sxs-lookup"><span data-stu-id="955e7-127">No</span></span></p></td>
<td><p><span data-ttu-id="955e7-128">否</span><span class="sxs-lookup"><span data-stu-id="955e7-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955e7-129">使用公共 IP 的单边</span><span class="sxs-lookup"><span data-stu-id="955e7-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="955e7-130">否</span><span class="sxs-lookup"><span data-stu-id="955e7-130">No</span></span></p></td>
<td><p><span data-ttu-id="955e7-131">否</span><span class="sxs-lookup"><span data-stu-id="955e7-131">No</span></span></p></td>
<td><p><span data-ttu-id="955e7-132">否</span><span class="sxs-lookup"><span data-stu-id="955e7-132">No</span></span></p></td>
<td><p><span data-ttu-id="955e7-133">否</span><span class="sxs-lookup"><span data-stu-id="955e7-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955e7-134">使用 NAT 进行缩放的边缘（DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="955e7-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="955e7-135">是</span><span class="sxs-lookup"><span data-stu-id="955e7-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="955e7-136">是</span><span class="sxs-lookup"><span data-stu-id="955e7-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="955e7-137">是</span><span class="sxs-lookup"><span data-stu-id="955e7-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955e7-138">使用公共 IP 进行缩放的边缘（DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="955e7-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="955e7-139">是</span><span class="sxs-lookup"><span data-stu-id="955e7-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="955e7-140">是</span><span class="sxs-lookup"><span data-stu-id="955e7-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="955e7-141">是</span><span class="sxs-lookup"><span data-stu-id="955e7-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955e7-142">缩放的边缘硬件负载平衡</span><span class="sxs-lookup"><span data-stu-id="955e7-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="955e7-143">是</span><span class="sxs-lookup"><span data-stu-id="955e7-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="955e7-144">不支持（每个 VIP 一个 DNS A 记录）</span><span class="sxs-lookup"><span data-stu-id="955e7-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="955e7-145">是</span><span class="sxs-lookup"><span data-stu-id="955e7-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="955e7-146">是</span><span class="sxs-lookup"><span data-stu-id="955e7-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="955e7-147">**\*** 用于公共即时消息（IM）连接和与运行 Office 通信服务器的服务器的联盟的故障转移无法通过 DNS 负载平衡提供。</span><span class="sxs-lookup"><span data-stu-id="955e7-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="955e7-148">Exchange UM （远程用户）使用 DNS 负载平衡的故障转移要求使用 Exchange Server 2010 SP1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="955e7-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="955e7-149">单个边缘和缩放的边缘（DNS 负载平衡）拓扑可以使用：</span><span class="sxs-lookup"><span data-stu-id="955e7-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="955e7-150">可路由的公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="955e7-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="955e7-151">如果使用对称网络地址转换（NAT），则无法路由的专用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="955e7-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="955e7-152">如果你将公共 IP 地址或专用 IP 地址与 NAT 配合使用，你仍将根据拓扑生成器中的配置选择使用相同数量的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="955e7-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="955e7-153">你可以将边缘服务器配置为对每个服务使用具有不同端口的单个 IP 地址，或对每个服务使用不同的 IP 地址，但使用同一端口（默认情况下为 TCP 443）。</span><span class="sxs-lookup"><span data-stu-id="955e7-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="955e7-154">如果您决定将不可路由的专用 IP 地址与 NAT 配合使用，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="955e7-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="955e7-155">必须在所有三个外部接口上使用可路由的专用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="955e7-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="955e7-156">必须为传入和传出流量配置对称 NAT</span><span class="sxs-lookup"><span data-stu-id="955e7-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="955e7-157">缩放边缘（硬件负载平衡）拓扑必须使用公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="955e7-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="955e7-158">Lync Server 2013 支持将 Access、Web 会议和 A/V 边缘外部接口放置在对单个和缩放的合并边缘服务器拓扑执行网络地址转换（NAT）的路由器或防火墙后面。</span><span class="sxs-lookup"><span data-stu-id="955e7-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="955e7-159">对所有 Edge 外部接口使用 NAT 需要使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="955e7-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="955e7-160">与使用硬件负载平衡器相比，使用硬件负载平衡器时，如果使用不带 NAT 的 DNS 负载平衡，则可以按下表中所述，减少边缘池中的每边缘服务器的公共 IP 地址数：</span><span class="sxs-lookup"><span data-stu-id="955e7-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="955e7-161">Lync Server 2013 缩放的合并边缘（DNS 负载平衡）需要一个 Edge 池中每个边缘服务器的三个公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="955e7-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="955e7-162">Lync Server 2013 缩放后的合并边缘（硬件负载平衡）需要三个公共 IP 地址用于负载平衡器虚拟 IP 地址（一次要求在将更多边缘服务器添加到池中时不增加）加上每个 IP 地址的三个公共 IP 地址在池中的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="955e7-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="955e7-163">缩放后的合并边缘的 IP 地址要求（每个角色的 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="955e7-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="955e7-164">每个池的边缘服务器数</span><span class="sxs-lookup"><span data-stu-id="955e7-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="955e7-165">Lync Server 2013 的必需 IP 地址数（DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="955e7-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="955e7-166">Lync Server 2013 的必需 IP 地址数（硬件负载平衡）</span><span class="sxs-lookup"><span data-stu-id="955e7-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="955e7-167">ppls-2</span><span class="sxs-lookup"><span data-stu-id="955e7-167">2</span></span></p></td>
<td><p><span data-ttu-id="955e7-168">6</span><span class="sxs-lookup"><span data-stu-id="955e7-168">6</span></span></p></td>
<td><p><span data-ttu-id="955e7-169">3（每个 VIP 1 个）6</span><span class="sxs-lookup"><span data-stu-id="955e7-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955e7-170">3</span><span class="sxs-lookup"><span data-stu-id="955e7-170">3</span></span></p></td>
<td><p><span data-ttu-id="955e7-171">db-9</span><span class="sxs-lookup"><span data-stu-id="955e7-171">9</span></span></p></td>
<td><p><span data-ttu-id="955e7-172">3（每个 VIP 1 个）9</span><span class="sxs-lookup"><span data-stu-id="955e7-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955e7-173">4</span><span class="sxs-lookup"><span data-stu-id="955e7-173">4</span></span></p></td>
<td><p><span data-ttu-id="955e7-174">至</span><span class="sxs-lookup"><span data-stu-id="955e7-174">12</span></span></p></td>
<td><p><span data-ttu-id="955e7-175">3（每个 VIP 1 个）12</span><span class="sxs-lookup"><span data-stu-id="955e7-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955e7-176">5</span><span class="sxs-lookup"><span data-stu-id="955e7-176">5</span></span></p></td>
<td><p><span data-ttu-id="955e7-177">岁</span><span class="sxs-lookup"><span data-stu-id="955e7-177">15</span></span></p></td>
<td><p><span data-ttu-id="955e7-178">3（每个 VIP 1 个） + 15</span><span class="sxs-lookup"><span data-stu-id="955e7-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="955e7-179">缩放后的合并边缘的 IP 地址要求（针对所有角色的单个 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="955e7-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="955e7-180">每个池的边缘服务器数</span><span class="sxs-lookup"><span data-stu-id="955e7-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="955e7-181">Lync Server 2013 的必需 IP 地址数（DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="955e7-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="955e7-182">Lync Server 2013 的必需 IP 地址数（硬件负载平衡）</span><span class="sxs-lookup"><span data-stu-id="955e7-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="955e7-183">2</span><span class="sxs-lookup"><span data-stu-id="955e7-183">2</span></span></p></td>
<td><p><span data-ttu-id="955e7-184">ppls-2</span><span class="sxs-lookup"><span data-stu-id="955e7-184">2</span></span></p></td>
<td><p><span data-ttu-id="955e7-185">1（每个 VIP 1 个）2</span><span class="sxs-lookup"><span data-stu-id="955e7-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955e7-186">3</span><span class="sxs-lookup"><span data-stu-id="955e7-186">3</span></span></p></td>
<td><p><span data-ttu-id="955e7-187">3</span><span class="sxs-lookup"><span data-stu-id="955e7-187">3</span></span></p></td>
<td><p><span data-ttu-id="955e7-188">1（每个 VIP 1 个）3</span><span class="sxs-lookup"><span data-stu-id="955e7-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="955e7-189">4</span><span class="sxs-lookup"><span data-stu-id="955e7-189">4</span></span></p></td>
<td><p><span data-ttu-id="955e7-190">4</span><span class="sxs-lookup"><span data-stu-id="955e7-190">4</span></span></p></td>
<td><p><span data-ttu-id="955e7-191">1（每个 VIP 1 个）4</span><span class="sxs-lookup"><span data-stu-id="955e7-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="955e7-192">5</span><span class="sxs-lookup"><span data-stu-id="955e7-192">5</span></span></p></td>
<td><p><span data-ttu-id="955e7-193">5</span><span class="sxs-lookup"><span data-stu-id="955e7-193">5</span></span></p></td>
<td><p><span data-ttu-id="955e7-194">1（每个 VIP 1 个）5</span><span class="sxs-lookup"><span data-stu-id="955e7-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="955e7-195">拓扑选择的主要决策点有高可用性和负载平衡。</span><span class="sxs-lookup"><span data-stu-id="955e7-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="955e7-196">高可用性的要求可能会影响负载平衡决策。</span><span class="sxs-lookup"><span data-stu-id="955e7-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="955e7-197">**高可用性**  如果需要高可用性，请在池中至少部署两台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="955e7-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="955e7-198">单个边缘池最多支持十二台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="955e7-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="955e7-199">如果需要更多容量，可以部署多个边缘池。</span><span class="sxs-lookup"><span data-stu-id="955e7-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="955e7-200">一般规则是给定用户群的10% 需要外部访问。</span><span class="sxs-lookup"><span data-stu-id="955e7-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="955e7-201">拓扑生成器将允许你在一个 Edge 池中最多配置二十台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="955e7-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="955e7-202">在池中经过测试和支持的最大边缘服务器数为12，如果拓扑生成器允许大于12的数字，则不应将单个 Edge 池中的12台以上服务器的暗示支持视为暗示支持。</span><span class="sxs-lookup"><span data-stu-id="955e7-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="955e7-203">**硬件负载平衡**  在对 Edge 外部接口使用公共可路由的 IP 地址时，使用硬件负载平衡支持 Lync Server 2013 Edge 服务器的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="955e7-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="955e7-204">例如，在以下情况下，你可以使用此方法：对以下任何应用程序进行故障切换：</span><span class="sxs-lookup"><span data-stu-id="955e7-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="955e7-205">公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="955e7-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="955e7-206">与运行 Microsoft Office 通信服务器2007或 Microsoft Office 通信服务器 2007 R2 的公司的联盟</span><span class="sxs-lookup"><span data-stu-id="955e7-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="955e7-207">对 Exchange 2007 统一消息（UM）或 Exchange 2010 UM 的外部访问</span><span class="sxs-lookup"><span data-stu-id="955e7-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="955e7-208">Exchange UM 支持 Exchange 2010 SP1 和更高版本的 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="955e7-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="955e7-209">这三个应用程序将继续运行，但它们不是 DNS 负载平衡感知，并且将仅连接到池中的第一个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="955e7-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="955e7-210">如果该服务器不可用，连接将失败。</span><span class="sxs-lookup"><span data-stu-id="955e7-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="955e7-211">例如，如果在池中部署了多个边缘服务器以处理联盟流量负载，则只有一个访问代理服务器在其他闲置时才会实际接收流量。</span><span class="sxs-lookup"><span data-stu-id="955e7-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="955e7-212">如果您使用 Lync Server 2010 和 Microsoft Office 365 联盟公司，则建议使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="955e7-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="955e7-213">请注意，如果大多数联盟伙伴使用的是 Office 通信服务器2007或 Office 通信服务器 2007 R2，则会对性能产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="955e7-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="955e7-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="955e7-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

