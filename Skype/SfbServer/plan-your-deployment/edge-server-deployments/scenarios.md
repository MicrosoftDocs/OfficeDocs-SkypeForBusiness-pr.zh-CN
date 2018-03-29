---
title: Skype for Business Server 2015 中的边缘服务器方案
ms.author: heidip
author: microsoftheidi
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 摘要： 审查这些方案，以帮助您规划业务服务器 2015 Skype 在边缘服务器拓扑。
ms.openlocfilehash: 30bce96e1764a608bf7bc8daeec3d918b9e5912c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-scenarios-in-skype-for-business-server-2015"></a><span data-ttu-id="85b7b-103">Skype for Business Server 2015 中的边缘服务器方案</span><span class="sxs-lookup"><span data-stu-id="85b7b-103">Edge Server scenarios in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="85b7b-104">**摘要：**检查这些方案，以帮助您规划业务服务器 2015 Skype 在边缘服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="85b7b-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server 2015 .</span></span>
  
<span data-ttu-id="85b7b-105">我们有一些方案图来帮助可视化和决定上什么 Skype 业务服务器边缘服务器拓扑结构您要实现的。</span><span class="sxs-lookup"><span data-stu-id="85b7b-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="85b7b-106">选择合适的候选方案后，可以继续阅读需要满足的环境要求。</span><span class="sxs-lookup"><span data-stu-id="85b7b-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="85b7b-107">以下内容适用于任何方案，所以我们先讲这些内容。</span><span class="sxs-lookup"><span data-stu-id="85b7b-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="85b7b-p102">下面的图仅作为示例显示（因此包含示例 IPv4 和 IPv6 数据），它们不表示实际通信流，而是表示可能的流量的高级视图。另外，可以在下面每个方案的端口图中找到端口详细信息。</span><span class="sxs-lookup"><span data-stu-id="85b7b-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="85b7b-110">这些图对外部接口显示 .com，对内部显示 .net，这也是示例资料；当然，在你组合出自己的最终边缘方案时，你自己的条目可能很不一样。</span><span class="sxs-lookup"><span data-stu-id="85b7b-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="85b7b-111">在任何关系图中，我们不包括控制器 （这是一个可选组件），但可以单独阅读有关的 （它在规划中的其他主题中提到）。</span><span class="sxs-lookup"><span data-stu-id="85b7b-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="85b7b-112">如前所述，图中有示例 IPv6 数据。</span><span class="sxs-lookup"><span data-stu-id="85b7b-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="85b7b-113">大部分[计划业务服务器 2015年的 Skype 在边缘服务器部署](edge-server-deployments.md)中的文档将指向 IPv4，但当然支持如果您想要使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="85b7b-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server 2015](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="85b7b-114">请注意，在分配的地址空间中，需要有 IPv6 地址，与 IPv4 IP 一样，它们也需要能用于内部和外部寻址。</span><span class="sxs-lookup"><span data-stu-id="85b7b-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="85b7b-115">多亏有了 Windows，你可以采用双协议栈功能，即 IPv4 和 IPv6 两个单独而不同的网络协议栈。</span><span class="sxs-lookup"><span data-stu-id="85b7b-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="85b7b-116">如果需要，这能让你同时分配 IPv4 和 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="85b7b-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="85b7b-117">没有允许 NAT64 的 NAT 设备 (IPv4 向 IPv6) 和 NAT66 (到 IPv6 IPv6))，这是有效使用 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="85b7b-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="85b7b-118">如果使用呼叫允许控制 (CAC)，就必须在内部接口上使用 IPv4 才能使 CAC 可供正常使用。</span><span class="sxs-lookup"><span data-stu-id="85b7b-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="85b7b-119">单与专用的 IP 地址和 NAT 的业务服务器边缘服务器整合 Skype</span><span class="sxs-lookup"><span data-stu-id="85b7b-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="85b7b-p104">此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。</span><span class="sxs-lookup"><span data-stu-id="85b7b-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![单个合并边缘的边缘方案（使用 NAT 通过专用 IP）](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="85b7b-124">端口图</span><span class="sxs-lookup"><span data-stu-id="85b7b-124">Port diagram</span></span>

<span data-ttu-id="85b7b-125">我们也有单个统一的边缘服务器端口的图。</span><span class="sxs-lookup"><span data-stu-id="85b7b-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="85b7b-127">单个合并的 Skype 业务服务器边缘服务器与公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="85b7b-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="85b7b-p105">此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。</span><span class="sxs-lookup"><span data-stu-id="85b7b-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![使用公共 IP 的单个合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="85b7b-132">端口图</span><span class="sxs-lookup"><span data-stu-id="85b7b-132">Port diagram</span></span>

<span data-ttu-id="85b7b-133">我们也有单个统一的边缘服务器端口的图。</span><span class="sxs-lookup"><span data-stu-id="85b7b-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="85b7b-135">缩放后的统一的 Skype 业务服务器边缘池与 DNS 负载平衡和专用 IP 地址和 NAT</span><span class="sxs-lookup"><span data-stu-id="85b7b-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="85b7b-136">使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="85b7b-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![扩展合并边缘的边缘方案（使用 NAT 通过专用 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="85b7b-138">端口图</span><span class="sxs-lookup"><span data-stu-id="85b7b-138">Port diagram</span></span>

<span data-ttu-id="85b7b-139">我们还提供有 DNS 负载平衡比例统一边缘池的图。</span><span class="sxs-lookup"><span data-stu-id="85b7b-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="85b7b-141">缩放后的统一的 Skype 业务服务器边缘池与 DNS 负载平衡和公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="85b7b-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="85b7b-142">使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="85b7b-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![扩展合并边缘的边缘方案（通过公共 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="85b7b-144">端口图</span><span class="sxs-lookup"><span data-stu-id="85b7b-144">Port diagram</span></span>

<span data-ttu-id="85b7b-145">我们还提供有 DNS 负载平衡比例统一边缘池的图。</span><span class="sxs-lookup"><span data-stu-id="85b7b-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="85b7b-147">缩放统一的 Skype 业务服务器边缘池，使用硬件负载平衡</span><span class="sxs-lookup"><span data-stu-id="85b7b-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="85b7b-148">使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="85b7b-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![带有 HLB 的扩展合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="85b7b-150">端口图</span><span class="sxs-lookup"><span data-stu-id="85b7b-150">Port diagram</span></span>

<span data-ttu-id="85b7b-151">我们还必须使用硬件负载平衡的比例统一边缘池的图</span><span class="sxs-lookup"><span data-stu-id="85b7b-151">We also have a diagram for scaled consolidated Edge pools with hardware load balancing</span></span>
  
![边缘服务器外围网络端口和协议](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

