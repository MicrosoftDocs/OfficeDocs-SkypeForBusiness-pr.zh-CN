---
title: Lync Server 2013：定义呼叫允许控制的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13a06cfc55481fcfada5782fcbedbac52e6a7660
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504419"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="1193b-102">在 Lync Server 2013 中定义呼叫允许控制的要求</span><span class="sxs-lookup"><span data-stu-id="1193b-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1193b-103">_**上次修改的主题：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="1193b-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="1193b-104">规划呼叫允许控制 (CAC) 需要有关企业网络拓扑的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1193b-104">Planning for call admission control (CAC) requires detailed information about your enterprise network topology.</span></span> <span data-ttu-id="1193b-105">若要帮助规划呼叫允许控制策略，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1193b-105">To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="1193b-106">确定企业网络中) *网络区域* 的集线器/中枢 (。</span><span class="sxs-lookup"><span data-stu-id="1193b-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="1193b-107">标识每个网络区域中称为 " *网络站点* " 的办公室或位置 () 。</span><span class="sxs-lookup"><span data-stu-id="1193b-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="1193b-108">确定每对网络区域之间的网络路由。</span><span class="sxs-lookup"><span data-stu-id="1193b-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="1193b-109">确定每个 WAN 链路的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="1193b-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1193b-110">带宽限制是指 WAN 链路上的多少带宽分配给企业语音和音频/视频流量。</span><span class="sxs-lookup"><span data-stu-id="1193b-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="1193b-111">当 WAN 链路被描述为 "带宽受限" 时，WAN 链路的带宽限制低于该链路上预期的峰值流量。</span><span class="sxs-lookup"><span data-stu-id="1193b-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="1193b-112">确定分配给每个网络站点的 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="1193b-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="1193b-113">为了说明这些概念，我们将使用下图中所示的示例网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="1193b-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="1193b-114">**呼叫允许控制的示例拓扑**</span><span class="sxs-lookup"><span data-stu-id="1193b-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="1193b-115">![Litware 的网络拓扑示例](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware 的网络拓扑示例")</span><span class="sxs-lookup"><span data-stu-id="1193b-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1193b-116">所有网络站点都与一个网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="1193b-116">All network sites are associated with a network region.</span></span> <span data-ttu-id="1193b-117">例如，"里诺" 和 "阿尔伯克基" 包含在北美区域中。</span><span class="sxs-lookup"><span data-stu-id="1193b-117">For example, Portland, Reno, and Albuquerque are included in the North America region.</span></span> <span data-ttu-id="1193b-118">在此图中，仅显示了已应用 CAC 策略的 WAN 链接，其中包含带宽限制。</span><span class="sxs-lookup"><span data-stu-id="1193b-118">In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits.</span></span> <span data-ttu-id="1193b-119">芝加哥、纽约和底特律的网络站点在北美地区椭圆中显示，因为它们不受带宽限制，因此不需要 CAC 策略。</span><span class="sxs-lookup"><span data-stu-id="1193b-119">The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="1193b-120">以下各节介绍了此示例拓扑的组件。</span><span class="sxs-lookup"><span data-stu-id="1193b-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="1193b-121">若要详细了解如何规划此拓扑（包括带宽限制），请参阅 [示例：在 Lync Server 2013 中收集呼叫允许控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1193b-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="1193b-122">标识网络区域</span><span class="sxs-lookup"><span data-stu-id="1193b-122">Identify Network Regions</span></span>

<span data-ttu-id="1193b-123">网络区域代表网络中枢或网络中心。</span><span class="sxs-lookup"><span data-stu-id="1193b-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="1193b-124">网络主干或集线器是用于互连网络不同部分的计算机网络基础结构的一部分，它提供了在不同 Lan 或子网之间交换信息的路径。</span><span class="sxs-lookup"><span data-stu-id="1193b-124">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets.</span></span> <span data-ttu-id="1193b-125">主干可将较小位置的各种网络与大地理区域关联起来。</span><span class="sxs-lookup"><span data-stu-id="1193b-125">A backbone can tie together diverse networks from a small location to a wide geographic area.</span></span> <span data-ttu-id="1193b-126">主干的容量通常大于连接到它的网络的容量。</span><span class="sxs-lookup"><span data-stu-id="1193b-126">The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="1193b-127">示例拓扑具有三个网络区域：北美、EMEA 和 APAC。</span><span class="sxs-lookup"><span data-stu-id="1193b-127">Our example topology has three network regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="1193b-128">网络区域包含一个网络站点集合 (请参阅本主题后面的网络站点的定义) 。</span><span class="sxs-lookup"><span data-stu-id="1193b-128">A network region contains a collection of network sites (see the definition of network sites later in this topic).</span></span> <span data-ttu-id="1193b-129">与您的网络运营团队合作，以确定您的网络区域。</span><span class="sxs-lookup"><span data-stu-id="1193b-129">Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="1193b-130">将中央站点与每个网络区域相关联</span><span class="sxs-lookup"><span data-stu-id="1193b-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="1193b-131">CAC 要求为每个网络区域定义 Lync Server 中心网站。</span><span class="sxs-lookup"><span data-stu-id="1193b-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="1193b-132">将选择中央网站，并将最佳网络连接和最大带宽用于该网络区域中的所有其他网站。</span><span class="sxs-lookup"><span data-stu-id="1193b-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="1193b-133">上面的网络拓扑示例显示三个网络区域，每个区域都有一个管理 CAC 决策的中央站点。</span><span class="sxs-lookup"><span data-stu-id="1193b-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="1193b-134">在上面的示例中，相应的关联如下表所示。</span><span class="sxs-lookup"><span data-stu-id="1193b-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1193b-135">中心站点并不一定对应于网络站点。</span><span class="sxs-lookup"><span data-stu-id="1193b-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="1193b-136">在本文档的示例中，一些中央站点（芝加哥、伦敦和北京）与网络站点共享相同的名称。</span><span class="sxs-lookup"><span data-stu-id="1193b-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="1193b-137">但是，即使中央站点和网络站点共享相同的名称，中心站点也是 Lync Server 拓扑的一个元素，而网络站点是 Lync Server 拓扑所驻留的整个网络的一部分。</span><span class="sxs-lookup"><span data-stu-id="1193b-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="1193b-138">网络区域、中央站点和网络站点</span><span class="sxs-lookup"><span data-stu-id="1193b-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1193b-139">网络区域</span><span class="sxs-lookup"><span data-stu-id="1193b-139">Network Region</span></span></th>
<th><span data-ttu-id="1193b-140">中央站点</span><span class="sxs-lookup"><span data-stu-id="1193b-140">Central Site</span></span></th>
<th><span data-ttu-id="1193b-141">网络站点</span><span class="sxs-lookup"><span data-stu-id="1193b-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1193b-142">北美</span><span class="sxs-lookup"><span data-stu-id="1193b-142">North America</span></span></p></td>
<td><p><span data-ttu-id="1193b-143">Chicago</span><span class="sxs-lookup"><span data-stu-id="1193b-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="1193b-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="1193b-144">Chicago</span></span></p>
<p><span data-ttu-id="1193b-145">纽约</span><span class="sxs-lookup"><span data-stu-id="1193b-145">New York</span></span></p>
<p><span data-ttu-id="1193b-146">底特律</span><span class="sxs-lookup"><span data-stu-id="1193b-146">Detroit</span></span></p>
<p><span data-ttu-id="1193b-147">波特兰</span><span class="sxs-lookup"><span data-stu-id="1193b-147">Portland</span></span></p>
<p><span data-ttu-id="1193b-148">里诺</span><span class="sxs-lookup"><span data-stu-id="1193b-148">Reno</span></span></p>
<p><span data-ttu-id="1193b-149">阿尔伯克基</span><span class="sxs-lookup"><span data-stu-id="1193b-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1193b-150">EMEA</span><span class="sxs-lookup"><span data-stu-id="1193b-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="1193b-151">南京</span><span class="sxs-lookup"><span data-stu-id="1193b-151">London</span></span></p></td>
<td><p><span data-ttu-id="1193b-152">南京</span><span class="sxs-lookup"><span data-stu-id="1193b-152">London</span></span></p>
<p><span data-ttu-id="1193b-153">Cologne</span><span class="sxs-lookup"><span data-stu-id="1193b-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1193b-154">APAC</span><span class="sxs-lookup"><span data-stu-id="1193b-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="1193b-155">首都</span><span class="sxs-lookup"><span data-stu-id="1193b-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="1193b-156">首都</span><span class="sxs-lookup"><span data-stu-id="1193b-156">Beijing</span></span></p>
<p><span data-ttu-id="1193b-157">Manila</span><span class="sxs-lookup"><span data-stu-id="1193b-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="1193b-158">标识网络站点</span><span class="sxs-lookup"><span data-stu-id="1193b-158">Identify Network Sites</span></span>

<span data-ttu-id="1193b-159">网络站点代表组织具有物理场所（例如，办公室、一组建筑物或校园）的位置。</span><span class="sxs-lookup"><span data-stu-id="1193b-159">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus.</span></span> <span data-ttu-id="1193b-160">具有 LAN 且具有与其他站点的 WAN 连接的物理场所被视为网络站点。</span><span class="sxs-lookup"><span data-stu-id="1193b-160">A physical venue with a LAN and has WAN connectivity to other sites is considered a network site.</span></span> <span data-ttu-id="1193b-161">首先，清点你的组织的所有办公室。</span><span class="sxs-lookup"><span data-stu-id="1193b-161">Start by inventorying all of your organization’s offices.</span></span> <span data-ttu-id="1193b-162">在我们的示例拓扑中，北美网络区域由以下网络站点组成：纽约、芝加哥、底特律、上海、里诺和阿尔伯克基。</span><span class="sxs-lookup"><span data-stu-id="1193b-162">In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="1193b-163">您必须将每个网络站点与一个网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="1193b-163">You must associate every network site with a network region.</span></span> <span data-ttu-id="1193b-164">根据网络站点是否具有受约束的 WAN 链路，带宽策略与网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="1193b-164">Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site.</span></span> <span data-ttu-id="1193b-165">有关 CAC 策略和使用它们分配的带宽的详细信息，请参阅本主题后面的 "定义带宽策略"。</span><span class="sxs-lookup"><span data-stu-id="1193b-165">For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic.</span></span> <span data-ttu-id="1193b-166">若要配置 CAC，请将网络站点与网络区域相关联，然后创建分配带宽的策略，以应用于给定站点或区域之间的带宽限制的连接以及站点和区域之间的 WAN 连接。</span><span class="sxs-lookup"><span data-stu-id="1193b-166">To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="1193b-167">标识网络链接</span><span class="sxs-lookup"><span data-stu-id="1193b-167">Identify Network Links</span></span>

<span data-ttu-id="1193b-168">网络链接代表与链接不同区域和站点的物理 WAN 的连接。</span><span class="sxs-lookup"><span data-stu-id="1193b-168">Network links represent connections to the physical WAN that links different regions and sites.</span></span> <span data-ttu-id="1193b-169">在我们的示例拓扑中，有两个区域网络链接、区域和网站之间有五个网络链接以及两个站点之间的一个网络链接。</span><span class="sxs-lookup"><span data-stu-id="1193b-169">In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="1193b-170">这两个区域链接介于北美和 EMEA 之间，表示为 NA-EMEA 链接，在 APAC 和 EMEA 之间，表示为 EMEA-APAC-链接。</span><span class="sxs-lookup"><span data-stu-id="1193b-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="1193b-171">站点链接由连接上海、里诺和阿尔伯克基到北美地区、Manila 到 APAC 地区和 Cologne 到 EMEA 地区的线路指示。</span><span class="sxs-lookup"><span data-stu-id="1193b-171">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region.</span></span> <span data-ttu-id="1193b-172">里诺和阿尔伯克基之间的线显示这两个站点之间的直接网络链接。</span><span class="sxs-lookup"><span data-stu-id="1193b-172">The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="1193b-173">定义带宽策略</span><span class="sxs-lookup"><span data-stu-id="1193b-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="1193b-174">与您的网络运营团队合作，以确定可用于组织中的 WAN 链接的实时音频和视频流量的 WAN 带宽量。</span><span class="sxs-lookup"><span data-stu-id="1193b-174">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization.</span></span> <span data-ttu-id="1193b-175">带宽策略通常适用于 WAN 链路（如果带宽使用受到限制）;也就是说，如果它应大于可为音频和视频形式分配的带宽。</span><span class="sxs-lookup"><span data-stu-id="1193b-175">Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="1193b-176">CAC *带宽策略* 定义可为实时音频和视频形式预留的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="1193b-176">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities.</span></span> <span data-ttu-id="1193b-177">由于 CAC 不会限制其他流量的带宽，因此不能阻止其他数据流量（如大型文件传输、音乐流）使用所有网络带宽。</span><span class="sxs-lookup"><span data-stu-id="1193b-177">Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="1193b-178">CAC 带宽策略可以定义以下任一或所有内容：</span><span class="sxs-lookup"><span data-stu-id="1193b-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="1193b-179">为音频分配的最大总带宽。</span><span class="sxs-lookup"><span data-stu-id="1193b-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="1193b-180">为视频分配的最大总带宽。</span><span class="sxs-lookup"><span data-stu-id="1193b-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="1193b-181">为单个音频呼叫分配的最大带宽 (会话) 。</span><span class="sxs-lookup"><span data-stu-id="1193b-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="1193b-182">为单个视频呼叫分配的最大带宽 (会话) 。</span><span class="sxs-lookup"><span data-stu-id="1193b-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1193b-183">所有 CAC 带宽值表示最大 <EM>单向</EM> 带宽限制。</span><span class="sxs-lookup"><span data-stu-id="1193b-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1193b-184">使用 Lync Server 2013 语音策略功能，可以覆盖用户的传入呼叫的带宽策略检查，而不是对用户) 发出的传出呼叫进行 (。</span><span class="sxs-lookup"><span data-stu-id="1193b-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="1193b-185">在建立会话之后，将准确地考虑带宽消耗。</span><span class="sxs-lookup"><span data-stu-id="1193b-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="1193b-186">应慎用此设置。</span><span class="sxs-lookup"><span data-stu-id="1193b-186">This setting should be used sparingly.</span></span> <span data-ttu-id="1193b-187">有关详细信息，请参阅部署文档中的在 lync <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">server 2013 中创建语音策略和配置 pstn 用法记录</A> 或在 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync Server 2013 中修改语音策略和配置 pstn 用法记录</A> 。</span><span class="sxs-lookup"><span data-stu-id="1193b-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="1193b-188">若要基于每个会话优化带宽使用率，请考虑将使用的音频和视频编码解码器的类型。</span><span class="sxs-lookup"><span data-stu-id="1193b-188">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used.</span></span> <span data-ttu-id="1193b-189">特别是，避免为您预计经常使用的编解码器分配足够的带宽。</span><span class="sxs-lookup"><span data-stu-id="1193b-189">In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently.</span></span> <span data-ttu-id="1193b-190">相反，如果要阻止媒体使用需要更多带宽的编解码器，则应将每个会话的最大带宽设置得足够低以防止此类使用。</span><span class="sxs-lookup"><span data-stu-id="1193b-190">Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use.</span></span> <span data-ttu-id="1193b-191">对于音频，并不是每个方案都提供了每个编解码器。</span><span class="sxs-lookup"><span data-stu-id="1193b-191">For audio, not every codec is available for every scenario.</span></span> <span data-ttu-id="1193b-192">例如：</span><span class="sxs-lookup"><span data-stu-id="1193b-192">For example:</span></span>

  - <span data-ttu-id="1193b-193">当您考虑编解码器的带宽和优先顺序时，Lync 终结点之间的对等音频呼叫将使用 RTAudio (8kHz) 或 RTAudio (16kHz) 。</span><span class="sxs-lookup"><span data-stu-id="1193b-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="1193b-194">Lync 终结点和 A/V 会议服务之间的会议呼叫将使用 g.722 或 Siren。</span><span class="sxs-lookup"><span data-stu-id="1193b-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="1193b-195">对公开交换电话网络 (PSTN) 或从 Lync 终结点进行的呼叫将使用 g.711 或 RTAudio (8kHz) 。</span><span class="sxs-lookup"><span data-stu-id="1193b-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="1193b-196">使用下表可帮助优化每个会话的最大带宽设置。</span><span class="sxs-lookup"><span data-stu-id="1193b-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="1193b-197">通过编解码器的带宽利用率</span><span class="sxs-lookup"><span data-stu-id="1193b-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1193b-198">编解码器</span><span class="sxs-lookup"><span data-stu-id="1193b-198">Codec</span></span></th>
<th><span data-ttu-id="1193b-199">没有转发错误纠正 (FEC 的带宽要求) </span><span class="sxs-lookup"><span data-stu-id="1193b-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="1193b-200">带前向纠错 (FEC) 的带宽要求</span><span class="sxs-lookup"><span data-stu-id="1193b-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1193b-201">RTAudio (8kHz) </span><span class="sxs-lookup"><span data-stu-id="1193b-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="1193b-202">49.8 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-203">61.6 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1193b-204">RTAudio (16kHz) </span><span class="sxs-lookup"><span data-stu-id="1193b-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="1193b-205">67 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-206">96 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1193b-207">Siren</span><span class="sxs-lookup"><span data-stu-id="1193b-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="1193b-208">57.6 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-209">73.6 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1193b-210">G. g.711</span><span class="sxs-lookup"><span data-stu-id="1193b-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="1193b-211">102 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-212">166 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1193b-213">G. g.722</span><span class="sxs-lookup"><span data-stu-id="1193b-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="1193b-214">105.6 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-215">169.6 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1193b-216">RTVideo (CIF 15 fps) </span><span class="sxs-lookup"><span data-stu-id="1193b-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="1193b-217">260 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-218">不适用</span><span class="sxs-lookup"><span data-stu-id="1193b-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1193b-219">RTVideo (VGA 30 fps) </span><span class="sxs-lookup"><span data-stu-id="1193b-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="1193b-220">610 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-221">不适用</span><span class="sxs-lookup"><span data-stu-id="1193b-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1193b-222">带宽要求考虑以下方面的开销：以太网 II、IP、用户数据报协议 (UDP) 、RTP (实时传输协议) 和 SRTP (安全实时传输协议) 。</span><span class="sxs-lookup"><span data-stu-id="1193b-222">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol).</span></span> <span data-ttu-id="1193b-223">它们还包括 10 kbps 的 RTCP 开销。</span><span class="sxs-lookup"><span data-stu-id="1193b-223">They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="1193b-224">722.1 和 Siren 编解码器类似，但它们提供不同的比特率。</span><span class="sxs-lookup"><span data-stu-id="1193b-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="1193b-225">G.722 （Lync Server 会议的默认编解码器）与722.1 和 Siren 编解码器完全不同。</span><span class="sxs-lookup"><span data-stu-id="1193b-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="1193b-226">在下列情况下，在 Lync Server 中使用 Siren 编解码器：</span><span class="sxs-lookup"><span data-stu-id="1193b-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="1193b-227">如果将 g.722 的带宽策略设置得太低，则无法使用。</span><span class="sxs-lookup"><span data-stu-id="1193b-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="1193b-228">如果通信服务器2007或通信服务器 2007 R2 客户端连接到 Lync Server 会议服务 (，因为这些客户端不支持 g.722 编解码器) 。</span><span class="sxs-lookup"><span data-stu-id="1193b-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="1193b-229">按方案的带宽使用情况</span><span class="sxs-lookup"><span data-stu-id="1193b-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1193b-230">方案</span><span class="sxs-lookup"><span data-stu-id="1193b-230">Scenario</span></span></th>
<th><span data-ttu-id="1193b-231">为 (kbps 的数量优化的带宽要求) </span><span class="sxs-lookup"><span data-stu-id="1193b-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="1193b-232">平衡模式 (kbps 的带宽要求) </span><span class="sxs-lookup"><span data-stu-id="1193b-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="1193b-233">为质量 (kbps 优化的带宽要求) </span><span class="sxs-lookup"><span data-stu-id="1193b-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1193b-234">对等音频呼叫</span><span class="sxs-lookup"><span data-stu-id="1193b-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="1193b-235">45 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-236">62 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-237">91 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1193b-238">会议呼叫</span><span class="sxs-lookup"><span data-stu-id="1193b-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="1193b-239">53 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-240">101 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-241">165 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1193b-242">PSTN 呼叫 (在 Lync 2013 和 PSTN 网关之间，具有媒体旁路) </span><span class="sxs-lookup"><span data-stu-id="1193b-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="1193b-243">97 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-245">161 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1193b-246">PSTN 呼叫在 Lync 2013 和中介服务器之间 (，无需媒体旁路) </span><span class="sxs-lookup"><span data-stu-id="1193b-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="1193b-247">45 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-248">97 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-249">161 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1193b-250">PSTN 呼叫 (中介服务器和 PSTN 网关之间，无需媒体旁路) </span><span class="sxs-lookup"><span data-stu-id="1193b-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="1193b-251">97 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-253">161 kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1193b-254">Lync-Polycom 呼叫</span><span class="sxs-lookup"><span data-stu-id="1193b-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="1193b-255">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-256">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="1193b-257">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="1193b-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="1193b-258">标识 IP 子网</span><span class="sxs-lookup"><span data-stu-id="1193b-258">Identify IP Subnets</span></span>

<span data-ttu-id="1193b-259">对于每个网络站点，您将需要与您的网络管理员合作，以确定分配给每个网络站点的 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="1193b-259">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site.</span></span> <span data-ttu-id="1193b-260">如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。</span><span class="sxs-lookup"><span data-stu-id="1193b-260">If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="1193b-261">在我们的示例中，向北美地区的纽约站点分配了以下 IP 子网： 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。</span><span class="sxs-lookup"><span data-stu-id="1193b-261">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="1193b-262">假设小明在底特律中工作的小明传播到纽约办公室进行培训。</span><span class="sxs-lookup"><span data-stu-id="1193b-262">Suppose Bob, who typically works in Detroit, travels to the New York office for training.</span></span> <span data-ttu-id="1193b-263">当他打开计算机并连接到网络时，他的计算机将在为纽约保留的四个区域之一中获取 IP 地址，例如172.29.80.103。</span><span class="sxs-lookup"><span data-stu-id="1193b-263">When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1193b-264">在服务器上的网络配置过程中指定的 IP 子网必须与客户端计算机提供的格式相匹配，以便能够正确地用于媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="1193b-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="1193b-265">Lync 客户端获取其本地 IP 地址，并使用关联的子网掩码屏蔽 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1193b-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="1193b-266">在确定与每个客户端关联的绕过 ID 时，注册器会将与每个网络站点关联的 IP 子网的列表与客户端提供的子网进行比较，以实现精确匹配。</span><span class="sxs-lookup"><span data-stu-id="1193b-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="1193b-267">因此，在服务器上的网络配置过程中输入的子网是实际的子网而不是虚拟子网，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="1193b-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="1193b-268"> (如果您部署了呼叫允许控制，但没有媒体旁路，则即使您配置了虚拟子网，呼叫允许控制也能正常运行。 ) </span><span class="sxs-lookup"><span data-stu-id="1193b-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="1193b-269">例如，如果客户端登录到 IP 地址为 172.29.81.57 ip 子网掩码为255.255.255.0 的计算机，Lync 2013 将请求与子网172.29.81.0 关联的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="1193b-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="1193b-270">如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。</span><span class="sxs-lookup"><span data-stu-id="1193b-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="1193b-271">因此，管理员应完全按照 Lync 客户端提供的方式输入子网， (通过静态或 DHCP 在网络配置期间为子网预配。 ) </span><span class="sxs-lookup"><span data-stu-id="1193b-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

