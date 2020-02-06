---
title: Skype for Business 服务器中的 Edge 服务器方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 摘要：查看这些方案，帮助你在 Skype for Business Server 中规划 Edge 服务器拓扑。
ms.openlocfilehash: a1d721ffabb78985d90848784cd587bda96300d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803352"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="74f4e-103">Skype for Business 服务器中的 Edge 服务器方案</span><span class="sxs-lookup"><span data-stu-id="74f4e-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="74f4e-104">**摘要：** 查看这些方案以帮助你在 Skype for Business 服务器中规划 Edge 服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="74f4e-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="74f4e-105">我们有一些方案图可帮助可视化和确定要实现的 Skype for business Server Edge 服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="74f4e-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="74f4e-106">选择合适的候选方案后，可以继续阅读需要满足的环境要求。</span><span class="sxs-lookup"><span data-stu-id="74f4e-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="74f4e-107">以下内容适用于任何方案，所以我们先讲这些内容。</span><span class="sxs-lookup"><span data-stu-id="74f4e-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="74f4e-p102">下面的图仅作为示例显示（因此包含示例 IPv4 和 IPv6 数据），它们不表示实际通信流，而是表示可能的流量的高级视图。另外，可以在下面每个方案的端口图中找到端口详细信息。</span><span class="sxs-lookup"><span data-stu-id="74f4e-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="74f4e-110">这些图对外部接口显示 .com，对内部显示 .net，这也是示例资料；当然，在你组合出自己的最终边缘方案时，你自己的条目可能很不一样。</span><span class="sxs-lookup"><span data-stu-id="74f4e-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="74f4e-111">我们不在任何图表中包含 Director （这是一个可选组件），但您可以单独阅读（在其他规划主题中提及）。</span><span class="sxs-lookup"><span data-stu-id="74f4e-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="74f4e-112">如前所述，图中有示例 IPv6 数据。</span><span class="sxs-lookup"><span data-stu-id="74f4e-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="74f4e-113">[在 Skype for Business 服务器中规划 Edge 服务器部署中](edge-server-deployments.md)的大部分文档将引用 IPv4，但如果你希望使用 IPv6，则可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="74f4e-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="74f4e-114">请注意，在分配的地址空间中，需要有 IPv6 地址，与 IPv4 IP 一样，它们也需要能用于内部和外部寻址。</span><span class="sxs-lookup"><span data-stu-id="74f4e-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="74f4e-115">多亏有了 Windows，你可以采用双协议栈功能，即 IPv4 和 IPv6 两个单独而不同的网络协议栈。</span><span class="sxs-lookup"><span data-stu-id="74f4e-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="74f4e-116">如果需要，这能让你同时分配 IPv4 和 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="74f4e-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="74f4e-117">存在允许 NAT64 （IPv6 到 IPv4）和 NAT66 （IPv6 到 IPv6）的 NAT 设备，并且这可用于 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="74f4e-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="74f4e-118">如果使用呼叫允许控制 (CAC)，就必须在内部接口上使用 IPv4 才能使 CAC 可供正常使用。</span><span class="sxs-lookup"><span data-stu-id="74f4e-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="74f4e-119">具有专用 IP 地址和 NAT 的单个统一 Skype for business 服务器边缘服务器</span><span class="sxs-lookup"><span data-stu-id="74f4e-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="74f4e-p104">此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。</span><span class="sxs-lookup"><span data-stu-id="74f4e-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![单个合并边缘的边缘方案（使用 NAT 通过专用 IP）](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="74f4e-124">端口图</span><span class="sxs-lookup"><span data-stu-id="74f4e-124">Port diagram</span></span>

<span data-ttu-id="74f4e-125">我们还为单个统一边缘服务器的端口提供了一个图表。</span><span class="sxs-lookup"><span data-stu-id="74f4e-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="74f4e-127">具有公共 IP 地址的单个统一 Skype for business 服务器边缘服务器</span><span class="sxs-lookup"><span data-stu-id="74f4e-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="74f4e-p105">此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。</span><span class="sxs-lookup"><span data-stu-id="74f4e-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![使用公共 IP 的单个合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="74f4e-132">端口图</span><span class="sxs-lookup"><span data-stu-id="74f4e-132">Port diagram</span></span>

<span data-ttu-id="74f4e-133">我们还为单个统一边缘服务器的端口提供了一个图表。</span><span class="sxs-lookup"><span data-stu-id="74f4e-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="74f4e-135">缩放的合并 Skype for business Server Edge 池，具有 DNS 负载平衡以及专用 IP 地址和 NAT</span><span class="sxs-lookup"><span data-stu-id="74f4e-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="74f4e-136">使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="74f4e-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![扩展合并边缘的边缘方案（使用 NAT 通过专用 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="74f4e-138">端口图</span><span class="sxs-lookup"><span data-stu-id="74f4e-138">Port diagram</span></span>

<span data-ttu-id="74f4e-139">我们还提供了一个图表，用于使用 DNS 负载平衡缩放的合并的边缘池。</span><span class="sxs-lookup"><span data-stu-id="74f4e-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="74f4e-141">缩放的合并 Skype for business 服务器 Edge 池，具有 DNS 负载平衡和公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="74f4e-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="74f4e-142">使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="74f4e-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![扩展合并边缘的边缘方案（通过公共 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="74f4e-144">端口图</span><span class="sxs-lookup"><span data-stu-id="74f4e-144">Port diagram</span></span>

<span data-ttu-id="74f4e-145">我们还提供了一个图表，用于使用 DNS 负载平衡缩放的合并的边缘池。</span><span class="sxs-lookup"><span data-stu-id="74f4e-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="74f4e-147">缩放的合并 Skype for business Server Edge 池，硬件负载平衡</span><span class="sxs-lookup"><span data-stu-id="74f4e-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="74f4e-148">使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="74f4e-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![带有 HLB 的扩展合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
