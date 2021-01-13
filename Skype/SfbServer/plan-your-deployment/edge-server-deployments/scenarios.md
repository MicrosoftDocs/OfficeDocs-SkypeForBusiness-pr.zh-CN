---
title: Skype for Business Server 中的边缘服务器方案
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：查看这些方案，帮助你在 Skype for Business Server 中规划边缘服务器拓扑。
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813788"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="3fad5-103">Skype for Business Server 中的边缘服务器方案</span><span class="sxs-lookup"><span data-stu-id="3fad5-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="3fad5-104">**摘要：** 查看这些方案有助于在 Skype for Business Server 中规划边缘服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="3fad5-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="3fad5-105">我们具有一些方案图，可帮助可视化和确定要实现哪些 Skype for Business Server 边缘服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="3fad5-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="3fad5-106">选择好候选人后，可以继续阅读需要满足的环境要求。</span><span class="sxs-lookup"><span data-stu-id="3fad5-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="3fad5-107">下面适用于任何方案，因此我们首先提到它。</span><span class="sxs-lookup"><span data-stu-id="3fad5-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="3fad5-108">这些图仅供 (所示，因此包含示例 IPv4 和 IPv6) ，并不表示实际的通信流，而是可能流量的高级别视图。</span><span class="sxs-lookup"><span data-stu-id="3fad5-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="3fad5-109">还可以在下面的每个方案的端口图中查看端口详细信息。</span><span class="sxs-lookup"><span data-stu-id="3fad5-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="3fad5-110">图中显示了外部接口的 .com 和内部接口的 .net，这也是示例材料;当然，在将自己的最终边缘计划放在一起时，你自己的条目可能会截然不同。</span><span class="sxs-lookup"><span data-stu-id="3fad5-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="3fad5-111">我们未在任何图中 (作为可选组件) 的 Director) ，但您可以单独阅读 (其他规划主题中) 。</span><span class="sxs-lookup"><span data-stu-id="3fad5-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="3fad5-112">如上所述，图表中有示例 IPv6 数据。</span><span class="sxs-lookup"><span data-stu-id="3fad5-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="3fad5-113">Skype [for Business Server](edge-server-deployments.md) 中"规划边缘服务器部署"中的大多数文档将引用 IPv4，但如果你想要使用 IPv6，则当然支持你。</span><span class="sxs-lookup"><span data-stu-id="3fad5-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="3fad5-114">请注意，你将需要分配的地址空间中的 IPv6 地址，并且它们将需要与 IPv4 IP 一样处理内部和外部寻址。</span><span class="sxs-lookup"><span data-stu-id="3fad5-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="3fad5-115">借助 Windows，你可以采用双协议栈功能，这是适用于 IPv4 和 IPv6 的单独且不同的网络堆栈。</span><span class="sxs-lookup"><span data-stu-id="3fad5-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="3fad5-116">如果需要，这将允许你同时分配 IPv4 和 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="3fad5-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="3fad5-117">存在允许 NAT64 (IPv6 到 IPv4) 和 NAT66 (IPv6 到 IPv6) ) 的 NAT 设备，这适用于 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="3fad5-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3fad5-118">如果使用呼叫允许控制 (CAC) 您必须在内部接口上使用 IPv4，它可以使用。</span><span class="sxs-lookup"><span data-stu-id="3fad5-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="3fad5-119">具有专用 IP 地址和 NAT 的单个合并 Skype for Business Server 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="3fad5-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="3fad5-120">在此方案中，没有高可用性选项。</span><span class="sxs-lookup"><span data-stu-id="3fad5-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="3fad5-121">这意味着在硬件上花费更少，部署更简单。</span><span class="sxs-lookup"><span data-stu-id="3fad5-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="3fad5-122">如果必须高可用性，请查看下面的扩展合并方案。</span><span class="sxs-lookup"><span data-stu-id="3fad5-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![使用 NAT 使用专用 IP 的单一合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="3fad5-124">端口图</span><span class="sxs-lookup"><span data-stu-id="3fad5-124">Port diagram</span></span>

<span data-ttu-id="3fad5-125">我们还具有单个合并边缘服务器的端口关系图。</span><span class="sxs-lookup"><span data-stu-id="3fad5-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![边缘方案单一合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="3fad5-127">具有公用 IP 地址的单一合并 Skype for Business Server 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="3fad5-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="3fad5-128">在此方案中，没有高可用性选项。</span><span class="sxs-lookup"><span data-stu-id="3fad5-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="3fad5-129">这意味着在硬件上花费更少，部署更简单。</span><span class="sxs-lookup"><span data-stu-id="3fad5-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="3fad5-130">如果必须高可用性，请查看下面的扩展合并方案。</span><span class="sxs-lookup"><span data-stu-id="3fad5-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![使用公共 IP 的单一合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="3fad5-132">端口图</span><span class="sxs-lookup"><span data-stu-id="3fad5-132">Port diagram</span></span>

<span data-ttu-id="3fad5-133">我们还具有单个合并边缘服务器的端口关系图。</span><span class="sxs-lookup"><span data-stu-id="3fad5-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![边缘方案单一合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="3fad5-135">扩展的合并 Skype for Business Server 边缘池，具有 DNS 负载平衡以及专用 IP 地址和 NAT</span><span class="sxs-lookup"><span data-stu-id="3fad5-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="3fad5-136">通过此方案，可以在边缘部署中实现高可用性，从而为您提供可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="3fad5-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![扩展合并边缘（使用 NAT 使用专用 IP 的 DNS LB）的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="3fad5-138">端口图</span><span class="sxs-lookup"><span data-stu-id="3fad5-138">Port diagram</span></span>

<span data-ttu-id="3fad5-139">我们还有一个包含 DNS 负载平衡的扩展合并边缘池的图。</span><span class="sxs-lookup"><span data-stu-id="3fad5-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![使用 DNS LB 扩展的合并边缘的边缘方案的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="3fad5-141">扩展的合并 Skype for Business Server 边缘池，具有 DNS 负载平衡和公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="3fad5-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="3fad5-142">通过此方案，可以在边缘部署中实现高可用性，从而为您提供可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="3fad5-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![扩展合并边缘的边缘方案（使用公共 IP 的 DNS LB）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="3fad5-144">端口图</span><span class="sxs-lookup"><span data-stu-id="3fad5-144">Port diagram</span></span>

<span data-ttu-id="3fad5-145">我们还有一个包含 DNS 负载平衡的扩展合并边缘池的图。</span><span class="sxs-lookup"><span data-stu-id="3fad5-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![使用 DNS LB 扩展的合并边缘的边缘方案的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="3fad5-147">扩展的合并 Skype for Business Server 边缘池，具有硬件负载平衡</span><span class="sxs-lookup"><span data-stu-id="3fad5-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="3fad5-148">通过此方案，可以在边缘部署中实现高可用性，从而为您提供可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="3fad5-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![使用 HLB 扩展的合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
