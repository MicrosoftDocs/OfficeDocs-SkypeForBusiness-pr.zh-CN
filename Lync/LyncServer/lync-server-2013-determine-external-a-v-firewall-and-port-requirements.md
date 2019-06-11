---
title: Lync Server 2013：确定外部 A/V 防火墙和端口要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b278c60eaca69fd17508d0e82198a002484ce586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="5f9c3-102">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="5f9c3-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f9c3-103">_**主题上次修改时间:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="5f9c3-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="5f9c3-104">音频/视频 (A/V) 通信可能很复杂。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="5f9c3-105">由于在 A/V 中使用的协议的性质以及客户端和服务器使用这些协议的方式, 因此有一个特殊的部分可以帮助解释客户端和服务器版本之间的差异。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="5f9c3-106">使用以下 A/V 防火墙和端口表确定防火墙要求和要打开的端口。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="5f9c3-107">然后, 查看网络地址转换 (NAT) 术语, 因为 NAT 可以采用多种不同的方式实现。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="5f9c3-108">有关防火墙端口设置的详细示例, 请参阅[Lync Server 2013 中用于外部用户访问的方案](lync-server-2013-scenarios-for-external-user-access.md)中的参考体系结构。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="5f9c3-109">音频/视频和媒体流量中的 UDP 和 TCP 的常规协议用法</span><span class="sxs-lookup"><span data-stu-id="5f9c3-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f9c3-110">音频/视频传输</span><span class="sxs-lookup"><span data-stu-id="5f9c3-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="5f9c3-111">使用</span><span class="sxs-lookup"><span data-stu-id="5f9c3-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f9c3-112">UDP</span><span class="sxs-lookup"><span data-stu-id="5f9c3-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-113">音频和视频的首选传输层协议</span><span class="sxs-lookup"><span data-stu-id="5f9c3-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9c3-114">TCP</span><span class="sxs-lookup"><span data-stu-id="5f9c3-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-115">音频和视频的回退传输层协议</span><span class="sxs-lookup"><span data-stu-id="5f9c3-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="5f9c3-116">Office 通信服务器的应用程序共享所需的传输层协议 2007 R2、Lync Server 2010 和 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f9c3-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="5f9c3-117">将文件传输到 Lync Server 2010 和 Lync Server 2013 所需的传输层协议</span><span class="sxs-lookup"><span data-stu-id="5f9c3-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="5f9c3-118">外部用户访问的外部 A/V 防火墙端口要求</span><span class="sxs-lookup"><span data-stu-id="5f9c3-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="5f9c3-119">无论客户端的版本或联合合作伙伴的版本如何, 外部 (和内部) SIP 和会议界面的防火墙端口要求都是一致的。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="5f9c3-120">音频/视频边缘外部界面同样不成立。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="5f9c3-121">对于使用 Office 通信服务器2007的联盟, A/V 边缘服务要求外部防火墙规则允许50000至59999端口范围内的 RTP/TCP 和 RTP/UDP 流量双向流动。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="5f9c3-122">上表假设 Lync Server 2013 是主联合身份验证伙伴, 并且配置为与列出的其他联合合作伙伴类型之一进行通信。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="5f9c3-123">配置 50000-59999 的音频/视频端口范围必须考虑到端口范围将包含用于与联合身份验证伙伴通信的源端口。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="5f9c3-124">在详细信息中, 请考虑从联合身份验证伙伴发起通信。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="5f9c3-125">从59999范围内的 A/V 边缘服务端口进行的通信将连接到合作伙伴的 A/V 边缘服务的预期端口 TCP 443。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="5f9c3-126">相反, 到 A/V 边缘服务端口 TCP 443 的入站流量将具有59999中的源端口。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="5f9c3-127">防火墙管理的不同防火墙和策略可能只需要配置目标规则, 也可能需要配置源和目标。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="5f9c3-128">如果您的要求仅适用于目的地端口, 音频/视频要求如下:</span><span class="sxs-lookup"><span data-stu-id="5f9c3-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f9c3-129">源 IP</span><span class="sxs-lookup"><span data-stu-id="5f9c3-129">Source IP</span></span></th>
<th><span data-ttu-id="5f9c3-130">目标 IP</span><span class="sxs-lookup"><span data-stu-id="5f9c3-130">Destination IP</span></span></th>
<th><span data-ttu-id="5f9c3-131">目标端口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f9c3-132">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-133">任意</span><span class="sxs-lookup"><span data-stu-id="5f9c3-133">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="5f9c3-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9c3-135">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-136">任意</span><span class="sxs-lookup"><span data-stu-id="5f9c3-136">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5f9c3-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9c3-138">任意</span><span class="sxs-lookup"><span data-stu-id="5f9c3-138">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-139">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="5f9c3-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9c3-141">任何</span><span class="sxs-lookup"><span data-stu-id="5f9c3-141">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-142">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5f9c3-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5f9c3-144">如果你的策略需要入站和出站防火墙规则定义, 音频/视频要求如下:</span><span class="sxs-lookup"><span data-stu-id="5f9c3-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f9c3-145">源 IP</span><span class="sxs-lookup"><span data-stu-id="5f9c3-145">Source IP</span></span></th>
<th><span data-ttu-id="5f9c3-146">目标 IP</span><span class="sxs-lookup"><span data-stu-id="5f9c3-146">Destination IP</span></span></th>
<th><span data-ttu-id="5f9c3-147">源端口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-147">Source Port</span></span></th>
<th><span data-ttu-id="5f9c3-148">目标端口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f9c3-149">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-150">任何</span><span class="sxs-lookup"><span data-stu-id="5f9c3-150">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-151">TCP 50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="5f9c3-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="5f9c3-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9c3-153">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-154">任意</span><span class="sxs-lookup"><span data-stu-id="5f9c3-154">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5f9c3-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5f9c3-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9c3-157">任意</span><span class="sxs-lookup"><span data-stu-id="5f9c3-157">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-158">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-159">任意</span><span class="sxs-lookup"><span data-stu-id="5f9c3-159">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="5f9c3-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9c3-161">任何</span><span class="sxs-lookup"><span data-stu-id="5f9c3-161">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-162">A/V 边缘服务接口</span><span class="sxs-lookup"><span data-stu-id="5f9c3-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-163">任意</span><span class="sxs-lookup"><span data-stu-id="5f9c3-163">Any</span></span></p></td>
<td><p><span data-ttu-id="5f9c3-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="5f9c3-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f9c3-165">Microsoft Office 通信服务器2007需要稍有不同的配置。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="5f9c3-166">TCP 和 UDP 端口范围59999必须打开入站和出站。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="5f9c3-167">此要求仅适用于 Office Communicator 2007。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="5f9c3-168">Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 仅要求 TCP 范围 50000-59999 打开出站。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="5f9c3-169">Edge 服务的 NAT 要求</span><span class="sxs-lookup"><span data-stu-id="5f9c3-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="5f9c3-170">如果你选择为 Edge 服务配置不可路由的专用 IP 地址, 则以下 NAT 要求适用:</span><span class="sxs-lookup"><span data-stu-id="5f9c3-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="5f9c3-171">NAT 仅可与 DNS 负载平衡配合使用。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="5f9c3-172">NAT 不受硬件负载平衡 (HLB) 边缘拓扑支持。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="5f9c3-173">NAT 仅可在外部边缘接口上使用。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="5f9c3-174">NAT 在内部边缘接口上不受支持。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="5f9c3-175">对于传入和传出通信, NAT 必须是对称的。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="5f9c3-176">对于来自 Internet 的流量, NAT 必须将目标 IP 地址从 A/V 边缘服务的支持 NAT 的公共 IP 地址更改为其外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="5f9c3-177">源 IP 地址必须保持不变, 以便 A/V 边缘服务可以找到最佳媒体路径。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="5f9c3-178">例如, 在下图中的入站方向上, 公共 IP 地址131.107.155.30 已更改为外部 (专用) IP 地址10.45.16.10。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="5f9c3-179">源 IP 地址保持不变。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="5f9c3-180">对于从 A/V 边缘服务到 Internet 的流量, NAT 必须将源 IP 地址从 A/V 边缘服务的外部 IP 地址更改为启用 NAT 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="5f9c3-181">例如, 在下图中的出站方向上, 外部 (专用) IP 地址10.45.16.10 已更改为公共 IP 地址131.107.155.30。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="5f9c3-182">**下图显示了 NAT 如何更改入站流量的目标 IP 地址和出站流量的源 IP 地址。**</span><span class="sxs-lookup"><span data-stu-id="5f9c3-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="5f9c3-183">![更改目的地/源 IP 地址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "更改目的地/源 IP 地址")</span><span class="sxs-lookup"><span data-stu-id="5f9c3-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="5f9c3-184">关键点是:</span><span class="sxs-lookup"><span data-stu-id="5f9c3-184">The key points are:</span></span>

  - <span data-ttu-id="5f9c3-185">入站到运行 A/V 边缘服务的服务器的通信, 源 IP 地址不会更改, 但目标 IP 地址会从131.107.155.30 更改为10.45.16.10 的已转换 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="5f9c3-186">从运行 A/V 边缘服务的服务器传出的流量返回到工作站, 源 IP 地址从服务器的公共 IP 地址更改为运行 A/V 边缘服务的服务器的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="5f9c3-187">目标 IP 将保留工作站的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="5f9c3-188">在数据包离开第一个 NAT 设备出站后, NAT 设备上的规则会将运行 A/V 边缘服务的外部接口 IP 地址 (10.45.16.10) 的服务器的源 IP 地址更改为其公共 IP 地址 (131.107.155.30)。</span><span class="sxs-lookup"><span data-stu-id="5f9c3-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

