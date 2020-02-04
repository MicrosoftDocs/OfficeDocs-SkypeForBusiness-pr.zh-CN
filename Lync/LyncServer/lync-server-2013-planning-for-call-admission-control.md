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
ms.openlocfilehash: de1f39b32503be758e10f3fbf712acdc07bd956b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="d396d-102">在 Lync Server 2013 中规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="d396d-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d396d-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d396d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d396d-104">对于基于 IP 的统一通信（UC）应用程序（如电话、视频和应用程序共享），企业网络的可用带宽一般视为 LAN 环境中的限制因素。</span><span class="sxs-lookup"><span data-stu-id="d396d-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="d396d-105">但是，在相互连接站点的 WAN 链路中，网络带宽可能受限。</span><span class="sxs-lookup"><span data-stu-id="d396d-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="d396d-106">当 oversubscribes WAN 链接的网络流量 influx 时，将使用队列、缓冲和数据包删除等当前机制来解决拥塞问题。</span><span class="sxs-lookup"><span data-stu-id="d396d-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="d396d-107">额外的流量通常会延迟，直到网络拥塞问题得以缓解，或者必要时会丢弃流量。</span><span class="sxs-lookup"><span data-stu-id="d396d-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="d396d-108">对于这些情况下的传统数据流量，接收客户端可以恢复。</span><span class="sxs-lookup"><span data-stu-id="d396d-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="d396d-109">对于实时通信（如统一通信），无法以这种方式解决网络拥塞，因为统一通信流量对延迟和数据包丢失都很敏感。</span><span class="sxs-lookup"><span data-stu-id="d396d-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="d396d-110">WAN 上的拥塞会导致用户的用户体验质量 (QoE) 降低。</span><span class="sxs-lookup"><span data-stu-id="d396d-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="d396d-111">对于在拥挤情况下的实时通信，最好拒绝呼叫，而不是提供质量较差的连接。</span><span class="sxs-lookup"><span data-stu-id="d396d-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="d396d-112">呼叫允许控制 (CAC) 可确定是否有足够的网络带宽来建立质量可接受的实时会话。</span><span class="sxs-lookup"><span data-stu-id="d396d-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="d396d-113">在 Lync Server 2013 中，CAC 仅控制音频和视频的实时流量，但不会影响数据流量。</span><span class="sxs-lookup"><span data-stu-id="d396d-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="d396d-114">如果默认 WAN 路径不具备所需的带宽，则 CAC 可尝试通过 Internet 路径或公用电话交换网 (PSTN) 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="d396d-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d396d-115">CAC 仅在 Lync Server 中可用。</span><span class="sxs-lookup"><span data-stu-id="d396d-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="d396d-116">本节介绍了呼叫允许控制功能，并解释了如何规划 CAC。</span><span class="sxs-lookup"><span data-stu-id="d396d-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d396d-117">Lync 服务器具有三个高级的企业语音功能：呼叫许可控制（CAC）、紧急服务（E9-1）和媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="d396d-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="d396d-118">有关所有三种功能通用的计划信息的概述，请参阅<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的高级企业语音功能的网络设置</A>。</span><span class="sxs-lookup"><span data-stu-id="d396d-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d396d-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="d396d-119">In This Section</span></span>

  - [<span data-ttu-id="d396d-120">Lync Server 2013 中的呼叫许可控制概述</span><span class="sxs-lookup"><span data-stu-id="d396d-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="d396d-121">在 Lync Server 2013 中定义呼叫允许控制要求</span><span class="sxs-lookup"><span data-stu-id="d396d-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="d396d-122">示例：在 Lync Server 2013 中收集呼叫许可控制的要求</span><span class="sxs-lookup"><span data-stu-id="d396d-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="d396d-123">Lync Server 2013 中 CAC 的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="d396d-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="d396d-124">Lync Server 2013 中呼叫允许控制的最佳做法</span><span class="sxs-lookup"><span data-stu-id="d396d-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="d396d-125">Lync Server 2013 中呼叫允许控制的部署清单</span><span class="sxs-lookup"><span data-stu-id="d396d-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

