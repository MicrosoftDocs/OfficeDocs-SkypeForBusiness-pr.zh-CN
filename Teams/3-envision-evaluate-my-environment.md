---
title: 评估 Microsoft Teams 云语音和工作负载的环境
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用角色和网络分析来评估组织的准备情况, 打开正确的 TCP 和 UDP 端口, 然后执行任何网络修正。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1500c9e10d3e8d951c465ce278595c5b17f7cc7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232313"
---
# <a name="evaluate-my-environment"></a><span data-ttu-id="676d4-103">评估环境</span><span class="sxs-lookup"><span data-stu-id="676d4-103">Evaluate my environment</span></span>

<span data-ttu-id="676d4-104">本文概述了正确评估当前环境使用云语音服务的要求。</span><span class="sxs-lookup"><span data-stu-id="676d4-104">This article gives an overview of the requirements for properly evaluating your current environment for using cloud voice services.</span></span> <span data-ttu-id="676d4-105">通过评估你的环境, 确定将影响你的整体云语音部署的风险和要求。</span><span class="sxs-lookup"><span data-stu-id="676d4-105">By evaluating your environment, you identify risks and requirements that will influence your overall cloud voice deployment.</span></span> <span data-ttu-id="676d4-106">通过预先确定这些项目, 您可以调整计划以推动成功。</span><span class="sxs-lookup"><span data-stu-id="676d4-106">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-evaluating-your-environment"></a><span data-ttu-id="676d4-107">评估环境简介</span><span class="sxs-lookup"><span data-stu-id="676d4-107">Introduction to evaluating your environment</span></span> 

<span data-ttu-id="676d4-108">为了实现客观的关键结果 (OKRs), 您以前已做出关键服务决策。</span><span class="sxs-lookup"><span data-stu-id="676d4-108">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="676d4-109">下一步是执行环境发现以评估与你的 IT 和电话基础结构、网络和操作相关的所有方面, 以确认你的组织已准备好实施解决方案。</span><span class="sxs-lookup"><span data-stu-id="676d4-109">The next step is to perform environmental discovery to evaluate all aspects relating to your IT and telephony infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span>

<span data-ttu-id="676d4-110">环境发现必须包含网络准备情况评估, 以确保你的网络能够支持通过呼叫计划服务实现音频会议或电话系统。</span><span class="sxs-lookup"><span data-stu-id="676d4-110">Environmental discovery must include network readiness assessment to ensure your network can support the implementation of the Audio Conferencing or Phone System with Calling Plan services.</span></span>

<span data-ttu-id="676d4-111">你可以将技术风险标识为环境评估和采纳准备情况评估的一部分, 并针对每个确定的风险制定一个缓解计划。</span><span class="sxs-lookup"><span data-stu-id="676d4-111">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span>
<span data-ttu-id="676d4-112">您应将此信息合并到风险注册中。</span><span class="sxs-lookup"><span data-stu-id="676d4-112">You should incorporate this information in the risk register.</span></span>

<!--ENDOFSECTION-->

## <a name="current-environment"></a><span data-ttu-id="676d4-113">当前环境</span><span class="sxs-lookup"><span data-stu-id="676d4-113">Current environment</span></span>

<span data-ttu-id="676d4-114">作为环境发现的一部分, 请包括与最终用户计算相关的所有事宜, 如电脑和移动设备的准备情况评估, 以支持音频会议和手机系统, 支持使用呼叫计划的业务使用案例, 从硬件要求到软件要求。</span><span class="sxs-lookup"><span data-stu-id="676d4-114">As part of your environmental discovery, include all matters related to end-user computing, such as a readiness assessment of PCs and mobile devices to support Audio Conferencing and Phone System with Calling Plan business use cases, from hardware requirements to software requirements.</span></span>

<span data-ttu-id="676d4-115">环境发现还可以揭示是否需要将[电话号码转移到 Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="676d4-115">Environmental discovery can also uncover whether you need to [transfer phone numbers to Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).</span></span>
<span data-ttu-id="676d4-116">了解此操作将帮助你的组织相应调整其项目计划, 并为数字移植准备必要的信息。</span><span class="sxs-lookup"><span data-stu-id="676d4-116">Knowing this will help your organization adjust its project plan accordingly and prepare the necessary information for number porting.</span></span> <span data-ttu-id="676d4-117">你可以使用[Microsoft 团队推出的环境发现](environmental-discovery-for-microsoft-teams-rollout.md)来执行环境发现。</span><span class="sxs-lookup"><span data-stu-id="676d4-117">You can use the [Environmental discovery for Microsoft Teams rollout](environmental-discovery-for-microsoft-teams-rollout.md) to perform environmental discovery.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="676d4-118">决策点</span><span class="sxs-lookup"><span data-stu-id="676d4-118">Decision points</span></span></td><td><ul><li><span data-ttu-id="676d4-119">谁将负责完成环境评估？</span><span class="sxs-lookup"><span data-stu-id="676d4-119">Who will be responsible for completing an environment assessment?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="676d4-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="676d4-120">Next steps</span></span></td><td><ul><li><span data-ttu-id="676d4-121">记录环境评估的结果。</span><span class="sxs-lookup"><span data-stu-id="676d4-121">Document the results of the environment assessment.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a><span data-ttu-id="676d4-122">采纳和更改管理评估功能</span><span class="sxs-lookup"><span data-stu-id="676d4-122">Adoption and change management assessment capabilities</span></span> 

<span data-ttu-id="676d4-123">部署为用户提供了一种新的技术, 但仅在用户真正将该解决方案视为自己的情况后才会实现业务结果。</span><span class="sxs-lookup"><span data-stu-id="676d4-123">Deployment puts a new technology at a user's fingertips, but business results are only realized after users truly adopt that solution as their own.</span></span> <span data-ttu-id="676d4-124">为了帮助确保持续接受新的解决方案, 你需要将精力集中在用户准备工作和更改管理上。</span><span class="sxs-lookup"><span data-stu-id="676d4-124">To help ensure sustained adoption of a new solution, you'll need to focus your efforts on user readiness and change management.</span></span> <span data-ttu-id="676d4-125">为获得最佳结果, 请将用户准备工作计划作为并行工作流提供给你的技术准备活动, 并合并以下活动:</span><span class="sxs-lookup"><span data-stu-id="676d4-125">For optimal results, conduct user readiness planning as a parallel workstream to your technical readiness activities and incorporate the following activities:</span></span>

-   <span data-ttu-id="676d4-126">**组织和用户分析:** 对组织 receptiveness 的分析, 以在使用案例和角色分析之外进行更改</span><span class="sxs-lookup"><span data-stu-id="676d4-126">**Organizational and user profiling:** Analysis of organizational receptiveness to change in addition to use case and persona analysis</span></span>

-   <span data-ttu-id="676d4-127">**准备情况和资源准备:** 创建目标范围和广泛关注的感知、培训和支持资源, 包括专注的价值消息传递以加速用户购买</span><span class="sxs-lookup"><span data-stu-id="676d4-127">**Readiness and resource preparation:** Creation of targeted and broad-reach awareness, training, and support resources, including focused value messaging to accelerate user buy-in</span></span>

<span data-ttu-id="676d4-128">使用以下注意事项评估组织的准备情况以解决用户更改管理问题。</span><span class="sxs-lookup"><span data-stu-id="676d4-128">Use the following considerations to assess your organization’s preparedness to address user change management.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="676d4-129">决策点</span><span class="sxs-lookup"><span data-stu-id="676d4-129">Decision points</span></span></td><td><ul><li><span data-ttu-id="676d4-130">您是否曾对使用软件或服务的用户进行了以前的成功？</span><span class="sxs-lookup"><span data-stu-id="676d4-130">Have you had previous success with user adoption of software or services?</span></span></li><li><span data-ttu-id="676d4-131">是否可以跟踪使用 uptake？</span><span class="sxs-lookup"><span data-stu-id="676d4-131">Can you track usage uptake?</span></span></li><li><span data-ttu-id="676d4-132">您是否有用于设计和管理初始&mdash;和正在进行&mdash;的采纳活动 (意识、培训和支持) 的资源？</span><span class="sxs-lookup"><span data-stu-id="676d4-132">Do you have the resources to design and manage an initial&mdash;and ongoing&mdash;adoption campaign (awareness, training, and support)?</span></span></li><li><span data-ttu-id="676d4-133">您是否有专门的用户采纳/更改管理团队, 是否可以购买这些资源以确保业务成果？</span><span class="sxs-lookup"><span data-stu-id="676d4-133">Do you have a dedicated user adoption/change management team, or can you invest in those resources to ensure business outcomes?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="676d4-134">后续步骤</span><span class="sxs-lookup"><span data-stu-id="676d4-134">Next steps</span></span></td><td><ul><li><span data-ttu-id="676d4-135">如果对上述&quot;全部&quot;项回答 "是", 请确定合适的用户变更管理利益干系人并开始准备用户规划。</span><span class="sxs-lookup"><span data-stu-id="676d4-135">If you answered &quot;yes&quot; to all of the above, identify the right user change management stakeholders and begin your user readiness planning.</span></span></li><li><span data-ttu-id="676d4-136">如果您回答&quot;的&quot;不是上述部分或全部, 请考虑向外部资源提供帮助, 帮助您组织的变更管理和与采纳相关的活动。</span><span class="sxs-lookup"><span data-stu-id="676d4-136">If you answered &quot;no&quot; to some or all of the above, consider engaging outside resources to assist with driving change management and adoption-related activities for your organization.</span></span></li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a><span data-ttu-id="676d4-137">网络准备情况</span><span class="sxs-lookup"><span data-stu-id="676d4-137">Network readiness</span></span>

<span data-ttu-id="676d4-138">团队使用音频和视频技术 (编解码器), 它可以在大多数网络条件下适应, 从而性能更好。</span><span class="sxs-lookup"><span data-stu-id="676d4-138">Teams uses audio and video technology (codecs) that can adapt to—and therefore perform better under—most network conditions.</span></span> <span data-ttu-id="676d4-139">为确保最佳性能, 应为团队准备网络。</span><span class="sxs-lookup"><span data-stu-id="676d4-139">To ensure optimal and consistent performance, you should prepare your network for Teams.</span></span>

<span data-ttu-id="676d4-140">![描述三个质量组件的图表](media/evaluate-my-environment-image1.png "描述三种质量组件以及服务管理如何与所有三个组件重叠的图表。将焦点放在网络上。")</span><span class="sxs-lookup"><span data-stu-id="676d4-140">![Diagram describing the three components of quality](media/evaluate-my-environment-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on the network.")</span></span>

## <a name="key-takeaways"></a><span data-ttu-id="676d4-141">关键优势</span><span class="sxs-lookup"><span data-stu-id="676d4-141">Key takeaways</span></span>

<span data-ttu-id="676d4-142">这是本指南的主要优点。</span><span class="sxs-lookup"><span data-stu-id="676d4-142">These are the main takeaways from this guidance.</span></span> <span data-ttu-id="676d4-143">您必须:</span><span class="sxs-lookup"><span data-stu-id="676d4-143">You must:</span></span>

-   <span data-ttu-id="676d4-144">打开从将使用团队的客户端传出的 TCP 端口80和443。</span><span class="sxs-lookup"><span data-stu-id="676d4-144">Open TCP ports 80 and 443 outgoing from clients that will use Teams.</span></span>

-   <span data-ttu-id="676d4-145">打开从将使用团队的客户端传出的 UDP 端口3478到3481。</span><span class="sxs-lookup"><span data-stu-id="676d4-145">Open UDP ports 3478 through 3481 outgoing from clients that will use Teams.</span></span>

-   <span data-ttu-id="676d4-146">确保您有足够的带宽来部署团队。</span><span class="sxs-lookup"><span data-stu-id="676d4-146">Ensure that you have sufficient bandwidth for deploying Teams.</span></span>

-   <span data-ttu-id="676d4-147">运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885), 确保满足从边缘段和客户端段的[媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中所述的要求。</span><span class="sxs-lookup"><span data-stu-id="676d4-147">Run the [Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) and ensure that you meet the requirements described in [Media quality and network connectivity performance](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) from both the edge segment and the client segment.</span></span>

## <a name="why-should-you-prepare-your-network"></a><span data-ttu-id="676d4-148">为什么要准备网络？</span><span class="sxs-lookup"><span data-stu-id="676d4-148">Why should you prepare your network?</span></span>

<span data-ttu-id="676d4-149">在查看要采取的步骤之前, 请务必了解哪些内容会影响团队的性能, 从而提高用户的幸福和满意度。</span><span class="sxs-lookup"><span data-stu-id="676d4-149">Before we look at the steps to be taken, it’s important to understand what can affect the performance of Teams and thereby user happiness and satisfaction.</span></span>
<span data-ttu-id="676d4-150">三个主要风险领域会影响用户对网络质量的理解:</span><span class="sxs-lookup"><span data-stu-id="676d4-150">Three major risk areas can affect how users perceive network quality:</span></span>

-   <span data-ttu-id="676d4-151">可用带宽不足</span><span class="sxs-lookup"><span data-stu-id="676d4-151">Insufficient bandwidth available</span></span>

-   <span data-ttu-id="676d4-152">防火墙和代理阻止程序</span><span class="sxs-lookup"><span data-stu-id="676d4-152">Firewall and proxy blockers</span></span>

-   <span data-ttu-id="676d4-153">网络障碍, 如抖动和数据包丢失</span><span class="sxs-lookup"><span data-stu-id="676d4-153">Network impairments such as jitter and packet loss</span></span>

<span data-ttu-id="676d4-154">下面介绍的步骤将帮助你确定你的部署是否受这些因素的影响, 并将帮助你转向解决方案。</span><span class="sxs-lookup"><span data-stu-id="676d4-154">The steps described below will help you determine whether your deployment might be affected by any of these factors and will help you move toward a resolution.</span></span>
<span data-ttu-id="676d4-155">无法准备网络可能会导致不满意的用户和非常昂贵的临时修补程序。</span><span class="sxs-lookup"><span data-stu-id="676d4-155">Failing to prepare your network will likely lead to dissatisfied users and costly, ad-hoc fixes.</span></span> <span data-ttu-id="676d4-156">通过为团队准备网络和你的组织, 你可以大大增加成功的可能性。</span><span class="sxs-lookup"><span data-stu-id="676d4-156">By preparing your network—and your organization—for Teams, you can dramatically increase your chance of success.</span></span>

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a><span data-ttu-id="676d4-157">带宽规划</span><span class="sxs-lookup"><span data-stu-id="676d4-157">Bandwidth planning</span></span>

<span data-ttu-id="676d4-158">网络准备情况的第一步是确保你的网络有足够的带宽可供形式团队提供给用户。</span><span class="sxs-lookup"><span data-stu-id="676d4-158">The first step toward network readiness is ensuring your network has enough bandwidth available for the modalities Teams will provide to users.</span></span> <span data-ttu-id="676d4-159">规划足够的带宽是一个非常简单的任务和一个非常低廉的起点, 可确保你的用户具有高质量的团队体验。</span><span class="sxs-lookup"><span data-stu-id="676d4-159">Planning for sufficient bandwidth is a fairly straightforward task and a very low-barrier start to ensure your users will have a high-quality Teams experience.</span></span>

### <a name="local-internet-egress"></a><span data-ttu-id="676d4-160">本地 Internet 出口</span><span class="sxs-lookup"><span data-stu-id="676d4-160">Local internet egress</span></span>

<span data-ttu-id="676d4-161">许多网络设计为使用中心和辐射型拓扑。</span><span class="sxs-lookup"><span data-stu-id="676d4-161">Many networks were designed to use a hub and spoke topology.</span></span> <span data-ttu-id="676d4-162">在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。</span><span class="sxs-lookup"><span data-stu-id="676d4-162">In this topology, internet traffic typically traverses the WAN to a central datacenter before it emerges (egresses) to the internet.</span></span> <span data-ttu-id="676d4-163">通常，这么做事为了集中网络安全设备，目的是降低总成本。</span><span class="sxs-lookup"><span data-stu-id="676d4-163">Often, this is done to centralize network security devices with the goal of reducing overall cost.</span></span>

<span data-ttu-id="676d4-164">经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="676d4-164">Back-hauling traffic across the WAN increases latency and has a negative impact on quality and the user experience.</span></span> <span data-ttu-id="676d4-165">由于 Microsoft Teams 在 Microsoft 的大型全局网络上运行，因此，用户附近通常会有网络对等位置。</span><span class="sxs-lookup"><span data-stu-id="676d4-165">Because Microsoft Teams runs on Microsoft’s large global network, there’s often a network peering location close to the user.</span></span> <span data-ttu-id="676d4-166">用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。</span><span class="sxs-lookup"><span data-stu-id="676d4-166">A user will most likely get better performance by egressing out of a local internet point close to their location and on to our voice-optimized network as soon as possible.</span></span> <span data-ttu-id="676d4-167">对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。</span><span class="sxs-lookup"><span data-stu-id="676d4-167">For some workloads, DNS requests are used to send traffic to the nearest front-end server.</span></span> <span data-ttu-id="676d4-168">在这种情况下，务必要在使用本地出口点时，将其与本地 DNS 解析配对。</span><span class="sxs-lookup"><span data-stu-id="676d4-168">In such cases, it’s important that when using a local egress point, it’s paired with local DNS resolution.</span></span>

<span data-ttu-id="676d4-169">优化指向 Microsoft 的全局网络的网络路径将会提高性能，并最终将为用户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="676d4-169">Optimizing the network path to Microsoft’s global network will improve performance and ultimately provide the best experience for users.</span></span> <span data-ttu-id="676d4-170">有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。</span><span class="sxs-lookup"><span data-stu-id="676d4-170">For more detail, see the blog post [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

### <a name="vpn"></a><span data-ttu-id="676d4-171">VPN</span><span class="sxs-lookup"><span data-stu-id="676d4-171">VPN</span></span>

<span data-ttu-id="676d4-172">VPN 为许多组织提供很有用的服务。</span><span class="sxs-lookup"><span data-stu-id="676d4-172">VPNs provide a valuable service to many organizations.</span></span> <span data-ttu-id="676d4-173">很遗憾, 它们通常不是为支持实时媒体而设计或配置的。</span><span class="sxs-lookup"><span data-stu-id="676d4-173">Unfortunately, they’re typically not designed or configured to support real-time media.</span></span> <span data-ttu-id="676d4-174">一些 VPN 可能还不支持 UDP。</span><span class="sxs-lookup"><span data-stu-id="676d4-174">Some VPNs might also not support UDP.</span></span> <span data-ttu-id="676d4-175">Vpn 还会在已加密的媒体流量顶部引入额外的加密层。</span><span class="sxs-lookup"><span data-stu-id="676d4-175">VPNs also introduce an extra layer of encryption on top of media traffic that’s already encrypted.</span></span> <span data-ttu-id="676d4-176">此外, 由于通过 VPN 设备有头发的流量, 到团队服务的连接可能不会有效。</span><span class="sxs-lookup"><span data-stu-id="676d4-176">In addition, connectivity to the Teams service might not be efficient due to hair-pinning traffic through a VPN device.</span></span>
<span data-ttu-id="676d4-177">此外, 它们不一定从容量角度进行设计, 以适应团队需要的预期负载。</span><span class="sxs-lookup"><span data-stu-id="676d4-177">Furthermore, they aren’t necessarily designed from a capacity perspective to accommodate the anticipated loads that Teams will require.</span></span>

<span data-ttu-id="676d4-178">建议提供一个备用路径，以便 Teams 流量绕过 VPN。</span><span class="sxs-lookup"><span data-stu-id="676d4-178">The recommendation is to provide an alternate path that bypasses the VPN for Teams traffic.</span></span> <span data-ttu-id="676d4-179">这通常称为*拆分隧道 VPN*。</span><span class="sxs-lookup"><span data-stu-id="676d4-179">This is commonly known as *split-tunnel VPN*.</span></span> <span data-ttu-id="676d4-180">拆分隧道意味着 Office 365 的流量不会遍历 VPN, 但会直接转到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="676d4-180">Split tunneling means that traffic for Office 365 won’t traverse the VPN but will go directly to Office 365.</span></span> <span data-ttu-id="676d4-181">此改变不仅有利于提高质量，而且还带来额外的好处，即降低 VPN 设备和组织网络的负荷。</span><span class="sxs-lookup"><span data-stu-id="676d4-181">This change will have a positive impact on quality, but also provides the secondary benefit of reducing load from the VPN devices and the organization’s network.</span></span>

<span data-ttu-id="676d4-182">要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="676d4-182">To implement a split-tunnel, consult with your VPN vendor for the configuration details.</span></span>

### <a name="wi-fi"></a><span data-ttu-id="676d4-183">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="676d4-183">Wi-Fi</span></span>

<span data-ttu-id="676d4-184">与 VPN 类似, Wlan 网络不一定设计或配置为支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="676d4-184">Like VPN, Wi-Fi networks aren’t necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="676d4-185">在高质量部署中, 为支持团队规划或优化 Wi-fi 网络是重要的考虑因素。</span><span class="sxs-lookup"><span data-stu-id="676d4-185">Planning for, or optimizing, a Wi-Fi network to support Teams is an important consideration for a high-quality deployment.</span></span>

<span data-ttu-id="676d4-186">优化 Wlan 网络有以下几个因素:</span><span class="sxs-lookup"><span data-stu-id="676d4-186">There are several factors that come into play for optimizing a Wi-Fi network:</span></span>

-   <span data-ttu-id="676d4-187">实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。</span><span class="sxs-lookup"><span data-stu-id="676d4-187">Implementing QoS or Wi-Fi Multimedia (WMM) to ensure that media traffic is getting prioritized accordingly over the Wi-Fi networks.</span></span>

-   <span data-ttu-id="676d4-188">规划和优化 Wi-fi 频带和接入点放置。</span><span class="sxs-lookup"><span data-stu-id="676d4-188">Planning and optimizing the Wi-Fi bands and access point placement.</span></span> <span data-ttu-id="676d4-189">2.4 GHz 范围可以根据接入点位置提供合乎需要的体验，但接入点通常受该范围内运行的使用者其他设备的影响。</span><span class="sxs-lookup"><span data-stu-id="676d4-189">The 2.4 GHz range may provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="676d4-190">5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="676d4-190">The 5 GHz range is better suited to real-time media due to their dense range but requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="676d4-191">此外，终结点还需要相应地支持该范围并配置为利用这些频带。</span><span class="sxs-lookup"><span data-stu-id="676d4-191">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span>

-   <span data-ttu-id="676d4-192">如果已部署了双频带 Wi-fi 网络, 请考虑实施频带筹划。</span><span class="sxs-lookup"><span data-stu-id="676d4-192">If dual-band Wi-Fi networks are deployed, consider implementing band steering.</span></span> <span data-ttu-id="676d4-193">波段控制是由 Wi-fi 供应商实施的一项技术, 可影响双层客户使用 5 GHz 范围。</span><span class="sxs-lookup"><span data-stu-id="676d4-193">Band steering is a technique implemented by Wi-Fi vendors to influence dual-band clients to use the 5 GHz range.</span></span>

-   <span data-ttu-id="676d4-194">当同一频道的接入点太靠近时, 它们可能会导致信号重叠并无意间竞争, 从而导致用户体验不良。</span><span class="sxs-lookup"><span data-stu-id="676d4-194">When access points of the same channel are too close together they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="676d4-195">确保彼此相邻的接入点位于不重叠的频道上。</span><span class="sxs-lookup"><span data-stu-id="676d4-195">Ensure that access points that are next to each other are on channels that don’t overlap.</span></span>

<span data-ttu-id="676d4-196">每个无线供应商都有自己的无线解决方案部署建议。</span><span class="sxs-lookup"><span data-stu-id="676d4-196">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="676d4-197">建议你咨询你的供应商了解具体指导。</span><span class="sxs-lookup"><span data-stu-id="676d4-197">We recommend that you consult your vendor for specific guidance.</span></span>

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a><span data-ttu-id="676d4-198">防火墙和代理要求</span><span class="sxs-lookup"><span data-stu-id="676d4-198">Firewall and proxy requirements</span></span>

<span data-ttu-id="676d4-199">Microsoft 团队连接到 Microsoft Online 服务, 并且需要 internet 连接才能实现此操作。</span><span class="sxs-lookup"><span data-stu-id="676d4-199">Microsoft Teams connects to Microsoft Online Services and needs internet connectivity for this.</span></span> <span data-ttu-id="676d4-200">要使团队正常运行, 必须从客户端打开 TCP 端口80和 443, 并从客户端到网络的 UDP 端口3478到3481。</span><span class="sxs-lookup"><span data-stu-id="676d4-200">For Teams to function correctly, you must open TCP ports 80 and 443 from the clients to the internet, and UDP ports 3478 through 3481 from the clients to the internet.</span></span> <span data-ttu-id="676d4-201">TCP 端口用于连接到基于 web 的内容, 如 SharePoint Online、Exchange Online 和团队聊天服务。</span><span class="sxs-lookup"><span data-stu-id="676d4-201">The TCP ports are used to connect to web-based content such as SharePoint Online, Exchange Online, and the Teams Chat services.</span></span>
<span data-ttu-id="676d4-202">插件和连接器也通过这些 TCP 端口进行连接。</span><span class="sxs-lookup"><span data-stu-id="676d4-202">Plug-ins and connectors also connect over these TCP ports.</span></span> <span data-ttu-id="676d4-203">四个 UDP 端口用于音频和视频等媒体, 以确保它们正常流动。</span><span class="sxs-lookup"><span data-stu-id="676d4-203">The four UDP ports are used for media such as audio and video, to ensure they flow correctly.</span></span>

<span data-ttu-id="676d4-204">打开这些端口对于可靠的团队部署非常重要。</span><span class="sxs-lookup"><span data-stu-id="676d4-204">Opening these ports is essential for a reliable Teams deployment.</span></span> <span data-ttu-id="676d4-205">阻止这些端口不受支持, 并且将对媒体质量产生影响。</span><span class="sxs-lookup"><span data-stu-id="676d4-205">Blocking these ports is unsupported and will have an effect on media quality.</span></span>

<span data-ttu-id="676d4-206">如果你的组织要求你指定应在其中打开这些端口的确切 IP 地址范围和域, 则可以限制这些端口的目标 IP 范围和域。</span><span class="sxs-lookup"><span data-stu-id="676d4-206">If your organization requires that you specify the exact IP address ranges and domains to which these ports should be opened, you can restrict the target IP ranges and domains for these ports.</span></span> <span data-ttu-id="676d4-207">有关确切的端口、协议和 IP 范围的列表, 请参阅[Office 365 url 和 ip 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。</span><span class="sxs-lookup"><span data-stu-id="676d4-207">For a list of exact ports, protocols, and IP ranges, see [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).</span></span>
<span data-ttu-id="676d4-208">如果你选择限制目标 IP 地址范围和域, 则必须确保将端口和范围的列表保持为最新, 因为它们可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="676d4-208">If you choose to restrict the target IP address ranges and domains, you must ensure that you keep the list of ports and ranges up to date because they might change.</span></span> <span data-ttu-id="676d4-209">你可以订阅[此 RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301), 以便在发生更改时进行更新。</span><span class="sxs-lookup"><span data-stu-id="676d4-209">You can subscribe to [this RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) to be updated when changes occur.</span></span> <span data-ttu-id="676d4-210">这也是一种很好的做法, 通过定期运行[Skype For Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试所有端口是否已打开。</span><span class="sxs-lookup"><span data-stu-id="676d4-210">It’s also a good practice to test whether all ports are opened by running the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) on a regular basis.</span></span> <span data-ttu-id="676d4-211">可在下一节中了解有关此工具的功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="676d4-211">You can find out more about the functionality of this tool in the next section.</span></span>

<span data-ttu-id="676d4-212">在正在部署的代理服务器事件中, 我们建议您绕过所有团队服务的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="676d4-212">In the event of a proxy server being deployed, we recommend that you bypass the proxy server for all Teams services.</span></span> <span data-ttu-id="676d4-213">虽然使用代理可能有效, 但由于媒体被迫使用 TCP 而不是 UDP, 因此很可能会降低质量。</span><span class="sxs-lookup"><span data-stu-id="676d4-213">Although using a proxy might work, it’s very likely that quality will be reduced due to media’s being forced to use TCP instead of UDP.</span></span> <span data-ttu-id="676d4-214">有关代理服务器和绕过的详细信息, 请参阅[Office 365 url 和 IP 地址范围](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="676d4-214">For more information about proxy servers and bypassing, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).</span></span>

<!--ENDOFSECTION-->

## <a name="test-the-network"></a><span data-ttu-id="676d4-215">测试网络</span><span class="sxs-lookup"><span data-stu-id="676d4-215">Test the network</span></span>

<span data-ttu-id="676d4-216">完成规划和网络准备 (包括升级带宽和打开防火墙中的端口) 后, 应测试网络的性能。</span><span class="sxs-lookup"><span data-stu-id="676d4-216">After you’ve completed your planning and network preparation—including upgrading bandwidth and opening ports in the firewall—you should test your network’s performance.</span></span> <span data-ttu-id="676d4-217">此测试的结果将绘制一个更清晰的图片, 让你的音频会议或电话系统成功完成所需的任何网络优化或补救措施。</span><span class="sxs-lookup"><span data-stu-id="676d4-217">The results of this testing will paint a clearer picture of any network optimization or remediation required for the success of your Audio Conferencing or Phone System with Calling Plan implementation.</span></span>

<span data-ttu-id="676d4-218">你可以下载[Skype For Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试你的网络是否已准备好进行团队。</span><span class="sxs-lookup"><span data-stu-id="676d4-218">You can download the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span> <span data-ttu-id="676d4-219">此工具提供双重功能: 它可以测试是否已打开所有正确的端口, 并且它可以测试网络是否有障碍。</span><span class="sxs-lookup"><span data-stu-id="676d4-219">The tool offers dual functionality: it can test whether all the correct ports have been opened, and it can test for network impairments.</span></span>

<span data-ttu-id="676d4-220">下载并安装该工具后, 您可以在 C:\\Program Files\\Microsoft Skype For business 网络评估工具中找到它。</span><span class="sxs-lookup"><span data-stu-id="676d4-220">After you download and install the tool, you can find it in C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool.</span></span> <span data-ttu-id="676d4-221">有关如何使用该工具的详细指南 (如 .docx) 包含在该目录中。</span><span class="sxs-lookup"><span data-stu-id="676d4-221">A detailed guide for how to use the tool, Usage.docx, is included in that directory.</span></span>

### <a name="test-for-opened-ports"></a><span data-ttu-id="676d4-222">测试打开的端口</span><span class="sxs-lookup"><span data-stu-id="676d4-222">Test for opened ports</span></span>

<span data-ttu-id="676d4-223">打开命令提示符窗口, 然后导航到 "网络评估" 工具目录, 方法是输入**Cd\\C\\: Program Files Microsoft Skype for business 网络评估工具**。</span><span class="sxs-lookup"><span data-stu-id="676d4-223">Open a Command prompt window and navigate to the Network Assessment Tool directory by entering **cd C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool**.</span></span> <span data-ttu-id="676d4-224">在命令提示符处, 通过输入**networkassessmenttool/connectivitycheck**开始测试已打开的端口</span><span class="sxs-lookup"><span data-stu-id="676d4-224">At the command prompt, start the test for opened ports by entering **networkassessmenttool.exe /connectivitycheck**</span></span>

<span data-ttu-id="676d4-225">运行检查后, 该工具将显示消息 "验证已成功完成" 或报告已阻止的端口。</span><span class="sxs-lookup"><span data-stu-id="676d4-225">After running the checks, the tool will either display the message “Verifications Completed Successfully” or report on the ports that were blocked.</span></span>
<span data-ttu-id="676d4-226">它还会生成一个名为 Connectivity_results 的文件, 其中包含该工具的输出, 并将其存储在% userprofile\\%\\appdata\\本地 microsoft skype for business 网络评估\\工具目录中。</span><span class="sxs-lookup"><span data-stu-id="676d4-226">It also generates a file named Connectivity_results.txt, which contains the output from the tool and stores it in the %userprofile%\\appdata\\local\\microsoft skype for business network assessment tool\\ directory.</span></span>

<span data-ttu-id="676d4-227">我们建议你定期运行连接检查, 以确保端口已打开并正常运行。</span><span class="sxs-lookup"><span data-stu-id="676d4-227">We recommend that you run the connectivity checks on a regular basis to ensure the ports have been opened and are functioning correctly.</span></span>

### <a name="test-for-network-impairments"></a><span data-ttu-id="676d4-228">测试网络是否有障碍</span><span class="sxs-lookup"><span data-stu-id="676d4-228">Test for network impairments</span></span>

<span data-ttu-id="676d4-229">为提高用户满意度, 您应该限制网络的任何障碍。</span><span class="sxs-lookup"><span data-stu-id="676d4-229">To increase user satisfaction, you should limit any impairments on your network.</span></span>
<span data-ttu-id="676d4-230">最常见的网络障碍是延迟 (延迟)、数据包丢失和抖动:</span><span class="sxs-lookup"><span data-stu-id="676d4-230">The most common network impairments are delay (latency), packet loss, and jitter:</span></span>

-   <span data-ttu-id="676d4-231">**延迟:** 这是将 IP 数据包从点 A 转到网络上的点 B 所需的时间。</span><span class="sxs-lookup"><span data-stu-id="676d4-231">**Latency:** This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="676d4-232">此网络传播延迟实质上与两个点之间的物理距离和光之间的距离保持联系, 包括不同路由器所用的额外开销。</span><span class="sxs-lookup"><span data-stu-id="676d4-232">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span>
    <span data-ttu-id="676d4-233">延迟是指单向或往返时间。</span><span class="sxs-lookup"><span data-stu-id="676d4-233">Latency is measured as one-way or round-trip time.</span></span>

-   <span data-ttu-id="676d4-234">**数据包丢失**: 这通常定义为在给定时间段内丢失的数据包的百分比。</span><span class="sxs-lookup"><span data-stu-id="676d4-234">**Packet loss**: This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="676d4-235">数据包丢失直接影响音频质量-从较小的单个丢失的数据包中, 几乎不会影响对导致音频完全减少的后端到后突发损失的影响。</span><span class="sxs-lookup"><span data-stu-id="676d4-235">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact to back-to-back burst losses that cause audio to cut out completely.</span></span>

-   <span data-ttu-id="676d4-236">**数据包间到达抖动或简单抖动:** 这是连续数据包之间的延迟的平均变化。</span><span class="sxs-lookup"><span data-stu-id="676d4-236">**Inter-packet arrival jitter, or simply jitter:** This is the average change in delay between successive packets.</span></span> <span data-ttu-id="676d4-237">大多数现代 VoIP 软件 (包括 Skype for Business) 可以通过缓冲来适应某些级别的抖动。</span><span class="sxs-lookup"><span data-stu-id="676d4-237">Most modern VoIP software, including Skype for Business, can adapt to some levels of jitter through buffering.</span></span> <span data-ttu-id="676d4-238">仅当抖动超过的是参与者将注意到抖动效果的缓冲时才会如此。</span><span class="sxs-lookup"><span data-stu-id="676d4-238">It's only when the jitter exceeds the buffering that a participant will notice the effects of jitter.</span></span>

<span data-ttu-id="676d4-239">在[媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中介绍了这些障碍的最大值。</span><span class="sxs-lookup"><span data-stu-id="676d4-239">The maximum values for these impairments are described in [Media quality and network connectivity performance](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>
<span data-ttu-id="676d4-240">测试这些障碍时, 请区分两个不同的段:</span><span class="sxs-lookup"><span data-stu-id="676d4-240">When testing for these impairments, we distinguish between two separate segments:</span></span>

-   <span data-ttu-id="676d4-241">*边缘段*是你的路由器所在的段。</span><span class="sxs-lookup"><span data-stu-id="676d4-241">The *edge segment* is the segment in which your router lives.</span></span> <span data-ttu-id="676d4-242">这是您的每个位置上连接到互联网的最接近的逻辑网络段。</span><span class="sxs-lookup"><span data-stu-id="676d4-242">This is the closest logical network segment connected to the internet at each of your locations.</span></span> <span data-ttu-id="676d4-243">在大多数情况下, 这是路由器的连接点, 或者是外围网络 (也称为*DMZ*、*隔离区*和*屏蔽子网*)。</span><span class="sxs-lookup"><span data-stu-id="676d4-243">In most cases, this is the connection point of the router, or possibly a perimeter network (also known as *DMZ*, *demilitarized zone*, and *screened subnet*).</span></span> <span data-ttu-id="676d4-244">除了路由器之外的设备之外, 任何其他通信量都不应出现在此网段和 internet 之间。</span><span class="sxs-lookup"><span data-stu-id="676d4-244">No further traffic that affects devices other than the router should occur between this segment and the internet.</span></span>

-   <span data-ttu-id="676d4-245">*客户端段*是客户端所在的逻辑网络段。</span><span class="sxs-lookup"><span data-stu-id="676d4-245">The *client segment* is the logical network segment in which your clients reside.</span></span>

<span data-ttu-id="676d4-246">你应该使用网络评估工具测试这两个段。</span><span class="sxs-lookup"><span data-stu-id="676d4-246">You should test both segments by using the Network Assessment Tool.</span></span> <span data-ttu-id="676d4-247">若要测试段, 请导航到目录并在命令提示符处输入**networkassessmenttool** 。</span><span class="sxs-lookup"><span data-stu-id="676d4-247">To test the segment, navigate to the directory and enter **networkassessmenttool.exe** at the command prompt.</span></span> <span data-ttu-id="676d4-248">结果将写入一个名为 tsv 的文件中, 您可以将其与每个段的[要求](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)进行比较。</span><span class="sxs-lookup"><span data-stu-id="676d4-248">The results are written to a file named Results.tsv, and you can compare them to the [requirements](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) for each segment.</span></span>

<span data-ttu-id="676d4-249">请注意, 两个段必须满足高质量部署的要求。</span><span class="sxs-lookup"><span data-stu-id="676d4-249">Note that both segments must meet the requirements for a high-quality deployment.</span></span> <span data-ttu-id="676d4-250">我们建议你在一小时内多次运行该工具, 以获得更好的网络性能指示。</span><span class="sxs-lookup"><span data-stu-id="676d4-250">We recommend that you run the tool multiple times for one hour straight to get a good indication of your network’s performance.</span></span>

<!--ENDOFSECTION-->

## <a name="network-remediation"></a><span data-ttu-id="676d4-251">网络修正</span><span class="sxs-lookup"><span data-stu-id="676d4-251">Network remediation</span></span>

<span data-ttu-id="676d4-252">如果带宽规划、端口测试或网络要求测试的结果显示您当前的网络需要补救措施才能部署团队, 则可以通过以下几种方式实现此目的:</span><span class="sxs-lookup"><span data-stu-id="676d4-252">If the results of bandwidth planning, port testing, or network requirements testing show that your current network needs remediation before you deploy Teams, you can accomplish this in several ways:</span></span>

-   <span data-ttu-id="676d4-253">如果带宽不足, 请升级连接, 以便到 Office 365 的通信流 unhindered。</span><span class="sxs-lookup"><span data-stu-id="676d4-253">For insufficient bandwidth, upgrade connections so that traffic to Office 365 can flow unhindered.</span></span>

-   <span data-ttu-id="676d4-254">对于已阻止的端口, 请更改防火墙规则并重新测试端口。</span><span class="sxs-lookup"><span data-stu-id="676d4-254">For blocked ports, change firewall rules and retest the ports.</span></span>

-   <span data-ttu-id="676d4-255">对于网络障碍, 请始终执行根本原因分析。</span><span class="sxs-lookup"><span data-stu-id="676d4-255">For network impairments, always perform a root-cause analysis.</span></span>

<span data-ttu-id="676d4-256">服务质量 (QoS) 可用于对流量进行排序和分隔, 从而使障碍更有障碍。</span><span class="sxs-lookup"><span data-stu-id="676d4-256">Quality of service (QoS) can be used to battle impairments by prioritizing and separating traffic.</span></span> <span data-ttu-id="676d4-257">某些组织选择部署 QoS 来克服带宽问题或限制流量的流量。</span><span class="sxs-lookup"><span data-stu-id="676d4-257">Some organizations choose to deploy QoS to overcome bandwidth issues or restrict the amount of traffic flowing.</span></span> <span data-ttu-id="676d4-258">这不会提高质量, 并将导致新问题。</span><span class="sxs-lookup"><span data-stu-id="676d4-258">This won’t improve quality and will lead to new problems.</span></span> <span data-ttu-id="676d4-259">当网络障碍超过要求时, 应始终执行根本原因分析。</span><span class="sxs-lookup"><span data-stu-id="676d4-259">A root-cause analysis should always be performed when network impairments exceed requirements.</span></span> <span data-ttu-id="676d4-260">QoS 可以是一个解决方案。</span><span class="sxs-lookup"><span data-stu-id="676d4-260">QoS can be a solution.</span></span>
<span data-ttu-id="676d4-261">有关详细信息, 请参阅[Microsoft 团队中的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="676d4-261">For more information, see [Quality of Service in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).</span></span>

>[!NOTE]
><span data-ttu-id="676d4-262">许多网络会由于升级、扩展或其他业务要求而逐渐发展。</span><span class="sxs-lookup"><span data-stu-id="676d4-262">Many networks evolve over time due to upgrades, expansion, or other business requirements.</span></span> <span data-ttu-id="676d4-263">请确保在你的服务管理规划中具有可操作的流程以维护这些方面。</span><span class="sxs-lookup"><span data-stu-id="676d4-263">Ensure that you have operational processes in place to maintain these areas as part of your service management planning.</span></span>


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="676d4-264">决策点</span><span class="sxs-lookup"><span data-stu-id="676d4-264">Decision points</span></span></td><td><ul><li><span data-ttu-id="676d4-265">谁将负责在所有网段和组织位置完成正确的网络评估？</span><span class="sxs-lookup"><span data-stu-id="676d4-265">Who will be responsible for completing proper network assessments across all network segments and organization locations?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="676d4-266">后续步骤</span><span class="sxs-lookup"><span data-stu-id="676d4-266">Next steps</span></span></td><td><ul><li><span data-ttu-id="676d4-267">你可以执行详细的网络评估, 以帮助确保你的网络为你的 Microsoft 团队部署做好准备。</span><span class="sxs-lookup"><span data-stu-id="676d4-267">You can perform a detailed network assessment to help ensure your network is ready for your Microsoft Teams deployment.</span></span></li><li><span data-ttu-id="676d4-268">基于针对每个网络段的评估结果执行网络修正。</span><span class="sxs-lookup"><span data-stu-id="676d4-268">Perform network remediation based on the results of the assessment for every network segment.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->