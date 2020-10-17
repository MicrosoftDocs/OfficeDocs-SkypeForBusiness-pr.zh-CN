---
title: Lync Server 2013 网络基础结构要求
description: Lync Server 2013 网络基础结构要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7ff21c2f936ef8e048f6831d55408994055400
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561498"
---
# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="4c20b-103">Lync Server 2013 的网络基础结构要求</span><span class="sxs-lookup"><span data-stu-id="4c20b-103">Network infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c20b-104">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="4c20b-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="4c20b-105">Lync Server 2013 拓扑中每台服务器的网络适配器卡必须至少支持1千兆位/秒 (Gbps) 。</span><span class="sxs-lookup"><span data-stu-id="4c20b-105">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="4c20b-106">通常情况下，应使用低延迟和高带宽本地局域网 (LAN) 在 Lync Server 拓扑中连接所有服务器角色。</span><span class="sxs-lookup"><span data-stu-id="4c20b-106">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="4c20b-107">LAN 的大小取决于拓扑的大小：</span><span class="sxs-lookup"><span data-stu-id="4c20b-107">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="4c20b-108">在标准版拓扑中，服务器应位于支持 1 Gbps 以太网或等效项的网络中。</span><span class="sxs-lookup"><span data-stu-id="4c20b-108">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="4c20b-109">在前端池拓扑中，大多数服务器应位于支持超过 1 Gbps 的网络中，尤其是在支持音频/视频 (A/V) 会议和应用程序共享时。</span><span class="sxs-lookup"><span data-stu-id="4c20b-109">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="4c20b-110">对于公用电话交换网 (PSTN) 集成，可以使用 T1/E1 线路或 SIP 中继进行集成。</span><span class="sxs-lookup"><span data-stu-id="4c20b-110">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="4c20b-111">音频/视频网络要求</span><span class="sxs-lookup"><span data-stu-id="4c20b-111">Audio/Video Network Requirements</span></span>

<span data-ttu-id="4c20b-112">在 Lync Server 部署中，音频/视频 (A/V) 的网络要求包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="4c20b-112">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="4c20b-113">如果要使用 DNS 负载平衡部署单个边缘服务器或边缘池，则可以将外部防火墙配置为 NAT。</span><span class="sxs-lookup"><span data-stu-id="4c20b-113">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="4c20b-114">不能配置内部防火墙作为 NAT。</span><span class="sxs-lookup"><span data-stu-id="4c20b-114">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="4c20b-115">有关这些要求的详细信息，请参阅规划文档中的 [确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="4c20b-115">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4c20b-116">如果你有一个边缘池，并且使用的是硬件负载平衡器，则必须在每台边缘服务器上使用公用 IP 地址，并且无法将 NAT 用于 NAT 设备上的服务器或池 (例如，防火墙或将 NAT 入站或出站通信) 的其他基础结构设备。</span><span class="sxs-lookup"><span data-stu-id="4c20b-116">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="4c20b-117">有关详细信息，请参阅规划外部用户访问文档中的在 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中的端口摘要-扩展的合并边缘和硬件负载平衡</A> 器。</span><span class="sxs-lookup"><span data-stu-id="4c20b-117">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="4c20b-118">如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。</span><span class="sxs-lookup"><span data-stu-id="4c20b-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="4c20b-119">如果使用 Internet 协议安全性 (IPsec)，建议在用于 A/V 流量的端口范围内禁用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="4c20b-119">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="4c20b-120">有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md) 。</span><span class="sxs-lookup"><span data-stu-id="4c20b-120">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="4c20b-121">要确保最佳媒体质量，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4c20b-121">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="4c20b-p105">设置网络链接，使之在高峰使用时段支持每个音频流 65 千位每秒 (Kbps) 和每个视频流（如果启用）500 Kbps 的吞吐量。一个双向音频或视频会话由两个流构成。</span><span class="sxs-lookup"><span data-stu-id="4c20b-p105">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods. A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="4c20b-124">若要处理此级别以上流量中的意外峰值和时间增加的使用率，Lync Server 媒体终结点可适应不同的网络条件，并支持三倍于吞吐量的负载。在仍然保留可接受质量的同时， (查看上一段) 的音频和视频。</span><span class="sxs-lookup"><span data-stu-id="4c20b-124">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="4c20b-125">但是，不要认为这种适应性能支持未充分设置的网络。</span><span class="sxs-lookup"><span data-stu-id="4c20b-125">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="4c20b-126">在预配网络中，Lync Server 媒体终结点能够动态处理不同的网络 (条件，例如，降低了临时数据包丢失) 。</span><span class="sxs-lookup"><span data-stu-id="4c20b-126">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="4c20b-127">如果网络链路的设置成本很高，而且难于操作，可能就需要考虑设置较低的流量。</span><span class="sxs-lookup"><span data-stu-id="4c20b-127">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="4c20b-128">在这种情况下，让 Lync Server 媒体终结点的弹性能够吸收流量量与峰值流量水平之间的差异，以降低语音质量的成本为代价。</span><span class="sxs-lookup"><span data-stu-id="4c20b-128">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="4c20b-129">此外，可用于吸收流量中的突发峰值的空间也会减少。</span><span class="sxs-lookup"><span data-stu-id="4c20b-129">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="4c20b-130">对于短期内无法正确配置的链路（例如 WAN 链路很差的站点），考虑对某些用户禁用视频。</span><span class="sxs-lookup"><span data-stu-id="4c20b-130">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="4c20b-131">配置网络，确保在高峰负载下的最大端到端延迟为 150 毫秒 (ms)。</span><span class="sxs-lookup"><span data-stu-id="4c20b-131">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="4c20b-132">延迟是 Lync Server 媒体组件无法降低的网络障碍，查找和消除薄弱点很重要。</span><span class="sxs-lookup"><span data-stu-id="4c20b-132">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="4c20b-133">对于运行防病毒软件的服务器，请在例外列表中包括运行 Lync Server 的所有服务器，以便提供最佳性能和音频质量。</span><span class="sxs-lookup"><span data-stu-id="4c20b-133">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="4c20b-134">会议网络要求</span><span class="sxs-lookup"><span data-stu-id="4c20b-134">Conferencing Network Requirements</span></span>

<span data-ttu-id="4c20b-135">从 Internet 信息服务 (IIS) server 中下载会议内容所使用的带宽取决于上载的内容的大小。</span><span class="sxs-lookup"><span data-stu-id="4c20b-135">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

