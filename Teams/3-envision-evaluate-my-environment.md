---
title: 评估云语音工作负荷的环境
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用角色和网络分析来评估组织的准备情况，打开正确的 TCP 和 UDP 端口，执行任何网络修正。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b65e6f2f6db4f5e824e55368d0a7a097eb39ad9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094770"
---
# <a name="evaluate-my-environment"></a><span data-ttu-id="e77f8-103">评估环境</span><span class="sxs-lookup"><span data-stu-id="e77f8-103">Evaluate my environment</span></span>

<span data-ttu-id="e77f8-104">本文概述了正确评估当前环境以使用云语音服务的要求。</span><span class="sxs-lookup"><span data-stu-id="e77f8-104">This article gives an overview of the requirements for properly evaluating your current environment for using cloud voice services.</span></span> <span data-ttu-id="e77f8-105">通过评估环境，可以识别影响整体云语音部署的风险和要求。</span><span class="sxs-lookup"><span data-stu-id="e77f8-105">By evaluating your environment, you identify risks and requirements that will influence your overall cloud voice deployment.</span></span> <span data-ttu-id="e77f8-106">通过事先确定这些项目，可以调整规划以推动成功。</span><span class="sxs-lookup"><span data-stu-id="e77f8-106">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-evaluating-your-environment"></a><span data-ttu-id="e77f8-107">环境评估简介</span><span class="sxs-lookup"><span data-stu-id="e77f8-107">Introduction to evaluating your environment</span></span>

<span data-ttu-id="e77f8-108">为了在 OKR (目标) ，你之前做出过关键服务决策。</span><span class="sxs-lookup"><span data-stu-id="e77f8-108">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="e77f8-109">下一步是执行环境发现，评估与 IT 和电话基础结构、网络和操作相关的所有方面，以确认组织已准备好实施解决方案。</span><span class="sxs-lookup"><span data-stu-id="e77f8-109">The next step is to perform environmental discovery to evaluate all aspects relating to your IT and telephony infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span>

<span data-ttu-id="e77f8-110">环境发现必须包含网络准备情况评估，以确保你的网络可以支持音频会议或电话系统与呼叫计划服务的实现。</span><span class="sxs-lookup"><span data-stu-id="e77f8-110">Environmental discovery must include network readiness assessment to ensure your network can support the implementation of the Audio Conferencing or Phone System with Calling Plan services.</span></span>

<span data-ttu-id="e77f8-111">在环境评估和采用就绪性评估中识别技术风险，并针对每个已识别的风险制定缓解计划。</span><span class="sxs-lookup"><span data-stu-id="e77f8-111">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span>
<span data-ttu-id="e77f8-112">应该将此信息合并到风险寄存器中。</span><span class="sxs-lookup"><span data-stu-id="e77f8-112">You should incorporate this information in the risk register.</span></span>

<!--ENDOFSECTION-->

## <a name="current-environment"></a><span data-ttu-id="e77f8-113">当前环境</span><span class="sxs-lookup"><span data-stu-id="e77f8-113">Current environment</span></span>

<span data-ttu-id="e77f8-114">作为环境发现的一部分，包括与最终用户计算相关的所有事项，例如电脑和移动设备的准备情况评估，以支持音频会议和电话系统与呼叫计划业务用例，从硬件要求到软件要求。</span><span class="sxs-lookup"><span data-stu-id="e77f8-114">As part of your environmental discovery, include all matters related to end-user computing, such as a readiness assessment of PCs and mobile devices to support Audio Conferencing and Phone System with Calling Plan business use cases, from hardware requirements to software requirements.</span></span>

<span data-ttu-id="e77f8-115">环境发现还可以发现是否需要将[电话号码转移到 Microsoft。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e77f8-115">Environmental discovery can also uncover whether you need to [transfer phone numbers to Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
<span data-ttu-id="e77f8-116">了解此信息有助于组织相应地调整其项目计划，并为号码移植准备必要的信息。</span><span class="sxs-lookup"><span data-stu-id="e77f8-116">Knowing this will help your organization adjust its project plan accordingly and prepare the necessary information for number porting.</span></span> <span data-ttu-id="e77f8-117">可以使用 Microsoft [Teams 的"环境发现"推出](environmental-discovery-for-microsoft-teams-rollout.md) 来执行环境发现。</span><span class="sxs-lookup"><span data-stu-id="e77f8-117">You can use the [Environmental discovery for Microsoft Teams rollout](environmental-discovery-for-microsoft-teams-rollout.md) to perform environmental discovery.</span></span>

<table>
<tr><td><span data-ttu-id="e77f8-118">标题</span><span class="sxs-lookup"><span data-stu-id="e77f8-118">Title</span></span></td><td><span data-ttu-id="e77f8-119">描述</span><span class="sxs-lookup"><span data-stu-id="e77f8-119">Description</span></span></td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="e77f8-120">决策点</span><span class="sxs-lookup"><span data-stu-id="e77f8-120">Decision points</span></span></td><td><ul><li><span data-ttu-id="e77f8-121">谁负责完成环境评估？</span><span class="sxs-lookup"><span data-stu-id="e77f8-121">Who will be responsible for completing an environment assessment?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="e77f8-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e77f8-122">Next steps</span></span></td><td><ul><li><span data-ttu-id="e77f8-123">记录环境评估的结果。</span><span class="sxs-lookup"><span data-stu-id="e77f8-123">Document the results of the environment assessment.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a><span data-ttu-id="e77f8-124">采用和更改管理评估功能</span><span class="sxs-lookup"><span data-stu-id="e77f8-124">Adoption and change management assessment capabilities</span></span>

<span data-ttu-id="e77f8-125">部署使一项新技术触手可及，但只有在用户真正将该解决方案采用为其自己的解决方案之后，才能实现业务成果。</span><span class="sxs-lookup"><span data-stu-id="e77f8-125">Deployment puts a new technology at a user's fingertips, but business results are only realized after users truly adopt that solution as their own.</span></span> <span data-ttu-id="e77f8-126">若要帮助确保持续采用新解决方案，需要将工作重心放在用户就绪状态和更改管理上。</span><span class="sxs-lookup"><span data-stu-id="e77f8-126">To help ensure sustained adoption of a new solution, you'll need to focus your efforts on user readiness and change management.</span></span> <span data-ttu-id="e77f8-127">为获得最佳结果，请作为技术准备活动的并行工作流进行用户准备情况规划，并整合以下活动：</span><span class="sxs-lookup"><span data-stu-id="e77f8-127">For optimal results, conduct user readiness planning as a parallel workstream to your technical readiness activities and incorporate the following activities:</span></span>

-   <span data-ttu-id="e77f8-128">**组织和用户分析：** 除了用例和人员分析外，还分析要更改的组织不活动性</span><span class="sxs-lookup"><span data-stu-id="e77f8-128">**Organizational and user profiling:** Analysis of organizational receptiveness to change in addition to use case and persona analysis</span></span>

-   <span data-ttu-id="e77f8-129">**准备和资源准备：** 创建针对性和广泛宣传的认知、培训和支持资源，包括重点价值消息传送以加速用户购买</span><span class="sxs-lookup"><span data-stu-id="e77f8-129">**Readiness and resource preparation:** Creation of targeted and broad-reach awareness, training, and support resources, including focused value messaging to accelerate user buy-in</span></span>

<span data-ttu-id="e77f8-130">使用以下注意事项评估组织解决用户更改管理问题的准备情况。</span><span class="sxs-lookup"><span data-stu-id="e77f8-130">Use the following considerations to assess your organization's preparedness to address user change management.</span></span>

<table>
<tr><td><span data-ttu-id="e77f8-131">标题</span><span class="sxs-lookup"><span data-stu-id="e77f8-131">Title</span></span></td><td><span data-ttu-id="e77f8-132">描述</span><span class="sxs-lookup"><span data-stu-id="e77f8-132">Description</span></span></td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="e77f8-133">决策点</span><span class="sxs-lookup"><span data-stu-id="e77f8-133">Decision points</span></span></td><td><ul><li><span data-ttu-id="e77f8-134">用户以前是否成功采用软件或服务？</span><span class="sxs-lookup"><span data-stu-id="e77f8-134">Have you had previous success with user adoption of software or services?</span></span></li><li><span data-ttu-id="e77f8-135">能否跟踪使用情况上升？</span><span class="sxs-lookup"><span data-stu-id="e77f8-135">Can you track usage uptake?</span></span></li><li><span data-ttu-id="e77f8-136">你是否拥有资源来设计和管理初始和持续采用活动， (认知、培训和 &mdash; &mdash; 支持) ？</span><span class="sxs-lookup"><span data-stu-id="e77f8-136">Do you have the resources to design and manage an initial&mdash;and ongoing&mdash;adoption campaign (awareness, training, and support)?</span></span></li><li><span data-ttu-id="e77f8-137">您是否有专门的用户采用/更改管理团队，或者您是否可以投资这些资源以确保业务成果？</span><span class="sxs-lookup"><span data-stu-id="e77f8-137">Do you have a dedicated user adoption/change management team, or can you invest in those resources to ensure business outcomes?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="e77f8-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e77f8-138">Next steps</span></span></td><td><ul><li><span data-ttu-id="e77f8-139">如果上述所有人员都回答了"是"，请确定适当的用户变更管理利益干系人 &quot; &quot; 并开始用户准备情况规划。</span><span class="sxs-lookup"><span data-stu-id="e77f8-139">If you answered &quot;yes&quot; to all of the above, identify the right user change management stakeholders and begin your user readiness planning.</span></span></li><li><span data-ttu-id="e77f8-140">如果你对上述部分或所有内容都回答了"否"，请考虑利用外部资源来帮助推动组织变更管理和采用 &quot; &quot; 相关的活动。</span><span class="sxs-lookup"><span data-stu-id="e77f8-140">If you answered &quot;no&quot; to some or all of the above, consider engaging outside resources to assist with driving change management and adoption-related activities for your organization.</span></span></li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a><span data-ttu-id="e77f8-141">网络就绪性</span><span class="sxs-lookup"><span data-stu-id="e77f8-141">Network readiness</span></span>

<span data-ttu-id="e77f8-142">Teams 使用音频和视频技术 (编) 编解码器，这些编解码器可以适应大多数网络条件，因此在大部分网络条件下性能更佳。</span><span class="sxs-lookup"><span data-stu-id="e77f8-142">Teams uses audio and video technology (codecs) that can adapt to—and therefore perform better under—most network conditions.</span></span> <span data-ttu-id="e77f8-143">为了确保最佳性能和一致性，应为 Teams 准备网络。</span><span class="sxs-lookup"><span data-stu-id="e77f8-143">To ensure optimal and consistent performance, you should prepare your network for Teams.</span></span>

<span data-ttu-id="e77f8-144">![描述质量的三个要素的示意图](media/evaluate-my-environment-image1.png "描述质量的三个组件以及服务管理如何与这三个组件重叠的示意图。将焦点放在网络上。")</span><span class="sxs-lookup"><span data-stu-id="e77f8-144">![Diagram describing the three components of quality](media/evaluate-my-environment-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on the network.")</span></span>

## <a name="key-takeaways"></a><span data-ttu-id="e77f8-145">要点</span><span class="sxs-lookup"><span data-stu-id="e77f8-145">Key takeaways</span></span>

<span data-ttu-id="e77f8-146">这些是本指南的主要要点。</span><span class="sxs-lookup"><span data-stu-id="e77f8-146">These are the main takeaways from this guidance.</span></span> <span data-ttu-id="e77f8-147">必须：</span><span class="sxs-lookup"><span data-stu-id="e77f8-147">You must:</span></span>

-   <span data-ttu-id="e77f8-148">打开从将使用 Teams 的客户端传出的 TCP 端口 80 和 443。</span><span class="sxs-lookup"><span data-stu-id="e77f8-148">Open TCP ports 80 and 443 outgoing from clients that will use Teams.</span></span>

-   <span data-ttu-id="e77f8-149">打开从将使用 Teams 的客户端传出的 UDP 端口 3478 到 3481。</span><span class="sxs-lookup"><span data-stu-id="e77f8-149">Open UDP ports 3478 through 3481 outgoing from clients that will use Teams.</span></span>

-   <span data-ttu-id="e77f8-150">确保有足够的带宽来部署 Teams。</span><span class="sxs-lookup"><span data-stu-id="e77f8-150">Ensure that you have sufficient bandwidth for deploying Teams.</span></span>

-   <span data-ttu-id="e77f8-151">运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)，确保满足边缘段和客户端段中媒体质量和[](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)网络连接性能中所述的要求。</span><span class="sxs-lookup"><span data-stu-id="e77f8-151">Run the [Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) and ensure that you meet the requirements described in [Media quality and network connectivity performance](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) from both the edge segment and the client segment.</span></span>

## <a name="why-should-you-prepare-your-network"></a><span data-ttu-id="e77f8-152">为什么要准备网络？</span><span class="sxs-lookup"><span data-stu-id="e77f8-152">Why should you prepare your network?</span></span>

<span data-ttu-id="e77f8-153">在查看要执行的步骤之前，必须了解哪些因素可能会影响 Teams 的性能，从而让用户感到快乐和满意。</span><span class="sxs-lookup"><span data-stu-id="e77f8-153">Before we look at the steps to be taken, it's important to understand what can affect the performance of Teams and thereby user happiness and satisfaction.</span></span>
<span data-ttu-id="e77f8-154">三个主要风险领域可能会影响用户对网络质量的看法：</span><span class="sxs-lookup"><span data-stu-id="e77f8-154">Three major risk areas can affect how users perceive network quality:</span></span>

-   <span data-ttu-id="e77f8-155">可用带宽不足</span><span class="sxs-lookup"><span data-stu-id="e77f8-155">Insufficient bandwidth available</span></span>

-   <span data-ttu-id="e77f8-156">防火墙和代理阻止程序</span><span class="sxs-lookup"><span data-stu-id="e77f8-156">Firewall and proxy blockers</span></span>

-   <span data-ttu-id="e77f8-157">网络障碍，例如抖动和数据包丢失</span><span class="sxs-lookup"><span data-stu-id="e77f8-157">Network impairments such as jitter and packet loss</span></span>

<span data-ttu-id="e77f8-158">下面的步骤可帮助确定部署是否可能受上述任何因素影响，并有助于解决问题。</span><span class="sxs-lookup"><span data-stu-id="e77f8-158">The steps described below will help you determine whether your deployment might be affected by any of these factors and will help you move toward a resolution.</span></span>
<span data-ttu-id="e77f8-159">无法准备网络可能会导致用户不满意，并需要临时修复费用。</span><span class="sxs-lookup"><span data-stu-id="e77f8-159">Failing to prepare your network will likely lead to dissatisfied users and costly, ad-hoc fixes.</span></span> <span data-ttu-id="e77f8-160">为 Teams 准备你的网络和你的组织，可以大幅提高成功的机会。</span><span class="sxs-lookup"><span data-stu-id="e77f8-160">By preparing your network—and your organization—for Teams, you can dramatically increase your chance of success.</span></span>

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a><span data-ttu-id="e77f8-161">带宽规划</span><span class="sxs-lookup"><span data-stu-id="e77f8-161">Bandwidth planning</span></span>

<span data-ttu-id="e77f8-162">网络就绪性的第一步是确保你的网络有足够的带宽，可用于 Teams 为用户提供的方式。</span><span class="sxs-lookup"><span data-stu-id="e77f8-162">The first step toward network readiness is ensuring your network has enough bandwidth available for the modalities Teams will provide to users.</span></span> <span data-ttu-id="e77f8-163">规划足够的带宽是一项相当简单的任务，也是一个低屏障的开始，可确保用户获得高质量的 Teams 体验。</span><span class="sxs-lookup"><span data-stu-id="e77f8-163">Planning for sufficient bandwidth is a fairly straightforward task and a very low-barrier start to ensure your users will have a high-quality Teams experience.</span></span>

### <a name="local-internet-egress"></a><span data-ttu-id="e77f8-164">本地 Internet 出口</span><span class="sxs-lookup"><span data-stu-id="e77f8-164">Local internet egress</span></span>

<span data-ttu-id="e77f8-165">许多网络设计为使用中心和辐射型拓扑。</span><span class="sxs-lookup"><span data-stu-id="e77f8-165">Many networks were designed to use a hub and spoke topology.</span></span> <span data-ttu-id="e77f8-166">在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。</span><span class="sxs-lookup"><span data-stu-id="e77f8-166">In this topology, internet traffic typically traverses the WAN to a central datacenter before it emerges (egresses) to the internet.</span></span> <span data-ttu-id="e77f8-167">通常，这么做事为了集中网络安全设备，目的是降低总成本。</span><span class="sxs-lookup"><span data-stu-id="e77f8-167">Often, this is done to centralize network security devices with the goal of reducing overall cost.</span></span>

<span data-ttu-id="e77f8-168">经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="e77f8-168">Back-hauling traffic across the WAN increases latency and has a negative impact on quality and the user experience.</span></span> <span data-ttu-id="e77f8-169">由于 Microsoft Teams 在 Microsoft 的大型全球网络上运行，因此通常存在靠近用户的网络对等互连位置。</span><span class="sxs-lookup"><span data-stu-id="e77f8-169">Because Microsoft Teams runs on Microsoft's large global network, there's often a network peering location close to the user.</span></span> <span data-ttu-id="e77f8-170">用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。</span><span class="sxs-lookup"><span data-stu-id="e77f8-170">A user will most likely get better performance by egressing out of a local internet point close to their location and on to our voice-optimized network as soon as possible.</span></span> <span data-ttu-id="e77f8-171">对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。</span><span class="sxs-lookup"><span data-stu-id="e77f8-171">For some workloads, DNS requests are used to send traffic to the nearest front-end server.</span></span> <span data-ttu-id="e77f8-172">在这种情况下，使用本地出口点时，必须搭配使用本地 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="e77f8-172">In such cases, it's important that when using a local egress point, it's paired with local DNS resolution.</span></span>

<span data-ttu-id="e77f8-173">优化 Microsoft 全球网络的网络路径将提高性能，并最终为用户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="e77f8-173">Optimizing the network path to Microsoft's global network will improve performance and ultimately provide the best experience for users.</span></span> <span data-ttu-id="e77f8-174">有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。</span><span class="sxs-lookup"><span data-stu-id="e77f8-174">For more detail, see the blog post [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

### <a name="vpn"></a><span data-ttu-id="e77f8-175">VPN</span><span class="sxs-lookup"><span data-stu-id="e77f8-175">VPN</span></span>

<span data-ttu-id="e77f8-176">VPN 为许多组织提供很有用的服务。</span><span class="sxs-lookup"><span data-stu-id="e77f8-176">VPNs provide a valuable service to many organizations.</span></span> <span data-ttu-id="e77f8-177">遗憾的是，它们通常未设计为或配置为支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="e77f8-177">Unfortunately, they're typically not designed or configured to support real-time media.</span></span> <span data-ttu-id="e77f8-178">一些 VPN 可能还不支持 UDP。</span><span class="sxs-lookup"><span data-stu-id="e77f8-178">Some VPNs might also not support UDP.</span></span> <span data-ttu-id="e77f8-179">VPN 还会在已加密的媒体流量上引入额外的加密层。</span><span class="sxs-lookup"><span data-stu-id="e77f8-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span> <span data-ttu-id="e77f8-180">此外，由于通过 VPN 设备将流量固定在一起，因此与 Teams 服务的连接可能不太高效。</span><span class="sxs-lookup"><span data-stu-id="e77f8-180">In addition, connectivity to the Teams service might not be efficient due to hair-pinning traffic through a VPN device.</span></span>
<span data-ttu-id="e77f8-181">此外，它们不一定从容量角度设计，以适应 Teams 需要的预期负载。</span><span class="sxs-lookup"><span data-stu-id="e77f8-181">Furthermore, they aren't necessarily designed from a capacity perspective to accommodate the anticipated loads that Teams will require.</span></span>

<span data-ttu-id="e77f8-182">建议提供一个备用路径，以便 Teams 流量绕过 VPN。</span><span class="sxs-lookup"><span data-stu-id="e77f8-182">The recommendation is to provide an alternate path that bypasses the VPN for Teams traffic.</span></span> <span data-ttu-id="e77f8-183">这通常称为 *拆分隧道 VPN。*</span><span class="sxs-lookup"><span data-stu-id="e77f8-183">This is commonly known as *split-tunnel VPN*.</span></span> <span data-ttu-id="e77f8-184">拆分隧道意味着 Microsoft 365 或 Office 365 的流量不会遍历 VPN，而是直接转到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e77f8-184">Split tunneling means that traffic for Microsoft 365 or Office 365 won't traverse the VPN but will go directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e77f8-185">此更改将对质量产生积极的影响，但也提供从 VPN 设备和组织网络减少负载的次要优势。</span><span class="sxs-lookup"><span data-stu-id="e77f8-185">This change will have a positive impact on quality, but also provides the secondary benefit of reducing load from the VPN devices and the organization's network.</span></span>

<span data-ttu-id="e77f8-186">要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="e77f8-186">To implement a split-tunnel, consult with your VPN vendor for the configuration details.</span></span>

### <a name="wi-fi"></a><span data-ttu-id="e77f8-187">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e77f8-187">Wi-Fi</span></span>

<span data-ttu-id="e77f8-188">与 VPN 一样，Wi-Fi网络不一定设计为或配置为支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="e77f8-188">Like VPN, Wi-Fi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="e77f8-189">规划或优化支持 Teams Wi-Fi是高质量部署的一个重要考虑因素。</span><span class="sxs-lookup"><span data-stu-id="e77f8-189">Planning for, or optimizing, a Wi-Fi network to support Teams is an important consideration for a high-quality deployment.</span></span>

<span data-ttu-id="e77f8-190">优化网络网络有几个因素Wi-Fi因素：</span><span class="sxs-lookup"><span data-stu-id="e77f8-190">There are several factors that come into play for optimizing a Wi-Fi network:</span></span>

-   <span data-ttu-id="e77f8-191">实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。</span><span class="sxs-lookup"><span data-stu-id="e77f8-191">Implementing QoS or Wi-Fi Multimedia (WMM) to ensure that media traffic is getting prioritized accordingly over the Wi-Fi networks.</span></span>

-   <span data-ttu-id="e77f8-192">规划和优化Wi-Fi和接入点位置。</span><span class="sxs-lookup"><span data-stu-id="e77f8-192">Planning and optimizing the Wi-Fi bands and access point placement.</span></span> <span data-ttu-id="e77f8-193">2.4 GHz 范围可以根据接入点位置提供合乎需要的体验，但接入点通常受该范围内运行的使用者其他设备的影响。</span><span class="sxs-lookup"><span data-stu-id="e77f8-193">The 2.4 GHz range may provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="e77f8-194">5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="e77f8-194">The 5 GHz range is better suited to real-time media due to their dense range but requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="e77f8-195">此外，终结点还需要相应地支持该范围并配置为利用这些频带。</span><span class="sxs-lookup"><span data-stu-id="e77f8-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span>

-   <span data-ttu-id="e77f8-196">如果部署了双Wi-Fi网络，请考虑实施带引导。</span><span class="sxs-lookup"><span data-stu-id="e77f8-196">If dual-band Wi-Fi networks are deployed, consider implementing band steering.</span></span> <span data-ttu-id="e77f8-197">带引导是一种由 Wi-Fi 实现的技术，用于影响双带客户端以使用 5 GHz 范围。</span><span class="sxs-lookup"><span data-stu-id="e77f8-197">Band steering is a technique implemented by Wi-Fi vendors to influence dual-band clients to use the 5 GHz range.</span></span>

-   <span data-ttu-id="e77f8-198">当同一通道的访问点过于靠近时，它们可能会导致信号重叠和意外竞争，从而导致用户体验不佳。</span><span class="sxs-lookup"><span data-stu-id="e77f8-198">When access points of the same channel are too close together they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="e77f8-199">确保彼此旁边的访问点位于不重叠的通道上。</span><span class="sxs-lookup"><span data-stu-id="e77f8-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span>

<span data-ttu-id="e77f8-200">每个无线供应商都有自己的无线解决方案部署建议。</span><span class="sxs-lookup"><span data-stu-id="e77f8-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="e77f8-201">建议你咨询你的供应商了解具体指导。</span><span class="sxs-lookup"><span data-stu-id="e77f8-201">We recommend that you consult your vendor for specific guidance.</span></span>

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a><span data-ttu-id="e77f8-202">防火墙和代理要求</span><span class="sxs-lookup"><span data-stu-id="e77f8-202">Firewall and proxy requirements</span></span>

<span data-ttu-id="e77f8-203">Microsoft Teams 连接到 Microsoft Online Services并需要 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="e77f8-203">Microsoft Teams connects to Microsoft Online Services and needs internet connectivity for this.</span></span> <span data-ttu-id="e77f8-204">若要让 Teams 正常运行，必须打开从客户端到 Internet 的 TCP 端口 80 和 443，以及从客户端到 Internet 的 UDP 端口 3478 到 3481。</span><span class="sxs-lookup"><span data-stu-id="e77f8-204">For Teams to function correctly, you must open TCP ports 80 and 443 from the clients to the internet, and UDP ports 3478 through 3481 from the clients to the internet.</span></span> <span data-ttu-id="e77f8-205">TCP 端口用于连接到基于 Web 的内容，例如 SharePoint Online、Exchange Online 和 Teams 聊天服务。</span><span class="sxs-lookup"><span data-stu-id="e77f8-205">The TCP ports are used to connect to web-based content such as SharePoint Online, Exchange Online, and the Teams Chat services.</span></span>
<span data-ttu-id="e77f8-206">插件和连接器还通过这些 TCP 端口进行连接。</span><span class="sxs-lookup"><span data-stu-id="e77f8-206">Plug-ins and connectors also connect over these TCP ports.</span></span> <span data-ttu-id="e77f8-207">四个 UDP 端口用于音频和视频等媒体，以确保它们正常运行。</span><span class="sxs-lookup"><span data-stu-id="e77f8-207">The four UDP ports are used for media such as audio and video, to ensure they flow correctly.</span></span>

<span data-ttu-id="e77f8-208">打开这些端口对于可靠的 Teams 部署至关重要。</span><span class="sxs-lookup"><span data-stu-id="e77f8-208">Opening these ports is essential for a reliable Teams deployment.</span></span> <span data-ttu-id="e77f8-209">阻止这些端口不受支持，并且将影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="e77f8-209">Blocking these ports is unsupported and will have an effect on media quality.</span></span>

<span data-ttu-id="e77f8-210">如果组织要求指定要打开这些端口的确切 IP 地址范围和域，可以限制这些端口的目标 IP 范围和域。</span><span class="sxs-lookup"><span data-stu-id="e77f8-210">If your organization requires that you specify the exact IP address ranges and domains to which these ports should be opened, you can restrict the target IP ranges and domains for these ports.</span></span> <span data-ttu-id="e77f8-211">有关确切端口、协议和 IP 范围的列表，请参阅 [Microsoft 365 或 Office 365 URL 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。</span><span class="sxs-lookup"><span data-stu-id="e77f8-211">For a list of exact ports, protocols, and IP ranges, see [Microsoft 365 or Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).</span></span>
<span data-ttu-id="e77f8-212">如果选择限制目标 IP 地址范围和域，必须确保端口和范围列表保持最新，因为它们可能会更改。</span><span class="sxs-lookup"><span data-stu-id="e77f8-212">If you choose to restrict the target IP address ranges and domains, you must ensure that you keep the list of ports and ranges up to date because they might change.</span></span> <span data-ttu-id="e77f8-213">您可以订阅此 [RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301) ，以在发生更改时进行更新。</span><span class="sxs-lookup"><span data-stu-id="e77f8-213">You can subscribe to [this RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) to be updated when changes occur.</span></span> <span data-ttu-id="e77f8-214">此外，通过定期运行 [Skype for Business](https://www.microsoft.com/download/details.aspx?id=53885) 网络评估工具来测试是否打开所有端口也是一个不错的做法。</span><span class="sxs-lookup"><span data-stu-id="e77f8-214">It's also a good practice to test whether all ports are opened by running the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) on a regular basis.</span></span> <span data-ttu-id="e77f8-215">可以在下一部分中详细了解此工具的功能。</span><span class="sxs-lookup"><span data-stu-id="e77f8-215">You can find out more about the functionality of this tool in the next section.</span></span>

<span data-ttu-id="e77f8-216">部署代理服务器时，建议绕过所有 Teams 服务的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="e77f8-216">In the event of a proxy server being deployed, we recommend that you bypass the proxy server for all Teams services.</span></span> <span data-ttu-id="e77f8-217">尽管使用代理可能正常工作，但由于媒体被强制使用 TCP 而不是 UDP，质量很可能降低。</span><span class="sxs-lookup"><span data-stu-id="e77f8-217">Although using a proxy might work, it's very likely that quality will be reduced due to media being forced to use TCP instead of UDP.</span></span> <span data-ttu-id="e77f8-218">有关代理服务器和绕过功能的信息，请参阅 Microsoft [365 或 Office 365 URL 和 IP 地址范围](./office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="e77f8-218">For more information about proxy servers and bypassing, see [Microsoft 365 or Office 365 URLs and IP address ranges](./office-365-urls-ip-address-ranges.md).</span></span>

<!--ENDOFSECTION-->

## <a name="test-the-network"></a><span data-ttu-id="e77f8-219">测试网络</span><span class="sxs-lookup"><span data-stu-id="e77f8-219">Test the network</span></span>

<span data-ttu-id="e77f8-220">完成规划和网络准备（包括升级带宽和在防火墙中打开端口）后，应测试网络的性能。</span><span class="sxs-lookup"><span data-stu-id="e77f8-220">After you've completed your planning and network preparation—including upgrading bandwidth and opening ports in the firewall—you should test your network's performance.</span></span> <span data-ttu-id="e77f8-221">此测试的结果将更清晰地显示音频会议或电话系统成功实施呼叫计划所需的任何网络优化或修正。</span><span class="sxs-lookup"><span data-stu-id="e77f8-221">The results of this testing will paint a clearer picture of any network optimization or remediation required for the success of your Audio Conferencing or Phone System with Calling Plan implementation.</span></span>

<span data-ttu-id="e77f8-222">你可以下载 [Skype for Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885) ，以测试你的网络是否已准备好供 Teams 使用。</span><span class="sxs-lookup"><span data-stu-id="e77f8-222">You can download the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span> <span data-ttu-id="e77f8-223">该工具提供双重功能：它可以测试是否已打开所有正确的端口，并且可以测试网络障碍。</span><span class="sxs-lookup"><span data-stu-id="e77f8-223">The tool offers dual functionality: it can test whether all the correct ports have been opened, and it can test for network impairments.</span></span>

<span data-ttu-id="e77f8-224">下载并安装该工具后，可在 C： Program Files \\ Microsoft \\ Skype for Business Network Assessment Tool（程序文件 Microsoft Skype for Business 网络评估工具）中查找该工具。</span><span class="sxs-lookup"><span data-stu-id="e77f8-224">After you download and install the tool, you can find it in C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool.</span></span> <span data-ttu-id="e77f8-225">该目录中包含有关如何使用该工具的详细Usage.docx，例如，</span><span class="sxs-lookup"><span data-stu-id="e77f8-225">A detailed guide for how to use the tool, Usage.docx, is included in that directory.</span></span>

### <a name="test-for-opened-ports"></a><span data-ttu-id="e77f8-226">测试打开的端口</span><span class="sxs-lookup"><span data-stu-id="e77f8-226">Test for opened ports</span></span>

<span data-ttu-id="e77f8-227">打开命令提示符窗口，并输入 cd C： Program Files Microsoft Skype for Business Network Assessment Tool 导航到网络评估 **\\ \\ 工具目录**。</span><span class="sxs-lookup"><span data-stu-id="e77f8-227">Open a Command prompt window and navigate to the Network Assessment Tool directory by entering **cd C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool**.</span></span> <span data-ttu-id="e77f8-228">在命令提示符下，输入 **/connectivitychecknetworkassessmenttool.exe打开的端口**</span><span class="sxs-lookup"><span data-stu-id="e77f8-228">At the command prompt, start the test for opened ports by entering **networkassessmenttool.exe /connectivitycheck**</span></span>

<span data-ttu-id="e77f8-229">运行检查后，该工具会显示消息"验证已成功完成"或报告已阻止的端口。</span><span class="sxs-lookup"><span data-stu-id="e77f8-229">After running the checks, the tool will either display the message "Verifications Completed Successfully" or report on the ports that were blocked.</span></span>
<span data-ttu-id="e77f8-230">它还生成名为 Connectivity_results.txt 的文件，其中包含该工具的输出，并存储在 %userprofile% appdata 本地 \\ Microsoft skype for business \\ \\ 网络评估工具 \\ 目录中。</span><span class="sxs-lookup"><span data-stu-id="e77f8-230">It also generates a file named Connectivity_results.txt, which contains the output from the tool and stores it in the %userprofile%\\appdata\\local\\microsoft skype for business network assessment tool\\ directory.</span></span>

<span data-ttu-id="e77f8-231">建议定期运行连接检查，确保端口已打开且正常运行。</span><span class="sxs-lookup"><span data-stu-id="e77f8-231">We recommend that you run the connectivity checks on a regular basis to ensure the ports have been opened and are functioning correctly.</span></span>

### <a name="test-for-network-impairments"></a><span data-ttu-id="e77f8-232">网络障碍测试</span><span class="sxs-lookup"><span data-stu-id="e77f8-232">Test for network impairments</span></span>

<span data-ttu-id="e77f8-233">若要提高用户满意度，应限制网络的任何障碍。</span><span class="sxs-lookup"><span data-stu-id="e77f8-233">To increase user satisfaction, you should limit any impairments on your network.</span></span>
<span data-ttu-id="e77f8-234">最常见的网络障碍是延迟 (延迟) 丢包和抖动：</span><span class="sxs-lookup"><span data-stu-id="e77f8-234">The most common network impairments are delay (latency), packet loss, and jitter:</span></span>

-   <span data-ttu-id="e77f8-235">**延迟：** 这是从网络上的点 A 到点 B 获取 IP 数据包所花的时间。</span><span class="sxs-lookup"><span data-stu-id="e77f8-235">**Latency:** This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="e77f8-236">此网络传播延迟实质上与两个点之间的物理距离和光速有关，包括介于两者之间的各种路由器所增加的开销。</span><span class="sxs-lookup"><span data-stu-id="e77f8-236">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span>
    <span data-ttu-id="e77f8-237">延迟以单向或往返时间度量。</span><span class="sxs-lookup"><span data-stu-id="e77f8-237">Latency is measured as one-way or round-trip time.</span></span>

-   <span data-ttu-id="e77f8-238">**数据包** 丢失：这通常定义为给定时间窗口中丢失的数据包的百分比。</span><span class="sxs-lookup"><span data-stu-id="e77f8-238">**Packet loss**: This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="e77f8-239">数据包丢失直接影响音频质量 - 从小型、单个丢失的数据包到导致音频完全中断的背对回突发丢失几乎没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="e77f8-239">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact to back-to-back burst losses that cause audio to cut out completely.</span></span>

-   <span data-ttu-id="e77f8-240">**数据包间到达抖动，或只是抖动：** 这是连续数据包之间的延迟的平均变化。</span><span class="sxs-lookup"><span data-stu-id="e77f8-240">**Inter-packet arrival jitter, or simply jitter:** This is the average change in delay between successive packets.</span></span> <span data-ttu-id="e77f8-241">大多数现代 VoIP 软件（包括 Skype for Business）可以通过缓冲来适应某些级别的抖动。</span><span class="sxs-lookup"><span data-stu-id="e77f8-241">Most modern VoIP software, including Skype for Business, can adapt to some levels of jitter through buffering.</span></span> <span data-ttu-id="e77f8-242">只有当抖动超过缓冲时，参与者才能注意到抖动的影响。</span><span class="sxs-lookup"><span data-stu-id="e77f8-242">It's only when the jitter exceeds the buffering that a participant will notice the effects of jitter.</span></span>

<span data-ttu-id="e77f8-243">媒体质量和网络连接性能中介绍了这些障碍 [的最大值](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。</span><span class="sxs-lookup"><span data-stu-id="e77f8-243">The maximum values for these impairments are described in [Media quality and network connectivity performance](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>
<span data-ttu-id="e77f8-244">在测试这些障碍时，我们会区分两个单独的段：</span><span class="sxs-lookup"><span data-stu-id="e77f8-244">When testing for these impairments, we distinguish between two separate segments:</span></span>

-   <span data-ttu-id="e77f8-245">*边缘段* 是路由器所位于的网段。</span><span class="sxs-lookup"><span data-stu-id="e77f8-245">The *edge segment* is the segment in which your router lives.</span></span> <span data-ttu-id="e77f8-246">这是连接到每个位置的 Internet 的最近逻辑网络段。</span><span class="sxs-lookup"><span data-stu-id="e77f8-246">This is the closest logical network segment connected to the internet at each of your locations.</span></span> <span data-ttu-id="e77f8-247">在大多数情况下，这是路由器的连接点，也可能是外围网络 (外围网络，也称为 *外围* 网络、外围安全区域以及屏蔽) 。  </span><span class="sxs-lookup"><span data-stu-id="e77f8-247">In most cases, this is the connection point of the router, or possibly a perimeter network (also known as *DMZ*, *demilitarized zone*, and *screened subnet*).</span></span> <span data-ttu-id="e77f8-248">此网段和 Internet 之间不应出现影响路由器外的其他设备的流量。</span><span class="sxs-lookup"><span data-stu-id="e77f8-248">No further traffic that affects devices other than the router should occur between this segment and the internet.</span></span>

-   <span data-ttu-id="e77f8-249">*客户端段* 是客户端所在的逻辑网络段。</span><span class="sxs-lookup"><span data-stu-id="e77f8-249">The *client segment* is the logical network segment in which your clients reside.</span></span>

<span data-ttu-id="e77f8-250">应该使用网络评估工具测试这两个段。</span><span class="sxs-lookup"><span data-stu-id="e77f8-250">You should test both segments by using the Network Assessment Tool.</span></span> <span data-ttu-id="e77f8-251">若要测试段，请导航到目录，并在命令 **networkassessmenttool.exe** 输入命令。</span><span class="sxs-lookup"><span data-stu-id="e77f8-251">To test the segment, navigate to the directory and enter **networkassessmenttool.exe** at the command prompt.</span></span> <span data-ttu-id="e77f8-252">结果将写入名为 Results.tsv 的文件，你可以将它们与 [每个段的要求](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 进行比较。</span><span class="sxs-lookup"><span data-stu-id="e77f8-252">The results are written to a file named Results.tsv, and you can compare them to the [requirements](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) for each segment.</span></span>

<span data-ttu-id="e77f8-253">请注意，这两个段必须满足高质量部署的要求。</span><span class="sxs-lookup"><span data-stu-id="e77f8-253">Note that both segments must meet the requirements for a high-quality deployment.</span></span> <span data-ttu-id="e77f8-254">建议直接在一小时内多次运行该工具，以良好地指示网络性能。</span><span class="sxs-lookup"><span data-stu-id="e77f8-254">We recommend that you run the tool multiple times for one hour straight to get a good indication of your network's performance.</span></span>

<!--ENDOFSECTION-->

## <a name="network-remediation"></a><span data-ttu-id="e77f8-255">网络修正</span><span class="sxs-lookup"><span data-stu-id="e77f8-255">Network remediation</span></span>

<span data-ttu-id="e77f8-256">如果带宽规划、端口测试或网络要求测试结果显示，在部署 Teams 之前，当前网络需要修正，则可通过多种方式实现此目的：</span><span class="sxs-lookup"><span data-stu-id="e77f8-256">If the results of bandwidth planning, port testing, or network requirements testing show that your current network needs remediation before you deploy Teams, you can accomplish this in several ways:</span></span>

-   <span data-ttu-id="e77f8-257">如果带宽不足，请升级连接，以便流向 Microsoft 365 或 Office 365 的流量不受阻碍。</span><span class="sxs-lookup"><span data-stu-id="e77f8-257">For insufficient bandwidth, upgrade connections so that traffic to Microsoft 365 or Office 365 can flow unhindered.</span></span>

-   <span data-ttu-id="e77f8-258">对于阻止的端口，请更改防火墙规则，然后重新测试端口。</span><span class="sxs-lookup"><span data-stu-id="e77f8-258">For blocked ports, change firewall rules and retest the ports.</span></span>

-   <span data-ttu-id="e77f8-259">对于网络障碍，请始终执行根本原因分析。</span><span class="sxs-lookup"><span data-stu-id="e77f8-259">For network impairments, always perform a root-cause analysis.</span></span>

<span data-ttu-id="e77f8-260">QoS (服务质量) 优先和分隔流量，从而解决障碍。</span><span class="sxs-lookup"><span data-stu-id="e77f8-260">Quality of service (QoS) can be used to battle impairments by prioritizing and separating traffic.</span></span> <span data-ttu-id="e77f8-261">某些组织选择部署 QoS 来克服带宽问题或限制流量流动量。</span><span class="sxs-lookup"><span data-stu-id="e77f8-261">Some organizations choose to deploy QoS to overcome bandwidth issues or restrict the amount of traffic flowing.</span></span> <span data-ttu-id="e77f8-262">这不会提高质量，也会导致新问题。</span><span class="sxs-lookup"><span data-stu-id="e77f8-262">This won't improve quality and will lead to new problems.</span></span> <span data-ttu-id="e77f8-263">当网络障碍超过要求时，应始终执行根本原因分析。</span><span class="sxs-lookup"><span data-stu-id="e77f8-263">A root-cause analysis should always be performed when network impairments exceed requirements.</span></span> <span data-ttu-id="e77f8-264">QoS 可以是一种解决方案。</span><span class="sxs-lookup"><span data-stu-id="e77f8-264">QoS can be a solution.</span></span>
<span data-ttu-id="e77f8-265">有关详细信息，请参阅 [Microsoft Teams 中的服务质量](./qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e77f8-265">For more information, see [Quality of Service in Microsoft Teams](./qos-in-teams.md).</span></span>

>[!NOTE]
><span data-ttu-id="e77f8-266">许多网络会由于升级、扩展或其他业务要求而逐渐发展。</span><span class="sxs-lookup"><span data-stu-id="e77f8-266">Many networks evolve over time due to upgrades, expansion, or other business requirements.</span></span> <span data-ttu-id="e77f8-267">请确保在你的服务管理规划中具有可操作的流程以维护这些方面。</span><span class="sxs-lookup"><span data-stu-id="e77f8-267">Ensure that you have operational processes in place to maintain these areas as part of your service management planning.</span></span>


<table>
<tr><td><span data-ttu-id="e77f8-268">标题</span><span class="sxs-lookup"><span data-stu-id="e77f8-268">Title</span></span></td><td><span data-ttu-id="e77f8-269">描述</span><span class="sxs-lookup"><span data-stu-id="e77f8-269">Description</span></span></td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="e77f8-270">决策点</span><span class="sxs-lookup"><span data-stu-id="e77f8-270">Decision points</span></span></td><td><ul><li><span data-ttu-id="e77f8-271">谁负责在所有网段和组织位置完成适当的网络评估？</span><span class="sxs-lookup"><span data-stu-id="e77f8-271">Who will be responsible for completing proper network assessments across all network segments and organization locations?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="e77f8-272">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e77f8-272">Next steps</span></span></td><td><ul><li><span data-ttu-id="e77f8-273">可以执行详细的网络评估，帮助确保网络已准备好进行 Microsoft Teams 部署。</span><span class="sxs-lookup"><span data-stu-id="e77f8-273">You can perform a detailed network assessment to help ensure your network is ready for your Microsoft Teams deployment.</span></span></li><li><span data-ttu-id="e77f8-274">根据每个网络段的评估结果执行网络修正。</span><span class="sxs-lookup"><span data-stu-id="e77f8-274">Perform network remediation based on the results of the assessment for every network segment.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->