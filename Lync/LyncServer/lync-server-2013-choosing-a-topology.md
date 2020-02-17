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
ms.openlocfilehash: c3a77a37cb9f9c4f92f344988082086834ab3489
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="8a099-102">在 Lync Server 2013 中选择拓扑</span><span class="sxs-lookup"><span data-stu-id="8a099-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="8a099-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8a099-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8a099-104">选择拓扑后，可以使用以下支持的拓扑选项之一：</span><span class="sxs-lookup"><span data-stu-id="8a099-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8a099-105">除非另有说明，否则，如果你有 Microsoft Lync Server 2010 的经验，你将在此处发现指南主要保持不变。</span><span class="sxs-lookup"><span data-stu-id="8a099-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="8a099-106">Lync Server 2013 中具有专用 IP 地址和 NAT 的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="8a099-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="8a099-107">Lync Server 2013 中具有公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="8a099-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="8a099-108">在 Lync Server 2013 中，扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8a099-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="8a099-109">在 Lync Server 2013 中，扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8a099-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="8a099-110">Lync Server 2013 中具有硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="8a099-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="8a099-p101">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="8a099-p101">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="8a099-113">下表汇总了支持的 Microsoft Lync Server 2013 拓扑结构中提供的功能。</span><span class="sxs-lookup"><span data-stu-id="8a099-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="8a099-114">列标题指明了给定的边缘配置选项可用的功能。</span><span class="sxs-lookup"><span data-stu-id="8a099-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="8a099-115">以“扩展边缘”（DNS 负载已平衡）选项为例，您可以了解到它支持高可用性、可以使用分配给边缘外部接口的不可路由专用 IP 地址（具有 NAT）或可路由的公用 IP 地址，并可降低成本（因为不需要硬件负载平衡器）。</span><span class="sxs-lookup"><span data-stu-id="8a099-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="8a099-116">DNS 负载平衡支持的边缘故障转移方案为 Lync 到 Lync 的点对点会话、Lync 会议会话、Lync 到 PSTN 会话和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8a099-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="8a099-117">无法从 DNS 负载平衡中受益的边缘故障转移方案是远程用户 Exchange 统一消息（UM）的故障转移（Exchange 2010 SP1 之前）、公共即时消息（IM）连接以及与运行 Office 通信的服务器的联盟服务器主板.</span><span class="sxs-lookup"><span data-stu-id="8a099-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="8a099-118">边缘服务器拓扑选项摘要</span><span class="sxs-lookup"><span data-stu-id="8a099-118">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="8a099-119">拓扑</span><span class="sxs-lookup"><span data-stu-id="8a099-119">Topology</span></span></th>
<th><span data-ttu-id="8a099-120">高可用性</span><span class="sxs-lookup"><span data-stu-id="8a099-120">High availability</span></span></th>
<th><span data-ttu-id="8a099-121">边缘池中的外部边缘服务器是否需要其他 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="8a099-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="8a099-122">Lync 到 Lync 会话的边缘故障转移</span><span class="sxs-lookup"><span data-stu-id="8a099-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="8a099-123">Lync to Lync EUM/PIC/OCS 联合会话的边缘故障转移</span><span class="sxs-lookup"><span data-stu-id="8a099-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a099-124">使用 NAT 的单个边缘</span><span class="sxs-lookup"><span data-stu-id="8a099-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="8a099-125">否</span><span class="sxs-lookup"><span data-stu-id="8a099-125">No</span></span></p></td>
<td><p><span data-ttu-id="8a099-126">否</span><span class="sxs-lookup"><span data-stu-id="8a099-126">No</span></span></p></td>
<td><p><span data-ttu-id="8a099-127">否</span><span class="sxs-lookup"><span data-stu-id="8a099-127">No</span></span></p></td>
<td><p><span data-ttu-id="8a099-128">否</span><span class="sxs-lookup"><span data-stu-id="8a099-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a099-129">使用公用 IP 的单个边缘</span><span class="sxs-lookup"><span data-stu-id="8a099-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="8a099-130">否</span><span class="sxs-lookup"><span data-stu-id="8a099-130">No</span></span></p></td>
<td><p><span data-ttu-id="8a099-131">否</span><span class="sxs-lookup"><span data-stu-id="8a099-131">No</span></span></p></td>
<td><p><span data-ttu-id="8a099-132">否</span><span class="sxs-lookup"><span data-stu-id="8a099-132">No</span></span></p></td>
<td><p><span data-ttu-id="8a099-133">否</span><span class="sxs-lookup"><span data-stu-id="8a099-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a099-134">使用 NAT 的扩展边缘（DNS 负载已平衡）</span><span class="sxs-lookup"><span data-stu-id="8a099-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="8a099-135">是</span><span class="sxs-lookup"><span data-stu-id="8a099-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="8a099-136">是</span><span class="sxs-lookup"><span data-stu-id="8a099-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="8a099-137">是</span><span class="sxs-lookup"><span data-stu-id="8a099-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a099-138">使用公用 IP 的扩展边缘（DNS 负载已平衡）</span><span class="sxs-lookup"><span data-stu-id="8a099-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="8a099-139">是</span><span class="sxs-lookup"><span data-stu-id="8a099-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="8a099-140">是</span><span class="sxs-lookup"><span data-stu-id="8a099-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="8a099-141">是</span><span class="sxs-lookup"><span data-stu-id="8a099-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a099-142">扩展边缘（硬件负载已平衡）</span><span class="sxs-lookup"><span data-stu-id="8a099-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="8a099-143">是</span><span class="sxs-lookup"><span data-stu-id="8a099-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="8a099-144">不支持（每个 VIP 一个 DNS A 记录）</span><span class="sxs-lookup"><span data-stu-id="8a099-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="8a099-145">是</span><span class="sxs-lookup"><span data-stu-id="8a099-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="8a099-146">是</span><span class="sxs-lookup"><span data-stu-id="8a099-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8a099-147">**\*** 用于公共即时消息（IM）连接的故障转移以及与运行 Office 通信服务器的服务器的联盟在 DNS 负载平衡中不可用。</span><span class="sxs-lookup"><span data-stu-id="8a099-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="8a099-148">使用 DNS 负载平衡的 exchange UM （远程用户）故障转移需要 Exchange Server 2010 SP1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8a099-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="8a099-149">单个边缘和扩展边缘（DNS 负载已平衡）拓扑可以使用：</span><span class="sxs-lookup"><span data-stu-id="8a099-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="8a099-150">可路由的公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8a099-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="8a099-151">如果使用对称网络地址转换（NAT），则不可路由的专用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8a099-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="8a099-152">如果使用公用 IP 地址或使用 NAT 的专用 IP 地址，则仍将根据拓扑生成器中的配置选择使用相同数量的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8a099-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="8a099-153">您可以将边缘服务器配置为对每个服务使用具有不同端口的单个 IP 地址，或对每个服务使用不同的 IP 地址，但使用相同的端口（默认情况下为 TCP 443）。</span><span class="sxs-lookup"><span data-stu-id="8a099-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="8a099-154">如果您决定使用与 NAT 的不可路由的专用 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="8a099-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="8a099-155">您必须在所有三个外部接口上使用可路由的专用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8a099-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="8a099-156">必须为传入和传出流量配置对称 NAT</span><span class="sxs-lookup"><span data-stu-id="8a099-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="8a099-157">扩展边缘（硬件负载已平衡）拓扑必须使用公用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8a099-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="8a099-158">Lync Server 2013 支持将访问、Web 会议和 A/V 边缘外部接口放置在为单一和扩展的合并边缘服务器拓扑执行网络地址转换（NAT）的路由器或防火墙后面。</span><span class="sxs-lookup"><span data-stu-id="8a099-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="8a099-p106">对所有边缘的外部接口使用 NAT 需要使用 DNS 负载平衡。与使用硬件负载平衡器相比，使用 DNS 负载平衡（不含 NAT）使您可以减少边缘池中每台边缘服务器的公用 IP 地址的数量，如以下列表所示：</span><span class="sxs-lookup"><span data-stu-id="8a099-p106">Using NAT for all Edge external interfaces requires the use of DNS load balancing. When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="8a099-161">Lync Server 2013 扩展的合并边缘（DNS 负载平衡）对边缘池中的每台边缘服务器都需要三个公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8a099-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="8a099-162">Lync Server 2013 扩展的合并边缘（硬件负载平衡）需要三个公共 IP 地址用于负载平衡器虚拟 IP 地址（一种时间要求，在将更多边缘服务器添加到池中时不增加）加上每个服务器的三个公用 IP 地址。池中的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="8a099-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="8a099-163">扩展的合并边缘的 IP 地址要求（每个角色一个 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="8a099-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a099-164">每个池的边缘服务器数量</span><span class="sxs-lookup"><span data-stu-id="8a099-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="8a099-165">所需 IP 地址的数目 Lync Server 2013 （DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8a099-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="8a099-166">所需 IP 地址的数目 Lync Server 2013 （硬件负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8a099-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a099-167">2 </span><span class="sxs-lookup"><span data-stu-id="8a099-167">2</span></span></p></td>
<td><p><span data-ttu-id="8a099-168">6 </span><span class="sxs-lookup"><span data-stu-id="8a099-168">6</span></span></p></td>
<td><p><span data-ttu-id="8a099-169">3（每个 VIP 1 个）+ 6</span><span class="sxs-lookup"><span data-stu-id="8a099-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a099-170">3 </span><span class="sxs-lookup"><span data-stu-id="8a099-170">3</span></span></p></td>
<td><p><span data-ttu-id="8a099-171">9 </span><span class="sxs-lookup"><span data-stu-id="8a099-171">9</span></span></p></td>
<td><p><span data-ttu-id="8a099-172">3（每个 VIP 1 个）+9</span><span class="sxs-lookup"><span data-stu-id="8a099-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a099-173">4 </span><span class="sxs-lookup"><span data-stu-id="8a099-173">4</span></span></p></td>
<td><p><span data-ttu-id="8a099-174">12</span><span class="sxs-lookup"><span data-stu-id="8a099-174">12</span></span></p></td>
<td><p><span data-ttu-id="8a099-175">3（每个 VIP 1 个）+12</span><span class="sxs-lookup"><span data-stu-id="8a099-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a099-176">5 </span><span class="sxs-lookup"><span data-stu-id="8a099-176">5</span></span></p></td>
<td><p><span data-ttu-id="8a099-177">15 </span><span class="sxs-lookup"><span data-stu-id="8a099-177">15</span></span></p></td>
<td><p><span data-ttu-id="8a099-178">3（每个 VIP 1 个）+15</span><span class="sxs-lookup"><span data-stu-id="8a099-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="8a099-179">扩展的合并边缘的 IP 地址要求（单个 IP 地址用于所有角色）</span><span class="sxs-lookup"><span data-stu-id="8a099-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a099-180">每个池的边缘服务器数量</span><span class="sxs-lookup"><span data-stu-id="8a099-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="8a099-181">所需 IP 地址的数目 Lync Server 2013 （DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8a099-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="8a099-182">所需 IP 地址的数目 Lync Server 2013 （硬件负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8a099-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a099-183">2 </span><span class="sxs-lookup"><span data-stu-id="8a099-183">2</span></span></p></td>
<td><p><span data-ttu-id="8a099-184">2 </span><span class="sxs-lookup"><span data-stu-id="8a099-184">2</span></span></p></td>
<td><p><span data-ttu-id="8a099-185">1（每个 VIP 1 个）2</span><span class="sxs-lookup"><span data-stu-id="8a099-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a099-186">3 </span><span class="sxs-lookup"><span data-stu-id="8a099-186">3</span></span></p></td>
<td><p><span data-ttu-id="8a099-187">3 </span><span class="sxs-lookup"><span data-stu-id="8a099-187">3</span></span></p></td>
<td><p><span data-ttu-id="8a099-188">1（每个 VIP 1 个）+ 3</span><span class="sxs-lookup"><span data-stu-id="8a099-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a099-189">4 </span><span class="sxs-lookup"><span data-stu-id="8a099-189">4</span></span></p></td>
<td><p><span data-ttu-id="8a099-190">4 </span><span class="sxs-lookup"><span data-stu-id="8a099-190">4</span></span></p></td>
<td><p><span data-ttu-id="8a099-191">1（每个 VIP 1 个）4</span><span class="sxs-lookup"><span data-stu-id="8a099-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a099-192">5 </span><span class="sxs-lookup"><span data-stu-id="8a099-192">5</span></span></p></td>
<td><p><span data-ttu-id="8a099-193">5</span><span class="sxs-lookup"><span data-stu-id="8a099-193">5</span></span></p></td>
<td><p><span data-ttu-id="8a099-194">1（每个 VIP 1 个）5</span><span class="sxs-lookup"><span data-stu-id="8a099-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8a099-p107">拓扑选择的主要决策点是高可用性和负载平衡。高可用性的要求会影响负载平衡决策。</span><span class="sxs-lookup"><span data-stu-id="8a099-p107">The primary decision points for topology selection are high availability and load balancing. The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="8a099-197">**高可用性**  如果需要高可用性，请在池中部署至少两台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="8a099-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="8a099-198">单个边缘池最长可支持12台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="8a099-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="8a099-199">如果需要更多的容量，可以部署多个边缘池。</span><span class="sxs-lookup"><span data-stu-id="8a099-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="8a099-200">一般规则是，如果给定用户群的10%，则需要外部访问。</span><span class="sxs-lookup"><span data-stu-id="8a099-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8a099-201">拓扑生成器将允许您在单个边缘池中配置最长20台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="8a099-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="8a099-202">池中经过测试且受支持的边缘服务器的最大数量为12，拓扑生成器允许大于12的值不应解释为单个边缘池中的12台边缘服务器的暗示支持。</span><span class="sxs-lookup"><span data-stu-id="8a099-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="8a099-203">**硬件负载平衡**  在对边缘外部接口使用可公开路由的 IP 地址时，对 Lync Server 2013 边缘服务器的负载平衡支持硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="8a099-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="8a099-204">例如，在以下任一应用程序需要故障转移的情况下，将使用此方法：</span><span class="sxs-lookup"><span data-stu-id="8a099-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="8a099-205">公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="8a099-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="8a099-206">与运行 Microsoft Office 通信服务器2007或 Microsoft Office 通信服务器 2007 R2 的公司的联盟</span><span class="sxs-lookup"><span data-stu-id="8a099-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="8a099-207">外部访问 Exchange 2007 统一消息 (UM) 或 Exchange 2010 UM</span><span class="sxs-lookup"><span data-stu-id="8a099-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="8a099-208">Exchange UM 支持 Exchange 2010 SP1 和更高版本的 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="8a099-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="8a099-p111">这三个应用程序将继续运行，但不会进行 DNS 负载平衡，而且只会连接到池中的第一台边缘服务器。如果该服务器不可用，则连接将失败。例如，如果在池中部署多台边缘服务器以处理联盟流量负载，则实际上只有一个访问代理会收到流量，而其他设备处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="8a099-p111">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool. If that server is unavailable, the connection will fail. For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8a099-212">如果要与使用 Lync Server 2010 和 Microsoft Office 365 的公司进行联盟，则建议使用 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="8a099-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="8a099-213">请注意，如果大多数联盟伙伴使用的是 Office 通信服务器2007或 Office 通信服务器 2007 R2，则会对性能产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="8a099-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="8a099-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8a099-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

