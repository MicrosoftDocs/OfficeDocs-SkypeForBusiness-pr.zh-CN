---
title: Lync Server 2013 网络基础结构要求
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
ms.openlocfilehash: fcded907075b6587eb62ea8b6b76566c4f29ac87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="6adec-102">Lync Server 2013 的网络基础结构要求</span><span class="sxs-lookup"><span data-stu-id="6adec-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6adec-103">_**主题上次修改时间：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6adec-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6adec-104">Lync Server 2013 拓扑中每台服务器的网络适配器卡必须支持至少1千兆位/秒（Gbps）。</span><span class="sxs-lookup"><span data-stu-id="6adec-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="6adec-105">通常，你应使用低延迟和高带宽局域网（LAN）连接 Lync Server 拓扑中的所有服务器角色。</span><span class="sxs-lookup"><span data-stu-id="6adec-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="6adec-106">LAN 的大小取决于拓扑的大小：</span><span class="sxs-lookup"><span data-stu-id="6adec-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="6adec-107">在标准版拓扑中，服务器应位于支持 1 Gbps 以太网或等效的网络中。</span><span class="sxs-lookup"><span data-stu-id="6adec-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="6adec-108">在前端池拓扑中，大多数服务器应位于支持超过 1 Gbps 的网络中，尤其是支持音频/视频（A/V）会议和应用程序共享时。</span><span class="sxs-lookup"><span data-stu-id="6adec-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="6adec-109">对于公用电话交换网 (PSTN) 集成，可以使用 T1/E1 线路或 SIP 中继进行集成。</span><span class="sxs-lookup"><span data-stu-id="6adec-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="6adec-110">音频/视频网络要求</span><span class="sxs-lookup"><span data-stu-id="6adec-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="6adec-111">Lync Server 部署中音频/视频（A/V）的网络要求包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="6adec-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="6adec-112">如果您使用 DNS 负载平衡部署单个边缘服务器或边缘池，则可以将外部防火墙配置为 NAT。</span><span class="sxs-lookup"><span data-stu-id="6adec-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="6adec-113">不能将内部防火墙配置为 NAT。</span><span class="sxs-lookup"><span data-stu-id="6adec-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="6adec-114">有关这些要求的详细信息，请参阅在规划文档中[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6adec-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6adec-115">如果你有一个 Edge 池，并且使用的是硬件负载平衡器，则必须在每个边缘服务器上使用公共 IP 地址，并且不能在你的 NAT 设备上使用 NAT （例如，防火墙或将 NAT inbou 的其他基础结构设备）。nd 或出站流量）。</span><span class="sxs-lookup"><span data-stu-id="6adec-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="6adec-116">有关详细信息，请参阅在规划外部用户访问文档中的<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中具有硬件负载平衡器的 "端口摘要-缩放的合并边缘</A>"。</span><span class="sxs-lookup"><span data-stu-id="6adec-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="6adec-117">如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。</span><span class="sxs-lookup"><span data-stu-id="6adec-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="6adec-118">如果使用 Internet 协议安全性 (IPsec)，建议在用于 A/V 流量的端口范围内禁用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="6adec-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="6adec-119">有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 IPsec 异常](lync-server-2013-ipsec-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="6adec-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="6adec-120">若要确保最佳的媒体质量，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6adec-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="6adec-121">设置您的网络链接以支持每个音频流的每秒 65 kbps 的吞吐量和每个视频流 500 Kbps （如果在高峰使用期间启用）。</span><span class="sxs-lookup"><span data-stu-id="6adec-121">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods.</span></span> <span data-ttu-id="6adec-122">双向音频或视频会话由两个流组成。</span><span class="sxs-lookup"><span data-stu-id="6adec-122">A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="6adec-123">为了处理此级别以上流量中的意外峰值和延长使用时间，Lync Server 媒体终结点可以适应不同的网络条件，并支持加载三倍于音频和视频的吞吐量（请参阅上一段），同时仍保留可接受的质量。</span><span class="sxs-lookup"><span data-stu-id="6adec-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="6adec-124">但是，不要假定此适应性将支持未预配的网络。</span><span class="sxs-lookup"><span data-stu-id="6adec-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="6adec-125">在预配网络中，Lync 服务器媒体终结点能够动态处理不同网络条件（例如，临时数据包丢失）的能力减少。</span><span class="sxs-lookup"><span data-stu-id="6adec-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="6adec-126">对于预配成本极其昂贵且非常困难的网络链接，你可能需要考虑为较低的流量量进行预配。</span><span class="sxs-lookup"><span data-stu-id="6adec-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="6adec-127">在这种情况下，让 Lync Server 媒体终结点的 elasticity 能够吸收流量音量与峰值流量级别之间的差异，降低语音质量的成本。</span><span class="sxs-lookup"><span data-stu-id="6adec-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="6adec-128">此外，还会减少余地的余地，但仍可吸收通信量突然出现高峰的情况。</span><span class="sxs-lookup"><span data-stu-id="6adec-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="6adec-129">对于在短期内无法正确设置的链接（例如，具有非常差的 WAN 链接的网站），请考虑为某些用户禁用视频。</span><span class="sxs-lookup"><span data-stu-id="6adec-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="6adec-130">预配你的网络，以确保最大的端到端延迟（延迟）在最大负载下150毫秒（ms）。</span><span class="sxs-lookup"><span data-stu-id="6adec-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="6adec-131">延迟是 Lync Server 媒体组件无法减少的网络问题，查找和消除薄弱点非常重要。</span><span class="sxs-lookup"><span data-stu-id="6adec-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="6adec-132">对于运行防病毒软件的服务器，请在例外列表中包括运行 Lync Server 的所有服务器，以便提供最佳性能和音频质量。</span><span class="sxs-lookup"><span data-stu-id="6adec-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="6adec-133">会议网络要求</span><span class="sxs-lookup"><span data-stu-id="6adec-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="6adec-134">从 Internet 信息服务（IIS）服务器下载会议内容所使用的带宽取决于上载的内容的大小。</span><span class="sxs-lookup"><span data-stu-id="6adec-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

