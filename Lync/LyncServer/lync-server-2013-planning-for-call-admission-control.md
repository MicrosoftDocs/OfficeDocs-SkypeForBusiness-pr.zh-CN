---
title: Lync Server 2013：规划呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c89b289158b36aa811e09e9db628850693dac5a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="c61e0-102">在 Lync Server 2013 中规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="c61e0-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c61e0-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c61e0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c61e0-p101">对于基于 IP 的统一通信 (UC) 应用程序，例如电话、视频和应用程序共享，通常不会将企业网络的可用带宽视为 LAN 环境内的限制因素。但是，在相互连接站点的 WAN 链路中，可以限制网络带宽。当过多网络流量通过 WAN 链路时，将使用当前的诸如队列、缓冲和数据包丢弃等机制解决拥塞问题。额外的流量通常会延迟，直到网络拥塞问题得以缓解，或者必要时会丢弃流量。对于这些情况下的传统数据流量，接收客户端可以恢复。对于实时流量（如统一通信），则不能采用这种方式解决网络拥塞问题，因为统一通信流量对延迟和数据包丢失非常敏感。WAN 上的拥塞会导致用户的用户体验质量 (QoE) 降低。对于发生拥塞时的实时流量，最好拒绝呼叫，而不是提供质量欠佳的连接。</span><span class="sxs-lookup"><span data-stu-id="c61e0-p101">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments. However, on WAN links that interconnect sites, network bandwidth can be limited. When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion. The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped. For conventional data traffic in such situations, the receiving client can recover. For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss. Congestion on the WAN can result in a poor Quality of Experience (QoE) for users. For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="c61e0-112">呼叫允许控制 (CAC) 可确定是否有足够的网络带宽来建立质量可接受的实时会话。</span><span class="sxs-lookup"><span data-stu-id="c61e0-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="c61e0-113">在 Lync Server 2013 中，CAC 仅控制音频和视频的实时流量，但不会影响数据流量。</span><span class="sxs-lookup"><span data-stu-id="c61e0-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="c61e0-114">如果默认 WAN 路径不具备所需的带宽，则 CAC 可尝试通过 Internet 路径或公用电话交换网 (PSTN) 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="c61e0-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="c61e0-115">CAC 仅在 Lync Server 中可用。</span><span class="sxs-lookup"><span data-stu-id="c61e0-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="c61e0-116">本节介绍了呼叫允许控制功能，并解释了如何规划 CAC。</span><span class="sxs-lookup"><span data-stu-id="c61e0-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c61e0-117">Lync Server 具有三个高级企业语音功能：呼叫允许控制（CAC）、紧急服务（E9-1-1）和媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="c61e0-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="c61e0-118">有关这三种功能共有的规划信息的概述，请参阅<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的 "高级企业语音功能的网络设置"</A>。</span><span class="sxs-lookup"><span data-stu-id="c61e0-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c61e0-119">本部分内容</span><span class="sxs-lookup"><span data-stu-id="c61e0-119">In This Section</span></span>

  - [<span data-ttu-id="c61e0-120">Lync Server 2013 中的呼叫允许控制概述</span><span class="sxs-lookup"><span data-stu-id="c61e0-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="c61e0-121">在 Lync Server 2013 中定义呼叫允许控制的要求</span><span class="sxs-lookup"><span data-stu-id="c61e0-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="c61e0-122">示例：收集 Lync Server 2013 中的呼叫允许控制要求</span><span class="sxs-lookup"><span data-stu-id="c61e0-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="c61e0-123">Lync Server 2013 中 CAC 的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="c61e0-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="c61e0-124">Lync Server 2013 中的呼叫允许控制最佳实践</span><span class="sxs-lookup"><span data-stu-id="c61e0-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="c61e0-125">Lync Server 2013 中呼叫允许控制的部署清单</span><span class="sxs-lookup"><span data-stu-id="c61e0-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

