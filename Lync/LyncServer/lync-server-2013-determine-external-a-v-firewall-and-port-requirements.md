---
title: Lync Server 2013：确定外部 A/V 防火墙和端口要求
description: Lync Server 2013：确定外部 A/V 防火墙和端口要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550928"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="23c79-103">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="23c79-103">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23c79-104">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="23c79-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="23c79-105">音频/视频 (A/V) 通信可能是一种复杂的。</span><span class="sxs-lookup"><span data-stu-id="23c79-105">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="23c79-106">由于在 A/V 中使用的协议的性质以及客户端和服务器使用这些协议的方式，因此有一个特殊的部分来说明客户端和服务器版本之间的差异。</span><span class="sxs-lookup"><span data-stu-id="23c79-106">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="23c79-107">使用下面的 A/V 防火墙和端口表来确定防火墙要求以及要打开的端口。</span><span class="sxs-lookup"><span data-stu-id="23c79-107">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="23c79-108">然后，检查网络地址转换 (NAT) 术语，因为可以通过多种不同方式实现 NAT。</span><span class="sxs-lookup"><span data-stu-id="23c79-108">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="23c79-109">有关防火墙端口设置的详细示例，请参阅 [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)中的参考体系结构。</span><span class="sxs-lookup"><span data-stu-id="23c79-109">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="23c79-110">音频/视频和媒体流量中的 UDP 和 TCP 的常规协议用法</span><span class="sxs-lookup"><span data-stu-id="23c79-110">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23c79-111">音频/视频传输</span><span class="sxs-lookup"><span data-stu-id="23c79-111">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="23c79-112">用法</span><span class="sxs-lookup"><span data-stu-id="23c79-112">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23c79-113">UDP</span><span class="sxs-lookup"><span data-stu-id="23c79-113">UDP</span></span></p></td>
<td><p><span data-ttu-id="23c79-114">音频和视频的首选传输层协议</span><span class="sxs-lookup"><span data-stu-id="23c79-114">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23c79-115">TCP</span><span class="sxs-lookup"><span data-stu-id="23c79-115">TCP</span></span></p></td>
<td><p><span data-ttu-id="23c79-116">音频和视频的回退传输层协议</span><span class="sxs-lookup"><span data-stu-id="23c79-116">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="23c79-117">适用于 Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的应用程序共享所需的传输层协议</span><span class="sxs-lookup"><span data-stu-id="23c79-117">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="23c79-118">文件传输到 Lync Server 2010 和 Lync Server 2013 所需的传输层协议</span><span class="sxs-lookup"><span data-stu-id="23c79-118">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="23c79-119">外部用户访问的外部 A/V 防火墙端口要求</span><span class="sxs-lookup"><span data-stu-id="23c79-119">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="23c79-120">外部 (和内部) SIP 和会议接口的防火墙端口要求是一致的，无论客户端的版本或联合合作伙伴的版本如何。</span><span class="sxs-lookup"><span data-stu-id="23c79-120">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="23c79-121">而音频/视频边缘外部接口却并非如此。</span><span class="sxs-lookup"><span data-stu-id="23c79-121">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="23c79-122">对于使用 Office 通信服务器2007的联盟，A/V 边缘服务要求外部防火墙规则允许在50000至59999端口范围内的 RTP/TCP 和 RTP/UDP 通信在两个方向流动。</span><span class="sxs-lookup"><span data-stu-id="23c79-122">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="23c79-123">上表假定 Lync Server 2013 是主联合身份验证伙伴，并且将其配置为与列出的其他联合合作伙伴类型之一进行通信。</span><span class="sxs-lookup"><span data-stu-id="23c79-123">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="23c79-124">若要配置59999的音频/视频端口范围，必须考虑端口范围将包含用于与联合身份验证伙伴通信的源端口。</span><span class="sxs-lookup"><span data-stu-id="23c79-124">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="23c79-125">在详细情况下，请考虑从联合身份验证合作伙伴启动通信。</span><span class="sxs-lookup"><span data-stu-id="23c79-125">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="23c79-126">从59999范围内的 A/V 边缘服务端口进行的通信将连接到合作伙伴的 A/V 边缘服务的预期端口 TCP 443。</span><span class="sxs-lookup"><span data-stu-id="23c79-126">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="23c79-127">相反，到 A/V 边缘服务端口 TCP 443 的入站通信的源端口范围为 50000-59999。</span><span class="sxs-lookup"><span data-stu-id="23c79-127">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="23c79-128">防火墙管理的不同防火墙和策略可能只需要配置目标规则，或者可能需要配置源和目标。</span><span class="sxs-lookup"><span data-stu-id="23c79-128">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="23c79-129">如果您的要求仅适用于目标端口，音频/视频要求为：</span><span class="sxs-lookup"><span data-stu-id="23c79-129">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23c79-130">源 IP</span><span class="sxs-lookup"><span data-stu-id="23c79-130">Source IP</span></span></th>
<th><span data-ttu-id="23c79-131">目标 IP</span><span class="sxs-lookup"><span data-stu-id="23c79-131">Destination IP</span></span></th>
<th><span data-ttu-id="23c79-132">目标端口</span><span class="sxs-lookup"><span data-stu-id="23c79-132">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23c79-133">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="23c79-133">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="23c79-134">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-134">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-135">TCP 443</span><span class="sxs-lookup"><span data-stu-id="23c79-135">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23c79-136">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="23c79-136">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="23c79-137">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-137">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-138">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="23c79-138">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23c79-139">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-139">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-140">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="23c79-140">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="23c79-141">TCP 443</span><span class="sxs-lookup"><span data-stu-id="23c79-141">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23c79-142">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-142">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-143">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="23c79-143">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="23c79-144">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="23c79-144">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23c79-145">如果您的策略需要入站和出站防火墙规则定义，音频/视频要求为：</span><span class="sxs-lookup"><span data-stu-id="23c79-145">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23c79-146">源 IP</span><span class="sxs-lookup"><span data-stu-id="23c79-146">Source IP</span></span></th>
<th><span data-ttu-id="23c79-147">目标 IP</span><span class="sxs-lookup"><span data-stu-id="23c79-147">Destination IP</span></span></th>
<th><span data-ttu-id="23c79-148">源端口</span><span class="sxs-lookup"><span data-stu-id="23c79-148">Source Port</span></span></th>
<th><span data-ttu-id="23c79-149">目标端口</span><span class="sxs-lookup"><span data-stu-id="23c79-149">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23c79-150">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="23c79-150">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="23c79-151">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-151">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-152">TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="23c79-152">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="23c79-153">TCP 443</span><span class="sxs-lookup"><span data-stu-id="23c79-153">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23c79-154">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="23c79-154">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="23c79-155">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-155">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="23c79-156">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="23c79-157">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="23c79-157">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23c79-158">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-158">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-159">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="23c79-159">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="23c79-160">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-160">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-161">TCP 443</span><span class="sxs-lookup"><span data-stu-id="23c79-161">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23c79-162">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-162">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-163">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="23c79-163">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="23c79-164">任何</span><span class="sxs-lookup"><span data-stu-id="23c79-164">Any</span></span></p></td>
<td><p><span data-ttu-id="23c79-165">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="23c79-165">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="23c79-166">Microsoft Office 通信服务器2007需要略有不同的配置。</span><span class="sxs-lookup"><span data-stu-id="23c79-166">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="23c79-167">TCP 和 UDP 端口范围为 50000-59999 必须打开入站和出站。</span><span class="sxs-lookup"><span data-stu-id="23c79-167">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="23c79-168">此要求仅适用于 Office Communicator 2007。</span><span class="sxs-lookup"><span data-stu-id="23c79-168">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="23c79-169">Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 仅要求 TCP 范围 50000-59999 打开出站。</span><span class="sxs-lookup"><span data-stu-id="23c79-169">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="23c79-170">边缘服务的 NAT 要求</span><span class="sxs-lookup"><span data-stu-id="23c79-170">NAT requirements for the Edge service</span></span>

<span data-ttu-id="23c79-171">如果您选择为边缘服务配置不可路由的专用 IP 地址，则以下 NAT 要求适用：</span><span class="sxs-lookup"><span data-stu-id="23c79-171">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="23c79-172">NAT 仅可用于 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="23c79-172">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="23c79-173">NAT 在硬件负载平衡 (HLB) 边缘拓扑中不受支持。</span><span class="sxs-lookup"><span data-stu-id="23c79-173">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="23c79-174">NAT 只能在外部边缘接口上使用。</span><span class="sxs-lookup"><span data-stu-id="23c79-174">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="23c79-175">内部边缘接口上不支持 NAT。</span><span class="sxs-lookup"><span data-stu-id="23c79-175">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="23c79-176">对于传入和传出流量，NAT 必须是对称的。</span><span class="sxs-lookup"><span data-stu-id="23c79-176">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="23c79-177">对于来自 Internet 的流量，NAT 必须将目标 IP 地址从 A/V 边缘服务的已启用 NAT 的公共 IP 地址更改为其外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23c79-177">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="23c79-178">源 IP 地址必须保持不变，以便 A/V 边缘服务可以找到最佳媒体路径。</span><span class="sxs-lookup"><span data-stu-id="23c79-178">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="23c79-179">例如，在下图中的入站方向上，公用 IP 地址131.107.155.30 已更改为外部 (private) IP address 10.45.16.10。</span><span class="sxs-lookup"><span data-stu-id="23c79-179">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="23c79-180">源 IP 地址保持不变。</span><span class="sxs-lookup"><span data-stu-id="23c79-180">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="23c79-181">对于从 A/V 边缘服务到 Internet 的流量，NAT 必须将源 IP 地址从 A/V 边缘服务的外部 IP 地址更改为启用了 NAT 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23c79-181">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="23c79-182">例如，在下图中的出站方向上，外部 (私有) IP 地址10.45.16.10 已更改为公用 IP 地址131.107.155.30。</span><span class="sxs-lookup"><span data-stu-id="23c79-182">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="23c79-183">**下图显示了 NAT 如何更改入站流量的目标 IP 地址和出站流量的源 IP 地址。**</span><span class="sxs-lookup"><span data-stu-id="23c79-183">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="23c79-184">![更改目标/源 IP 地址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "更改目标/源 IP 地址")</span><span class="sxs-lookup"><span data-stu-id="23c79-184">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="23c79-185">要点包括：</span><span class="sxs-lookup"><span data-stu-id="23c79-185">The key points are:</span></span>

  - <span data-ttu-id="23c79-186">入站到运行 A/V 边缘服务的服务器的通信，源 IP 地址不会发生更改，但目标 IP 地址将从131.107.155.30 更改为10.45.16.10 的转换 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23c79-186">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="23c79-187">从运行 A/V 边缘服务的服务器出站的流量返回到工作站，源 IP 地址将从服务器的公共 IP 地址更改为运行 A/V 边缘服务的服务器的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23c79-187">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="23c79-188">目标 IP 仍为工作站的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23c79-188">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="23c79-189">在数据包离开第一个 NAT 设备出站后，NAT 设备上的规则会将运行 A/V 边缘服务的服务器的源 IP 地址更改为运行 A/V 边缘服务的外部接口 IP 地址 (10.45.16.10) 到其公共 IP 地址 (131.107.155.30) 。</span><span class="sxs-lookup"><span data-stu-id="23c79-189">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

