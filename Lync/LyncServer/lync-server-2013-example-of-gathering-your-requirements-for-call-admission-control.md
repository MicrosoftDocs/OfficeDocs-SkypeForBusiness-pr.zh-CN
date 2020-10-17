---
title: 收集呼叫允许控制要求的示例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89983ae54e879bdb55691b33a0512a00e5883735
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528439"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="89a94-102">示例：收集 Lync Server 2013 中的呼叫允许控制要求</span><span class="sxs-lookup"><span data-stu-id="89a94-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89a94-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="89a94-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="89a94-p101">此示例显示如何规划和实现呼叫允许控制 (CAC)。总体来说，包括以下活动：</span><span class="sxs-lookup"><span data-stu-id="89a94-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="89a94-106">标识所有网络中心和网络中枢（称为*网络区域*）。</span><span class="sxs-lookup"><span data-stu-id="89a94-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="89a94-107">确定将管理每个网络区域的 CAC 的 Lync Server 中央站点。</span><span class="sxs-lookup"><span data-stu-id="89a94-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="89a94-108">标识并定义连接到每个网络区域的*网络站点*。</span><span class="sxs-lookup"><span data-stu-id="89a94-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="89a94-109">对于每个与 WAN 的连接受带宽限制的网络站点，请描述 WAN 连接的带宽容量以及网络管理员为 Lync Server 媒体流量设置的带宽限制（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="89a94-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="89a94-110">不需要包括与 WAN 的连接不受带宽限制的站点。</span><span class="sxs-lookup"><span data-stu-id="89a94-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="89a94-111">将网络中的每个子网与一个网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="89a94-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="89a94-112">映射网络区域之间的链路。</span><span class="sxs-lookup"><span data-stu-id="89a94-112">Map the links between the network regions.</span></span> <span data-ttu-id="89a94-113">对于每个链接，描述其带宽容量以及网络管理员对 Lync Server 媒体流量所放置的任何限制。</span><span class="sxs-lookup"><span data-stu-id="89a94-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="89a94-114">定义每对网络区域之间的路由。</span><span class="sxs-lookup"><span data-stu-id="89a94-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="89a94-115">收集所需信息</span><span class="sxs-lookup"><span data-stu-id="89a94-115">Gather the Required Information</span></span>

<span data-ttu-id="89a94-116">要准备呼叫允许控制，请收集以下步骤中描述的信息：</span><span class="sxs-lookup"><span data-stu-id="89a94-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="89a94-p104">标识网络区域。网络区域代表网络中枢或网络中心。</span><span class="sxs-lookup"><span data-stu-id="89a94-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="89a94-p105">网络中枢或网络中心是计算机网络基础结构的一部分，它将网络的各个部分相互连接起来，提供在不同 LAN 或子网之间交换信息的路径。网络中枢可以将各种网络关联在一起，适用范围从较小区域到广阔的地理区域。网络中枢的容量通常大于与其连接的网络的容量。</span><span class="sxs-lookup"><span data-stu-id="89a94-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="89a94-p106">示例拓扑具有三个网络区域：北美、EMEA 和 APAC。网络区域包含网络站点的集合。与网络管理员合作以定义企业的网络区域。</span><span class="sxs-lookup"><span data-stu-id="89a94-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="89a94-125">标识每个网络区域关联的中央站点。</span><span class="sxs-lookup"><span data-stu-id="89a94-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="89a94-126">中央站点包含至少一台前端服务器，并且是 Lync Server 部署，它将管理通过网络区域的 WAN 连接的所有媒体流量的 CAC。</span><span class="sxs-lookup"><span data-stu-id="89a94-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="89a94-127">**分为三个网络区域的企业网络示例**</span><span class="sxs-lookup"><span data-stu-id="89a94-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="89a94-128">![包含3个网络区域的网络拓扑示例](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "包含3个网络区域的网络拓扑示例")</span><span class="sxs-lookup"><span data-stu-id="89a94-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="89a94-129">多协议标签交换 (MPLS) 网络应代表一个网络区域，在该网络区域中，每个物理位置都具有一个相应的网络站点。</span><span class="sxs-lookup"><span data-stu-id="89a94-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="89a94-130">有关详细信息，请参阅规划文档中的 "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">使用 Lync Server 2013 的 MPLS 网络上的呼叫允许控制</A>" 主题。</span><span class="sxs-lookup"><span data-stu-id="89a94-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="89a94-131">在上面的网络拓扑示例中，有三个网络区域，每个区域都有一个管理 CAC 的 Lync Server 中央站点。</span><span class="sxs-lookup"><span data-stu-id="89a94-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="89a94-132">按地理距离选择网络区域相应的中央站点。</span><span class="sxs-lookup"><span data-stu-id="89a94-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="89a94-133">由于网络区域内的媒体流量最多，按地理距离选择中央站点使网络区域能够独立运行，因此即使其他中央站点不可用，网络区域也可以继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="89a94-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="89a94-134">在此示例中，名为芝加哥的 Lync Server 部署是北美地区的中心网站。</span><span class="sxs-lookup"><span data-stu-id="89a94-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="89a94-135">北美的所有 Lync 用户都驻留在芝加哥部署中的服务器上。</span><span class="sxs-lookup"><span data-stu-id="89a94-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="89a94-136">下表显示了所有三个网络区域的中央站点。</span><span class="sxs-lookup"><span data-stu-id="89a94-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="89a94-137">网络区域及其关联的中央站点</span><span class="sxs-lookup"><span data-stu-id="89a94-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="89a94-138">网络区域</span><span class="sxs-lookup"><span data-stu-id="89a94-138">Network Region</span></span></th>
    <th><span data-ttu-id="89a94-139">中央站点</span><span class="sxs-lookup"><span data-stu-id="89a94-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-140">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-141">Chicago</span><span class="sxs-lookup"><span data-stu-id="89a94-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-142">EMEA</span><span class="sxs-lookup"><span data-stu-id="89a94-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="89a94-143">南京</span><span class="sxs-lookup"><span data-stu-id="89a94-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-144">APAC</span><span class="sxs-lookup"><span data-stu-id="89a94-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="89a94-145">首都</span><span class="sxs-lookup"><span data-stu-id="89a94-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="89a94-146">根据你的 Lync Server 拓扑，可以将相同的中央站点分配给多个网络区域。</span><span class="sxs-lookup"><span data-stu-id="89a94-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="89a94-p111">对于每个网络区域，标识其 WAN 连接不受带宽限制的所有网络站点（办公室或位置）。由于这些站点不受带宽限制，因此无需对其应用 CAC 带宽策略。</span><span class="sxs-lookup"><span data-stu-id="89a94-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="89a94-149">在下表显示的示例中，有三个网络站点没有受带宽限制的 WAN 链路：纽约、芝加哥和底特律。</span><span class="sxs-lookup"><span data-stu-id="89a94-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="89a94-150">不受 WAN 带宽限制的网络站点</span><span class="sxs-lookup"><span data-stu-id="89a94-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="89a94-151">网络站点</span><span class="sxs-lookup"><span data-stu-id="89a94-151">Network Site</span></span></th>
    <th><span data-ttu-id="89a94-152">网络区域</span><span class="sxs-lookup"><span data-stu-id="89a94-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-153">纽约</span><span class="sxs-lookup"><span data-stu-id="89a94-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="89a94-154">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-155">Chicago</span><span class="sxs-lookup"><span data-stu-id="89a94-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="89a94-156">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-157">底特律</span><span class="sxs-lookup"><span data-stu-id="89a94-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="89a94-158">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="89a94-159">对于每个网络区域，标识所有通过受带宽限制的 WAN 链路连接到网络区域的网络站点。</span><span class="sxs-lookup"><span data-stu-id="89a94-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="89a94-160">为了帮助确保音频和视频质量，我们建议这些受带宽限制的网络站点监控其 WAN，并拥有限制流入和流出网络区域的媒体（音频或视频）流量的 CAC 带宽策略。</span><span class="sxs-lookup"><span data-stu-id="89a94-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="89a94-161">在下表显示的示例中，有三个受 WAN 带宽限制的网络站点：波特兰、里诺和阿尔伯克基。</span><span class="sxs-lookup"><span data-stu-id="89a94-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="89a94-162">受 WAN 带宽限制的网络站点</span><span class="sxs-lookup"><span data-stu-id="89a94-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="89a94-163">网络站点</span><span class="sxs-lookup"><span data-stu-id="89a94-163">Network Site</span></span></th>
    <th><span data-ttu-id="89a94-164">网络区域</span><span class="sxs-lookup"><span data-stu-id="89a94-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-165">阿尔伯克基</span><span class="sxs-lookup"><span data-stu-id="89a94-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="89a94-166">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-167">里诺</span><span class="sxs-lookup"><span data-stu-id="89a94-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="89a94-168">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-169">波特兰</span><span class="sxs-lookup"><span data-stu-id="89a94-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="89a94-170">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="89a94-171">**CAC 网络区域北美拥有三个不受带宽限制的网络站点（芝加哥、纽约和底特律）和三个受 WAN 带宽限制的网络站点（波特兰、里诺和阿尔伯克基）。**</span><span class="sxs-lookup"><span data-stu-id="89a94-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="89a94-172">![受 WAN 带宽限制的网络站点示例](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "受 WAN 带宽限制的网络站点示例")</span><span class="sxs-lookup"><span data-stu-id="89a94-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="89a94-173">对于每个受带宽限制的 WAN 链路，需确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="89a94-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="89a94-174">要为所有并发音频会话设置的总体带宽限制。</span><span class="sxs-lookup"><span data-stu-id="89a94-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="89a94-175">如果新的音频会话将导致超出此限制，则 Lync Server 不允许会话启动。</span><span class="sxs-lookup"><span data-stu-id="89a94-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="89a94-p113">要为每个单独的音频会话设置的带宽限制。默认 CAC 带宽限制是 175 kbps，但是管理员可修改该值。</span><span class="sxs-lookup"><span data-stu-id="89a94-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="89a94-178">要为所有并发视频会话设置的总体带宽限制。</span><span class="sxs-lookup"><span data-stu-id="89a94-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="89a94-179">如果新的视频会话将导致超出此限制，则 Lync Server 不允许会话启动。</span><span class="sxs-lookup"><span data-stu-id="89a94-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="89a94-p115">要为每个单独的视频会话设置的带宽限制。默认 CAC 带宽限制是 700 kbps，但是管理员可修改该值。</span><span class="sxs-lookup"><span data-stu-id="89a94-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="89a94-182">具有 WAN 带宽限制信息（带宽单位：kbps）的网络站点</span><span class="sxs-lookup"><span data-stu-id="89a94-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="89a94-183">网络站点</span><span class="sxs-lookup"><span data-stu-id="89a94-183">Network Site</span></span></th>
    <th><span data-ttu-id="89a94-184">网络区域</span><span class="sxs-lookup"><span data-stu-id="89a94-184">Network Region</span></span></th>
    <th><span data-ttu-id="89a94-185">BW 限制</span><span class="sxs-lookup"><span data-stu-id="89a94-185">BW Limit</span></span></th>
    <th><span data-ttu-id="89a94-186">音频限制</span><span class="sxs-lookup"><span data-stu-id="89a94-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="89a94-187">音频会话限制</span><span class="sxs-lookup"><span data-stu-id="89a94-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="89a94-188">视频限制</span><span class="sxs-lookup"><span data-stu-id="89a94-188">Video Limit</span></span></th>
    <th><span data-ttu-id="89a94-189">视频会话限制</span><span class="sxs-lookup"><span data-stu-id="89a94-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-190">阿尔伯克基</span><span class="sxs-lookup"><span data-stu-id="89a94-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="89a94-191">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-192">5,000</span><span class="sxs-lookup"><span data-stu-id="89a94-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-193">2,000</span><span class="sxs-lookup"><span data-stu-id="89a94-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-194">175</span><span class="sxs-lookup"><span data-stu-id="89a94-194">175</span></span></p></td>
    <td><p><span data-ttu-id="89a94-195">1400</span><span class="sxs-lookup"><span data-stu-id="89a94-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="89a94-196">700</span><span class="sxs-lookup"><span data-stu-id="89a94-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-197">里诺</span><span class="sxs-lookup"><span data-stu-id="89a94-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="89a94-198">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-199">10,000</span><span class="sxs-lookup"><span data-stu-id="89a94-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-200">4000</span><span class="sxs-lookup"><span data-stu-id="89a94-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-201">175</span><span class="sxs-lookup"><span data-stu-id="89a94-201">175</span></span></p></td>
    <td><p><span data-ttu-id="89a94-202">2800</span><span class="sxs-lookup"><span data-stu-id="89a94-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="89a94-203">700</span><span class="sxs-lookup"><span data-stu-id="89a94-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-204">波特兰</span><span class="sxs-lookup"><span data-stu-id="89a94-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="89a94-205">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-206">5,000</span><span class="sxs-lookup"><span data-stu-id="89a94-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-207">4000</span><span class="sxs-lookup"><span data-stu-id="89a94-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-208">175</span><span class="sxs-lookup"><span data-stu-id="89a94-208">175</span></span></p></td>
    <td><p><span data-ttu-id="89a94-209">2800</span><span class="sxs-lookup"><span data-stu-id="89a94-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="89a94-210">700</span><span class="sxs-lookup"><span data-stu-id="89a94-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-211">纽约</span><span class="sxs-lookup"><span data-stu-id="89a94-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="89a94-212">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-213">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-214">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-215">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-216">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-217">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-218">Chicago</span><span class="sxs-lookup"><span data-stu-id="89a94-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="89a94-219">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-220">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-221">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-222">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-223">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-224">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-225">底特律</span><span class="sxs-lookup"><span data-stu-id="89a94-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="89a94-226">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-227">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-228">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-229">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-230">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-231">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="89a94-232">对于网络中的每个子网，指定其关联的网络站点。</span><span class="sxs-lookup"><span data-stu-id="89a94-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="89a94-p116">即使网络站点不受带宽限制，网络中的每个子网也必须与一个网络站点相关联。这是因为呼叫允许控制使用子网信息来确定终结点所在的网络站点。确定会话双方的位置后，呼叫允许控制可以确定是否有足够的带宽来建立呼叫。当通过没有带宽限制的链路建立会话时，会生成警报。</span><span class="sxs-lookup"><span data-stu-id="89a94-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="89a94-237">如果部署音频/视频边缘服务器，则每台边缘服务器的公共 IP 地址都必须与部署边缘服务器的网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="89a94-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="89a94-238">必须将 A/V 边缘服务器的每个公共 IP 地址作为子网掩码为 32 的子网添加到网络配置设置中。</span><span class="sxs-lookup"><span data-stu-id="89a94-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="89a94-239">例如，如果在芝加哥部署 A/V 边缘服务器，则为这些服务器的每个外部 IP 地址创建一个子网掩码为 32 的子网，并将网络站点芝加哥与这些子网相关联。</span><span class="sxs-lookup"><span data-stu-id="89a94-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="89a94-240">有关公用 IP 地址的详细信息，请参阅规划文档中的 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</A> 。</span><span class="sxs-lookup"><span data-stu-id="89a94-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="89a94-p118">生成关键运行状况指示器 (KHI) 警报，指定存在于网络中但不与子网关联的 IP 地址列表，或指定包含 IP 地址的子网不与网络站点关联。该警报在 8 小时内只产生一次。相关的警报信息和示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="89a94-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="89a94-244"><STRONG>源：</STRONG> CS 带宽策略服务 (核心) </span><span class="sxs-lookup"><span data-stu-id="89a94-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="89a94-245"><STRONG>事件编号：</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="89a94-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="89a94-246"><STRONG>级别：</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="89a94-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="89a94-247"><STRONG>说明：</STRONG> 以下 IP 地址的子网： &lt; 未配置 IP 地址列表， &gt; 或者子网未与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="89a94-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="89a94-248"><STRONG>原因：</STRONG> 网络配置设置中缺少对应 IP 地址的子网，或者子网未与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="89a94-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="89a94-249"><STRONG>解决方法：</STRONG> 将与前面的 IP 地址列表对应的子网添加到网络配置设置中，并将每个子网与一个网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="89a94-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="89a94-p119">例如，如果警报中的 IP 地址列表指定 10.121.248.226 和 10.121.249.20，则可能是这些 IP 地址没有与子网关联，或者与其关联的子网不属于网络站点。如果 10.121.248.0/24 和 10.121.249.0/24 是与这些地址对应的子网，则可按如下所示解决此问题：</span><span class="sxs-lookup"><span data-stu-id="89a94-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="89a94-252">确保 IP 地址 10.121.248.226 与子网 10.121.248.0/24 关联，IP 地址 10.121.249.20 与子网 10.121.249.0/24 关联。</span><span class="sxs-lookup"><span data-stu-id="89a94-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="89a94-253">确保子网 10.121.248.0/24 和 10.121.249.0/24 分别与一个网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="89a94-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="89a94-254">网络站点和关联子网（带宽单位：kbps）</span><span class="sxs-lookup"><span data-stu-id="89a94-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="89a94-255">网络站点</span><span class="sxs-lookup"><span data-stu-id="89a94-255">Network Site</span></span></th>
    <th><span data-ttu-id="89a94-256">网络区域</span><span class="sxs-lookup"><span data-stu-id="89a94-256">Network Region</span></span></th>
    <th><span data-ttu-id="89a94-257">BW 限制</span><span class="sxs-lookup"><span data-stu-id="89a94-257">BW Limit</span></span></th>
    <th><span data-ttu-id="89a94-258">音频限制</span><span class="sxs-lookup"><span data-stu-id="89a94-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="89a94-259">音频会话限制</span><span class="sxs-lookup"><span data-stu-id="89a94-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="89a94-260">视频限制</span><span class="sxs-lookup"><span data-stu-id="89a94-260">Video Limit</span></span></th>
    <th><span data-ttu-id="89a94-261">视频会话限制</span><span class="sxs-lookup"><span data-stu-id="89a94-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="89a94-262">子网</span><span class="sxs-lookup"><span data-stu-id="89a94-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-263">阿尔伯克基</span><span class="sxs-lookup"><span data-stu-id="89a94-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="89a94-264">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-265">5,000</span><span class="sxs-lookup"><span data-stu-id="89a94-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-266">2,000</span><span class="sxs-lookup"><span data-stu-id="89a94-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-267">175</span><span class="sxs-lookup"><span data-stu-id="89a94-267">175</span></span></p></td>
    <td><p><span data-ttu-id="89a94-268">1400</span><span class="sxs-lookup"><span data-stu-id="89a94-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="89a94-269">700</span><span class="sxs-lookup"><span data-stu-id="89a94-269">700</span></span></p></td>
    <td><p><span data-ttu-id="89a94-270">172.29.79.0/23、157.57.215.0/25、172.29.90.0/23、172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="89a94-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-271">里诺</span><span class="sxs-lookup"><span data-stu-id="89a94-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="89a94-272">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-273">10,000</span><span class="sxs-lookup"><span data-stu-id="89a94-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-274">4000</span><span class="sxs-lookup"><span data-stu-id="89a94-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-275">175</span><span class="sxs-lookup"><span data-stu-id="89a94-275">175</span></span></p></td>
    <td><p><span data-ttu-id="89a94-276">2800</span><span class="sxs-lookup"><span data-stu-id="89a94-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="89a94-277">700</span><span class="sxs-lookup"><span data-stu-id="89a94-277">700</span></span></p></td>
    <td><p><span data-ttu-id="89a94-278">157.57.210.0/23、172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="89a94-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-279">波特兰</span><span class="sxs-lookup"><span data-stu-id="89a94-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="89a94-280">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-281">5,000</span><span class="sxs-lookup"><span data-stu-id="89a94-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-282">4000</span><span class="sxs-lookup"><span data-stu-id="89a94-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-283">175</span><span class="sxs-lookup"><span data-stu-id="89a94-283">175</span></span></p></td>
    <td><p><span data-ttu-id="89a94-284">2800</span><span class="sxs-lookup"><span data-stu-id="89a94-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="89a94-285">700</span><span class="sxs-lookup"><span data-stu-id="89a94-285">700</span></span></p></td>
    <td><p><span data-ttu-id="89a94-286">172.29.77.0/24 10.71.108.0/24、157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="89a94-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-287">纽约</span><span class="sxs-lookup"><span data-stu-id="89a94-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="89a94-288">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-289">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-290">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-291">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-292">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-293">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-294">172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="89a94-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-295">Chicago</span><span class="sxs-lookup"><span data-stu-id="89a94-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="89a94-296">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-297">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-298">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-299">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-300">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-301">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-302">157.57.211.0/23、172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="89a94-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-303">底特律</span><span class="sxs-lookup"><span data-stu-id="89a94-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="89a94-304">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-305">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-306">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-307">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-308">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-309">（没有限制）</span><span class="sxs-lookup"><span data-stu-id="89a94-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="89a94-310">172.29.78.0/24 10.71.109.0/24、157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="89a94-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="89a94-311">在 Lync Server 呼叫许可控制中，网络区域之间的连接称为 *区域链接*。</span><span class="sxs-lookup"><span data-stu-id="89a94-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="89a94-312">对于每个区域链路，按照对网络站点执行的操作，确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="89a94-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="89a94-313">要为所有并发音频会话设置的总体带宽限制。</span><span class="sxs-lookup"><span data-stu-id="89a94-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="89a94-314">如果新的音频会话将导致超出此限制，则 Lync Server 不允许会话启动。</span><span class="sxs-lookup"><span data-stu-id="89a94-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="89a94-p122">要为每个单独的音频会话设置的带宽限制。默认 CAC 带宽限制是 175 kbps，但是管理员可修改该值。</span><span class="sxs-lookup"><span data-stu-id="89a94-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="89a94-317">要为所有并发视频会话设置的总体带宽限制。</span><span class="sxs-lookup"><span data-stu-id="89a94-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="89a94-318">如果新的视频会话将导致超出此限制，则 Lync Server 不允许会话启动。</span><span class="sxs-lookup"><span data-stu-id="89a94-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="89a94-p124">要为每个单独的视频会话设置的带宽限制。默认 CAC 带宽限制是 700 kbps，但是管理员可修改该值。</span><span class="sxs-lookup"><span data-stu-id="89a94-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="89a94-321">**具有关联带宽限制的网络区域链路**</span><span class="sxs-lookup"><span data-stu-id="89a94-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="89a94-322">![3个地区之间的限制示例](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3个地区之间的限制示例")</span><span class="sxs-lookup"><span data-stu-id="89a94-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="89a94-323">区域链路带宽信息（带宽单位：kbps）</span><span class="sxs-lookup"><span data-stu-id="89a94-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="89a94-324">区域链路名称</span><span class="sxs-lookup"><span data-stu-id="89a94-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="89a94-325">第一个区域</span><span class="sxs-lookup"><span data-stu-id="89a94-325">First Region</span></span></th>
    <th><span data-ttu-id="89a94-326">第二个区域</span><span class="sxs-lookup"><span data-stu-id="89a94-326">Second Region</span></span></th>
    <th><span data-ttu-id="89a94-327">BW 限制</span><span class="sxs-lookup"><span data-stu-id="89a94-327">BW Limit</span></span></th>
    <th><span data-ttu-id="89a94-328">音频限制</span><span class="sxs-lookup"><span data-stu-id="89a94-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="89a94-329">音频会话限制</span><span class="sxs-lookup"><span data-stu-id="89a94-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="89a94-330">视频限制</span><span class="sxs-lookup"><span data-stu-id="89a94-330">Video Limit</span></span></th>
    <th><span data-ttu-id="89a94-331">视频会话限制</span><span class="sxs-lookup"><span data-stu-id="89a94-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-332">NA-EMEA-链接</span><span class="sxs-lookup"><span data-stu-id="89a94-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="89a94-333">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-334">EMEA</span><span class="sxs-lookup"><span data-stu-id="89a94-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="89a94-335">50,000</span><span class="sxs-lookup"><span data-stu-id="89a94-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-336">20,000</span><span class="sxs-lookup"><span data-stu-id="89a94-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-337">175</span><span class="sxs-lookup"><span data-stu-id="89a94-337">175</span></span></p></td>
    <td><p><span data-ttu-id="89a94-338">14000</span><span class="sxs-lookup"><span data-stu-id="89a94-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-339">700</span><span class="sxs-lookup"><span data-stu-id="89a94-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-340">EMEA-APAC-链接</span><span class="sxs-lookup"><span data-stu-id="89a94-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="89a94-341">EMEA</span><span class="sxs-lookup"><span data-stu-id="89a94-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="89a94-342">APAC</span><span class="sxs-lookup"><span data-stu-id="89a94-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="89a94-343">25,000</span><span class="sxs-lookup"><span data-stu-id="89a94-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-344">10,000</span><span class="sxs-lookup"><span data-stu-id="89a94-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-345">175</span><span class="sxs-lookup"><span data-stu-id="89a94-345">175</span></span></p></td>
    <td><p><span data-ttu-id="89a94-346">7000</span><span class="sxs-lookup"><span data-stu-id="89a94-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-347">700</span><span class="sxs-lookup"><span data-stu-id="89a94-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="89a94-348">定义每对网络区域之间的路由。</span><span class="sxs-lookup"><span data-stu-id="89a94-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="89a94-349">北美和 APAC 区域之间的路由需要两个链路，因为没有直接连接这两个区域的区域链路。</span><span class="sxs-lookup"><span data-stu-id="89a94-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="89a94-350">区域路由</span><span class="sxs-lookup"><span data-stu-id="89a94-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="89a94-351">区域路由名称</span><span class="sxs-lookup"><span data-stu-id="89a94-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="89a94-352">第一个区域</span><span class="sxs-lookup"><span data-stu-id="89a94-352">First Region</span></span></th>
    <th><span data-ttu-id="89a94-353">第二个区域</span><span class="sxs-lookup"><span data-stu-id="89a94-353">Second Region</span></span></th>
    <th><span data-ttu-id="89a94-354">区域链路</span><span class="sxs-lookup"><span data-stu-id="89a94-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-355">NA-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="89a94-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="89a94-356">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-357">EMEA</span><span class="sxs-lookup"><span data-stu-id="89a94-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="89a94-358">NA-EMEA-链接</span><span class="sxs-lookup"><span data-stu-id="89a94-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="89a94-359">EMEA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="89a94-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="89a94-360">EMEA</span><span class="sxs-lookup"><span data-stu-id="89a94-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="89a94-361">APAC</span><span class="sxs-lookup"><span data-stu-id="89a94-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="89a94-362">EMEA-APAC-链接</span><span class="sxs-lookup"><span data-stu-id="89a94-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-363">NA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="89a94-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="89a94-364">北美</span><span class="sxs-lookup"><span data-stu-id="89a94-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="89a94-365">APAC</span><span class="sxs-lookup"><span data-stu-id="89a94-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="89a94-366">NA-EMEA-LINK、EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="89a94-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="89a94-367">对于通过单链路（称为*站点间* 链路）直接进行连接的每对网络站点，需确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="89a94-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="89a94-368">要为所有并发音频会话设置的总体带宽限制。</span><span class="sxs-lookup"><span data-stu-id="89a94-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="89a94-369">如果新的音频会话将导致超出此限制，则 Lync Server 不允许会话启动。</span><span class="sxs-lookup"><span data-stu-id="89a94-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="89a94-p126">要为每个单独的音频会话设置的带宽限制。默认 CAC 带宽限制是 175 kbps，但是管理员可修改该值。</span><span class="sxs-lookup"><span data-stu-id="89a94-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="89a94-372">要为所有并发视频会话设置的总体带宽限制。</span><span class="sxs-lookup"><span data-stu-id="89a94-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="89a94-373">如果新的视频会话将导致超出此限制，则 Lync Server 不允许会话启动。</span><span class="sxs-lookup"><span data-stu-id="89a94-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="89a94-p128">要为每个单独的视频会话设置的带宽限制。默认 CAC 带宽限制是 700 kbps，但是管理员可修改该值。</span><span class="sxs-lookup"><span data-stu-id="89a94-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="89a94-376">**CAC 网络区域北美显示里诺和阿尔伯克基之间的站点间链路的带宽容量和带宽限制。**</span><span class="sxs-lookup"><span data-stu-id="89a94-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="89a94-377">![受 WAN 带宽限制的网络站点示例](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "受 WAN 带宽限制的网络站点示例")</span><span class="sxs-lookup"><span data-stu-id="89a94-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="89a94-378">两个网络站点间的站点间链路的带宽信息（带宽单位：kbps）</span><span class="sxs-lookup"><span data-stu-id="89a94-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="89a94-379">站点间链路名称</span><span class="sxs-lookup"><span data-stu-id="89a94-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="89a94-380">第一个站点</span><span class="sxs-lookup"><span data-stu-id="89a94-380">First Site</span></span></th>
    <th><span data-ttu-id="89a94-381">第二个站点</span><span class="sxs-lookup"><span data-stu-id="89a94-381">Second Site</span></span></th>
    <th><span data-ttu-id="89a94-382">BW 限制</span><span class="sxs-lookup"><span data-stu-id="89a94-382">BW Limit</span></span></th>
    <th><span data-ttu-id="89a94-383">音频限制</span><span class="sxs-lookup"><span data-stu-id="89a94-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="89a94-384">音频会话限制</span><span class="sxs-lookup"><span data-stu-id="89a94-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="89a94-385">视频限制</span><span class="sxs-lookup"><span data-stu-id="89a94-385">Video Limit</span></span></th>
    <th><span data-ttu-id="89a94-386">视频会话限制</span><span class="sxs-lookup"><span data-stu-id="89a94-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="89a94-387">里诺-Albu-站点间链接</span><span class="sxs-lookup"><span data-stu-id="89a94-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="89a94-388">里诺</span><span class="sxs-lookup"><span data-stu-id="89a94-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="89a94-389">阿尔伯克基</span><span class="sxs-lookup"><span data-stu-id="89a94-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="89a94-390">20,000</span><span class="sxs-lookup"><span data-stu-id="89a94-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-391">12000</span><span class="sxs-lookup"><span data-stu-id="89a94-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-392">175</span><span class="sxs-lookup"><span data-stu-id="89a94-392">175</span></span></p></td>
    <td><p><span data-ttu-id="89a94-393">5,000</span><span class="sxs-lookup"><span data-stu-id="89a94-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="89a94-394">700</span><span class="sxs-lookup"><span data-stu-id="89a94-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="89a94-395">后续步骤</span><span class="sxs-lookup"><span data-stu-id="89a94-395">Next Steps</span></span>

<span data-ttu-id="89a94-396">收集所需的信息后，您可以使用 Lync Server 命令行管理程序或 Lync Server 控制面板执行 CAC 部署。</span><span class="sxs-lookup"><span data-stu-id="89a94-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="89a94-397">虽然您可以使用 Lync Server 控制面板执行大多数网络配置任务，但若要创建子网和站点间链接，则必须使用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="89a94-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="89a94-398">有关详细信息，请参阅 Lync Server 命令行管理程序文档，了解 <STRONG>CsNetworkSubnet</STRONG> Cmdlet 和 <STRONG>new-csnetworkintersitepolicy</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="89a94-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

