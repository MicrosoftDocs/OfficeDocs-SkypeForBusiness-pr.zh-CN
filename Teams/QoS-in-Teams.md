---
title: Microsoft Teams 中的服务质量 - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 针对 Microsoft Teams 的服务质量 (QoS) 准备贵组织的网络。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5e6b37a0daff06a4676a7ecba1b67ecdd03649a
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789091"
---
# <a name="quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="6a085-103">Microsoft Teams 中的服务质量 (QoS)</span><span class="sxs-lookup"><span data-stu-id="6a085-103">Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="6a085-104">本文将帮助您的服务质量 (QoS) 中的 Microsoft 团队准备贵组织的网络。</span><span class="sxs-lookup"><span data-stu-id="6a085-104">This article will help you prepare your organization's network for Quality of Service (QoS) in Microsoft Teams.</span></span>

<span data-ttu-id="6a085-105">您可以使用 QoS 设置优先级通过不太敏感的流量对网络延迟敏感的网络流量。</span><span class="sxs-lookup"><span data-stu-id="6a085-105">You can use QoS to prioritize network traffic that is sensitive to network delays over traffic that is less sensitive.</span></span> <span data-ttu-id="6a085-106">简单葡萄形状是 QoS 创建虚拟数据中的"乘泳道"从不网络因此某些类型的数据或很少遇到延迟。</span><span class="sxs-lookup"><span data-stu-id="6a085-106">A simple analogy is that QoS creates virtual “carpool lanes” in your data network so some types of data never or rarely encounter delays.</span></span>
<span data-ttu-id="6a085-107">设置优先级的实时通信，如呼叫或团队可以共享的会议流量时详细可靠地提供业务级的用户体验。</span><span class="sxs-lookup"><span data-stu-id="6a085-107">When you prioritize the traffic for real-time communications such as calls or shared meetings in Teams you can more reliably deliver a business-grade user experience.</span></span> <span data-ttu-id="6a085-108">如果没有 QoS 某种形式，您可能会看到以下语音和视频质量问题：</span><span class="sxs-lookup"><span data-stu-id="6a085-108">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="6a085-109">抖动 – 到达不同的比率的媒体数据包。</span><span class="sxs-lookup"><span data-stu-id="6a085-109">Jitter – media packets arriving at different rates.</span></span>
- <span data-ttu-id="6a085-110">数据包丢失 – 数据包而丢弃，这可能会导致缺少单词或音节。</span><span class="sxs-lookup"><span data-stu-id="6a085-110">Packet loss – packets dropped, which can result in missing words or syllables.</span></span>
- <span data-ttu-id="6a085-111">延迟的往返时间 (RTT) – 需要很长的时间到达其目标媒体数据包。</span><span class="sxs-lookup"><span data-stu-id="6a085-111">Delayed round trip time (RTT) – media packets taking a long time to reach their destinations.</span></span>

<span data-ttu-id="6a085-112">对于要真正有效的 QoS，一致 QoS 设置需要应用端到端中您的组织 （用户 Pc、 网络交换机和路由器到云），因为无法支持 QoS 优先级路径的任何部分会降低呼叫质量视频和屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="6a085-112">For QoS to be truly effective, consistent QoS settings need to be applied from end to end in your organization (user PCs, network switches, and routers to the cloud), because any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen shares.</span></span>

<span data-ttu-id="6a085-113">![组织的网络和 Office 365 服务之间的关系： 本地网络和设备将与反过来连接和 Office 365 云语音和音频会议服务互连网络连接。](media/Qos-in-Teams-Image1.png "组织的网络和 Office 365 服务之间的关系： 本地网络和设备将与反过来连接和 Office 365 云语音和音频会议服务互连网络连接。")</span><span class="sxs-lookup"><span data-stu-id="6a085-113">![The relationship between an organization's networks and Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Office 365 Cloud Voice and Audio Conferencing services.](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

<span data-ttu-id="6a085-114">_图 1。组织的网络和 Office 365 服务之间的关系_</span><span class="sxs-lookup"><span data-stu-id="6a085-114">_Figure 1. The relationship between an organization’s networks and Office 365 services_</span></span>


<span data-ttu-id="6a085-115">在大多数情况下，该互连网络将非托管的网络 internet 连接。</span><span class="sxs-lookup"><span data-stu-id="6a085-115">In most cases, the interconnect network will be an unmanaged network internet connection.</span></span> 

<span data-ttu-id="6a085-116">一个选项可用于解决端到端 QoS 是[Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)。</span><span class="sxs-lookup"><span data-stu-id="6a085-116">One option available to address end-to-end QoS is [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).</span></span> <span data-ttu-id="6a085-117">我们仍建议您实现您的本地网络上的 QoS。</span><span class="sxs-lookup"><span data-stu-id="6a085-117">We still recommend that you implement QoS on your on-premises network.</span></span> <span data-ttu-id="6a085-118">这将提高整个部署的实时通信工作负载的质量，并解决阻塞点。</span><span class="sxs-lookup"><span data-stu-id="6a085-118">This will increase the quality of real-time communication workloads throughout your deployment and alleviate chokepoints.</span></span> 


## <a name="prioritize-teams-network-traffic-for-qos"></a><span data-ttu-id="6a085-119">设置团队网络流量优先级的 QoS</span><span class="sxs-lookup"><span data-stu-id="6a085-119">Prioritize Teams network traffic for QoS</span></span> 

<span data-ttu-id="6a085-120">本文重点介绍如何设置优先级团队实时通信流量 — 即，语音和视频。</span><span class="sxs-lookup"><span data-stu-id="6a085-120">This article focuses on how to prioritize Teams real-time communications traffic—namely, voice and video.</span></span> <span data-ttu-id="6a085-121">您还可以设置优先级其他类型的通信，根据您的需求。</span><span class="sxs-lookup"><span data-stu-id="6a085-121">You can also prioritize other types of traffic, based on your needs.</span></span>

<span data-ttu-id="6a085-122">有几种方法来确定优先级流量，但最常见使用区分的服务代码点 (DSCP) 标记。</span><span class="sxs-lookup"><span data-stu-id="6a085-122">There are several ways to prioritize traffic, but the most common is by using differentiated services code point (DSCP) markings.</span></span> <span data-ttu-id="6a085-123">它们可以应用 （"已标记"） 基于端口范围或通过组策略对象。</span><span class="sxs-lookup"><span data-stu-id="6a085-123">They can be applied (“tagged”) based on port ranges or via Group Policy objects.</span></span> <span data-ttu-id="6a085-124">我们将介绍均位于这篇文章。</span><span class="sxs-lookup"><span data-stu-id="6a085-124">We’ll cover both in this article.</span></span> <span data-ttu-id="6a085-125">我们建议您使用标记基于端口范围，因为它适用于所有设备，而不仅仅是加入到域。</span><span class="sxs-lookup"><span data-stu-id="6a085-125">We recommend that you use tagging based on port ranges because it will work for all devices, not just those joined to the domain.</span></span>

<span data-ttu-id="6a085-126">控制通过组策略对象 DSCP 标记确保加入域的计算机接收设置正确，并且只有管理员可以管理其。</span><span class="sxs-lookup"><span data-stu-id="6a085-126">Controlling the DSCP marking via Group Policy objects ensures that domain-joined computers receive the correct settings and that only an administrator can manage them.</span></span>

<span data-ttu-id="6a085-127">务必了解 QoS 在连接到另一个呼叫者的所有链接上实现时才有效。</span><span class="sxs-lookup"><span data-stu-id="6a085-127">It’s important to understand that QoS only works when implemented on all links that connect caller to another.</span></span> <span data-ttu-id="6a085-128">如果您使用内部网络上的 QoS，一个用户登录从远程位置，您可以仅设置优先级内部、 托管网络中。</span><span class="sxs-lookup"><span data-stu-id="6a085-128">If you use QoS on the internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="6a085-129">尽管远程位置可以通过实现虚拟专用网络 (VPN) 接收托管的连接，我们建议您避免运行实时通信流量通过 VPN。</span><span class="sxs-lookup"><span data-stu-id="6a085-129">Although remote locations can receive a managed connection by implementing a virtual private network (VPN), we  recommend that you avoid running real-time communications traffic over the VPN.</span></span>

> [!NOTE]
> <span data-ttu-id="6a085-130">我们建议您实现拆分隧道 VPN 连接远程用户最大化的用户体验质量。</span><span class="sxs-lookup"><span data-stu-id="6a085-130">We recommend that you implement split tunneling for VPN-connected remote users to maximize the quality of the user experience.</span></span> <span data-ttu-id="6a085-131">将文档[部署指南 VPN 拆分隧道](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 )从 MyAdvisor 下载的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6a085-131">Download the document [Deploy-Guidance-VPN Split Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) from MyAdvisor for more information.</span></span>

<span data-ttu-id="6a085-132">在全局组织中使用托管跨洲的链接，强烈建议 QoS 因为这些链接的带宽有限 LAN 进行对比。</span><span class="sxs-lookup"><span data-stu-id="6a085-132">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="qos-queues"></a><span data-ttu-id="6a085-133">QoS 队列</span><span class="sxs-lookup"><span data-stu-id="6a085-133">QoS queues</span></span>

<span data-ttu-id="6a085-134">若要提供 QoS，网络设备必须具有分类通信的方式，并且必须能够与其他网络流量区分语音或视频。</span><span class="sxs-lookup"><span data-stu-id="6a085-134">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span> 

<span data-ttu-id="6a085-135">区分的服务 (DiffServ) 使用服务 （直观操作方法） 的 IPv4/IPv6 数据包标头中的字段的类型设置网络设备的优先级。</span><span class="sxs-lookup"><span data-stu-id="6a085-135">Differentiated services (DiffServ) uses the type of services (ToS) field in the header of an IPv4/IPv6 packet to set priority for network devices.</span></span> <span data-ttu-id="6a085-136">DiffServ 字段的六个最重要位是区分的服务代码点或 DSCP。</span><span class="sxs-lookup"><span data-stu-id="6a085-136">The six most significant bits of the DiffServ field are the differentiated services code point, or DSCP.</span></span> <span data-ttu-id="6a085-137">使用这种情况，流量可以是归类为特定类型 （例如，语音），然后将标记 （101110 或 46 的语音流量的十进制），以便相应地时网络设备处理这些标记，可以确定优先级流量 （中快速转发，此示例中）。</span><span class="sxs-lookup"><span data-stu-id="6a085-137">Using this, traffic can be classified as a particular type (for example, voice), and then marked (101110, or 46 in decimal for voice traffic), so that when network devices process these markings, the traffic can be prioritized accordingly (expedited forwarding, in this example).</span></span>

<span data-ttu-id="6a085-138">当网络流量进入路由器时，流量放入队列。</span><span class="sxs-lookup"><span data-stu-id="6a085-138">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="6a085-139">如果没有任何 QoS 就地，没有为只有一个队列，并且数据处理为第一项，先出。这意味着语音通信 （这是非常对延迟敏感） 可能停滞后面流量从联机流服务。</span><span class="sxs-lookup"><span data-stu-id="6a085-139">If there is no QoS in place, there is only one queue, and data is treated as first-in, first-out. That means voice traffic (which is very sensitive to delays) might get stuck behind traffic from online streaming services.</span></span> <span data-ttu-id="6a085-140">实现 QoS 时，您可以使用不同的拥塞管理功能 （如 Cisco 的优先级队列和基于类的加权公平队列 [CBWFQ]） 和拥塞避免功能 （如加权随机早期检测 [定义多个队列WRED])。</span><span class="sxs-lookup"><span data-stu-id="6a085-140">When you implement QoS, you can define multiple queues by using different congestion management features (such as Cisco’s priority queuing and class-based weighted fair queue [CBWFQ]) and congestion avoidance features (such as weighted random early detection [WRED]).</span></span>

<span data-ttu-id="6a085-141">![全部可用带宽分为多个队列 — 音频、 视频和其他通信 — 的已分配不同的优先级。](media/Qos-in-Teams-Image2.png "全部可用带宽分为多个队列 — 音频、 视频和其他通信 — 的已分配不同的优先级。")</span><span class="sxs-lookup"><span data-stu-id="6a085-141">![Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="6a085-142">_图 2。QoS 队列的示例_</span><span class="sxs-lookup"><span data-stu-id="6a085-142">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="6a085-143">这些条目准备就绪后，就可以传递可预测的 QoS，因为基础的托管的网络现在了解如何进行分类，将标记，并设置其优先级流量。</span><span class="sxs-lookup"><span data-stu-id="6a085-143">After these pieces are in place, it’s possible to deliver predictable QoS because the underlying managed network now understands how to classify, mark, and prioritize traffic.</span></span> <span data-ttu-id="6a085-144">从工作组角度来看，最重要的配置步骤的分类和标记的数据包，但在进行端到端 QoS 成功您还需要仔细对齐的基础的网络配置的应用程序的配置。</span><span class="sxs-lookup"><span data-stu-id="6a085-144">From the Teams perspective, the most important configuration step is the classification and marking of packets, but for end-to-end QoS to be successful you also need to carefully align the application’s configuration with the underlying network configuration.</span></span>

## <a name="teams-qos-scenarios"></a><span data-ttu-id="6a085-145">团队 QoS 方案</span><span class="sxs-lookup"><span data-stu-id="6a085-145">Teams QoS scenarios</span></span>

<span data-ttu-id="6a085-146">有关 QoS 团队的实施的指南基于四种方案：</span><span class="sxs-lookup"><span data-stu-id="6a085-146">The guidance for implementing QoS for Teams is based on four scenarios:</span></span>

*  <span data-ttu-id="6a085-147">**方案 1:** 您已部署或要部署团队并计划实现 QoS 通过基于端口的标记。</span><span class="sxs-lookup"><span data-stu-id="6a085-147">**Scenario 1:** You’ve deployed or are deploying Teams and plan to implement QoS via port-based tagging.</span></span> <span data-ttu-id="6a085-148">基于端口的标记处于最可靠的方法，因为它适用于所有平台上的全局和是最容易实现。</span><span class="sxs-lookup"><span data-stu-id="6a085-148">Port-based tagging is the most reliable method because it works universally on all platforms and is the easiest to implement.</span></span>  

*  <span data-ttu-id="6a085-149">**方案 2:** 您已部署或要部署团队并计划通过组策略对象标记实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="6a085-149">**Scenario 2:** You’ve deployed or are deploying Teams and plan to implement QoS via Group Policy object tagging.</span></span> <span data-ttu-id="6a085-150">此方案有时会与方案 1 结合使用。</span><span class="sxs-lookup"><span data-stu-id="6a085-150">This is sometimes used in combination with scenario 1.</span></span> <span data-ttu-id="6a085-151">尽管这种情况下完全无效，但它仅适用于加入域的 Windows 客户端。</span><span class="sxs-lookup"><span data-stu-id="6a085-151">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="6a085-152">未加入域的 Windows 客户端的任何设备不启用 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="6a085-152">Any device that isn’t a domain-joined Windows client won’t be enabled for DSCP tagging.</span></span>

*  <span data-ttu-id="6a085-153">**方案 3:** 您已部署 Skype 业务 Online，包括 QoS 标记，并立即部署团队。</span><span class="sxs-lookup"><span data-stu-id="6a085-153">**Scenario 3:** You’ve deployed Skype for Business Online, including QoS tagging, and are now deploying Teams.</span></span> <span data-ttu-id="6a085-154">如果是你，Teams 将遵循现有配置，并且将使用与 Skype for Business 客户端相同的端口范围和标记。</span><span class="sxs-lookup"><span data-stu-id="6a085-154">If this is you, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="6a085-155">在大多数情况下，将不需要任何其他配置。</span><span class="sxs-lookup"><span data-stu-id="6a085-155">In most cases, no additional configuration will be needed.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="6a085-156">如果您使用的应用程序名称 QoS 标记通过组策略，您必须添加 Teams.exe 作为应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="6a085-156">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

*  <span data-ttu-id="6a085-157">**方案 4:** 已部署或要部署团队，希望通过基于端口的标记使用的自定义端口范围中实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="6a085-157">**Scenario 4:** You’ve deployed or are deploying Teams and want to implement QoS via port-based tagging by using a custom port range.</span></span>

## <a name="implement-qos"></a><span data-ttu-id="6a085-158">实施 QoS</span><span class="sxs-lookup"><span data-stu-id="6a085-158">Implement QoS</span></span>

<span data-ttu-id="6a085-159">在非常高级别，实现 QoS 需要以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6a085-159">At a very high level, implementing QoS requires these steps:</span></span>

1. <span data-ttu-id="6a085-160">确定您路由和带宽的要求。</span><span class="sxs-lookup"><span data-stu-id="6a085-160">Determine your route and bandwidth requirements.</span></span>

2. <span data-ttu-id="6a085-161">使用 DSCP 标记和端口范围分类流量。</span><span class="sxs-lookup"><span data-stu-id="6a085-161">Use DSCP markings and port ranges to classify traffic.</span></span>

3. <span data-ttu-id="6a085-162">配置组策略对象中的基于策略的 QoS 设置。</span><span class="sxs-lookup"><span data-stu-id="6a085-162">Configure the policy-based QoS settings within a Group Policy object.</span></span>

4. <span data-ttu-id="6a085-163">验证在组策略对象的端口范围。</span><span class="sxs-lookup"><span data-stu-id="6a085-163">Verify the port ranges in the Group Policy object.</span></span>

5. <span data-ttu-id="6a085-164">验证通过分析团队流量网络上的 QoS。</span><span class="sxs-lookup"><span data-stu-id="6a085-164">Validate QoS by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="6a085-165">准备实现 QoS 时，请记住以下准则：</span><span class="sxs-lookup"><span data-stu-id="6a085-165">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="6a085-166">Office 365 的最短路径是最佳。</span><span class="sxs-lookup"><span data-stu-id="6a085-166">The shortest path to Office 365 is best.</span></span>

- <span data-ttu-id="6a085-167">关闭端口仅将导致质量下降。</span><span class="sxs-lookup"><span data-stu-id="6a085-167">Closing ports will only lead to quality degradation.</span></span>

- <span data-ttu-id="6a085-168">任何障碍中间，如代理，不建议使用。</span><span class="sxs-lookup"><span data-stu-id="6a085-168">Any obstacles in-between, such as proxies, are not recommended.</span></span>

- <span data-ttu-id="6a085-169">限制跃距数：</span><span class="sxs-lookup"><span data-stu-id="6a085-169">Limit the number of hops:</span></span>

    - <span data-ttu-id="6a085-170">客户端到网络边缘 – 3 到 5 跃点数。</span><span class="sxs-lookup"><span data-stu-id="6a085-170">Client to network edge – 3 to 5 hops.</span></span>
    - <span data-ttu-id="6a085-171">Microsoft 网络边缘 – 3 个跳跃 ISP</span><span class="sxs-lookup"><span data-stu-id="6a085-171">ISP to Microsoft network edge – 3 hops</span></span>
    - <span data-ttu-id="6a085-172">Microsoft 网络边缘到最终目的地 – 无关</span><span class="sxs-lookup"><span data-stu-id="6a085-172">Microsoft network edge to final destination – irrelevant</span></span> 

<span data-ttu-id="6a085-173">有关配置防火墙端口的信息，请转到[Office 365 Url 和 IP 范围](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="6a085-173">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="determine-bandwidth-requirements"></a><span data-ttu-id="6a085-174">确定带宽要求</span><span class="sxs-lookup"><span data-stu-id="6a085-174">Determine bandwidth requirements</span></span>

<span data-ttu-id="6a085-175">配置 Microsoft 团队的 QoS 之前，请务必为 Microsoft 团队准备您的网络并确定您的带宽要求。</span><span class="sxs-lookup"><span data-stu-id="6a085-175">Before you configure QoS for Microsoft Teams, it’s important to prepare your network for Microsoft Teams and determine your bandwidth requirements.</span></span> <span data-ttu-id="6a085-176">QoS 提供网络中的实时通信要求保留每个链接上定义带宽量。</span><span class="sxs-lookup"><span data-stu-id="6a085-176">Providing QoS in your network requires the reservation of a defined amount of bandwidth on each link for real-time traffic.</span></span> <span data-ttu-id="6a085-177">（如果在任何时候，该带宽不是必需的实时通信，它可用于其他通信。）</span><span class="sxs-lookup"><span data-stu-id="6a085-177">(If that bandwidth isn’t required for real-time traffic at any time, it can be used for other traffic.)</span></span>

<span data-ttu-id="6a085-178">通过网络流量拥塞将会显著影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="6a085-178">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="6a085-179">缺乏带宽导致性能下降和很差的用户体验，因此请考虑带宽规划团队部署的起始点。</span><span class="sxs-lookup"><span data-stu-id="6a085-179">A lack of bandwidth leads to performance degradation and a poor user experience, so consider bandwidth planning as a starting point for Teams deployment.</span></span> <span data-ttu-id="6a085-180">随着团队应用和使用情况，则可以使用报告功能，来进行必要的调整。</span><span class="sxs-lookup"><span data-stu-id="6a085-180">As Teams adoption and usage grows, use reporting to make necessary adjustments.</span></span> 

<span data-ttu-id="6a085-181">确定带宽要求时，可以帮助网络规划人员 FastTrack 上可用。</span><span class="sxs-lookup"><span data-stu-id="6a085-181">The Network Planner available on FastTrack is helpful when you are determining bandwidth requirements.</span></span>

### <a name="requirements-for-a-connection-from-your-network-to-microsoft-network-edge"></a><span data-ttu-id="6a085-182">用于从您的网络连接到 Microsoft 网络边缘的要求</span><span class="sxs-lookup"><span data-stu-id="6a085-182">Requirements for a connection from your network to Microsoft network edge</span></span>

<span data-ttu-id="6a085-183">作为最佳媒体质量，表 1 中显示的阈值的网络性能目标所需从组织的网络连接到 Microsoft 网络边缘。</span><span class="sxs-lookup"><span data-stu-id="6a085-183">For the best media quality, the network performance targets or thresholds shown in Table 1 are required for a connection from your organization’s network to the Microsoft network edge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a085-184">连接到 Office 365 服务公司网络上的团队客户端之间必须满足以下网络性能要求。</span><span class="sxs-lookup"><span data-stu-id="6a085-184">Connectivity between a Teams client on your company network to Office 365 services must meet the following network performance requirements.</span></span>

<span data-ttu-id="6a085-185">_表 1。网络性能指标-到 Office 365 服务的客户端_</span><span class="sxs-lookup"><span data-stu-id="6a085-185">_Table 1. Network performance metrics - client to Office 365 services_</span></span>

| <span data-ttu-id="6a085-186">指标</span><span class="sxs-lookup"><span data-stu-id="6a085-186">Metric</span></span> | <span data-ttu-id="6a085-187">目标</span><span class="sxs-lookup"><span data-stu-id="6a085-187">Target</span></span> |
|--------|--------|
| <span data-ttu-id="6a085-188">延迟（单向）</span><span class="sxs-lookup"><span data-stu-id="6a085-188">Latency (one way)</span></span> | <span data-ttu-id="6a085-189">< 50 毫秒</span><span class="sxs-lookup"><span data-stu-id="6a085-189">< 50 milliseconds</span></span> |
| <span data-ttu-id="6a085-190">延迟 （来回行程时间 (RTT)</span><span class="sxs-lookup"><span data-stu-id="6a085-190">Latency (round trip time (RTT)</span></span> | <span data-ttu-id="6a085-191">< 100 毫秒</span><span class="sxs-lookup"><span data-stu-id="6a085-191">< 100 milliseconds</span></span> |
| <span data-ttu-id="6a085-192">突发数据包丢失</span><span class="sxs-lookup"><span data-stu-id="6a085-192">Burst packet loss</span></span> | <span data-ttu-id="6a085-193">任何 200 毫秒的时间间隔期间 < 10%</span><span class="sxs-lookup"><span data-stu-id="6a085-193">< 10% during any 200 millisecond interval</span></span> |
| <span data-ttu-id="6a085-194">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="6a085-194">Packet loss</span></span> | <span data-ttu-id="6a085-195">任何 15 的第二个间隔期间 < 1%</span><span class="sxs-lookup"><span data-stu-id="6a085-195">< 1% during any 15 second interval</span></span> |
| <span data-ttu-id="6a085-196">数据包间到达抖动</span><span class="sxs-lookup"><span data-stu-id="6a085-196">Packet inter-arrival jitter</span></span> | <span data-ttu-id="6a085-197">任何 15 的第二个间隔期间 < 30 毫秒</span><span class="sxs-lookup"><span data-stu-id="6a085-197">< 30 milliseconds during any 15 second interval</span></span> |
| <span data-ttu-id="6a085-198">数据包重新排序</span><span class="sxs-lookup"><span data-stu-id="6a085-198">Packet reorder</span></span> | <span data-ttu-id="6a085-199">利用顺序数据包 < 0.05%</span><span class="sxs-lookup"><span data-stu-id="6a085-199">< 0.05% out of order packets</span></span> |

<span data-ttu-id="6a085-200">延迟指标目标假定您的公司网站和 Microsoft 边缘位于同一洲。</span><span class="sxs-lookup"><span data-stu-id="6a085-200">The latency metric target assumes your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="6a085-201">Microsoft 网络边缘连接到您公司网站中包含第一个跃点网络访问，可以是 WiFi 或其他无线技术。</span><span class="sxs-lookup"><span data-stu-id="6a085-201">Your company site to the Microsoft network edge connection includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="6a085-202">网络性能目标假定适当的带宽和/或 QoS 规划。</span><span class="sxs-lookup"><span data-stu-id="6a085-202">The network performance target assumes proper bandwidth and/or QoS planning.</span></span> <span data-ttu-id="6a085-203">换句话说的要求适用于团队实时的媒体流量直接峰值负载下的网络连接时。</span><span class="sxs-lookup"><span data-stu-id="6a085-203">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

### <a name="requirements-for-a-connection-from-your-network-edge-to-microsoft-network-edge"></a><span data-ttu-id="6a085-204">用于从您网络边缘连接到 Microsoft 要求网络边缘</span><span class="sxs-lookup"><span data-stu-id="6a085-204">Requirements for a connection from your network edge to Microsoft network edge</span></span>

<span data-ttu-id="6a085-205">表 2 显示网络性能目标或所需的网络边缘和 Microsoft 网络边缘之间的连接的阈值。</span><span class="sxs-lookup"><span data-stu-id="6a085-205">Table 2 shows the network performance targets or thresholds that are required for the connection between your network edge and the Microsoft network edge.</span></span> <span data-ttu-id="6a085-206">这排除贵组织的内部网络或 WAN，并测试网络流量通过 internet 或通过 ExpressRoute 合作伙伴网络发送时用作指南。</span><span class="sxs-lookup"><span data-stu-id="6a085-206">This excludes your organization’s internal network or WAN, and is intended as a guide when you test network traffic that is sent over the internet or through an ExpressRoute partner network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a085-207">您的公司网络边缘到 Microsoft 网络边缘之间的连接必须满足以下网络性能要求。</span><span class="sxs-lookup"><span data-stu-id="6a085-207">Connectivity between your company's network edge to the Microsoft network edges must meet the following network performance requirements.</span></span>

<span data-ttu-id="6a085-208">_表 2。网络性能指标-边缘到边缘_</span><span class="sxs-lookup"><span data-stu-id="6a085-208">_Table 2. Network performance metrics - edge to edge_</span></span>

| <span data-ttu-id="6a085-209">指标</span><span class="sxs-lookup"><span data-stu-id="6a085-209">Metric</span></span> | <span data-ttu-id="6a085-210">目标</span><span class="sxs-lookup"><span data-stu-id="6a085-210">Target</span></span> |
|--------|--------|
| <span data-ttu-id="6a085-211">延迟（单向）</span><span class="sxs-lookup"><span data-stu-id="6a085-211">Latency (one way)</span></span> | <span data-ttu-id="6a085-212">< 30 毫秒</span><span class="sxs-lookup"><span data-stu-id="6a085-212">< 30 milliseconds</span></span> |
| <span data-ttu-id="6a085-213">延迟 （来回行程时间 (RTT)</span><span class="sxs-lookup"><span data-stu-id="6a085-213">Latency (round trip time (RTT)</span></span> | <span data-ttu-id="6a085-214">< 60 毫秒</span><span class="sxs-lookup"><span data-stu-id="6a085-214">< 60 milliseconds</span></span> |
| <span data-ttu-id="6a085-215">突发数据包丢失</span><span class="sxs-lookup"><span data-stu-id="6a085-215">Burst packet loss</span></span> | <span data-ttu-id="6a085-216">任何 200 毫秒的时间间隔期间 < 1%</span><span class="sxs-lookup"><span data-stu-id="6a085-216">< 1% during any 200 millisecond interval</span></span> |
| <span data-ttu-id="6a085-217">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="6a085-217">Packet loss</span></span> | <span data-ttu-id="6a085-218">任何 15 的第二个间隔期间 < 0.1%</span><span class="sxs-lookup"><span data-stu-id="6a085-218">< 0.1% during any 15 second interval</span></span> |
| <span data-ttu-id="6a085-219">数据包间到达抖动</span><span class="sxs-lookup"><span data-stu-id="6a085-219">Packet inter-arrival jitter</span></span> | <span data-ttu-id="6a085-220">任何 15 的第二个间隔期间 < 15 毫秒</span><span class="sxs-lookup"><span data-stu-id="6a085-220">< 15 milliseconds during any 15 second interval</span></span> |
| <span data-ttu-id="6a085-221">数据包重新排序</span><span class="sxs-lookup"><span data-stu-id="6a085-221">Packet reorder</span></span> | <span data-ttu-id="6a085-222">利用顺序数据包 < 0.01%</span><span class="sxs-lookup"><span data-stu-id="6a085-222">< 0.01% out of order packets</span></span> |


## <a name="recommended-dscp-markings"></a><span data-ttu-id="6a085-223">建议的 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="6a085-223">Recommended DSCP markings</span></span>

<span data-ttu-id="6a085-224">您已准备好配置 QoS，您第一步是进行分类 （如音频和视频） 通信流通过将 DSCP 值分配给的唯一的非重叠端口范围。</span><span class="sxs-lookup"><span data-stu-id="6a085-224">When you're ready to configure QoS, your first step is to classify the traffic flows (such as audio and video) by assigning DSCP values to the unique, non-overlapping port ranges.</span></span> <span data-ttu-id="6a085-225">此处分配的 DSCP 值将决定需要通过网络，根据网络配置的流量的优先级。</span><span class="sxs-lookup"><span data-stu-id="6a085-225">The DSCP value assigned here will determine the priority of the traffic going through the network, based on network configuration.</span></span> <span data-ttu-id="6a085-226">每个工作负荷获取其自己的 DSCP 值，但不一定的唯一值 — 可能想要设置相同的语音和视频的工作负荷，值为他们提供网络中的相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="6a085-226">Each workload gets its own DSCP value, though not necessarily a unique value—you might want to set the same value for voice and video workloads, giving them the same priority in the network.</span></span>  

<span data-ttu-id="6a085-227">要使用的 DSCP 值取决于您希望如何设置优先级工作负荷。</span><span class="sxs-lookup"><span data-stu-id="6a085-227">The DSCP value to use depends on how you want to prioritize the workload.</span></span> <span data-ttu-id="6a085-228">例如，业务要求可能要求您提供应用程序共享按视频的优先级 （并因此使用视频相同的 DSCP 值标记它）。</span><span class="sxs-lookup"><span data-stu-id="6a085-228">For example, business requirements might dictate that you give application sharing the same priority as video (and therefore mark it with the same DSCP value as video).</span></span> <span data-ttu-id="6a085-229">其他环境可能具有现有的 QoS 策略就地，这将帮助您确定网络工作负荷的优先级。</span><span class="sxs-lookup"><span data-stu-id="6a085-229">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span> 

<span data-ttu-id="6a085-230">表 3 显示与 ExpressRoute 团队所需的 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="6a085-230">Table 3 shows the DSCP markings required for Teams with ExpressRoute.</span></span> <span data-ttu-id="6a085-231">这些标记可能用作不能确定要在其自己的环境中使用的客户的良好的起始点。</span><span class="sxs-lookup"><span data-stu-id="6a085-231">These markings might serve as a good starting point for customers who are unsure what to use in their own environments.</span></span> <span data-ttu-id="6a085-232">要了解详细信息，请阅读 [ExpressRoute QoS 要求](https://docs.microsoft.com/azure/expressroute/expressroute-qos)。</span><span class="sxs-lookup"><span data-stu-id="6a085-232">To learn more, read [ExpressRoute QoS requirements](https://docs.microsoft.com/azure/expressroute/expressroute-qos).</span></span>

<span data-ttu-id="6a085-233">_表 3。DSCP 标记_</span><span class="sxs-lookup"><span data-stu-id="6a085-233">_Table 3. DSCP markings_</span></span>

| <span data-ttu-id="6a085-234">客户端源端口范围</span><span class="sxs-lookup"><span data-stu-id="6a085-234">Client source port range</span></span> |<span data-ttu-id="6a085-235">协议</span><span class="sxs-lookup"><span data-stu-id="6a085-235">Protocol</span></span>|<span data-ttu-id="6a085-236">媒体类别</span><span class="sxs-lookup"><span data-stu-id="6a085-236">Media category</span></span>|<span data-ttu-id="6a085-237">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="6a085-237">DSCP value</span></span>|<span data-ttu-id="6a085-238">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="6a085-238">DSCP class</span></span>|
|---------|---------|---------|---------|---------|
| <span data-ttu-id="6a085-239">50000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="6a085-239">50,000–50,019</span></span>|<span data-ttu-id="6a085-240">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="6a085-240">TCP/UDP</span></span>|<span data-ttu-id="6a085-241">音频</span><span class="sxs-lookup"><span data-stu-id="6a085-241">Audio</span></span>|<span data-ttu-id="6a085-242">46</span><span class="sxs-lookup"><span data-stu-id="6a085-242">46</span></span>|<span data-ttu-id="6a085-243">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="6a085-243">Expedited Forwarding (EF)</span></span>|
| <span data-ttu-id="6a085-244">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="6a085-244">50,020–50,039</span></span>|<span data-ttu-id="6a085-245">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="6a085-245">TCP/UDP</span></span>|<span data-ttu-id="6a085-246">视频</span><span class="sxs-lookup"><span data-stu-id="6a085-246">Video</span></span>|<span data-ttu-id="6a085-247">34</span><span class="sxs-lookup"><span data-stu-id="6a085-247">34</span></span>|<span data-ttu-id="6a085-248">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="6a085-248">Assured Forwarding (AF41)</span></span>|
| <span data-ttu-id="6a085-249">50,040 – 50,059</span><span class="sxs-lookup"><span data-stu-id="6a085-249">50,040–50,059</span></span>|<span data-ttu-id="6a085-250">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="6a085-250">TCP/UDP</span></span>|<span data-ttu-id="6a085-251">应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="6a085-251">Application/Desktop Sharing</span></span>|<span data-ttu-id="6a085-252">18</span><span class="sxs-lookup"><span data-stu-id="6a085-252">18</span></span>|<span data-ttu-id="6a085-253">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="6a085-253">Assured Forwarding (AF21)</span></span>|

<span data-ttu-id="6a085-254">表 3 中使用的信息时要注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="6a085-254">Be aware of the following when you use the information in Table 3:</span></span>

-  <span data-ttu-id="6a085-255">如果您计划将来实现 ExpressRoute 并没有尚未实施 QoS，我们建议您遵循表 3 中的指南，以便是来自到接收方的发件人相同的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="6a085-255">If you plan to implement ExpressRoute in the future and haven’t yet implemented QoS, we recommend that you follow the guidance in Table 3 so that DSCP values are the same from sender to receiver.</span></span> 

-  <span data-ttu-id="6a085-256">所有客户端，其中包括移动客户端和团队设备，将使用这些端口范围，并将受您实现任何 DSCP 策略使用这些源端口范围。</span><span class="sxs-lookup"><span data-stu-id="6a085-256">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="6a085-257">将继续使用动态端口的唯一客户端是基于浏览器的客户端 （即，这些客户端，允许使用其浏览器加入会议的参与者）。</span><span class="sxs-lookup"><span data-stu-id="6a085-257">The only clients that will continue to use dynamic ports are the browser-based clients (that is, those clients that let participants join meetings by using their browsers).</span></span>

-  <span data-ttu-id="6a085-258">尽管 Mac 客户端使用相同的端口范围，但它还使用硬编码为值 （ef） 级别音频和视频 (AF41)。</span><span class="sxs-lookup"><span data-stu-id="6a085-258">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="6a085-259">这些值是不可配置。</span><span class="sxs-lookup"><span data-stu-id="6a085-259">These values are not configurable.</span></span>


## <a name="source-ports-used-by-teams"></a><span data-ttu-id="6a085-260">Teams 使用的源端口</span><span class="sxs-lookup"><span data-stu-id="6a085-260">Source ports used by Teams</span></span>

<span data-ttu-id="6a085-261">在 Teams 中，应根据不同工作负荷使用的源端口配置 QoS。</span><span class="sxs-lookup"><span data-stu-id="6a085-261">In Teams, QoS should be configured based on the source ports used by the different workloads.</span></span> <span data-ttu-id="6a085-262">目前，可以配置的任何服务器端和客户端端口范围。</span><span class="sxs-lookup"><span data-stu-id="6a085-262">Currently, neither server-side nor client-side port ranges are configurable.</span></span> 

<span data-ttu-id="6a085-263">表 3 中列出的客户端源端口范围还适用于团队，并使用其关联的 QoS DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="6a085-263">The client source port ranges listed in Table 3 also apply to Teams and use their associated QoS DSCP markings.</span></span>

<span data-ttu-id="6a085-264">实现这些 QoS 策略的推荐的方法是使用客户端源端口源和目标 IP 地址为"任何。"</span><span class="sxs-lookup"><span data-stu-id="6a085-264">The recommended method of implementing these QoS policies is to use the client source ports with a source and destination IP address of “any.”</span></span> <span data-ttu-id="6a085-265">这将在内部网络中捕获这两个传入和传出的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="6a085-265">This will catch both incoming and outgoing media traffic on the internal network.</span></span> 

> [!NOTE]
> <span data-ttu-id="6a085-266">如果您已经配置 QoS 基于源的端口范围的 Skype 业务联机，相同的配置将应用于工作组和需要进一步的更改。</span><span class="sxs-lookup"><span data-stu-id="6a085-266">If you've already configured QoS based on source port ranges for Skype for Business Online, the same configuration will apply to Teams and no further changes will be required.</span></span> <span data-ttu-id="6a085-267">如果您已为 Business Server 本地部署 Skype，您需要重新检查 QoS 策略，并根据需要调整这些。</span><span class="sxs-lookup"><span data-stu-id="6a085-267">If you’ve deployed Skype for Business Server on-premises, you’ll need to re-examine your QoS policies and adjust them if necessary.</span></span>

## <a name="set-dscp-markings"></a><span data-ttu-id="6a085-268">设置 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="6a085-268">Set DSCP markings</span></span>

<span data-ttu-id="6a085-269">有多个方法设置通信量分类适当的 DSCP 标记：</span><span class="sxs-lookup"><span data-stu-id="6a085-269">There are multiple approaches to setting the proper DSCP markings for traffic classification:</span></span>

-  <span data-ttu-id="6a085-270">**端点处的 DSCP 标记：** 这通常是首选的选项，因为本身的终结点提供适当的标记。</span><span class="sxs-lookup"><span data-stu-id="6a085-270">**DSCP marking at the endpoint:** This is generally the preferred option, because the endpoint itself provides the proper markings.</span></span> <span data-ttu-id="6a085-271">当前这可以通过使用组策略对象，但它仅可加入域的 Windows 客户端上。</span><span class="sxs-lookup"><span data-stu-id="6a085-271">Currently this can be done by using a Group Policy object, but it can only be used on domain-joined Windows clients.</span></span> <span data-ttu-id="6a085-272">移动客户端不提供通过使用 DSCP 值标记流量的机制。</span><span class="sxs-lookup"><span data-stu-id="6a085-272">Mobile clients don’t provide a mechanism to mark traffic by using DSCP values.</span></span> <span data-ttu-id="6a085-273">尽管您无法配置非&ndash;标记流量，客户端 Mac OS 如加入域的 Windows 客户端具有硬编码标记，并将始终标记流量，如上文所述。</span><span class="sxs-lookup"><span data-stu-id="6a085-273">Although you can’t configure non&ndash;domain-joined Windows clients to tag traffic, clients such as Mac OS have hard-coded tags and will always tag traffic as described above.</span></span>

-  <span data-ttu-id="6a085-274">**基于端口的 DSCP 标记使用路由器上的访问控制列表 (Acl):** 这是在异类 Windows 和 Mac 环境中遇到非常常见选项。</span><span class="sxs-lookup"><span data-stu-id="6a085-274">**Port-based DSCP tagging by using access control lists (ACLs) on routers:** This is a very common option encountered in heterogeneous Windows and Mac environments.</span></span> <span data-ttu-id="6a085-275">在此方案中，网络团队标记基于定义每种形式的源端口范围的入站/出站路由器 （通常位于 WAN） 通信。</span><span class="sxs-lookup"><span data-stu-id="6a085-275">In this scenario, the network team marks the traffic at the ingress/egress routers (typically located on the WAN) based on the source port ranges defined for each modality.</span></span> <span data-ttu-id="6a085-276">虽然这可以工作跨平台，仅标记在 WAN 边缘流量 — 不一直到客户端计算机 — 和因此产生管理开销。</span><span class="sxs-lookup"><span data-stu-id="6a085-276">Although this works across platforms, it only marks traffic at the WAN edge—not all the way to the client machine—and therefore incurs management overhead.</span></span>

-  <span data-ttu-id="6a085-277">**组合的终结点和基于端口的路由器上的 Acl 的 DSCP 标记：** 我们建议此组合方案，如有可能在您的环境中。</span><span class="sxs-lookup"><span data-stu-id="6a085-277">**A combination of DSCP markings at the endpoint and port-based ACLs on routers:** We recommend this combination, if possible in your environment.</span></span> <span data-ttu-id="6a085-278">使用组策略对象捕获大多数客户端，并且使用基于端口的 DSCP 标记，以确保该 mobile、 Mac 和其他客户端将仍获取 QoS 诊 （至少部分）。</span><span class="sxs-lookup"><span data-stu-id="6a085-278">Use a Group Policy object to catch the majority of clients, and also use port-based DSCP tagging to ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="6a085-279">您可以使用基于策略的 QoS 组策略中设置团队客户端中的预定义的源端口范围的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="6a085-279">You can use policy-based QoS within Group Policy to set the DSCP value for the predefined source port range in the Teams client.</span></span> <span data-ttu-id="6a085-280">使用表 3 中指定的端口范围创建的每个工作负荷策略。</span><span class="sxs-lookup"><span data-stu-id="6a085-280">Use the port ranges specified in Table 3 to create a policy for each workload.</span></span>

<span data-ttu-id="6a085-281">您已确定的端口范围后下, 一步是配置组策略对象中的基于策略的 QoS 设置。</span><span class="sxs-lookup"><span data-stu-id="6a085-281">After you’ve identified the port ranges, the next step is to configure the policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="6a085-282">[配置端口范围和客户端 Skype 业务服务器上的服务质量策略](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)中，可以找到有关这些步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6a085-282">You can find more information about these steps in [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10).</span></span>

<span data-ttu-id="6a085-283">若要创建 Windows 10 计算机音频 QoS 策略，首次登录到计算机上安装的组策略管理。</span><span class="sxs-lookup"><span data-stu-id="6a085-283">To create a QoS audio policy for Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="6a085-284">打开组策略管理 （单击开始、 管理工具，，然后单击组策略管理），然后完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6a085-284">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="6a085-285">在组策略管理中，找到应在其中创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="6a085-285">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="6a085-286">例如，如果您的所有客户端计算机位于名为**客户端**OU，应客户端 OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="6a085-286">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="6a085-287">右键单击相应的容器，然后单击**创建在这个域 GPO 并在此处链接**。</span><span class="sxs-lookup"><span data-stu-id="6a085-287">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="6a085-288">**新建 GPO**对话框中，在**名称**框中，键入新的组策略对象的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a085-288">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="6a085-289">右键单击新建的策略，，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="6a085-289">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="6a085-290">在组策略管理编辑器中，展开**计算机配置**，展开**Windows 设置**、**基于策略的 QoS**，右键单击，然后单击**新建策略**。</span><span class="sxs-lookup"><span data-stu-id="6a085-290">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="6a085-291">在**基于策略的 QoS**对话框中，在打开页上，键入**名称**框中的新策略的名称。</span><span class="sxs-lookup"><span data-stu-id="6a085-291">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="6a085-292">选择**指定 DSCP 值**并将值设置为**46**。</span><span class="sxs-lookup"><span data-stu-id="6a085-292">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="6a085-293">保留未选择，**指定出站调节率**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6a085-293">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="6a085-294">在下一页上，确保选中**所有应用程序**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6a085-294">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="6a085-295">此设置指示网络以查找所有包的特定应用程序创建的 46，而不仅仅是数据包的 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="6a085-295">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8. <span data-ttu-id="6a085-296">在第三页上，确保同时**任何源 IP 地址**和**任何目标 IP 地址**选中，则，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6a085-296">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="6a085-297">这两个设置确保将管理数据包而不考虑哪台计算机 （IP 地址） 发送数据包和哪台计算机 （IP 地址） 将接收数据包。</span><span class="sxs-lookup"><span data-stu-id="6a085-297">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="6a085-298">在四页中，从**选择此 QoS 策略应用于的协议**下拉列表中选择**TCP 和 UDP** 。</span><span class="sxs-lookup"><span data-stu-id="6a085-298">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="6a085-299">TCP （传输控制协议） 和 UDP （用户数据报协议） 是最常使用的两个网络协议。</span><span class="sxs-lookup"><span data-stu-id="6a085-299">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="6a085-300">在标题下**指定源端口号**，**从此源端口或范围**中进行选择。</span><span class="sxs-lookup"><span data-stu-id="6a085-300">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="6a085-301">在相应的文本框中，键入供音频传输的端口范围。</span><span class="sxs-lookup"><span data-stu-id="6a085-301">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="6a085-302">例如，如果预留端口 50000 到音频流量的端口 50019，输入使用以下格式的端口范围： **50000:50019**。</span><span class="sxs-lookup"><span data-stu-id="6a085-302">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="6a085-303">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="6a085-303">Click **Finish**.</span></span>

<span data-ttu-id="6a085-304">已在客户端计算机上刷新组策略之前，您已创建的新策略不会生效。</span><span class="sxs-lookup"><span data-stu-id="6a085-304">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="6a085-305">尽管自己定期刷新组策略，您可以强制立即刷新。</span><span class="sxs-lookup"><span data-stu-id="6a085-305">Although Group Policy periodically refreshes on its own, you can force an immediate refresh.</span></span>

### <a name="force-group-policy-refresh"></a><span data-ttu-id="6a085-306">强制组策略刷新</span><span class="sxs-lookup"><span data-stu-id="6a085-306">Force Group Policy refresh</span></span>

1. <span data-ttu-id="6a085-307">在您要刷新组策略的每台计算机上打开命令控制台。</span><span class="sxs-lookup"><span data-stu-id="6a085-307">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="6a085-308">确保命令控制台设置以管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="6a085-308">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="6a085-309">在命令提示符处，输入</span><span class="sxs-lookup"><span data-stu-id="6a085-309">At the command prompt, enter</span></span>
   ```
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="6a085-310">验证 DSCP 标记中的组策略对象</span><span class="sxs-lookup"><span data-stu-id="6a085-310">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="6a085-311">若要验证已设置的组策略对象的值，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="6a085-311">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="6a085-312">打开一个命令控制台。</span><span class="sxs-lookup"><span data-stu-id="6a085-312">Open a command console.</span></span> <span data-ttu-id="6a085-313">确保命令控制台设置以管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="6a085-313">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="6a085-314">在命令提示符处，输入</span><span class="sxs-lookup"><span data-stu-id="6a085-314">At the command prompt, enter</span></span> 
   ```
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="6a085-315">这将生成一个报告，并将其发送到一个名为 gp.txt 文本文件。</span><span class="sxs-lookup"><span data-stu-id="6a085-315">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="6a085-316">或者，您可以输入以下命令以生成更容易阅读 HTML 报表名为 gp.html 中相同的数据：</span><span class="sxs-lookup"><span data-stu-id="6a085-316">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>
   ```
   gpresult /H >gp.html
   ```

   <span data-ttu-id="6a085-317">![运行 gpresult 命令控制台窗口的屏幕截图。](media/Qos-in-Teams-Image3.png "运行 gpresult 命令控制台窗口的屏幕截图。")</span><span class="sxs-lookup"><span data-stu-id="6a085-317">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="6a085-318">在生成的文件中，查找的标题**应用组策略对象**和验证前面创建的组策略对象的名称位于应用策略的列表。</span><span class="sxs-lookup"><span data-stu-id="6a085-318">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span> 

4. <span data-ttu-id="6a085-319">打开注册表编辑器中，并转到：</span><span class="sxs-lookup"><span data-stu-id="6a085-319">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="6a085-320">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span><span class="sxs-lookup"><span data-stu-id="6a085-320">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span></span>

   <span data-ttu-id="6a085-321">验证表 4 中列出的注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="6a085-321">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="6a085-322">_表 4。QoS 程序的 Windows 注册表项的值_</span><span class="sxs-lookup"><span data-stu-id="6a085-322">_Table 4. Values for Windows registry entries for QoS_</span></span>


   |          <span data-ttu-id="6a085-323">名称</span><span class="sxs-lookup"><span data-stu-id="6a085-323">Name</span></span>          |  <span data-ttu-id="6a085-324">类型</span><span class="sxs-lookup"><span data-stu-id="6a085-324">Type</span></span>  |    <span data-ttu-id="6a085-325">数据</span><span class="sxs-lookup"><span data-stu-id="6a085-325">Data</span></span>     |
   |------------------------|--------|-------------|
   |    <span data-ttu-id="6a085-326">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="6a085-326">Application Name</span></span>    | <span data-ttu-id="6a085-327">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-327">REG_SZ</span></span> |  <span data-ttu-id="6a085-328">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="6a085-328">Teams.exe</span></span>  |
   |       <span data-ttu-id="6a085-329">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="6a085-329">DSCP Value</span></span>       | <span data-ttu-id="6a085-330">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-330">REG_SZ</span></span> |     <span data-ttu-id="6a085-331">46</span><span class="sxs-lookup"><span data-stu-id="6a085-331">46</span></span>      |
   |        <span data-ttu-id="6a085-332">本地 IP</span><span class="sxs-lookup"><span data-stu-id="6a085-332">Local IP</span></span>        | <span data-ttu-id="6a085-333">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-333">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="6a085-334">本地 IP 前缀长度</span><span class="sxs-lookup"><span data-stu-id="6a085-334">Local IP Prefix Length</span></span> | <span data-ttu-id="6a085-335">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-335">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="6a085-336">本地端口</span><span class="sxs-lookup"><span data-stu-id="6a085-336">Local Port</span></span>       | <span data-ttu-id="6a085-337">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-337">REG_SZ</span></span> | <span data-ttu-id="6a085-338">50000-50019</span><span class="sxs-lookup"><span data-stu-id="6a085-338">50000-50019</span></span> |
   |        <span data-ttu-id="6a085-339">协议</span><span class="sxs-lookup"><span data-stu-id="6a085-339">Protocol</span></span>        | <span data-ttu-id="6a085-340">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-340">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="6a085-341">远程 IP</span><span class="sxs-lookup"><span data-stu-id="6a085-341">Remote IP</span></span>        | <span data-ttu-id="6a085-342">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-342">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="6a085-343">远程 IP 前缀</span><span class="sxs-lookup"><span data-stu-id="6a085-343">Remote IP Prefix</span></span>    | <span data-ttu-id="6a085-344">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-344">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="6a085-345">远程端口</span><span class="sxs-lookup"><span data-stu-id="6a085-345">Remote Port</span></span>       | <span data-ttu-id="6a085-346">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-346">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="6a085-347">限制率</span><span class="sxs-lookup"><span data-stu-id="6a085-347">Throttle Rate</span></span>      | <span data-ttu-id="6a085-348">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a085-348">REG_SZ</span></span> |     <span data-ttu-id="6a085-349">-1</span><span class="sxs-lookup"><span data-stu-id="6a085-349">-1</span></span>      |


5. <span data-ttu-id="6a085-350">验证应用程序名称条目的值正确客户端使用，并确认的 DSCP 值和本地端口条目反映中的组策略对象的设置。</span><span class="sxs-lookup"><span data-stu-id="6a085-350">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a><span data-ttu-id="6a085-351">验证通过分析团队流量网络上的 QoS</span><span class="sxs-lookup"><span data-stu-id="6a085-351">Validate QoS by analyzing Teams traffic on the network</span></span>

<span data-ttu-id="6a085-352">有关 QoS 可以取得高效率、 DSCP 值设置组策略对象都需要呼叫两端都存在。</span><span class="sxs-lookup"><span data-stu-id="6a085-352">For QoS to be effective, the DSCP value set by the Group Policy object needs to be present at both ends of a call.</span></span> <span data-ttu-id="6a085-353">通过查看生成的团队客户端的通信，您可以验证的 DSCP 值不更改或去除团队工作负荷通信量遍历移动通过网络。</span><span class="sxs-lookup"><span data-stu-id="6a085-353">By looking at the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic traverses moves through the network.</span></span>

<span data-ttu-id="6a085-354">最好，您可以捕获网络出口点处的流量。</span><span class="sxs-lookup"><span data-stu-id="6a085-354">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="6a085-355">您可以使用端口镜像开关或路由器上与此帮助。</span><span class="sxs-lookup"><span data-stu-id="6a085-355">You can use port mirroring on a switch or router to help with this.</span></span>

### <a name="use-network-monitor-to-verify-dscp-values"></a><span data-ttu-id="6a085-356">使用网络监视器验证 DSCP 值</span><span class="sxs-lookup"><span data-stu-id="6a085-356">Use Network Monitor to verify DSCP values</span></span>

<span data-ttu-id="6a085-357">网络监视器是您可以[从 Microsoft 下载](https://www.microsoft.com/download/4865)分析网络流量的工具。</span><span class="sxs-lookup"><span data-stu-id="6a085-357">Network Monitor is a tool you can [download from Microsoft](https://www.microsoft.com/download/4865) to analyze network traffic.</span></span>

1. <span data-ttu-id="6a085-358">在 PC 上运行网络监视器，连接到端口镜像和开始捕获数据包已配置的端口。</span><span class="sxs-lookup"><span data-stu-id="6a085-358">On the PC running Network Monitor, connect to the port that has been configured for port mirroring and start capturing packets.</span></span> 

2. <span data-ttu-id="6a085-359">使用团队客户端发起呼叫。</span><span class="sxs-lookup"><span data-stu-id="6a085-359">Make a call by using the Teams client.</span></span> <span data-ttu-id="6a085-360">请确保媒体建立挂断呼叫之前。</span><span class="sxs-lookup"><span data-stu-id="6a085-360">Make sure media has been established before hanging up the call.</span></span> 

3. <span data-ttu-id="6a085-361">停止捕获。</span><span class="sxs-lookup"><span data-stu-id="6a085-361">Stop the capture.</span></span>

4. <span data-ttu-id="6a085-362">在**显示筛选器**字段中，使用源 IP 地址的 pc 的发出呼叫，并通过定义作为搜索条件的 DSCP 值 46 (hex 0xb8) 优化筛选器，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="6a085-362">In the **Display Filter** field, use the source IP address of the PC that made the call, and refine the filter by defining DSCP value 46 (hex 0xb8) as search criteria, as shown in the following example:</span></span>

    <span data-ttu-id="6a085-363">Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8</span><span class="sxs-lookup"><span data-stu-id="6a085-363">Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8</span></span> 

    <span data-ttu-id="6a085-364">![网络监视器，显示应用的筛选器中的显示筛选器对话框的屏幕快照。](media/Qos-in-Teams-Image4.png "网络监视器，显示应用的筛选器中的显示筛选器对话框的屏幕快照。")</span><span class="sxs-lookup"><span data-stu-id="6a085-364">![Screenshot of the Display Filter dialog box in Network Monitor, showing the filters to apply.](media/Qos-in-Teams-Image4.png "Screenshot of the Display Filter dialog box in Network Monitor, showing the filters to apply.")</span></span>

5. <span data-ttu-id="6a085-365">选择**应用**以激活筛选器。</span><span class="sxs-lookup"><span data-stu-id="6a085-365">Select **Apply** to activate the filter.</span></span>

6. <span data-ttu-id="6a085-366">在**帧摘要**窗口中，选择第一个 UDP 数据包。</span><span class="sxs-lookup"><span data-stu-id="6a085-366">In the **Frame Summary** window, select the first UDP packet.</span></span>

7. <span data-ttu-id="6a085-367">在**帧详细信息**窗口中，展开 IPv4 列表项，并注意末尾的行的开头**DSCP**值。</span><span class="sxs-lookup"><span data-stu-id="6a085-367">In the **Frame Details** window, expand the IPv4 list item and note the value at the end of the line that begins with **DSCP**.</span></span> 

    <span data-ttu-id="6a085-368">![网络监视器，突出显示 DSCP 设置中的帧详细信息对话框的屏幕快照。](media/Qos-in-Teams-Image5.png "网络监视器，突出显示 DSCP 设置中的帧详细信息对话框的屏幕快照。")</span><span class="sxs-lookup"><span data-stu-id="6a085-368">![Screenshot of the Frame Details dialog box in Network Monitor, highlighting DSCP settings.](media/Qos-in-Teams-Image5.png "Screenshot of the Frame Details dialog box in Network Monitor, highlighting DSCP settings.")</span></span>

<span data-ttu-id="6a085-369">在此示例中的 DSCP 值设置为 46。</span><span class="sxs-lookup"><span data-stu-id="6a085-369">In this example, the DSCP value is set to 46.</span></span> <span data-ttu-id="6a085-370">这是正确的因为使用的源端口是 50019，表示这是语音工作负荷。</span><span class="sxs-lookup"><span data-stu-id="6a085-370">This is correct, because the source port used is 50019, which indicates that this is a voice workload.</span></span> 

<span data-ttu-id="6a085-371">为 GPO 标记的每个工作负荷重复执行验证。</span><span class="sxs-lookup"><span data-stu-id="6a085-371">Repeat the verification for each workload that has been marked by the GPO.</span></span> 

## <a name="more-information"></a><span data-ttu-id="6a085-372">更多信息</span><span class="sxs-lookup"><span data-stu-id="6a085-372">More information</span></span>

[<span data-ttu-id="6a085-373">为 Microsoft Teams 准备贵组织的网络</span><span class="sxs-lookup"><span data-stu-id="6a085-373">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

[<span data-ttu-id="6a085-374">ExpressRout QoS 要求</span><span class="sxs-lookup"><span data-stu-id="6a085-374">ExpressRout QoS requirements</span></span>](https://docs.microsoft.com/azure/expressroute/expressroute-qos)