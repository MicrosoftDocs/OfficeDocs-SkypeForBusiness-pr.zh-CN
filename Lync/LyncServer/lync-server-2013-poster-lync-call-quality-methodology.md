---
title: Lync Server 2013：海报： Lync 呼叫质量方法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 849e74fb4857dd7b3ab98b8a8efd9c3ce3781e35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a><span data-ttu-id="977da-102">Lync Server 2013 中的 lync 呼叫质量方法</span><span class="sxs-lookup"><span data-stu-id="977da-102">Lync Call Quality Methodology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="977da-103">_**上次修改的主题：** 2016-06-24_</span><span class="sxs-lookup"><span data-stu-id="977da-103">_**Topic Last Modified:** 2016-06-24_</span></span>

<span data-ttu-id="977da-104">本文是[Lync 呼叫质量方法](http://go.microsoft.com/fwlink/?linkid=391841)海报的附带，可以从下载中心下载。</span><span class="sxs-lookup"><span data-stu-id="977da-104">This article is a companion to the [Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="977da-105">![描述 CQM 过程的海报](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "描述 CQM 过程的海报")</span><span class="sxs-lookup"><span data-stu-id="977da-105">![Poster describing the CQM process](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster describing the CQM process")</span></span>

<span data-ttu-id="977da-106">您可以使用此海报了解 CQM、Lync 2013 和2010的呼叫质量方法，可帮助您查找并消除影响包含企业语音功能的 Lync 实现的呼叫质量和用户体验的问题。</span><span class="sxs-lookup"><span data-stu-id="977da-106">You can use this poster to learn about CQM, the Call Quality Methodology for Lync 2013 and 2010 that helps you find and eliminate issues affecting call quality and user experience for Lync implementations that include enterprise voice features.</span></span> <span data-ttu-id="977da-107">呼叫质量方法是一种新的故障排除和服务管理框架，可以更好地集中精力改进 Lync 中的企业语音服务。</span><span class="sxs-lookup"><span data-stu-id="977da-107">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="977da-108">在本文中，您可以详细了解 CQM、所监视的服务器和解决方案的种类，以及如何处理所收集的遥测数据。</span><span class="sxs-lookup"><span data-stu-id="977da-108">In this article, you can learn more about CQM, the kinds of servers and solutions that are monitored, and what to do with the collected telemetry data.</span></span>

<span data-ttu-id="977da-109">如果您对如何使用 CQM 有疑问，可以将问题提交到 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="977da-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="977da-110">海报对以下方面进行了说明：</span><span class="sxs-lookup"><span data-stu-id="977da-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="977da-111">什么是 Lync CQM？</span><span class="sxs-lookup"><span data-stu-id="977da-111">What is Lync CQM?</span></span>

  - <span data-ttu-id="977da-112">优先顺序：运行趋势查询</span><span class="sxs-lookup"><span data-stu-id="977da-112">Prioritize: Run Trending Queries</span></span>

  - <span data-ttu-id="977da-113">PCD</span><span class="sxs-lookup"><span data-stu-id="977da-113">PCD</span></span>

  - <span data-ttu-id="977da-114">托管/非托管</span><span class="sxs-lookup"><span data-stu-id="977da-114">Managed/Unmanaged</span></span>

  - <span data-ttu-id="977da-115">服务器植物道路</span><span class="sxs-lookup"><span data-stu-id="977da-115">The Server Plant Road</span></span>

  - <span data-ttu-id="977da-116">最后一英里路</span><span class="sxs-lookup"><span data-stu-id="977da-116">The Last Mile Road</span></span>

  - <span data-ttu-id="977da-117">终结点道路</span><span class="sxs-lookup"><span data-stu-id="977da-117">The End Points Road</span></span>

  - <span data-ttu-id="977da-118">服务管理</span><span class="sxs-lookup"><span data-stu-id="977da-118">Service Management</span></span>

  - <span data-ttu-id="977da-119">董事会游戏规则</span><span class="sxs-lookup"><span data-stu-id="977da-119">Board Game Rules</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a><span data-ttu-id="977da-120">什么是 Lync CQM？</span><span class="sxs-lookup"><span data-stu-id="977da-120">What is Lync CQM?</span></span>

<span data-ttu-id="977da-121">呼叫质量方法是一种新的故障排除和服务管理框架，可以更好地集中精力改进 Lync 中的企业语音服务。</span><span class="sxs-lookup"><span data-stu-id="977da-121">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="977da-122">当您使用 CQM 时，需要付出的精力更少，以确保呼叫质量和用户对企业语音服务的满意度。</span><span class="sxs-lookup"><span data-stu-id="977da-122">When you use CQM, less effort is needed to assure call quality and user satisfaction for enterprise voice services.</span></span> <span data-ttu-id="977da-123">在[通话质量方法](http://go.microsoft.com/fwlink/p/?linkid=615208)中，CQM 更全面地说明。</span><span class="sxs-lookup"><span data-stu-id="977da-123">CQM is more fully explained in the [Call Quality Methodology](http://go.microsoft.com/fwlink/p/?linkid=615208).</span></span> <span data-ttu-id="977da-124">本文和海报是这些内容的摘要。</span><span class="sxs-lookup"><span data-stu-id="977da-124">This article and the poster are summaries of that content.</span></span>

<span data-ttu-id="977da-125">CQM 将系统故障排除分解为三个路径或 "道路"。</span><span class="sxs-lookup"><span data-stu-id="977da-125">CQM breaks down System troubleshooting into three paths or “Roads.”</span></span> <span data-ttu-id="977da-126">这些是：服务器植物道路，它看起来是服务器和它们之间的链接、结束点线，它看起来是用户设备和用于拨打呼叫的媒体，最后是一次英里路，可解决传统交换电话网络呼叫的集成。</span><span class="sxs-lookup"><span data-stu-id="977da-126">These are: the Server Plant Road, which looks at the servers and the links between them, the End Points Road, which looks at user devices and media used to carry calls, and the Last Mile Road, which addresses integration of traditional switched telephone network calls.</span></span>

<span data-ttu-id="977da-127">每个道路分成多个与特定区域或主题相关的段，并在每个段定义中建立了什么是可接受的质量级别，执行操作以实现该质量级别，并实施服务管理计划以保持该质量级别，然后再转到下一主题。</span><span class="sxs-lookup"><span data-stu-id="977da-127">Each Road is divided into several segments relating to a specific area or topic, and at each segment definitions are made about what is an acceptable quality level, actions are taken to achieve that quality level, and a service management plan is put in place to maintain that quality level before moving on to the next topic.</span></span>

<span data-ttu-id="977da-128">海报将 Lync CQM 作为一局游戏提供给三个玩家，每个玩家都会经历一条道路。</span><span class="sxs-lookup"><span data-stu-id="977da-128">The poster presents Lync CQM as a board game for three players, each of whom will go through one of the roads.</span></span> <span data-ttu-id="977da-129">下载中附带的卡片用于模拟必须克服的呼叫质量障碍。</span><span class="sxs-lookup"><span data-stu-id="977da-129">Cards included with the download are used to simulate impediments to call quality that must be overcome.</span></span> <span data-ttu-id="977da-130">有关目标和如何实现它们的提示和建议包括在三个路径中，以及确定在实际应用程序中首先推荐的道路的优先级准则（在游戏中，所有三个道路都以并行方式解决）。</span><span class="sxs-lookup"><span data-stu-id="977da-130">Hints and suggestions about targets and how to achieve them are included along the three paths, as well as prioritization guidelines for which road to pursue first in actual applications (in the game, all three roads are addressed in parallel).</span></span>

<span data-ttu-id="977da-131">CQM 在早期版本的 Lync 中如何工作？</span><span class="sxs-lookup"><span data-stu-id="977da-131">How does CQM work in earlier versions of Lync?</span></span> <span data-ttu-id="977da-132">CQM 是 Lync 2013 的新版，但其中的大部分可适应与 Lync 2010 一起使用。</span><span class="sxs-lookup"><span data-stu-id="977da-132">CQM is new for Lync 2013, but most of it can be adapted to be used with Lync 2010.</span></span> <span data-ttu-id="977da-133">CQM 可能会对 Microsoft Office Communicator 有一定程度的作用，但此操作未经测试且不受支持。</span><span class="sxs-lookup"><span data-stu-id="977da-133">CQM may work to a degree with Microsoft Office Communicator, but this is untested and not supported.</span></span>

<span data-ttu-id="977da-134">如果您对如何使用 CQM 有疑问，可以将问题提交到 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="977da-134">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a><span data-ttu-id="977da-135">优先顺序：运行趋势查询</span><span class="sxs-lookup"><span data-stu-id="977da-135">Prioritize: Run Trending Queries</span></span>

<span data-ttu-id="977da-136">CQM 中的第一步是运行两周的每个趋势查询，然后分析结果。</span><span class="sxs-lookup"><span data-stu-id="977da-136">The first step in CQM is to run each of the trending queries for two weeks and then analyze the results.</span></span> <span data-ttu-id="977da-137">按最大流参与者、最高较差的流比率和受管理的区域（您控制的区域）确定纠正措施的优先级。</span><span class="sxs-lookup"><span data-stu-id="977da-137">Prioritize corrective action by the largest stream contributor, the highest poor stream ratio, and managed areas (ones you control).</span></span><span data-ttu-id="977da-138">如果音频/视频多点控制单元（AV MCU）或中介查询显示较差的结果，则从红色或服务器植物路上开始。</span><span class="sxs-lookup"><span data-stu-id="977da-138">  If the Audio/Video Multi-point Control Unit (AV MCU) or Mediation queries show poor results, start on the Red or Server Plant road.</span></span><span data-ttu-id="977da-139">如果有线或无线查询显示较差的结果，则从蓝色或最后一英里路上开始。</span><span class="sxs-lookup"><span data-stu-id="977da-139">  If the Wired or Wireless queries show poor results, start on the Blue or Last Mile road.</span></span><span data-ttu-id="977da-140">如果 VPN 或外部查询显示较差的结果，则从绿色或终结点路上开始。</span><span class="sxs-lookup"><span data-stu-id="977da-140">  If the VPN or External queries show poor results, start on the Green or End Points road.</span></span>

<span data-ttu-id="977da-141">选择开始使用的道路后，为每个区域定义一个目标（断言），工作以满足该目标（实现），然后实施过程以保持目标（维护）。</span><span class="sxs-lookup"><span data-stu-id="977da-141">After you choose a road to start with, define a target for each area (Assert), work to meet that target (Achieve) and then implement procedures to stay on target (Maintain).</span></span> <span data-ttu-id="977da-142">您还可以将此海报用作游戏，以了解 CQM 背后的原则。</span><span class="sxs-lookup"><span data-stu-id="977da-142">You can also use this poster as a game to understand the principles behind CQM.</span></span>

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a><span data-ttu-id="977da-143">PCD</span><span class="sxs-lookup"><span data-stu-id="977da-143">PCD</span></span>

<span data-ttu-id="977da-144">PreCall 诊断工具（PCD）可帮助您识别和诊断外围网络中的问题（QoE 数据库不会收集边缘或外围网络上的信息），还可用于排除最后英里中的连接故障。</span><span class="sxs-lookup"><span data-stu-id="977da-144">The PreCall Diagnostics tool (PCD) will help you identify and diagnose problems in your perimeter network (the QoE database doesn’t collect information on your edge or perimeter network) and also to troubleshoot connections in the Last Mile.</span></span> <span data-ttu-id="977da-145">该工具可作为 Windows 8 新式应用或 Windows 桌面应用程序http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88。</span><span class="sxs-lookup"><span data-stu-id="977da-145">The tool is available as both a Windows 8 Modern App or a Windows Desktop App at http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.</span></span>

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a><span data-ttu-id="977da-146">托管/非托管</span><span class="sxs-lookup"><span data-stu-id="977da-146">Managed/Unmanaged</span></span>

<span data-ttu-id="977da-147">Lync Server 部署和网络基础结构通常可分为托管和非托管空间。</span><span class="sxs-lookup"><span data-stu-id="977da-147">The Lync Server deployment and network infrastructure can usually be divided into managed and unmanaged spaces.</span></span> <span data-ttu-id="977da-148">管理空间包括您的整个内部有线网络和服务器基础结构。</span><span class="sxs-lookup"><span data-stu-id="977da-148">The managed space includes your entire inside wired network and server infrastructure.</span></span> <span data-ttu-id="977da-149">非托管空间是无线基础结构和外部网络基础结构。</span><span class="sxs-lookup"><span data-stu-id="977da-149">The unmanaged space is the wireless infrastructure and the outside network infrastructure.</span></span>

<span data-ttu-id="977da-150">进行这种区分会提高数据的清晰度，并帮助您的组织专注于将对用户的语音和视频质量产生实实在在影响的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="977da-150">Making this distinction increases the clarity of your data and helps your organization focus on workloads that will have a measurable impact on your users’ voice and video quality.</span></span> <span data-ttu-id="977da-151">如果将呼叫置于您拥有（托管）的基础结构上，并且对部分其他实体（非托管）进行控制，则用户具有不同的质量预期。</span><span class="sxs-lookup"><span data-stu-id="977da-151">Users have a different expectation of quality if the call is placed on infrastructure that you own (managed) versus infrastructure that is partly under the control of some other entity (unmanaged).</span></span> <span data-ttu-id="977da-152">这并不意味着无线用户会离开自己的设备，以获得出色的 Lync Server 体验。</span><span class="sxs-lookup"><span data-stu-id="977da-152">This is not to say that wireless users are left to their own devices to have excellent Lync Server experiences.</span></span>

<span data-ttu-id="977da-153">在非托管空间中提高语音质量要求在管理空间中具有高质量。</span><span class="sxs-lookup"><span data-stu-id="977da-153">Improving voice quality in the unmanaged space requires you to have high quality in the managed space.</span></span> <span data-ttu-id="977da-154">无线（Wi-fi）是否被视为托管或非托管空间由您的组织决定。</span><span class="sxs-lookup"><span data-stu-id="977da-154">Whether wireless (Wi-Fi) is considered managed or unmanaged space is up to your organization.</span></span> <span data-ttu-id="977da-155">实现正常运行环境的方法在两个空间中不同，这是解决方案。</span><span class="sxs-lookup"><span data-stu-id="977da-155">The techniques to achieve a healthy environment are different in the two spaces, as are the solutions.</span></span>

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a><span data-ttu-id="977da-156">服务器植物道路</span><span class="sxs-lookup"><span data-stu-id="977da-156">The Server Plant Road</span></span>

<span data-ttu-id="977da-157">服务器植物公路的第1部分解决了 Lync 实施中的实际服务器。</span><span class="sxs-lookup"><span data-stu-id="977da-157">Segment 1 of the Server Plant Road addresses the actual servers in the Lync implementation.</span></span> <span data-ttu-id="977da-158">收集有关服务器本身及其在实施中的角色的 KHI 数据，并分析结果。</span><span class="sxs-lookup"><span data-stu-id="977da-158">Gather KHI data regarding both the server itself and its role in the implementation and analyze the result.</span></span> <span data-ttu-id="977da-159">如果操作是保证的，请更正发现的任何问题。</span><span class="sxs-lookup"><span data-stu-id="977da-159">If action is warranted, correct any problems found.</span></span> <span data-ttu-id="977da-160">有关此主题的更多详细信息，请参阅 KHI 海报随附的[Lync Server 2013 中的关键运行状况指示器](lync-server-2013-poster-key-health-indicators.md)一文。</span><span class="sxs-lookup"><span data-stu-id="977da-160">More detail on this topic is presented in the article about [Key Health Indicators in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) that accompanies the KHI poster.</span></span>

<span data-ttu-id="977da-161">下一段用于解决 AV MCU 服务器和中介服务器之间的媒体流。</span><span class="sxs-lookup"><span data-stu-id="977da-161">The next segment addresses media streams between the AV MCU server and mediation server.</span></span> <span data-ttu-id="977da-162">首先，确定数据流阈值较差的目标。</span><span class="sxs-lookup"><span data-stu-id="977da-162">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="977da-163">较差的流通常\>为 PacketLossRate .01 \>或 PacketLossRateMax。</span><span class="sxs-lookup"><span data-stu-id="977da-163">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="977da-164">另一个理想目标是\< PoorStreamsRatio 2%。</span><span class="sxs-lookup"><span data-stu-id="977da-164">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="977da-165">接下来，使用详细的查询来查找 AVMCU 和中介服务器对，其中包含较差的流、调查不良流的原因、查看较差流路径中的网络设备、修正较差的流以及定义网络的最佳或 "黄金" 配置器械.</span><span class="sxs-lookup"><span data-stu-id="977da-165">Next, use detailed queries to find AVMCU and Mediation server pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="977da-166">若要维护您的成就，请实施流程和工具来管理配置偏移并报告新的问题区域。</span><span class="sxs-lookup"><span data-stu-id="977da-166">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="977da-167">接下来，检查中介服务器和公用电话交换网（PSTN）网关之间的媒体流。</span><span class="sxs-lookup"><span data-stu-id="977da-167">Next, examine the media streams between the Mediation server and the Public Switched Telephone Network (PSTN) gateway.</span></span> <span data-ttu-id="977da-168">首先，确定数据流阈值较差的目标。</span><span class="sxs-lookup"><span data-stu-id="977da-168">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="977da-169">较差的流通常\>为 PacketLossRate .01 \>或 PacketLossRateMax。</span><span class="sxs-lookup"><span data-stu-id="977da-169">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="977da-170">另一个理想目标是\< PoorStreamsRatio 2%。</span><span class="sxs-lookup"><span data-stu-id="977da-170">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="977da-171">接下来，使用详细查询查找具有较差流的中介服务器和网关对，调查不良流的原因、查看较差流路径中的网络设备、修正较差的流和为网络定义最优或 "黄金" 配置器械.</span><span class="sxs-lookup"><span data-stu-id="977da-171">Next, use detailed queries to find Mediation server and gateway pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="977da-172">若要维护您的成就，请实施流程和工具来管理配置偏移并报告新的问题区域。</span><span class="sxs-lookup"><span data-stu-id="977da-172">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="977da-173">最后，检查 PSTN 网关的运行状况指标。</span><span class="sxs-lookup"><span data-stu-id="977da-173">Finally, examine the health metrics for your PSTN gateway.</span></span> <span data-ttu-id="977da-174">确定显示运行状况的统计信息并为其定义目标。</span><span class="sxs-lookup"><span data-stu-id="977da-174">Identify the statistics that show health and define targets against them.</span></span> <span data-ttu-id="977da-175">此处不提供任何特定指导，因为可以使用多个可能的网关。</span><span class="sxs-lookup"><span data-stu-id="977da-175">No specific guidance is provided here as many possible gateways can be used.</span></span> <span data-ttu-id="977da-176">建立目标后，根据需要进行补救以实现目标;在此过程中，您可能会定义网关的 "黄金" 或最佳配置。</span><span class="sxs-lookup"><span data-stu-id="977da-176">Once targets are established, remediate as needed to achieve the target; in the process you will likely define a “gold” or optimal configuration for the gateway.</span></span> <span data-ttu-id="977da-177">若要维护您的成就，请实施流程和工具来管理配置偏移并报告新的问题区域。</span><span class="sxs-lookup"><span data-stu-id="977da-177">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span> <span data-ttu-id="977da-178">请注意，固件和软件更新可能会改变您的配置，或让您更改 "黄金" 配置的定义，因此需要谨慎使用这些活动。</span><span class="sxs-lookup"><span data-stu-id="977da-178">Be aware that firmware and software updates may alter your configuration or lead you to change the definition of the “gold” configuration, so approach these activities with care.</span></span>

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a><span data-ttu-id="977da-179">最后一英里路</span><span class="sxs-lookup"><span data-stu-id="977da-179">The Last Mile Road</span></span>

<span data-ttu-id="977da-180">在客户端连接到网络的两种方式中，有线预期能够提供最高的质量，并且相应的问题必须是最后一个英里问题的初始焦点。</span><span class="sxs-lookup"><span data-stu-id="977da-180">Of the two ways clients connect to the network, wired is expected to deliver the highest quality and correspondingly this must be your initial focus for last mile issues.</span></span> <span data-ttu-id="977da-181">使用 CQM 有线查询（LastMile\_0\_有线）和它所提供的不良流比率数据。</span><span class="sxs-lookup"><span data-stu-id="977da-181">Use the CQM Wired query (LastMile\_0\_Wired) and the Poor Streams ratio data it provides.</span></span> <span data-ttu-id="977da-182">建议为包含\> 300 流的\<网站定义目标 PoorStreamsRatio 5%）。</span><span class="sxs-lookup"><span data-stu-id="977da-182">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="977da-183">若要实现目标，请将从最差订购的子网修正为最佳，并实施 QoS。</span><span class="sxs-lookup"><span data-stu-id="977da-183">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

<span data-ttu-id="977da-184">优化有线连接的质量后，提高无线质量会变得更加轻松，因为无线基础结构在每个位置驻留在有线内核顶部。</span><span class="sxs-lookup"><span data-stu-id="977da-184">After you optimize the quality of your wired connections, improving wireless quality becomes easier because the wireless infrastructure sits atop the wired core at each location.</span></span> <span data-ttu-id="977da-185">具有较好的有线质量的站点中的无线流较差必须具有特定的无线组件。</span><span class="sxs-lookup"><span data-stu-id="977da-185">Poor wireless streams in a site with good wired quality must be attributed to the specific wireless components.</span></span> <span data-ttu-id="977da-186">CQM 无线查询（LastMile\_1\_无线）在某个日期范围内运行，并将从 Lync 客户端到或从会议服务器或中介服务器返回您环境中的所有内部无线流。</span><span class="sxs-lookup"><span data-stu-id="977da-186">The CQM Wireless query (LastMile\_1\_Wireless) operates on a date range and will return all internal wireless streams in your environment from Lync clients to or from either conferencing servers or mediation servers.</span></span> <span data-ttu-id="977da-187">建议为包含\> 300 流的\<网站定义目标 PoorStreamsRatio 5%）。</span><span class="sxs-lookup"><span data-stu-id="977da-187">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="977da-188">若要实现目标，请将从最差订购的子网修正为最佳，并实施 QoS。</span><span class="sxs-lookup"><span data-stu-id="977da-188">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a><span data-ttu-id="977da-189">终结点道路</span><span class="sxs-lookup"><span data-stu-id="977da-189">The End Points Road</span></span>

<span data-ttu-id="977da-190">在与 Lync 配合使用时，可以通过耳机和已知生成可接受质量的其他设备来开始查询终结点道路。</span><span class="sxs-lookup"><span data-stu-id="977da-190">Begin inquiries into the End Points Road with the headsets and other devices known to produce acceptable quality when used with Lync.</span></span> <span data-ttu-id="977da-191">我们建议将目标 AvgSendListen MOS \> 3.6 用于包含100个以上流的实现。通过识别有问题的设备并修复或替换它们来实现目标。</span><span class="sxs-lookup"><span data-stu-id="977da-191">We suggest a target AvgSendListen MOS \> 3.6 for implementations with over 100 streams.) Achieve the target by identifying problematic devices and fix or replace them.</span></span>

<span data-ttu-id="977da-192">接下来，检查设备或电脑处理音频的最终用户呼叫。</span><span class="sxs-lookup"><span data-stu-id="977da-192">Next, examine the device or PC processing the audio for end user calls.</span></span> <span data-ttu-id="977da-193">建议的目标质量指标是 AudioMicGlitchRate \<= 1。</span><span class="sxs-lookup"><span data-stu-id="977da-193">A suggested target quality metric is an AudioMicGlitchRate \<= 1.</span></span> <span data-ttu-id="977da-194">在确定用户系统的最佳系统配置时，请定义包括驱动程序版本的 "黄金" PC 配置。</span><span class="sxs-lookup"><span data-stu-id="977da-194">As you identify optimal system configurations for the user systems, define a “golden” PC configuration including driver versions.</span></span>

<span data-ttu-id="977da-195">现在，检查音频流从 Lync 终结点系统获取的网络路径，这可能会导致音频质量不佳。</span><span class="sxs-lookup"><span data-stu-id="977da-195">Now examine the network path an audio stream takes from a Lync endpoint system, which can cause poor audio quality.</span></span> <span data-ttu-id="977da-196">如果音频通过 VPN 连接，您可能会看到延迟问题。</span><span class="sxs-lookup"><span data-stu-id="977da-196">If audio travels over a VPN connection you might see latency issues.</span></span> <span data-ttu-id="977da-197">如果内部 Lync 客户端无法为两方或对等呼叫的其他内部 Lync 客户端建立直接媒体流，它将回退到通过 Lync Edge 服务器中继的路径，这会导致延迟问题，并增加可能丢失和抖动。</span><span class="sxs-lookup"><span data-stu-id="977da-197">If an internal Lync client cannot establish a direct media stream to another internal Lync client for a two-party or peer-to-peer call, it will fall back to a path that relays through a Lync Edge server, again leading to latency issues as well as increased potential for loss and jitter.</span></span> <span data-ttu-id="977da-198">我们建议你在 VPN 上定义质量指标0% 的媒体。</span><span class="sxs-lookup"><span data-stu-id="977da-198">We suggest you define a quality metric of 0% Media over VPN.</span></span> <span data-ttu-id="977da-199">在您进行修正以实现您设置的目标时，请确定问题子网并调查防火墙规则、数据包 shapers 和其他相关的网络设备配置。</span><span class="sxs-lookup"><span data-stu-id="977da-199">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

<span data-ttu-id="977da-200">IP 数据包可以使用传输控制协议（TCP）或用户数据报协议（UDP）。</span><span class="sxs-lookup"><span data-stu-id="977da-200">IP Packets can use either Transmission Control Protocol (TCP) or User Datagram Protocol (UDP).</span></span> <span data-ttu-id="977da-201">TCP 对于数据流而言是最佳的。</span><span class="sxs-lookup"><span data-stu-id="977da-201">TCP is optimal for data streams.</span></span> <span data-ttu-id="977da-202">UDP 是无连接的，更有效的媒体，因为 TCP 恢复机制无法及时解决实时媒体丢失的情况。</span><span class="sxs-lookup"><span data-stu-id="977da-202">UDP is connectionless and is more efficient for media since TCP recovery mechanisms cannot address loss in real time media.</span></span> <span data-ttu-id="977da-203">Lync 始终首选 UDP，但如果无法建立 UDP 会话，则将还原为 TCP。</span><span class="sxs-lookup"><span data-stu-id="977da-203">Lync always prefers UDP, but will revert to TCP if a UDP session cannot be established.</span></span> <span data-ttu-id="977da-204">通过 TCP 的媒体会话将表现出比通过 UDP 更差的质量。</span><span class="sxs-lookup"><span data-stu-id="977da-204">Media sessions over TCP will exhibit poorer quality than over UDP.</span></span> <span data-ttu-id="977da-205">我们建议通过 TCP 的高质量定义连接0%。</span><span class="sxs-lookup"><span data-stu-id="977da-205">We recommend a quality definition of 0% connections over TCP.</span></span> <span data-ttu-id="977da-206">在您进行修正以实现您设置的目标时，请确定问题子网并调查防火墙规则、数据包 shapers 和其他相关的网络设备配置。</span><span class="sxs-lookup"><span data-stu-id="977da-206">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a><span data-ttu-id="977da-207">服务管理</span><span class="sxs-lookup"><span data-stu-id="977da-207">Service Management</span></span>

<span data-ttu-id="977da-208">服务管理是 CQM 的结束状态和所有三个道路的目标。</span><span class="sxs-lookup"><span data-stu-id="977da-208">Service management is the end state of CQM, and the destination for all three roads.</span></span> <span data-ttu-id="977da-209">若要维护高级别的呼叫质量，请监视以下方面：</span><span class="sxs-lookup"><span data-stu-id="977da-209">To maintain high levels of call quality, monitor these areas:</span></span>

1.  <span data-ttu-id="977da-210">**用户**-补救活动应显示用户满意度的实实在在增长。</span><span class="sxs-lookup"><span data-stu-id="977da-210">**Users** - Remediation activities should show a measurable increase in user satisfaction.</span></span> <span data-ttu-id="977da-211">您可以通过问题票证或其他反馈机制对此进行衡量。</span><span class="sxs-lookup"><span data-stu-id="977da-211">You can measure this by problem tickets or other feedback mechanisms.</span></span> <span data-ttu-id="977da-212">您还可以发布质量指标。</span><span class="sxs-lookup"><span data-stu-id="977da-212">You can also publish quality metrics.</span></span>

2.  <span data-ttu-id="977da-213">**Process** -定义 operationalize CQM 的每日、每周和每月进程。</span><span class="sxs-lookup"><span data-stu-id="977da-213">**Process** - define daily, weekly and monthly processes to operationalize CQM.</span></span> <span data-ttu-id="977da-214">在您进行补救时（每天），监视节奏将以更高的频率启动，并在您趋于稳定时（按月）移动到较低频率。</span><span class="sxs-lookup"><span data-stu-id="977da-214">Monitoring rhythm starts at a higher frequency while you are remediating (daily) and moves to a lower frequency (monthly) as you stabilize.</span></span>

3.  <span data-ttu-id="977da-215">**Tools** -确定用于衡量和修正的工具。</span><span class="sxs-lookup"><span data-stu-id="977da-215">**Tools** - identify tools to both measure and remediate.</span></span> <span data-ttu-id="977da-216">您可能会发现，自动运行 CQM 查询以支持您的过程非常有用。</span><span class="sxs-lookup"><span data-stu-id="977da-216">You may find it useful to automate running the CQM queries to support your processes.</span></span> <span data-ttu-id="977da-217">修正可能需要其他工具，例如，在网络元素上强制实施标准化配置或在不良流中排除丢失问题。</span><span class="sxs-lookup"><span data-stu-id="977da-217">Remediation may require additional tools for example to enforce standardized configurations on network elements or troubleshooting loss in poor streams.</span></span>

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a><span data-ttu-id="977da-218">董事会游戏规则</span><span class="sxs-lookup"><span data-stu-id="977da-218">Board Game Rules</span></span>

<span data-ttu-id="977da-219">您可以使用此海报作为对 CQM 实现的引用或作为一种练习这些概念的游戏。</span><span class="sxs-lookup"><span data-stu-id="977da-219">You can use this poster either as a reference to a CQM implementation or as a game to practice the concepts.</span></span> <span data-ttu-id="977da-220">若要播放，你将需要 1 6 侧骰子和所提供的卡。</span><span class="sxs-lookup"><span data-stu-id="977da-220">To play, you will need one six-sided die and the cards provided.</span></span> <span data-ttu-id="977da-221">可在标准 Avery 5871 名片上进行打印的卡片的可下载版本。</span><span class="sxs-lookup"><span data-stu-id="977da-221">A downloadable version of the cards is available to print on standard Avery 5871 business cards.</span></span>

<span data-ttu-id="977da-222">游戏适用于3个玩家。</span><span class="sxs-lookup"><span data-stu-id="977da-222">The game is for 3 players.</span></span> <span data-ttu-id="977da-223">播放机可使用三种路径达到所需质量并达到中心服务管理状态：服务器工厂、终结点和最后英里。</span><span class="sxs-lookup"><span data-stu-id="977da-223">There are three paths the players can use to achieve the desired quality and reach the center Service Management state: Server Plant, End Point, and Last Mile.</span></span> <span data-ttu-id="977da-224">每个路径在断言质量目标、实现目标和维护系统方面都有停止的方式。</span><span class="sxs-lookup"><span data-stu-id="977da-224">Each path has stops along the way where you Assert quality targets, Achieve goals, and Maintain an aspect of your system.</span></span> <span data-ttu-id="977da-225">将卡片放在上面的指示区域中，然后绘制5张卡片。</span><span class="sxs-lookup"><span data-stu-id="977da-225">Place the cards in the indicated area above, and then draw 5 cards.</span></span> <span data-ttu-id="977da-226">查看已绘制的卡片并将其放在相关的板段上。</span><span class="sxs-lookup"><span data-stu-id="977da-226">Review the cards you’ve drawn and place them on the relevant board segment.</span></span> <span data-ttu-id="977da-227">每个玩家逐步在卡片上移动，断言质量目标，实现这些目标，并维护服务级别。</span><span class="sxs-lookup"><span data-stu-id="977da-227">Each player moves through the cards on their path step by step, asserting quality targets, achieving those targets, and maintaining the service levels.</span></span> <span data-ttu-id="977da-228">当所有玩家都达到中心服务管理状态时，就完成了游戏。</span><span class="sxs-lookup"><span data-stu-id="977da-228">The game is completed when all players reach the center Service Management state.</span></span> <span data-ttu-id="977da-229">游戏卡下载中提供了更详细的规则。</span><span class="sxs-lookup"><span data-stu-id="977da-229">More detailed rules are provided with the game card download.</span></span>

<span data-ttu-id="977da-230">若要**断言**质量目标，请查看适用于该目标的参数，并将所需的内容弄清楚并不能选择接受。</span><span class="sxs-lookup"><span data-stu-id="977da-230">To **Assert** a quality target, review the parameters applicable to that target, and state out loud what you will and won’t choose to accept.</span></span> <span data-ttu-id="977da-231">我们建议的起始点，但您必须进行最后的调用。</span><span class="sxs-lookup"><span data-stu-id="977da-231">We have recommended beginning points, but you must make the final call.</span></span> <span data-ttu-id="977da-232">例外情况是 KHI 数据，应使用 Microsoft 建立的标准。</span><span class="sxs-lookup"><span data-stu-id="977da-232">The exception is KHI data, where the standards established by Microsoft should be used.</span></span> <span data-ttu-id="977da-233">请参阅随附的 KHI 海报。</span><span class="sxs-lookup"><span data-stu-id="977da-233">See the accompanying KHI poster.</span></span>

<span data-ttu-id="977da-234">若要在游戏中**实现**，请使用提供的卡片代替 KHI 数据和系统查询。</span><span class="sxs-lookup"><span data-stu-id="977da-234">To **Achieve** in the game, use the cards provided in place of KHI data and system queries.</span></span> <span data-ttu-id="977da-235">如果游戏开始时未与给定的方位一起绘制卡片，可以继续执行此操作。</span><span class="sxs-lookup"><span data-stu-id="977da-235">If at the start of the game you did not draw a card relating to a given aspect, you can continue past it.</span></span> <span data-ttu-id="977da-236">如果有相关卡片，请滚动骰子。</span><span class="sxs-lookup"><span data-stu-id="977da-236">If there is a relevant card, roll the die.</span></span> <span data-ttu-id="977da-237">如果您在卡片上显示的数字下滚动，说明您已成功。</span><span class="sxs-lookup"><span data-stu-id="977da-237">If you rolled under the number indicated on the card, you have succeeded.</span></span> <span data-ttu-id="977da-238">如果您在指定的数字上滚动，则必须从卡片组中绘制另一个卡片。</span><span class="sxs-lookup"><span data-stu-id="977da-238">If you roll at or over the indicated number, you must draw another card from the deck.</span></span> <span data-ttu-id="977da-239">如果该卡片指示两个或更多玩家需要滚动，则必须全部成功滚动。</span><span class="sxs-lookup"><span data-stu-id="977da-239">If the card indicates two or more players need to roll, they must all roll successfully.</span></span>

<span data-ttu-id="977da-240">若要在游戏中**维护**，请将有关 Lync 环境的服务管理计划更高的状态反馈。</span><span class="sxs-lookup"><span data-stu-id="977da-240">To **Maintain** in the game, state out loud the service management plan regarding that aspect of the Lync environment.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="977da-241">另请参阅</span><span class="sxs-lookup"><span data-stu-id="977da-241">See Also</span></span>


[<span data-ttu-id="977da-242">Lync Server 网络指南</span><span class="sxs-lookup"><span data-stu-id="977da-242">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="977da-243">关键运行状况指示器：用于维护正常运行的 Lync 服务器的基础</span><span class="sxs-lookup"><span data-stu-id="977da-243">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="977da-244">Lync 呼叫质量方法</span><span class="sxs-lookup"><span data-stu-id="977da-244">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

