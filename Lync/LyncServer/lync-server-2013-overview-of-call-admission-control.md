---
title: Lync Server 2013：呼叫允许控制概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ad2be78d3e2af4c5b016b02e152ba0430d2a1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="7a2c3-102">Lync Server 2013 中的呼叫允许控制概述</span><span class="sxs-lookup"><span data-stu-id="7a2c3-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a2c3-103">_**上次修改的主题：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="7a2c3-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="7a2c3-104">实时通信会受到拥堵网络上可能发生的延迟和数据包丢失情况的影响。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="7a2c3-105">呼叫允许控制 (CAC) 根据可用网络带宽确定是否允许建立实时通信会话（如语音呼叫或视频呼叫）。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="7a2c3-106">Lync Server 2013 中的 CAC 设计提供了四个主要属性：</span><span class="sxs-lookup"><span data-stu-id="7a2c3-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="7a2c3-107">不需要使用其他设备（如经过特殊配置的路由器），即可轻松部署和管理。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="7a2c3-p102">它可处理关键的统一通信用例，例如漫游用户和多点登录。根据终结点的位置（而非用户的驻留位置）实施 CAC 策略。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="7a2c3-110">除了语音呼叫，它还可以应用于其他通信，例如视频呼叫和音频/视频会议会话。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="7a2c3-111">能够灵活地表示各种网络拓扑。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="7a2c3-112">有关示例，请参阅[Lync Server 2013 中的 CAC 的组件和拓扑](lync-server-2013-components-and-topologies-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="7a2c3-113">如果新语音会话或视频会话超出您在 WAN 链路上设置的带宽限制，该会话将被阻止或（仅在电话呼叫情况下）重新路由至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="7a2c3-p104">CAC 仅控制实时语音和视频流量，不控制数据流量。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="7a2c3-116">管理员定义 CAC 策略，这些策略由随每个前端池一起安装的带宽策略服务强制实施。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="7a2c3-117">CAC 设置将自动传播到网络中的所有 Lync Server 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="7a2c3-118">对于因 CAC 策略而失败的呼叫，重新路由呼叫的优先顺序如下：</span><span class="sxs-lookup"><span data-stu-id="7a2c3-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="7a2c3-119">Internet</span><span class="sxs-lookup"><span data-stu-id="7a2c3-119">Internet</span></span>

2.  <span data-ttu-id="7a2c3-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="7a2c3-120">PSTN</span></span>

3.  <span data-ttu-id="7a2c3-121">语音邮件</span><span class="sxs-lookup"><span data-stu-id="7a2c3-121">Voice mail</span></span>

<span data-ttu-id="7a2c3-p106">呼叫详细信息记录 (CDR) 捕获有关重新路由至 PSTN 或语音邮件的呼叫的信息。CDR 不会捕获有关重新路由至 Internet 的呼叫的信息，因为 Internet 被视为备用路径而非次要选项。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a2c3-124">语音邮件处理不会因为带宽限制而被拒绝。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="7a2c3-p107">带宽策略服务生成两种逗号分隔值 (CSV) 格式的日志文件。“检查失败”\*\*\*\* 日志文件捕获带宽请求被拒绝时的信息。“链接利用率”\*\*\*\* 日志文件捕获网络拓扑快照和 WAN 链路带宽用量。这两种日志文件都有助于根据利用率微调 CAC 策略。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="7a2c3-129">呼叫允许控制注意事项</span><span class="sxs-lookup"><span data-stu-id="7a2c3-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="7a2c3-130">管理员选择将带宽策略服务安装在中央站点中配置的第一个池上。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="7a2c3-131">由于每个网络区域有一个中央站点，因此每个网络区域只有一个带宽策略服务，它管理用于该区域、其关联站点和到这些站点的链接的带宽策略。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="7a2c3-132">带宽策略服务作为前端服务器的一部分运行，因此在该池内内置了高可用性。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="7a2c3-133">每台前端服务器上运行的带宽策略服务每15秒同步一次。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="7a2c3-134">如果前端池发生故障，则在前端池之前，不会再为该站点强制使用 CAC 策略，因此带宽策略服务将再次正常运行。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="7a2c3-135">这意味着，在带宽策略服务停用期间，所有呼叫都将通过。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="7a2c3-136">因此，在此期间可能会出现链接的带宽订阅过度的情况。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="7a2c3-137">带宽策略服务在前端池内提供了高可用性;但是，它不提供跨前端池的冗余。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="7a2c3-138">带宽策略服务无法从一个前端池故障转移到另一个前端池。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="7a2c3-139">在还原对前端池的服务后，会恢复带宽策略服务，并可以再次强制实施带宽策略检查。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="7a2c3-140">网络注意事项</span><span class="sxs-lookup"><span data-stu-id="7a2c3-140">Network Considerations</span></span>

<span data-ttu-id="7a2c3-141">尽管 Lync Server 2013 中的带宽策略服务强制执行音频和视频的带宽限制，但不会在网络路由器（第2层和第3层）上强制此限制。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="7a2c3-142">Lync Server 2010 CAC 无法阻止数据应用程序，例如，在 WAN 链路上使用整个网络带宽，包括您的 CAC 策略为音频和视频保留的带宽。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="7a2c3-143">要提供必需的网络带宽保护，您可以部署服务质量 (QoS) 协议，例如差分服务 (DiffServ)。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="7a2c3-144">因此，最佳实践是协调按照您可能部署的任何 QoS 设置定义的 CAC 带宽策略。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="7a2c3-145">VPN 上的媒体和信号路径</span><span class="sxs-lookup"><span data-stu-id="7a2c3-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="7a2c3-p111">如果您的企业支持通过 VPN 的媒体，则请确保媒体流和信号流都能通过 VPN，或两者都通过 Internet 进行路由。默认情况下，媒体流和信号流通过 VPN 通道。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="7a2c3-148">外部用户的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="7a2c3-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="7a2c3-149">不对通过 Internet 传输网络流量的远程用户实施呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="7a2c3-150">由于媒体流量正在遍历 Internet （不受 Lync Server 管理），因此无法应用 CAC。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="7a2c3-151">但是，仍将对通过企业网络的部分呼叫执行 CAC 检查。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="7a2c3-152">PSTN 连接的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="7a2c3-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="7a2c3-153">呼叫允许控制在中介服务器上是可强制的，而不管它是连接到 IP/PBX、PSTN 网关还是 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="7a2c3-154">由于中介服务器是后端到后端用户代理（B2BUA），因此它会终止媒体。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="7a2c3-155">它有两个连接方：连接到 Lync Server 的一端，以及连接到 PSTN 网关、IP/Pbx 或 SIP 中继的网关端。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="7a2c3-156">有关 PSTN 连接的详细信息，请参阅[在 Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="7a2c3-157">除非启用媒体旁路，否则在中介服务器的两端都可以实施 CAC。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="7a2c3-158">如果启用媒体旁路，媒体流量不会遍历中介服务器，而是直接在 Lync 客户端和网关之间流动。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="7a2c3-159">在这种情况下，不需要使用 CAC。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="7a2c3-160">有关详细信息，请参阅[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="7a2c3-161">下图说明了如何在启用和不启用媒体旁路的情况下在 PSTN 连接上实施 CAC。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="7a2c3-162">**在 PSTN 连接上实施呼叫允许控制**</span><span class="sxs-lookup"><span data-stu-id="7a2c3-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="7a2c3-163">![语音 CAC 媒体绕过连接强制实施](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "语音 CAC 媒体绕过连接强制实施")</span><span class="sxs-lookup"><span data-stu-id="7a2c3-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="7a2c3-164">呼叫允许控制与早期版本的 Office Communications Server 的兼容性</span><span class="sxs-lookup"><span data-stu-id="7a2c3-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="7a2c3-165">只能在为 Lync Server 2010 和更高版本启用的终结点上启用呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="7a2c3-166">无法在运行 Office Communicator 2007 R2 或更早版本的终结点上启用呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="7a2c3-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="7a2c3-167">**在不同版本的 Lync Server 上应用 CAC**</span><span class="sxs-lookup"><span data-stu-id="7a2c3-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="7a2c3-168">![语音 CAC 版本比较关系图](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "语音 CAC 版本比较关系图")</span><span class="sxs-lookup"><span data-stu-id="7a2c3-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

