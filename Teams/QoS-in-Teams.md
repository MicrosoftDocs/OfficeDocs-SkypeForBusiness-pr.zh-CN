---
title: "Microsoft Teams 中的服务质量 (QoS)"
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 02/16/2018
ms.topic: article
ms.service: msteams
description: "针对 Microsoft Teams 的服务质量 (QoS) 准备贵组织的网络。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 61bebd64c7d1478c16e114631b696dee2bf59625
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
<a name="quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="429bd-103">Microsoft Teams 中的服务质量 (QoS)</span><span class="sxs-lookup"><span data-stu-id="429bd-103">Quality of Service (QoS) in Microsoft Teams</span></span>
==========================================
<span data-ttu-id="429bd-104">本指南将帮助你针对 Teams 的服务质量 (QoS) 准备贵组织的网络。</span><span class="sxs-lookup"><span data-stu-id="429bd-104">This guide will help you prepare your organization's network for Quality of Service (QoS) in Teams.</span></span>


<span data-ttu-id="429bd-105">服务质量 (QoS) 机制允许你对特定类型的网络流量进行优先排序。</span><span class="sxs-lookup"><span data-stu-id="429bd-105">Quality of Service (QoS) is a mechanism that lets you prioritize certain types of network traffic.</span></span> <span data-ttu-id="429bd-106">为提供企业级用户体验，对实时通讯服务（如 Teams）的流量进行优先排序至关重要。</span><span class="sxs-lookup"><span data-stu-id="429bd-106">Prioritizing the traffic for real-time communications services such as Teams is important in order to deliver a business-grade user experience.</span></span> <span data-ttu-id="429bd-107">为了使 QoS 真正有效，必须配置端到端的 QoS 兼容连接（PC、网络交换机和路由器到云），因为此路径中的任何部分无法支持 QoS 都可能会降低整个通话的质量。</span><span class="sxs-lookup"><span data-stu-id="429bd-107">For QoS to be truly effective, a QoS-capable connection must be configured end-to-end (PC, network switches, and routers to the cloud), because any part in the path that fails to support QoS could degrade the quality of the entire call.</span></span>


![说明组织网络与 Office 365 服务之间关系的图的屏幕截图](media/Qos-in-Teams-Image1.png)

 

<span data-ttu-id="429bd-109">大多数情况下，互联网络是非托管网络，即互联网连接。</span><span class="sxs-lookup"><span data-stu-id="429bd-109">In most cases, the interconnect network will be an unmanaged network, an internet connection.</span></span> <span data-ttu-id="429bd-110">解决端到端 QoS 的一个可用选项是 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)。</span><span class="sxs-lookup"><span data-stu-id="429bd-110">One option available to address end-to-end QoS is [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).</span></span> <span data-ttu-id="429bd-111">我们建议仍在你控制的网络部分（即本地网络）实施 QoS。</span><span class="sxs-lookup"><span data-stu-id="429bd-111">It is our recommendation to still implement QoS on the portions of the network you have control over, namely your on-premises network.</span></span> <span data-ttu-id="429bd-112">这会提高整个部署中实时通讯工作负荷的质量，并化解现有部署中的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="429bd-112">This will increase the quality of real time communication workloads throughout your deployment and will alleviate choke points in your existing deployment.</span></span> 

## <a name="objectives"></a><span data-ttu-id="429bd-113">目标</span><span class="sxs-lookup"><span data-stu-id="429bd-113">Objectives</span></span> 

<span data-ttu-id="429bd-114">本指南重点介绍如何对实时通讯流量（即语音和视频）进行优先排序。</span><span class="sxs-lookup"><span data-stu-id="429bd-114">This guide will focus on how to prioritize Teams real-time communications traffic, namely voice and video.</span></span> <span data-ttu-id="429bd-115">其他类型的流量也可以根据需要进行优先排序。</span><span class="sxs-lookup"><span data-stu-id="429bd-115">Other types of traffic can also be prioritized based on your needs.</span></span>

<span data-ttu-id="429bd-116">有多种方式对流量进行优先排序，最常用的是使用区分服务代码点 (DSCP) 标记。</span><span class="sxs-lookup"><span data-stu-id="429bd-116">There are multiple ways to prioritize traffic, but the most common is by using differentiated services code point (DSCP) markings.</span></span> <span data-ttu-id="429bd-117">这可以根据端口范围，但也需通过组策略对象进行应用。</span><span class="sxs-lookup"><span data-stu-id="429bd-117">They can be applied based on port ranges but also via Group Policy objects.</span></span> <span data-ttu-id="429bd-118">本文档中将会介绍这两个方面。</span><span class="sxs-lookup"><span data-stu-id="429bd-118">We will cover both in this document.</span></span>

<span data-ttu-id="429bd-119">通过组策略对象 (GPO) 控制 DSCP 标记可以确保加入域的计算机收到正确设置，且这些设置仅由管理员来管理。</span><span class="sxs-lookup"><span data-stu-id="429bd-119">Controlling the DSCP marking via Group Policy objects (GPO) ensures that domain-joined computers receive the correct settings and that these settings can only be managed by an administrator.</span></span> 

<span data-ttu-id="429bd-120">QoS 仅当在将呼叫方连接到被叫方的所有链路上实施时才有效，请务必了解这一点。</span><span class="sxs-lookup"><span data-stu-id="429bd-120">It’s important to understand that QoS only works when implemented on all links connecting caller to callee.</span></span> <span data-ttu-id="429bd-121">如果我们在内部网络上使用 QoS，并且用户从远程位置登录，我们只能在内部的托管网络内进行优先排序。</span><span class="sxs-lookup"><span data-stu-id="429bd-121">If we use QoS on the internal network and a user signs in from a remote location, we can only prioritize within our internal, managed, network.</span></span> <span data-ttu-id="429bd-122">通过实施 VPN 远程位置可能可以收到托管连接，但不建议通过 VPN 运行实时通讯流量。</span><span class="sxs-lookup"><span data-stu-id="429bd-122">While remote locations could receive a managed connection by implementing a VPN, it is not recommended to run real-time communications traffic over the VPN.</span></span>

> [!NOTE]
> <span data-ttu-id="429bd-123">我们建议为 VPN 连接的远程用户实施拆分隧道，以最大限度地改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="429bd-123">Our recommendation is to implement split tunneling for VPN connected remote users to maximize the user experience.</span></span> <span data-ttu-id="429bd-124">有关详细信息，请参阅文档 [VPN 拆分隧道部署指南](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 )。</span><span class="sxs-lookup"><span data-stu-id="429bd-124">See the document [Deploy-Guidance-VPN Split Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) for more information.</span></span>

<span data-ttu-id="429bd-125">在具有跨越大洲的托管链接的全局组织中，强烈建议使用 QoS，因为与本地网络 (LAN) 相比其带宽有限。</span><span class="sxs-lookup"><span data-stu-id="429bd-125">In a global organization with managed links spanning continents, QoS is highly recommended since the bandwidth is limited in comparisons to the local network (LAN).</span></span>

## <a name="quality-of-service"></a><span data-ttu-id="429bd-126">服务质量</span><span class="sxs-lookup"><span data-stu-id="429bd-126">Managing Quality of Service</span></span>

<span data-ttu-id="429bd-127">为了给网络上的应用程序提供有保证的服务级别，基础网络设备必须有办法对不同类型的流量进行分类。</span><span class="sxs-lookup"><span data-stu-id="429bd-127">In order to provide a guaranteed level of service for an application on the network, the underlying network devices must have a way to classify different types of traffic.</span></span> <span data-ttu-id="429bd-128">例如，如果希望语音得到更好的处理，路由器必须能够区分语音流量和正常的 Web 浏览流量。</span><span class="sxs-lookup"><span data-stu-id="429bd-128">A router, for example, must be able to distinguish between voice traffic and normal web browsing traffic, if there is an expectation that voice receives better treatment.</span></span> 

<span data-ttu-id="429bd-129">区分服务 (DiffServ) 提供了一个框架，其中流量由网络设备根据 IPv4/IPv6 包的标题中的服务类型 (ToS) 字段进行处理。</span><span class="sxs-lookup"><span data-stu-id="429bd-129">Differentiated Services (DiffServ) provides a framework in which traffic is treated by network devices with priorities based on the type of services (ToS) field in the header of an IPv4/IPv6 packet.</span></span> <span data-ttu-id="429bd-130">DiffServ 字段最重要的六个数字称为区分服务代码点 (DSCP)。</span><span class="sxs-lookup"><span data-stu-id="429bd-130">The six most significant bits of the DiffServ field is known as the Differentiated Services Code Point, or DSCP.</span></span> <span data-ttu-id="429bd-131">使用此框架，可以将流量分为特定类型的流量（语音），然后进行标记（101110，或十进制 46），例如当网络设备处理这些标记时，可以对流量进行相应地优先排序（本示例中为加速转发）。</span><span class="sxs-lookup"><span data-stu-id="429bd-131">Using this framework, traffic can be classified as a particular type of traffic (voice), and then marked (101110, or 46 in decimal), such that when network devices process these markings, the traffic can be prioritized accordingly (Expedited Forwarding, in this example).</span></span>

<span data-ttu-id="429bd-132">当网络流量进入路由器时，流量将置于队列中，如果没有 QoS，尤其是当仅有一个队列时，数据将按先进先出的顺序处理。这意味着，语音流量（对延迟非常敏感）可能会被在线流服务的流量卡住。</span><span class="sxs-lookup"><span data-stu-id="429bd-132">When network traffic enters a router, the traffic is placed into a queue – if there is no QoS in place, essentially there is only one queue, and data is treated as first-in, first-out. That means voice traffic (which is very sensitive to delays) could get stuck behind traffic from online streaming services.</span></span> <span data-ttu-id="429bd-133">实施 QoS 时，可以定义多个队列，它们具有不同的拥挤管理功能（如 Cisco 的优先排队 (PQ) 和基于类的加权公平队列 (CBWFQ)）以及拥挤避免功能（如加权随机早期检测 (WRED)）。</span><span class="sxs-lookup"><span data-stu-id="429bd-133">When implementing QoS, multiple queues can be defined, with different congestion management features (such as Cisco’s Priority Queuing (PQ) and Class Based Weighted Fair Queue (CBWFQ)) and congestion avoidance features (such as Weighted Random Early Detection (WRED)).</span></span>

![说明 Teams 中 QoS 队列的图的屏幕截图。](media/Qos-in-Teams-Image2.png)

<span data-ttu-id="429bd-135">图 1：QoS 队列可视化</span><span class="sxs-lookup"><span data-stu-id="429bd-135">Figure 1: QoS queues visualized</span></span>

<span data-ttu-id="429bd-136">这些内容就绪后，可以提供可预测的服务质量，因为基础的托管网络现在已经了解如何对流量进行分类、标记和优先排序。</span><span class="sxs-lookup"><span data-stu-id="429bd-136">Once these pieces are in place, a predictable quality of service can be delivered, as the underlying managed network now understands how to classify, mark and prioritize traffic.</span></span> <span data-ttu-id="429bd-137">从 Teams 角度看，最重要的配置项是数据包的分类和标记，但要使应用程序的配置与基础网络配置相符，必须进行谨慎规划，以使端到端 QoS 成功。</span><span class="sxs-lookup"><span data-stu-id="429bd-137">From the Teams perspective, the most important configuration item is the classification and marking of packets – but careful planning is involved to align the application’s configuration with the underlying network configuration for end-to-end QoS to be successful.</span></span>

## <a name="qos-scenarios"></a><span data-ttu-id="429bd-138">QoS 方案</span><span class="sxs-lookup"><span data-stu-id="429bd-138">QoS scenarios</span></span>

<span data-ttu-id="429bd-139">为 Teams 实施 QoS 时，我们以四个开始方案为依据制定了指南：</span><span class="sxs-lookup"><span data-stu-id="429bd-139">When implementing QoS for Teams, we’ve based our guidance on four starting scenarios:</span></span>

1.  <span data-ttu-id="429bd-140">你已部署或正在部署 Teams 并且正在计划通过基于端口的标记实施 QoS。</span><span class="sxs-lookup"><span data-stu-id="429bd-140">You’ve deployed or are deploying Teams and are planning on implementing QoS via Port Based Tagging.</span></span> <span data-ttu-id="429bd-141">基于端口的标记是最可靠的的方法，因为它在所有平台中一致工作且最易于实施。</span><span class="sxs-lookup"><span data-stu-id="429bd-141">Port Based Tagging is the most reliable method since it works universally throughout all platforms and is the easiest to implement.</span></span> 

2.  <span data-ttu-id="429bd-142">你已部署或正在部署 Teams 并且正在计划通过组策略对象标记实施 QoS。</span><span class="sxs-lookup"><span data-stu-id="429bd-142">You’ve deployed or are deploying Teams and are planning to implement QoS via Group Policy Object tagging.</span></span> <span data-ttu-id="429bd-143">此方案有时会与方案 1 结合使用。</span><span class="sxs-lookup"><span data-stu-id="429bd-143">This is sometimes used in combination with scenario 1.</span></span> <span data-ttu-id="429bd-144">此方案非常有效（如下所述），但需要注意的是，它仅适用于已加入域的 Windows 客户端。</span><span class="sxs-lookup"><span data-stu-id="429bd-144">While this scenario is entirely valid and described below, it is important to understand this will only work for Domain Joined Windows Clients.</span></span> <span data-ttu-id="429bd-145">任何不是已加入域的 Windows 客户端的设备不会启用 QoS\DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="429bd-145">Any device that is not a Windows Domain Joined Client will not be enabled for QoS\DSCP Tagging.</span></span> 

3.  <span data-ttu-id="429bd-146">你已部署 Skype for Business Online（包括 QoS 标记）且正在部署 Teams。</span><span class="sxs-lookup"><span data-stu-id="429bd-146">You have Skype for Business Online deployed including QoS Tagging and are now deploying Teams.</span></span> <span data-ttu-id="429bd-147">如果是你，Teams 将遵循现有配置，并且将使用与 Skype for Business 客户端相同的端口范围和标记。</span><span class="sxs-lookup"><span data-stu-id="429bd-147">If this is you, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="429bd-148">不需要进行额外配置。</span><span class="sxs-lookup"><span data-stu-id="429bd-148">No additional configuration should be needed.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="429bd-149">如果你正在使用通过组策略的应用程序名称 QoS 标记，应将“Teams.exe”添加为应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="429bd-149">If you're using Application Name QoS tagging via Group Policy you should add “Teams.exe” as Application Name.</span></span>
4.  <span data-ttu-id="429bd-150">你已部署或正在部署 Teams 并且想要通过基于端口的标记使用自定义端口范围实施 QoS。</span><span class="sxs-lookup"><span data-stu-id="429bd-150">You’ve deployed or are deploying Teams and want to implement QoS via port-based tagging with a custom port range.</span></span>

## <a name="recommended-differentiated-services-code-point-dscp-markings"></a><span data-ttu-id="429bd-151">建议的区分服务代码点 (DSCP) 标记</span><span class="sxs-lookup"><span data-stu-id="429bd-151">Recommended differentiated services code point (DSCP) markings</span></span>

<span data-ttu-id="429bd-152">第一步是利用具有 DSC 值的非重叠唯一端口范围对流量（如音频和视频）进行分类。</span><span class="sxs-lookup"><span data-stu-id="429bd-152">The first step is to classify the traffic flows (such as audio and video) by leveraging the unique, non-overlapping port ranges with a DSCP-value.</span></span> <span data-ttu-id="429bd-153">此处分配的 DSC 值将根据网络配置，确定网络中的流量优先级。</span><span class="sxs-lookup"><span data-stu-id="429bd-153">The DSCP value assigned here will determine the priority of the traffic going through the network (based on the network configuration).</span></span> <span data-ttu-id="429bd-154">每个工作负荷都有自己的 DSCP 值，尽管有些客户可能会对语音和视频设置相同的值，让他们在网络中具有相同优先级。</span><span class="sxs-lookup"><span data-stu-id="429bd-154">Each workload gets its own DSCP value, although some customers might set the same value on voice and video, giving them the same priority in the network.</span></span> 

<span data-ttu-id="429bd-155">要使用的 DSCP 值取决于工作负荷的优先级。</span><span class="sxs-lookup"><span data-stu-id="429bd-155">What DSCP value to use depends on how a workload is prioritized.</span></span> <span data-ttu-id="429bd-156">例如，业务要求可能决定使用与视频相同的优先级（因此会标记与视频相同的 DSCP 值）处理应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="429bd-156">For example, business requirements could dictate that application sharing is to be treated with the same level of priority as video (and as such, marked with the same DSCP-value as video).</span></span> <span data-ttu-id="429bd-157">其他环境可能已有 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="429bd-157">Other environments might have an existing QoS strategy in place already.</span></span> 

<span data-ttu-id="429bd-158">下面的表 1 显示了将 Teams 与 ExpressRoute 结合使用时所需的 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="429bd-158">Table 1 below shows the required DSCP markings when utilizing Teams with ExpressRoute.</span></span> <span data-ttu-id="429bd-159">对于不确定在自己环境中使用哪些标记的客户而言，这是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="429bd-159">This could serve as a good starting point for customers unsure what to use in their own environment.</span></span> <span data-ttu-id="429bd-160">要了解详细信息，请阅读 [ExpressRoute QoS 要求](https://docs.microsoft.com/azure/expressroute/expressroute-qos)。</span><span class="sxs-lookup"><span data-stu-id="429bd-160">To learn more, read [ExpressRoute QoS requirements](https://docs.microsoft.com/azure/expressroute/expressroute-qos).</span></span>


| <span data-ttu-id="429bd-161">客户端源端口</span><span class="sxs-lookup"><span data-stu-id="429bd-161">Client source port</span></span>|<span data-ttu-id="429bd-162">协议</span><span class="sxs-lookup"><span data-stu-id="429bd-162">Protocol</span></span>|<span data-ttu-id="429bd-163">媒体类别</span><span class="sxs-lookup"><span data-stu-id="429bd-163">Media category</span></span>|<span data-ttu-id="429bd-164">常用 DSCP 值</span><span class="sxs-lookup"><span data-stu-id="429bd-164">Common DSCP value</span></span>|<span data-ttu-id="429bd-165">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="429bd-165">DSCP class</span></span>|
|---------|---------|---------|---------|---------|
| <span data-ttu-id="429bd-166">50,000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="429bd-166">50,000 – 50,019</span></span>|<span data-ttu-id="429bd-167">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="429bd-167">TCP/UDP</span></span>|<span data-ttu-id="429bd-168">音频</span><span class="sxs-lookup"><span data-stu-id="429bd-168">Audio</span></span>|<span data-ttu-id="429bd-169">46</span><span class="sxs-lookup"><span data-stu-id="429bd-169">46</span></span>|<span data-ttu-id="429bd-170">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="429bd-170">Expedited Forwarding (EF)</span></span>|
| <span data-ttu-id="429bd-171">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="429bd-171">50,020 – 50,039</span></span>|<span data-ttu-id="429bd-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="429bd-172">TCP/UDP</span></span>|<span data-ttu-id="429bd-173">视频</span><span class="sxs-lookup"><span data-stu-id="429bd-173">Video</span></span>|<span data-ttu-id="429bd-174">34</span><span class="sxs-lookup"><span data-stu-id="429bd-174">3-4</span></span>|<span data-ttu-id="429bd-175">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="429bd-175">Assured Forwarding (AF41)</span></span>|
| <span data-ttu-id="429bd-176">50,040 – 50,059</span><span class="sxs-lookup"><span data-stu-id="429bd-176">50,040 – 50,059</span></span>|<span data-ttu-id="429bd-177">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="429bd-177">TCP/UDP</span></span>|<span data-ttu-id="429bd-178">应用程序/桌面共享和文件传输</span><span class="sxs-lookup"><span data-stu-id="429bd-178">Application/Desktop Sharing and File Transfer</span></span>|<span data-ttu-id="429bd-179">18</span><span class="sxs-lookup"><span data-stu-id="429bd-179">18</span></span>|<span data-ttu-id="429bd-180">类选择器 (CS3)</span><span class="sxs-lookup"><span data-stu-id="429bd-180">Class Selector (CS3)</span></span>|

<span data-ttu-id="429bd-181">表 1：DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="429bd-181">Table 1: DSCP markings</span></span>

<span data-ttu-id="429bd-182">下面是使用表 1 中的信息时的一些注意事项：</span><span class="sxs-lookup"><span data-stu-id="429bd-182">Here are some caveats to understand when you use the information in Table 1:</span></span>

- <span data-ttu-id="429bd-183">文件共享和应用程序共享使用相同的源端口范围，因此，在使用基于端口的标记时将使用相同的 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="429bd-183">File sharing and application sharing use the same source port range – and as such, would use the same DSCP markings when using Port Based Tagging.</span></span> <span data-ttu-id="429bd-184">因此，它还会确定哪个优先级对*两种*模式（交互式或默认）最适用。</span><span class="sxs-lookup"><span data-stu-id="429bd-184">Because of this, it should be determined which priority is most applicable to *both* modalities (Interactive or Default).</span></span>
    
- <span data-ttu-id="429bd-185">如果计划在未来实施 ExpressRoute 且尚未实施 QoS，建议遵循上述指南，因此发送者和接收者的 DSCP 值将相同。</span><span class="sxs-lookup"><span data-stu-id="429bd-185">If there’s a plan to implement ExpressRoute in the future and QoS has not yet been implemented, the recommendation is to follow the guidance given above so that DSCP values are the same from sender to receiver.</span></span> 
    
## <a name="source-ports-used-by-teams"></a><span data-ttu-id="429bd-186">Teams 使用的源端口</span><span class="sxs-lookup"><span data-stu-id="429bd-186">Source ports used by Teams</span></span>

<span data-ttu-id="429bd-187">在 Teams 中，应根据不同工作负荷使用的源端口配置 QoS。</span><span class="sxs-lookup"><span data-stu-id="429bd-187">In Teams, QoS should be configured based on the source ports used by the different workloads.</span></span> <span data-ttu-id="429bd-188">此时服务器端和客户端的端口范围均不可配置。</span><span class="sxs-lookup"><span data-stu-id="429bd-188">Both server-side and client-side port ranges are non-configurable at this point.</span></span> 

<span data-ttu-id="429bd-189">为部署 QoS，请使用表 2 中列出的客户端源端口范围及其相关的 QoS DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="429bd-189">To deploy QoS, use the client source port ranges listed in Table 2, with their associated QoS DSCP markings.</span></span>

| <span data-ttu-id="429bd-190">客户端源端口</span><span class="sxs-lookup"><span data-stu-id="429bd-190">Client source port</span></span>|<span data-ttu-id="429bd-191">协议</span><span class="sxs-lookup"><span data-stu-id="429bd-191">Protocol</span></span>|<span data-ttu-id="429bd-192">媒体类别</span><span class="sxs-lookup"><span data-stu-id="429bd-192">Media category</span></span>|<span data-ttu-id="429bd-193">常用 DSCP 值</span><span class="sxs-lookup"><span data-stu-id="429bd-193">Common DSCP value</span></span>|<span data-ttu-id="429bd-194">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="429bd-194">DSCP class</span></span>|
|---------|---------|---------|---------|---------|
| <span data-ttu-id="429bd-195">50,000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="429bd-195">50,000 – 50,019</span></span>|<span data-ttu-id="429bd-196">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="429bd-196">TCP/UDP</span></span>|<span data-ttu-id="429bd-197">音频</span><span class="sxs-lookup"><span data-stu-id="429bd-197">Audio</span></span>|<span data-ttu-id="429bd-198">46</span><span class="sxs-lookup"><span data-stu-id="429bd-198">46</span></span>|<span data-ttu-id="429bd-199">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="429bd-199">Expedited Forwarding (EF)</span></span>|
| <span data-ttu-id="429bd-200">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="429bd-200">50,020 – 50,039</span></span>|<span data-ttu-id="429bd-201">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="429bd-201">TCP/UDP</span></span>|<span data-ttu-id="429bd-202">视频</span><span class="sxs-lookup"><span data-stu-id="429bd-202">Video</span></span>|<span data-ttu-id="429bd-203">34</span><span class="sxs-lookup"><span data-stu-id="429bd-203">3-4</span></span>|<span data-ttu-id="429bd-204">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="429bd-204">Assured Forwarding (AF41)</span></span>|
| <span data-ttu-id="429bd-205">50,040 – 50,059</span><span class="sxs-lookup"><span data-stu-id="429bd-205">50,040 – 50,059</span></span>|<span data-ttu-id="429bd-206">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="429bd-206">TCP/UDP</span></span>|<span data-ttu-id="429bd-207">应用程序/桌面共享和文件传输</span><span class="sxs-lookup"><span data-stu-id="429bd-207">Application/Desktop Sharing and File Transfer</span></span>|<span data-ttu-id="429bd-208">18</span><span class="sxs-lookup"><span data-stu-id="429bd-208">18</span></span>|<span data-ttu-id="429bd-209">类选择器 (CS3)</span><span class="sxs-lookup"><span data-stu-id="429bd-209">Class Selector (CS3)</span></span>|

<span data-ttu-id="429bd-210">表 2：客户端源端口范围</span><span class="sxs-lookup"><span data-stu-id="429bd-210">Table 2: Client source port ranges</span></span>

> [!NOTE]
> <span data-ttu-id="429bd-211">如果你已根据 Skype for Business Online 的源端口范围配置 QoS，相同配置将适用于 Teams，无需进行其他更改。</span><span class="sxs-lookup"><span data-stu-id="429bd-211">If you've already configured QoS based on source port ranges for Skype for Business Online, the same configuration will apply to Teams and no further changes are required.</span></span> <span data-ttu-id="429bd-212">如果你已经部署 Skype for Business 服务器（本地），则需要重新设计 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="429bd-212">If you’ve deployed Skype for Business Server (on premises), you will need to redesign your QoS Policies.</span></span>

## <a name="setting-differentiated-services-code-point-dscp-markings"></a><span data-ttu-id="429bd-213">设置区分服务代码点 (DSCP) 标记</span><span class="sxs-lookup"><span data-stu-id="429bd-213">Setting differentiated services code point (DSCP) markings</span></span>

<span data-ttu-id="429bd-214">有多种方法设置正确的 DSCP 标记以进行流量分类。</span><span class="sxs-lookup"><span data-stu-id="429bd-214">There are multiple approaches to setting the proper DSCP markings for traffic classification.</span></span>

- <span data-ttu-id="429bd-215">端点处的 DSCP 标记：通常这是首选选项，因为端点本身可提供正确标记。</span><span class="sxs-lookup"><span data-stu-id="429bd-215">DSCP marking at the endpoint: This is the preferred option in general, as the endpoint itself is providing the proper markings.</span></span> <span data-ttu-id="429bd-216">目前这可以使用 GPO 完成，但这仅在已加入域的 Windows 客户端上可行。</span><span class="sxs-lookup"><span data-stu-id="429bd-216">Currently this could be done by using a GPO, but this is only possible on domain-joined Windows clients.</span></span> <span data-ttu-id="429bd-217">例如，Mac OSX 或移动客户端不提供使用 DSCP 值标记流量的机制。</span><span class="sxs-lookup"><span data-stu-id="429bd-217">Mac OSX or mobile clients, for example, do not provide a mechanism to mark traffic with DSCP values.</span></span>

- <span data-ttu-id="429bd-218">基于端口，使用路由器上的 ACL：这在 Windows 和 Mac 的异构环境中是常用选项。</span><span class="sxs-lookup"><span data-stu-id="429bd-218">Port-based using ACLs on routers: This is a very common option encountered in heterogeneous environments of Windows and Mac.</span></span> <span data-ttu-id="429bd-219">在此方案中，网络团队根据为每种模式定义的源端口范围标记入口/出口路由器（通常位于广域网 (WAN)）的流量。</span><span class="sxs-lookup"><span data-stu-id="429bd-219">In this scenario, the network team marks the traffic at the ingress/egress routers (typically on the Wide Area Network (WAN)) based on the source port ranges defined for each modality.</span></span> <span data-ttu-id="429bd-220">这种方法适用于各种平台，但它仅在 WAN 边缘进行标记，而不是一直标记到客户端计算机，并且会产生管理费用。</span><span class="sxs-lookup"><span data-stu-id="429bd-220">While this works across platforms, it only marks at the WAN edge – not all the way to the client machine – and incurs management overhead.</span></span>
    
- <span data-ttu-id="429bd-221">在客户端上使用 DSCP 标记，在路由器上使用基于端口的 ACL。</span><span class="sxs-lookup"><span data-stu-id="429bd-221">A combination of DSCP markings on the client and port-based ACLs on routers.</span></span>
    
<span data-ttu-id="429bd-222">如果可行，我们建议结合使用两者，以便使用 GPO 控制大部分客户端，同时使用基于端口的 DSCP 标记确保移动客户端、Mac 和其他客户端仍会获得（部分）QoS 处理。</span><span class="sxs-lookup"><span data-stu-id="429bd-222">If possible, we recommend a combination of both, to use a GPO to catch the majority of clients, and to also use port based DSCP tagging to ensure mobile clients, Mac and other clients will still get a (partial) QoS treatment.</span></span>

<span data-ttu-id="429bd-223">可以使用组策略内基于策略的 QoS 为 Teams 客户端中的预定义源端口范围设置 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="429bd-223">Setting the DSCP value for the pre-defined source port range in the Teams client can be done using policy-based QoS within Group Policy.</span></span> <span data-ttu-id="429bd-224">下表使用表中指定的端口范围为每种工作负荷创建策略。</span><span class="sxs-lookup"><span data-stu-id="429bd-224">The following table uses the port ranges specified in the table to create a policy for each workload.</span></span>

| <span data-ttu-id="429bd-225">客户端流量类型</span><span class="sxs-lookup"><span data-stu-id="429bd-225">Client traffic type</span></span>|<span data-ttu-id="429bd-226">端口范围起始值</span><span class="sxs-lookup"><span data-stu-id="429bd-226">Port range start</span></span>|<span data-ttu-id="429bd-227">端口范围结束值</span><span class="sxs-lookup"><span data-stu-id="429bd-227">Port range end</span></span>|<span data-ttu-id="429bd-228">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="429bd-228">DSCP value</span></span>|
|---------|---------|---------|--------|
| <span data-ttu-id="429bd-229">音频</span><span class="sxs-lookup"><span data-stu-id="429bd-229">Audio</span></span>|<span data-ttu-id="429bd-230">50000</span><span class="sxs-lookup"><span data-stu-id="429bd-230">50000</span></span>|<span data-ttu-id="429bd-231">50019</span><span class="sxs-lookup"><span data-stu-id="429bd-231">50019</span></span>|<span data-ttu-id="429bd-232">46</span><span class="sxs-lookup"><span data-stu-id="429bd-232">46</span></span>|
| <span data-ttu-id="429bd-233">视频</span><span class="sxs-lookup"><span data-stu-id="429bd-233">Video</span></span>|<span data-ttu-id="429bd-234">50020</span><span class="sxs-lookup"><span data-stu-id="429bd-234">50020</span></span>|<span data-ttu-id="429bd-235">50039</span><span class="sxs-lookup"><span data-stu-id="429bd-235">50039</span></span>|<span data-ttu-id="429bd-236">34</span><span class="sxs-lookup"><span data-stu-id="429bd-236">3-4</span></span>|
| <span data-ttu-id="429bd-237">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="429bd-237">Application sharing</span></span>|<span data-ttu-id="429bd-238">50040</span><span class="sxs-lookup"><span data-stu-id="429bd-238">50040</span></span>|<span data-ttu-id="429bd-239">50059</span><span class="sxs-lookup"><span data-stu-id="429bd-239">50059</span></span>|<span data-ttu-id="429bd-240">18</span><span class="sxs-lookup"><span data-stu-id="429bd-240">18</span></span>|
| <span data-ttu-id="429bd-241">文件传输</span><span class="sxs-lookup"><span data-stu-id="429bd-241">File transfer</span></span>|<span data-ttu-id="429bd-242">50040</span><span class="sxs-lookup"><span data-stu-id="429bd-242">50040</span></span>|<span data-ttu-id="429bd-243">50059</span><span class="sxs-lookup"><span data-stu-id="429bd-243">50059</span></span>|<span data-ttu-id="429bd-244">18</span><span class="sxs-lookup"><span data-stu-id="429bd-244">18</span></span>|

<span data-ttu-id="429bd-245">表 3：按流量类型的端口范围</span><span class="sxs-lookup"><span data-stu-id="429bd-245">Table 3: Port ranges by traffic type</span></span>

<span data-ttu-id="429bd-246">注意：Teams 设置的端口范围无法更改。</span><span class="sxs-lookup"><span data-stu-id="429bd-246">Note: The port ranges set by Teams cannot be changed or altered.</span></span> <span data-ttu-id="429bd-247">有关最新信息，请查看此页面：https://support.microsoft.com/ kb/2409256</span><span class="sxs-lookup"><span data-stu-id="429bd-247">Please review this page for the latest information: https://support.microsoft.com/ kb/2409256</span></span>

<span data-ttu-id="429bd-248">确定端口范围后，下一步是在组策略对象 (GPO) 内配置基于策略的 QoS 设置。</span><span class="sxs-lookup"><span data-stu-id="429bd-248">Once the port ranges have been determined, the next step is to configure the policy-based QoS settings within a Group Policy Object (GPO).</span></span> <span data-ttu-id="429bd-249">有关这些步骤的详细信息，请访问 [TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="429bd-249">Details for these steps can be found on [TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx).</span></span> 

<span data-ttu-id="429bd-250">必须在客户端计算机上刷新组策略，然后你创建的新策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="429bd-250">The new policies you have created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="429bd-251">尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="429bd-251">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

        gpudate.exe /force

<span data-ttu-id="429bd-252">此命令可以从在管理员凭据下运行的任何命令窗口运行。</span><span class="sxs-lookup"><span data-stu-id="429bd-252">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="429bd-253">若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="429bd-253">To open a command window, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

## <a name="verifying-the-dscp-markings-in-gpo"></a><span data-ttu-id="429bd-254">验证 GPO 中的 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="429bd-254">Verifying the DSCP markings in GPO</span></span>

<span data-ttu-id="429bd-255">要验证是否已设置 GPO 的值，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="429bd-255">To verify that the values from the GPO has been set, please perform the following steps:</span></span>

1.  <span data-ttu-id="429bd-256">使用 gpresult 验证本地 PC 是否已收到 GPO 的设置。</span><span class="sxs-lookup"><span data-stu-id="429bd-256">Use gpresult to verify that the settings from the GPO has been received by the local PC.</span></span> <span data-ttu-id="429bd-257">gpresult /R >gp.txt 将生成一个报告并发送到文本文件 gp.txt。</span><span class="sxs-lookup"><span data-stu-id="429bd-257">gpresult /R >gp.txt will generate a report and send it to a text file, gp.txt.</span></span>

    ![运行 gpresult 命令的管理员命令提示符的屏幕截图。](media/Qos-in-Teams-Image3.png)

    <span data-ttu-id="429bd-259">图 2：验证应用的组策略对象</span><span class="sxs-lookup"><span data-stu-id="429bd-259">Figure 2: Verify Applied Group Policy Objects</span></span>
    > [!NOTE]
    > <span data-ttu-id="429bd-260">或者，你可以运行 gpresult /H gp.html，以更加用户友好的 HTML 报告形式生成相同数据。</span><span class="sxs-lookup"><span data-stu-id="429bd-260">Alternatively, you can run gpresult /H gp.html to produce the same data in more user-friendly HTML report.</span></span> 
2.  <span data-ttu-id="429bd-261">在生成的文件中查找标头“应用的组策略对象”并验证应用的策略列表中包含之前创建的 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="429bd-261">In the generated file look for the heading: Applied Group Policy Objects and verify that the names of the GPO’s created earlier is in the list of applied policies.</span></span> 

3.  <span data-ttu-id="429bd-262">打开注册表编辑器并导航到：</span><span class="sxs-lookup"><span data-stu-id="429bd-262">Open the registry editor and navigate to:</span></span>

    <span data-ttu-id="429bd-263">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span><span class="sxs-lookup"><span data-stu-id="429bd-263">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span></span>

    <span data-ttu-id="429bd-264">验证下面的表 3 中列出的注册表值。</span><span class="sxs-lookup"><span data-stu-id="429bd-264">Verify the registry values listed in Table 3 below.</span></span>
    
    | <span data-ttu-id="429bd-265">名称</span><span class="sxs-lookup"><span data-stu-id="429bd-265">Name</span></span> | <span data-ttu-id="429bd-266">类型</span><span class="sxs-lookup"><span data-stu-id="429bd-266">Type</span></span> | <span data-ttu-id="429bd-267">数据</span><span class="sxs-lookup"><span data-stu-id="429bd-267">Data</span></span>|
    |---------|---------|---------
    | <span data-ttu-id="429bd-268">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="429bd-268">Application Name</span></span>|<span data-ttu-id="429bd-269">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-269">REG_SZ</span></span>|<span data-ttu-id="429bd-270">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="429bd-270">Teams.exe</span></span>|
    | <span data-ttu-id="429bd-271">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="429bd-271">DSCP Value - 10</span></span>|<span data-ttu-id="429bd-272">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-272">REG_SZ</span></span>|<span data-ttu-id="429bd-273">46</span><span class="sxs-lookup"><span data-stu-id="429bd-273">46</span></span>|
    | <span data-ttu-id="429bd-274">本地 IP</span><span class="sxs-lookup"><span data-stu-id="429bd-274">Second Reflexive Local IP</span></span>|<span data-ttu-id="429bd-275">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-275">REG_SZ</span></span>|*|
    | <span data-ttu-id="429bd-276">本地 IP 前缀长度</span><span class="sxs-lookup"><span data-stu-id="429bd-276">Local IP Prefix Length</span></span>|<span data-ttu-id="429bd-277">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-277">REG_SZ</span></span>|*|
    | <span data-ttu-id="429bd-278">本地端口</span><span class="sxs-lookup"><span data-stu-id="429bd-278">Local Port</span></span>|<span data-ttu-id="429bd-279">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-279">REG_SZ</span></span>|<span data-ttu-id="429bd-280">50000-50019</span><span class="sxs-lookup"><span data-stu-id="429bd-280">50000-50019</span></span>|
    | <span data-ttu-id="429bd-281">协议</span><span class="sxs-lookup"><span data-stu-id="429bd-281">Protocol</span></span>|<span data-ttu-id="429bd-282">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-282">REG_SZ</span></span>|*|
    | <span data-ttu-id="429bd-283">远程 IP</span><span class="sxs-lookup"><span data-stu-id="429bd-283">Remote IP</span></span>|<span data-ttu-id="429bd-284">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-284">REG_SZ</span></span>|*|
    | <span data-ttu-id="429bd-285">远程 IP 前缀</span><span class="sxs-lookup"><span data-stu-id="429bd-285">Remote Ip Prefix</span></span>|<span data-ttu-id="429bd-286">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-286">REG_SZ</span></span>|*|
    | <span data-ttu-id="429bd-287">远程端口</span><span class="sxs-lookup"><span data-stu-id="429bd-287">Remote Port</span></span>|<span data-ttu-id="429bd-288">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-288">REG_SZ</span></span>|*|
    | <span data-ttu-id="429bd-289">限制率</span><span class="sxs-lookup"><span data-stu-id="429bd-289">Throttle Rate</span></span>|<span data-ttu-id="429bd-290">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="429bd-290">REG_SZ</span></span>|<span data-ttu-id="429bd-291">-1</span><span class="sxs-lookup"><span data-stu-id="429bd-291">$1</span></span>|
    
    <span data-ttu-id="429bd-292">表 3：QoS 的 Windows 注册表值</span><span class="sxs-lookup"><span data-stu-id="429bd-292">Table 3: Windows registry values for QoS</span></span>

4.  <span data-ttu-id="429bd-293">验证应用程序名称对你使用的客户端是否正确，并验证 DSCP 值和本地端口是否反映了 GPO 中的设置。</span><span class="sxs-lookup"><span data-stu-id="429bd-293">Verify that the Application Name is correct for the client you are using, and verify that both DSCP value and Local Port reflect the settings in the GPO.</span></span>

## <a name="validating-qos-analyzing-teams-traffic-on-the-network"></a><span data-ttu-id="429bd-294">验证 QoS：分析网络上的 Teams 流量</span><span class="sxs-lookup"><span data-stu-id="429bd-294">Validating QoS: Analyzing Teams traffic on the network</span></span>

<span data-ttu-id="429bd-295">GPO 设置的 DSCP 值需要从呼叫方呈现给被叫方，以使 QoS 生效。</span><span class="sxs-lookup"><span data-stu-id="429bd-295">The DSCP value set by the GPO needs to be present from caller to callee in order for QoS to be affective.</span></span> <span data-ttu-id="429bd-296">通过检查 Teams 客户端生成的流量，我们可以验证遍历网络时 DSCP 是否未更改或者未消失。</span><span class="sxs-lookup"><span data-stu-id="429bd-296">By looking at the traffic generated by the Teams client we can verify that the DSCP is not changed or stripped out when traversing the network.</span></span> 

<span data-ttu-id="429bd-297">我们倾向于捕获网络入口点的流量。</span><span class="sxs-lookup"><span data-stu-id="429bd-297">Preferably we would capture traffic at the network egress point.</span></span> <span data-ttu-id="429bd-298">可以在交换机或路由器上使用端口镜像，以帮助捕获网络上的流量。</span><span class="sxs-lookup"><span data-stu-id="429bd-298">Port mirroring can be used on a switch or router to aid in capturing traffic on the network.</span></span> 

### <a name="looking-at-network-traffic-using-network-monitor"></a><span data-ttu-id="429bd-299">使用网络监视器查看网络流量</span><span class="sxs-lookup"><span data-stu-id="429bd-299">Looking at network traffic using Network Monitor</span></span>

<span data-ttu-id="429bd-300">网络监视器是一款可以从 Microsoft 下载以分析流量的工具。</span><span class="sxs-lookup"><span data-stu-id="429bd-300">Network Monitor is a tool you can download from Microsoft to analyze network traffic.</span></span> <span data-ttu-id="429bd-301">下载[网络监视器 3.4](https://www.microsoft.com/download/4865)。</span><span class="sxs-lookup"><span data-stu-id="429bd-301">Download [Network Monitor 3.4](https://www.microsoft.com/download/4865).</span></span>

<span data-ttu-id="429bd-302">连接到运行网络监视器的 PC 上配置为端口镜像的端口并开始捕获数据包。</span><span class="sxs-lookup"><span data-stu-id="429bd-302">Connect to PC running network monitor to the port that has been configured for port mirroring and start capturing packets.</span></span> <span data-ttu-id="429bd-303">使用 Skype for Business 客户端拨打电话。</span><span class="sxs-lookup"><span data-stu-id="429bd-303">Make and receive a video call using Skype for Business</span></span> <span data-ttu-id="429bd-304">在挂断电话之前确保媒体已建立。</span><span class="sxs-lookup"><span data-stu-id="429bd-304">Make sure media is established before hanging up the call.</span></span> <span data-ttu-id="429bd-305">停止捕获，创建与拨打电话的 PC 的源 IP 相匹配的显示筛选器，并将 DSCP 值 46 (hex 0xb8) 定义为搜索条件以缩小筛选范围：</span><span class="sxs-lookup"><span data-stu-id="429bd-305">Stop the capture create a Display Filter that matches the source IP of the PC that made the call and refine the filter by defining DSCP value 46 (hex 0xb8) as search criteria:</span></span>

<span data-ttu-id="429bd-306">Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8</span><span class="sxs-lookup"><span data-stu-id="429bd-306">Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8</span></span> 

![网络监视器中“显示筛选器”对话框的屏幕截图，显示要应用的筛选器。](media/Qos-in-Teams-Image4.png)


<span data-ttu-id="429bd-308">单击“应用”****以激活筛选器。</span><span class="sxs-lookup"><span data-stu-id="429bd-308">Click **Apply** to activate the filter.</span></span> <span data-ttu-id="429bd-309">在“帧摘要”****窗口中，选择第一个 UDP 包并查看帧详细信息：</span><span class="sxs-lookup"><span data-stu-id="429bd-309">In the **Frame Summary** window, select the first UDP packet and look at the Frame Details:</span></span>

![网络监视器中“帧详细信息”对话框的屏幕截图，突出显示 DSCP 设置。](media/Qos-in-Teams-Image5.png)

<span data-ttu-id="429bd-311">扩展 IPv4 并查看 DSCP 行末尾的值。</span><span class="sxs-lookup"><span data-stu-id="429bd-311">Expand IPv4 and look at the value at the end of the DSCP line.</span></span> <span data-ttu-id="429bd-312">在本示例中，我们看到 DSCP 值设置为 46，这是正确的，因为使用的源端口是 50019，这告诉我们工作负荷是语音。</span><span class="sxs-lookup"><span data-stu-id="429bd-312">In this example we see that the DSCP value is set to 46 which is correct since the source port used is 50019 which tells us that the workload is voice.</span></span> 

<span data-ttu-id="429bd-313">为 GPO 标记的每个工作负荷重复执行验证。</span><span class="sxs-lookup"><span data-stu-id="429bd-313">Repeat the verification for each workload that has been marked by the GPO.</span></span> 

> [!NOTE]
> <span data-ttu-id="429bd-314">验证标记对点对点流量也同样适用。</span><span class="sxs-lookup"><span data-stu-id="429bd-314">Verify that markings are honored for peer-to-peer traffic as well.</span></span> <span data-ttu-id="429bd-315">可以通过在两个客户端上安装网络监视器并在这两个客户端之间拨打电话来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="429bd-315">This can be done by installing Network Monitor on two clients and placing calls between the two clients.</span></span> <span data-ttu-id="429bd-316">按上面所述的相同方式查看客户端之间的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="429bd-316">Look at the media traffic flowing between clients in the same manner as described above.</span></span>

### <a name="sample-filters-to-use-for-network-monitor-or-wireshark"></a><span data-ttu-id="429bd-317">用于网络监视器或 Wireshark 的示例筛选器</span><span class="sxs-lookup"><span data-stu-id="429bd-317">Sample filters to use for Network Monitor or Wireshark</span></span>

|<span data-ttu-id="429bd-318">用法</span><span class="sxs-lookup"><span data-stu-id="429bd-318">Usage</span></span>  |<span data-ttu-id="429bd-319">示例筛选器</span><span class="sxs-lookup"><span data-stu-id="429bd-319">Sample filter</span></span>  |
|---------|---------|
|<span data-ttu-id="429bd-320">语音（注意：必须关闭复用）</span><span class="sxs-lookup"><span data-stu-id="429bd-320">Voice (note: muxing must be turned off)</span></span>     |   <span data-ttu-id="429bd-321">udp.port==3479 AND Ipv4.DifferentiatedServicesField.DSCP==46</span><span class="sxs-lookup"><span data-stu-id="429bd-321">udp.port==3479 AND Ipv4.DifferentiatedServicesField.DSCP==46</span></span>      |
|<span data-ttu-id="429bd-322">视频</span><span class="sxs-lookup"><span data-stu-id="429bd-322">Video</span></span>     | <span data-ttu-id="429bd-323">udp.port==3480 AND Ipv4.DifferentiatedServicesField.DSCP==34</span><span class="sxs-lookup"><span data-stu-id="429bd-323">udp.port==3480 AND Ipv4.DifferentiatedServicesField.DSCP==34</span></span>        |
|<span data-ttu-id="429bd-324">屏幕共享</span><span class="sxs-lookup"><span data-stu-id="429bd-324">Screen sharing</span></span>     |  <span data-ttu-id="429bd-325">udp.port==3481 AND Ipv4.DifferentiatedServicesField.DSCP==18</span><span class="sxs-lookup"><span data-stu-id="429bd-325">udp.port==3481 AND Ipv4.DifferentiatedServicesField.DSCP==18</span></span>       |

### <a name="filter-media-traffic-from-microsoft-relays-requires-azure-expressroutehttpsazuremicrosoftcomservicesexpressroute"></a><span data-ttu-id="429bd-326">筛选器：来自 Microsoft 中继的媒体流量（需要 [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)）</span><span class="sxs-lookup"><span data-stu-id="429bd-326">Filter: Media traffic from Microsoft relays (requires [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/))</span></span>

<span data-ttu-id="429bd-327">{52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} 中的 ip.src 和 {3479 3480 3481} 中的 (udp.srcport 或 (udp.srcport ge 50000 和 udp.srcport lt 60000))</span><span class="sxs-lookup"><span data-stu-id="429bd-327">ip.src in {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} and (udp.srcport in {3479 3480 3481} or (udp.srcport ge 50000 and udp.srcport lt 60000))</span></span>

### <a name="filter-media-traffic-to-microsoft-relays"></a><span data-ttu-id="429bd-328">筛选器：发送到 Microsoft 中继的媒体流量</span><span class="sxs-lookup"><span data-stu-id="429bd-328">Filter: Media traffic to Microsoft relays</span></span>

<span data-ttu-id="429bd-329">{52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} 中的 ip.dst 和 {3479 3480 3481} 中的 (udp.dstport 或 (udp.dstport ge 50000 和 udp.dstport lt 60000))</span><span class="sxs-lookup"><span data-stu-id="429bd-329">ip.dst in {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} and (udp.dstport in {3479 3480 3481} or (udp.dstport ge 50000 and udp.dstport lt 60000))</span></span>


<span data-ttu-id="429bd-330">你应该会看到发送到和来自 Microsoft 中继的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="429bd-330">You should see traffic to and from the Microsoft relays.</span></span> <span data-ttu-id="429bd-331">你可以检查 Wireshark 中 IP 层上的 DSCP 标记，如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="429bd-331">You can check DSCP markings on the IP layer in Wireshark, as shown in the next section.</span></span>

### <a name="expected-dscp-markings"></a><span data-ttu-id="429bd-332">预期的 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="429bd-332">Expected DSCP markings</span></span>

<span data-ttu-id="429bd-333">音频流：46</span><span class="sxs-lookup"><span data-stu-id="429bd-333">Audio streams: 46</span></span>

<span data-ttu-id="429bd-334">视频流：34</span><span class="sxs-lookup"><span data-stu-id="429bd-334">Video streams: 34</span></span>

<span data-ttu-id="429bd-335">数据流：18</span><span class="sxs-lookup"><span data-stu-id="429bd-335">Data streams: 18</span></span>

### <a name="filter-dscp-condition-to-network"></a><span data-ttu-id="429bd-336">筛选器：网络的 DSCP 条件</span><span class="sxs-lookup"><span data-stu-id="429bd-336">Filter: DSCP condition to network</span></span>

<span data-ttu-id="429bd-337">{46 34 18} 中的 ip.dsfield.dscp</span><span class="sxs-lookup"><span data-stu-id="429bd-337">ip.dsfield.dscp in {46 34 18}</span></span>



### <a name="looking-at-network-traffic-using-wireshark"></a><span data-ttu-id="429bd-338">使用 Wireshark 查看网络流量</span><span class="sxs-lookup"><span data-stu-id="429bd-338">Looking at network traffic using Wireshark</span></span>

<span data-ttu-id="429bd-339">Wireshark (https://www.wireshark.org/) 是一款功能强大的功能，允许用户筛选和记录网络数据以供进一步分析。</span><span class="sxs-lookup"><span data-stu-id="429bd-339">Wireshark, https://www.wireshark.org/, is a powerful tool that allows us to filter and record network data for further analysis.</span></span> <span data-ttu-id="429bd-340">连接到运行 Wireshark 的 PC 上配置为端口镜像的端口并开始捕获数据包。</span><span class="sxs-lookup"><span data-stu-id="429bd-340">Connect a PC running Wireshark to the port that has been configured for port mirroring and start capturing packets.</span></span> <span data-ttu-id="429bd-341">使用 Teams 客户端拨打电话。</span><span class="sxs-lookup"><span data-stu-id="429bd-341">Make a call using the Teams client.</span></span> <span data-ttu-id="429bd-342">在挂断电话之前确保媒体已建立。</span><span class="sxs-lookup"><span data-stu-id="429bd-342">Make sure media is established before hanging up the call.</span></span>

<span data-ttu-id="429bd-343">停止数据包跟踪并创建仅显示安装 Teams 客户端的 PC 的源 IP 的筛选器，例如 *ip.src_host == 192.168.137.201*。查找使用来自为语音指定的范围 (50,000 – 50,019) 的源端口的数据包：</span><span class="sxs-lookup"><span data-stu-id="429bd-343">Stop the packet trace and create a filter that only displays the source IP of the PC where the Teams client is installed, for example, *ip.src_host == 192.168.137.201* and looks for packages that use a source port from the range specified for voice, 50,000 – 50,019:</span></span>

![具有筛选器设置的 Wireshark 的屏幕截图](media/Qos-in-Teams-Image6.png)
 

<span data-ttu-id="429bd-345">在数据包详细信息窗格中标记数据包并展开 Internet 协议版本 4 (IPV4) 标头：</span><span class="sxs-lookup"><span data-stu-id="429bd-345">Mark the package and expand the Internet Protocol Version 4 (IPV4) header in the packet detail pane:</span></span>

![突出显示区分服务代码点设置的 Wireshark 的屏幕截图。](media/Qos-in-Teams-Image7.png)
 

<span data-ttu-id="429bd-347">验证*区分服务代码点*的值是否与特定工作负荷的值匹配，本示例中语音的值为 46（二进制 101110）。</span><span class="sxs-lookup"><span data-stu-id="429bd-347">Verify that the value for *Differentiated Services Codepoint* match the value for the specific workload, in this case 46 (binary 101110) for voice.</span></span>

<span data-ttu-id="429bd-348">为 GPO 标记的每个工作负荷重复执行验证。</span><span class="sxs-lookup"><span data-stu-id="429bd-348">Repeat the verification for each workload that has been marked by the GPO.</span></span>

> [!NOTE]
> <span data-ttu-id="429bd-349">验证标记对点对点流量适用。</span><span class="sxs-lookup"><span data-stu-id="429bd-349">Verify that markings are honored for peer-to-peer traffic.</span></span> <span data-ttu-id="429bd-350">可以通过在两个客户端上安装 WireShark 或网络监视器并在这两个客户端之间拨打电话来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="429bd-350">This can be done by installing WireShark or Network Monitor on two clients and placing calls between the two clients.</span></span> <span data-ttu-id="429bd-351">按上面所述的相同方式查看客户端之间的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="429bd-351">Look at the media traffic flowing between clients in the same manner as described above.</span></span>

## <a name="summary"></a><span data-ttu-id="429bd-352">摘要</span><span class="sxs-lookup"><span data-stu-id="429bd-352">Summary</span></span>

<span data-ttu-id="429bd-353">要提供 Teams 企业级体验，服务质量的重要性不容忽视。</span><span class="sxs-lookup"><span data-stu-id="429bd-353">Quality of Service is an important piece of the puzzle when providing business-class experiences with Teams.</span></span> <span data-ttu-id="429bd-354">但是，必须始终牢记，QoS 仅对正确托管的网络有效。</span><span class="sxs-lookup"><span data-stu-id="429bd-354">However, it is important to always remember that QoS is only effective on properly managed networks.</span></span> <span data-ttu-id="429bd-355">因此，部署团队必须与网络团队密切合作，确保在网络层传递正确的信息，理想情况是从端到端进行托管。</span><span class="sxs-lookup"><span data-stu-id="429bd-355">As such, the deployment team must work very closely with the networking teams to ensure the proper information is passed at the network layer, ideally managed from end-to-end.</span></span>

