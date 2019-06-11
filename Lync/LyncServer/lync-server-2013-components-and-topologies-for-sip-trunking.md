---
title: Lync Server 2013：用于 SIP 中继的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1b80078f942f3f70957a7af6b27b7dd9210046
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="33fb4-102">Lync Server 2013 中用于 SIP 中继的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="33fb4-102">Components and topologies for SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33fb4-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="33fb4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="33fb4-104">下图描绘了 Lync Server 中的 SIP 中继拓扑。</span><span class="sxs-lookup"><span data-stu-id="33fb4-104">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="33fb4-105">**SIP 中继拓扑**</span><span class="sxs-lookup"><span data-stu-id="33fb4-105">**SIP trunking topology**</span></span>

<span data-ttu-id="33fb4-106">![SIP 中继拓扑](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 中继拓扑")</span><span class="sxs-lookup"><span data-stu-id="33fb4-106">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="33fb4-p101">如图所示，企业网络与公用电话交换网 (PSTN) 服务提供商之间的连接使用 IP 虚拟专用网络 (VPN)。这个专用网络旨在提供 IP 连接、增强安全性和（可选的）获取服务质量 (QoS) 保证。由于 VPN 的特性，您无需为 SIP 信号流量使用传输层安全性 (TLS)，也无需为媒体流量使用安全实时传输协议 (SRTP)。因此，企业与服务提供商之间的连接由用于 SIP 的普通 TCP 连接以及用于通过 IP VPN 进行隧道传输的媒体的普通实时传输协议 (RTP)（通过 UDP）构成。确保 VPN 路由器之间的所有防火墙打开端口以允许 VPN 路由器进行通信，并且 VPN 路由器外部边缘上的 IP 地址公共可路由。</span><span class="sxs-lookup"><span data-stu-id="33fb4-p101">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="33fb4-112">请与服务提供商联系，以确定是否提供包括故障转移在内的高可用性支持。</span><span class="sxs-lookup"><span data-stu-id="33fb4-112">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="33fb4-113">如果提供，则需要确定设置过程。</span><span class="sxs-lookup"><span data-stu-id="33fb4-113">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="33fb4-114">例如, 你只需要在每个中介服务器上配置一个 IP 地址和一个 SIP 中继, 还是需要在每个中介服务器上配置多个 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="33fb4-114">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="33fb4-115">如果您有多个中心网站, 还询问服务提供商是否有能力启用与另一个中心站点的连接。</span><span class="sxs-lookup"><span data-stu-id="33fb4-115">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="33fb4-116">对于 SIP 中继, 强烈建议你部署独立的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="33fb4-116">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="33fb4-117">有关详细信息, 请参阅部署文档中的在<A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync Server 2013 中部署中介服务器和定义对等</A>。</span><span class="sxs-lookup"><span data-stu-id="33fb4-117">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="33fb4-118">为 SIP 中继保护中介服务器的安全</span><span class="sxs-lookup"><span data-stu-id="33fb4-118">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="33fb4-p104">为安全起见，应为两个 VPN 路由器之间的每个连接设置一个虚拟 LAN (VLAN)。设置 VLAN 的实际过程因路由器制造商而异。请与路由器供应商联系以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="33fb4-p104">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="33fb4-122">建议您遵循下列准则：</span><span class="sxs-lookup"><span data-stu-id="33fb4-122">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="33fb4-123">在外围网络 (也称为 DMZ、隔离区和屏蔽子网) 之间的中介服务器和 VPN 路由器之间设置虚拟 LAN (VLAN)。</span><span class="sxs-lookup"><span data-stu-id="33fb4-123">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="33fb4-124">不允许将广播数据包或多播数据包从路由器传输到 VLAN。</span><span class="sxs-lookup"><span data-stu-id="33fb4-124">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="33fb4-125">阻止将流量从路由器路由到除中介服务器之外的任何位置的任何路由规则。</span><span class="sxs-lookup"><span data-stu-id="33fb4-125">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="33fb4-126">如果使用 VPN 服务器，建议您遵循下列准则：</span><span class="sxs-lookup"><span data-stu-id="33fb4-126">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="33fb4-127">在 VPN 服务器和中介服务器之间设置 VLAN。</span><span class="sxs-lookup"><span data-stu-id="33fb4-127">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="33fb4-128">不允许将广播数据包或多播数据包从 VPN 服务器传输到 VLAN。</span><span class="sxs-lookup"><span data-stu-id="33fb4-128">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="33fb4-129">阻止将 VPN 服务器流量路由到除中介服务器之外的任何位置的任何路由规则。</span><span class="sxs-lookup"><span data-stu-id="33fb4-129">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="33fb4-130">使用基本路由封装 (GRE) 加密 VPN 上的数据。</span><span class="sxs-lookup"><span data-stu-id="33fb4-130">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

