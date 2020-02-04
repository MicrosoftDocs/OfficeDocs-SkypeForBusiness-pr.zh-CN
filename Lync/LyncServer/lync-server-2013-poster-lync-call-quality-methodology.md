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
ms.openlocfilehash: 95105501d0403600e88d01ad5fa84363c1e81785
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a><span data-ttu-id="e1df5-102">Lync Server 2013 中的 Lync 呼叫质量方法</span><span class="sxs-lookup"><span data-stu-id="e1df5-102">Lync Call Quality Methodology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1df5-103">_**主题上次修改时间：** 2016-06-24_</span><span class="sxs-lookup"><span data-stu-id="e1df5-103">_**Topic Last Modified:** 2016-06-24_</span></span>

<span data-ttu-id="e1df5-104">本文是[Lync 呼叫质量方法](http://go.microsoft.com/fwlink/?linkid=391841)海报的随附内容，您可以从下载中心下载。</span><span class="sxs-lookup"><span data-stu-id="e1df5-104">This article is a companion to the [Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="e1df5-105">![描述 CQM 流程的海报](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "描述 CQM 流程的海报")</span><span class="sxs-lookup"><span data-stu-id="e1df5-105">![Poster describing the CQM process](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster describing the CQM process")</span></span>

<span data-ttu-id="e1df5-106">你可以使用此海报了解 Lync 2013 和2010的通话质量方法，该方法可帮助你查找并消除影响呼叫质量和包含企业语音功能的 Lync 实现的用户体验的问题。</span><span class="sxs-lookup"><span data-stu-id="e1df5-106">You can use this poster to learn about CQM, the Call Quality Methodology for Lync 2013 and 2010 that helps you find and eliminate issues affecting call quality and user experience for Lync implementations that include enterprise voice features.</span></span> <span data-ttu-id="e1df5-107">通话质量方法是一种新的疑难解答和服务管理框架，可更好地集中精力改进 Lync 中的企业语音服务。</span><span class="sxs-lookup"><span data-stu-id="e1df5-107">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="e1df5-108">在本文中，你可以了解有关 CQM、受监视的服务器和解决方案的种类以及如何处理所收集的遥测数据的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e1df5-108">In this article, you can learn more about CQM, the kinds of servers and solutions that are monitored, and what to do with the collected telemetry data.</span></span>

<span data-ttu-id="e1df5-109">如果对如何使用 CQM 有疑问，可以将问题提交到 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e1df5-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="e1df5-110">海报介绍以下方面：</span><span class="sxs-lookup"><span data-stu-id="e1df5-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="e1df5-111">什么是 Lync CQM？</span><span class="sxs-lookup"><span data-stu-id="e1df5-111">What is Lync CQM?</span></span>

  - <span data-ttu-id="e1df5-112">优先顺序：运行趋势查询</span><span class="sxs-lookup"><span data-stu-id="e1df5-112">Prioritize: Run Trending Queries</span></span>

  - <span data-ttu-id="e1df5-113">PCD</span><span class="sxs-lookup"><span data-stu-id="e1df5-113">PCD</span></span>

  - <span data-ttu-id="e1df5-114">托管/非托管</span><span class="sxs-lookup"><span data-stu-id="e1df5-114">Managed/Unmanaged</span></span>

  - <span data-ttu-id="e1df5-115">服务器植物道路</span><span class="sxs-lookup"><span data-stu-id="e1df5-115">The Server Plant Road</span></span>

  - <span data-ttu-id="e1df5-116">最后一英里的道路</span><span class="sxs-lookup"><span data-stu-id="e1df5-116">The Last Mile Road</span></span>

  - <span data-ttu-id="e1df5-117">终结点道路</span><span class="sxs-lookup"><span data-stu-id="e1df5-117">The End Points Road</span></span>

  - <span data-ttu-id="e1df5-118">服务管理</span><span class="sxs-lookup"><span data-stu-id="e1df5-118">Service Management</span></span>

  - <span data-ttu-id="e1df5-119">董事会游戏规则</span><span class="sxs-lookup"><span data-stu-id="e1df5-119">Board Game Rules</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a><span data-ttu-id="e1df5-120">什么是 Lync CQM？</span><span class="sxs-lookup"><span data-stu-id="e1df5-120">What is Lync CQM?</span></span>

<span data-ttu-id="e1df5-121">通话质量方法是一种新的疑难解答和服务管理框架，可更好地集中精力改进 Lync 中的企业语音服务。</span><span class="sxs-lookup"><span data-stu-id="e1df5-121">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="e1df5-122">使用 CQM 时，需要付出较少的精力才能确保呼叫质量和用户对企业语音服务的满意度。</span><span class="sxs-lookup"><span data-stu-id="e1df5-122">When you use CQM, less effort is needed to assure call quality and user satisfaction for enterprise voice services.</span></span> <span data-ttu-id="e1df5-123">[通话质量方法](http://go.microsoft.com/fwlink/p/?linkid=615208)中的 CQM 更充分地解释。</span><span class="sxs-lookup"><span data-stu-id="e1df5-123">CQM is more fully explained in the [Call Quality Methodology](http://go.microsoft.com/fwlink/p/?linkid=615208).</span></span> <span data-ttu-id="e1df5-124">本文和海报是该内容的摘要。</span><span class="sxs-lookup"><span data-stu-id="e1df5-124">This article and the poster are summaries of that content.</span></span>

<span data-ttu-id="e1df5-125">CQM 将系统故障排除分解为三个路径或 "道路"。</span><span class="sxs-lookup"><span data-stu-id="e1df5-125">CQM breaks down System troubleshooting into three paths or “Roads.”</span></span> <span data-ttu-id="e1df5-126">这些是：服务器植物的道路，它看起来是服务器和它们之间的链接、端点道路，它查看用户设备和用于执行呼叫的媒体，以及用于解决传统交换电话网络通话的集成的最后一英里路上。</span><span class="sxs-lookup"><span data-stu-id="e1df5-126">These are: the Server Plant Road, which looks at the servers and the links between them, the End Points Road, which looks at user devices and media used to carry calls, and the Last Mile Road, which addresses integration of traditional switched telephone network calls.</span></span>

<span data-ttu-id="e1df5-127">每个道路都划分为与特定区域或主题相关的多个段，并且在每个段定义中可以获得哪些内容是可接受的质量级别，采取行动以达到该质量级别，并实施服务管理计划以保持该质量级别，然后再转到下一主题。</span><span class="sxs-lookup"><span data-stu-id="e1df5-127">Each Road is divided into several segments relating to a specific area or topic, and at each segment definitions are made about what is an acceptable quality level, actions are taken to achieve that quality level, and a service management plan is put in place to maintain that quality level before moving on to the next topic.</span></span>

<span data-ttu-id="e1df5-128">标牌将 Lync CQM 作为一局游戏提供给三位玩家，每个玩家都将经历其中一条道路。</span><span class="sxs-lookup"><span data-stu-id="e1df5-128">The poster presents Lync CQM as a board game for three players, each of whom will go through one of the roads.</span></span> <span data-ttu-id="e1df5-129">下载中包含的卡用于模拟必须克服的障碍通话质量。</span><span class="sxs-lookup"><span data-stu-id="e1df5-129">Cards included with the download are used to simulate impediments to call quality that must be overcome.</span></span> <span data-ttu-id="e1df5-130">有关目标以及如何实现它们的提示和建议包括在三个路径中，以及确定首次在实际应用程序中首次着手的优先级原则（在游戏中，所有三条道路均以并行方式解决）。</span><span class="sxs-lookup"><span data-stu-id="e1df5-130">Hints and suggestions about targets and how to achieve them are included along the three paths, as well as prioritization guidelines for which road to pursue first in actual applications (in the game, all three roads are addressed in parallel).</span></span>

<span data-ttu-id="e1df5-131">CQM 在早期版本的 Lync 中如何工作？</span><span class="sxs-lookup"><span data-stu-id="e1df5-131">How does CQM work in earlier versions of Lync?</span></span> <span data-ttu-id="e1df5-132">CQM 是 Lync 2013 的新增功能，但其中大部分功能可用于 Lync 2010。</span><span class="sxs-lookup"><span data-stu-id="e1df5-132">CQM is new for Lync 2013, but most of it can be adapted to be used with Lync 2010.</span></span> <span data-ttu-id="e1df5-133">CQM 可能会对 Microsoft Office Communicator 有一定的作用，但此操作未经测试且不受支持。</span><span class="sxs-lookup"><span data-stu-id="e1df5-133">CQM may work to a degree with Microsoft Office Communicator, but this is untested and not supported.</span></span>

<span data-ttu-id="e1df5-134">如果对如何使用 CQM 有疑问，可以将问题提交到 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e1df5-134">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a><span data-ttu-id="e1df5-135">优先顺序：运行趋势查询</span><span class="sxs-lookup"><span data-stu-id="e1df5-135">Prioritize: Run Trending Queries</span></span>

<span data-ttu-id="e1df5-136">CQM 的第一步是运行两周的每个趋势查询，然后分析结果。</span><span class="sxs-lookup"><span data-stu-id="e1df5-136">The first step in CQM is to run each of the trending queries for two weeks and then analyze the results.</span></span> <span data-ttu-id="e1df5-137">按最大流参与者、最高不良流比率和托管区域（你控制的区域）优先顺序纠正操作。</span><span class="sxs-lookup"><span data-stu-id="e1df5-137">Prioritize corrective action by the largest stream contributor, the highest poor stream ratio, and managed areas (ones you control).</span></span><span data-ttu-id="e1df5-138">如果音频/视频多点控制单元（AV MCU）或中介查询显示较差的结果，请从红色或服务器植物路上开始。</span><span class="sxs-lookup"><span data-stu-id="e1df5-138">  If the Audio/Video Multi-point Control Unit (AV MCU) or Mediation queries show poor results, start on the Red or Server Plant road.</span></span><span data-ttu-id="e1df5-139">如果有线或无线查询显示较差的结果，请从蓝色或最后一英里路上开始。</span><span class="sxs-lookup"><span data-stu-id="e1df5-139">  If the Wired or Wireless queries show poor results, start on the Blue or Last Mile road.</span></span><span data-ttu-id="e1df5-140">如果 VPN 或外部查询显示较差的结果，请从绿色或结束点路上开始。</span><span class="sxs-lookup"><span data-stu-id="e1df5-140">  If the VPN or External queries show poor results, start on the Green or End Points road.</span></span>

<span data-ttu-id="e1df5-141">选择开始使用的道路后，为每个区域定义一个目标（Assert），工作以满足该目标（实现），然后实施过程来保持目标（维护）。</span><span class="sxs-lookup"><span data-stu-id="e1df5-141">After you choose a road to start with, define a target for each area (Assert), work to meet that target (Achieve) and then implement procedures to stay on target (Maintain).</span></span> <span data-ttu-id="e1df5-142">您还可以将此海报用作游戏，以了解 CQM 背后的原则。</span><span class="sxs-lookup"><span data-stu-id="e1df5-142">You can also use this poster as a game to understand the principles behind CQM.</span></span>

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a><span data-ttu-id="e1df5-143">PCD</span><span class="sxs-lookup"><span data-stu-id="e1df5-143">PCD</span></span>

<span data-ttu-id="e1df5-144">PreCall 诊断工具（PCD）将帮助你识别和诊断你的外围网络中的问题（QoE 数据库不会收集你的 edge 或外围网络上的信息），并且还可以解决最后一英里的连接问题。</span><span class="sxs-lookup"><span data-stu-id="e1df5-144">The PreCall Diagnostics tool (PCD) will help you identify and diagnose problems in your perimeter network (the QoE database doesn’t collect information on your edge or perimeter network) and also to troubleshoot connections in the Last Mile.</span></span> <span data-ttu-id="e1df5-145">该工具既可用作 Windows 8 新式应用，也可在 Windows 桌面应用程序http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88中使用。</span><span class="sxs-lookup"><span data-stu-id="e1df5-145">The tool is available as both a Windows 8 Modern App or a Windows Desktop App at http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.</span></span>

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a><span data-ttu-id="e1df5-146">托管/非托管</span><span class="sxs-lookup"><span data-stu-id="e1df5-146">Managed/Unmanaged</span></span>

<span data-ttu-id="e1df5-147">Lync 服务器部署和网络基础结构通常可分为托管和非托管空间。</span><span class="sxs-lookup"><span data-stu-id="e1df5-147">The Lync Server deployment and network infrastructure can usually be divided into managed and unmanaged spaces.</span></span> <span data-ttu-id="e1df5-148">托管空间包括您的整个内部有线网络和服务器基础结构。</span><span class="sxs-lookup"><span data-stu-id="e1df5-148">The managed space includes your entire inside wired network and server infrastructure.</span></span> <span data-ttu-id="e1df5-149">非托管空间是无线基础结构和外部网络基础结构。</span><span class="sxs-lookup"><span data-stu-id="e1df5-149">The unmanaged space is the wireless infrastructure and the outside network infrastructure.</span></span>

<span data-ttu-id="e1df5-150">这种区别提高了数据的清晰度，并帮助您的组织集中关注将对用户的语音和视频质量产生显著影响的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="e1df5-150">Making this distinction increases the clarity of your data and helps your organization focus on workloads that will have a measurable impact on your users’ voice and video quality.</span></span> <span data-ttu-id="e1df5-151">如果将呼叫放置在你拥有（托管）的基础结构上，而不是部分受其他实体（非托管）控制的基础结构上，则用户有不同的预期质量。</span><span class="sxs-lookup"><span data-stu-id="e1df5-151">Users have a different expectation of quality if the call is placed on infrastructure that you own (managed) versus infrastructure that is partly under the control of some other entity (unmanaged).</span></span> <span data-ttu-id="e1df5-152">这并不是说无线用户离开其自己的设备，以便获得出色的 Lync 服务器体验。</span><span class="sxs-lookup"><span data-stu-id="e1df5-152">This is not to say that wireless users are left to their own devices to have excellent Lync Server experiences.</span></span>

<span data-ttu-id="e1df5-153">在非托管空间中提高语音质量要求在托管空间中具有高质量。</span><span class="sxs-lookup"><span data-stu-id="e1df5-153">Improving voice quality in the unmanaged space requires you to have high quality in the managed space.</span></span> <span data-ttu-id="e1df5-154">无线（Wi-fi）是否被视为托管或非托管空间由你的组织决定。</span><span class="sxs-lookup"><span data-stu-id="e1df5-154">Whether wireless (Wi-Fi) is considered managed or unmanaged space is up to your organization.</span></span> <span data-ttu-id="e1df5-155">实现正常环境的技术在两个空间中有所不同，就像解决方案一样。</span><span class="sxs-lookup"><span data-stu-id="e1df5-155">The techniques to achieve a healthy environment are different in the two spaces, as are the solutions.</span></span>

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a><span data-ttu-id="e1df5-156">服务器植物道路</span><span class="sxs-lookup"><span data-stu-id="e1df5-156">The Server Plant Road</span></span>

<span data-ttu-id="e1df5-157">服务器植物公路的第1部分用于解决 Lync 实现中的实际服务器。</span><span class="sxs-lookup"><span data-stu-id="e1df5-157">Segment 1 of the Server Plant Road addresses the actual servers in the Lync implementation.</span></span> <span data-ttu-id="e1df5-158">收集有关服务器本身及其在实现中的角色的 KHI 数据并分析结果。</span><span class="sxs-lookup"><span data-stu-id="e1df5-158">Gather KHI data regarding both the server itself and its role in the implementation and analyze the result.</span></span> <span data-ttu-id="e1df5-159">如果操作是保证的，请更正发现的任何问题。</span><span class="sxs-lookup"><span data-stu-id="e1df5-159">If action is warranted, correct any problems found.</span></span> <span data-ttu-id="e1df5-160">有关此主题的更多详细信息，请在 KHI 海报附带的[Lync Server 2013 中介绍的关键运行状况指示器](lync-server-2013-poster-key-health-indicators.md)中介绍。</span><span class="sxs-lookup"><span data-stu-id="e1df5-160">More detail on this topic is presented in the article about [Key Health Indicators in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) that accompanies the KHI poster.</span></span>

<span data-ttu-id="e1df5-161">下一段用于解决 AV MCU 服务器和中介服务器之间的媒体流。</span><span class="sxs-lookup"><span data-stu-id="e1df5-161">The next segment addresses media streams between the AV MCU server and mediation server.</span></span> <span data-ttu-id="e1df5-162">首先确定数据流阈值较差的目标。</span><span class="sxs-lookup"><span data-stu-id="e1df5-162">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="e1df5-163">较差的流通常\>是 PacketLossRate .01 \>或 PacketLossRateMax。</span><span class="sxs-lookup"><span data-stu-id="e1df5-163">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="e1df5-164">另一个理想目标是\< PoorStreamsRatio 2%。</span><span class="sxs-lookup"><span data-stu-id="e1df5-164">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="e1df5-165">接下来，使用详细查询查找具有不良流的 AVMCU 和中介服务器对，调查不良流的原因，查看不良流路径中的网络设备，纠正不良流，并为网络定义最佳或 "黄金" 配置机房.</span><span class="sxs-lookup"><span data-stu-id="e1df5-165">Next, use detailed queries to find AVMCU and Mediation server pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="e1df5-166">若要保持成就，请实施流程和工具以管理配置偏移，并报告新的问题区域。</span><span class="sxs-lookup"><span data-stu-id="e1df5-166">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="e1df5-167">接下来，检查中介服务器和公共交换电话网络（PSTN）网关之间的媒体流。</span><span class="sxs-lookup"><span data-stu-id="e1df5-167">Next, examine the media streams between the Mediation server and the Public Switched Telephone Network (PSTN) gateway.</span></span> <span data-ttu-id="e1df5-168">首先确定数据流阈值较差的目标。</span><span class="sxs-lookup"><span data-stu-id="e1df5-168">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="e1df5-169">较差的流通常\>是 PacketLossRate .01 \>或 PacketLossRateMax。</span><span class="sxs-lookup"><span data-stu-id="e1df5-169">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="e1df5-170">另一个理想目标是\< PoorStreamsRatio 2%。</span><span class="sxs-lookup"><span data-stu-id="e1df5-170">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="e1df5-171">接下来，使用详细查询查找具有不良流的中介服务器和网关对，调查不良流的原因，查看不良流路径中的网络设备，纠正不良流，并为网络定义最佳或 "黄金" 配置机房.</span><span class="sxs-lookup"><span data-stu-id="e1df5-171">Next, use detailed queries to find Mediation server and gateway pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="e1df5-172">若要保持成就，请实施流程和工具以管理配置偏移，并报告新的问题区域。</span><span class="sxs-lookup"><span data-stu-id="e1df5-172">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="e1df5-173">最后，检查你的 PSTN 网关的运行状况指标。</span><span class="sxs-lookup"><span data-stu-id="e1df5-173">Finally, examine the health metrics for your PSTN gateway.</span></span> <span data-ttu-id="e1df5-174">标识显示运行状况并针对它们定义目标的统计信息。</span><span class="sxs-lookup"><span data-stu-id="e1df5-174">Identify the statistics that show health and define targets against them.</span></span> <span data-ttu-id="e1df5-175">此处未提供任何特定指南，因为可以使用多个可能的网关。</span><span class="sxs-lookup"><span data-stu-id="e1df5-175">No specific guidance is provided here as many possible gateways can be used.</span></span> <span data-ttu-id="e1df5-176">建立目标后，根据需要进行补救以实现目标;在该过程中，你可能会为网关定义 "金色" 或最佳配置。</span><span class="sxs-lookup"><span data-stu-id="e1df5-176">Once targets are established, remediate as needed to achieve the target; in the process you will likely define a “gold” or optimal configuration for the gateway.</span></span> <span data-ttu-id="e1df5-177">若要保持成就，请实施流程和工具以管理配置偏移，并报告新的问题区域。</span><span class="sxs-lookup"><span data-stu-id="e1df5-177">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span> <span data-ttu-id="e1df5-178">请注意，固件和软件更新可能会改变你的配置，或导致你更改 "黄金" 配置的定义，因此请注意这些活动。</span><span class="sxs-lookup"><span data-stu-id="e1df5-178">Be aware that firmware and software updates may alter your configuration or lead you to change the definition of the “gold” configuration, so approach these activities with care.</span></span>

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a><span data-ttu-id="e1df5-179">最后一英里的道路</span><span class="sxs-lookup"><span data-stu-id="e1df5-179">The Last Mile Road</span></span>

<span data-ttu-id="e1df5-180">客户端连接到网络的两种方法中，有线预期提供最高的质量，并且相应地必须是最后一个英里问题的初始焦点。</span><span class="sxs-lookup"><span data-stu-id="e1df5-180">Of the two ways clients connect to the network, wired is expected to deliver the highest quality and correspondingly this must be your initial focus for last mile issues.</span></span> <span data-ttu-id="e1df5-181">使用 CQM 有线查询（LastMile\_0\_有线）和它提供的不良流比率数据。</span><span class="sxs-lookup"><span data-stu-id="e1df5-181">Use the CQM Wired query (LastMile\_0\_Wired) and the Poor Streams ratio data it provides.</span></span> <span data-ttu-id="e1df5-182">我们建议为包含\< \> 300 流的网站定义目标 PoorStreamsRatio 5%）。</span><span class="sxs-lookup"><span data-stu-id="e1df5-182">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="e1df5-183">若要实现目标，请将从最差订购的子网修正为最佳，并实施 QoS。</span><span class="sxs-lookup"><span data-stu-id="e1df5-183">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

<span data-ttu-id="e1df5-184">优化有线连接的质量后，提高无线质量将变得更容易，因为无线基础结构位于每个位置的有线内核顶部。</span><span class="sxs-lookup"><span data-stu-id="e1df5-184">After you optimize the quality of your wired connections, improving wireless quality becomes easier because the wireless infrastructure sits atop the wired core at each location.</span></span> <span data-ttu-id="e1df5-185">具有良好有线质量的网站中的较差无线流必须属于特定无线组件。</span><span class="sxs-lookup"><span data-stu-id="e1df5-185">Poor wireless streams in a site with good wired quality must be attributed to the specific wireless components.</span></span> <span data-ttu-id="e1df5-186">CQM 无线查询（LastMile\_1\_无线）在某个日期范围内运行，并将你环境中的所有内部无线流从 Lync 客户端返回到任何会议服务器或中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e1df5-186">The CQM Wireless query (LastMile\_1\_Wireless) operates on a date range and will return all internal wireless streams in your environment from Lync clients to or from either conferencing servers or mediation servers.</span></span> <span data-ttu-id="e1df5-187">我们建议为包含\< \> 300 流的网站定义目标 PoorStreamsRatio 5%）。</span><span class="sxs-lookup"><span data-stu-id="e1df5-187">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="e1df5-188">若要实现目标，请将从最差订购的子网修正为最佳，并实施 QoS。</span><span class="sxs-lookup"><span data-stu-id="e1df5-188">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a><span data-ttu-id="e1df5-189">终结点道路</span><span class="sxs-lookup"><span data-stu-id="e1df5-189">The End Points Road</span></span>

<span data-ttu-id="e1df5-190">在与 Lync 配合使用时，通过耳机和已知的其他设备生成可接受质量，开始查询。</span><span class="sxs-lookup"><span data-stu-id="e1df5-190">Begin inquiries into the End Points Road with the headsets and other devices known to produce acceptable quality when used with Lync.</span></span> <span data-ttu-id="e1df5-191">我们建议使用超过100个\>流的实现目标 AvgSendListen MOS 3.6。）通过识别有问题的设备并修复或替换它们来实现目标。</span><span class="sxs-lookup"><span data-stu-id="e1df5-191">We suggest a target AvgSendListen MOS \> 3.6 for implementations with over 100 streams.) Achieve the target by identifying problematic devices and fix or replace them.</span></span>

<span data-ttu-id="e1df5-192">接下来，检查设备或电脑处理音频以查找最终用户呼叫。</span><span class="sxs-lookup"><span data-stu-id="e1df5-192">Next, examine the device or PC processing the audio for end user calls.</span></span> <span data-ttu-id="e1df5-193">建议的目标质量指标为 AudioMicGlitchRate \<= 1。</span><span class="sxs-lookup"><span data-stu-id="e1df5-193">A suggested target quality metric is an AudioMicGlitchRate \<= 1.</span></span> <span data-ttu-id="e1df5-194">为用户系统确定最佳系统配置时，请定义一个 "黄金" PC 配置，包括驱动程序版本。</span><span class="sxs-lookup"><span data-stu-id="e1df5-194">As you identify optimal system configurations for the user systems, define a “golden” PC configuration including driver versions.</span></span>

<span data-ttu-id="e1df5-195">现在，检查音频流从 Lync 终结点系统获取的网络路径，这可能会导致音频质量较差。</span><span class="sxs-lookup"><span data-stu-id="e1df5-195">Now examine the network path an audio stream takes from a Lync endpoint system, which can cause poor audio quality.</span></span> <span data-ttu-id="e1df5-196">如果音频通过 VPN 连接，您可能会看到延迟问题。</span><span class="sxs-lookup"><span data-stu-id="e1df5-196">If audio travels over a VPN connection you might see latency issues.</span></span> <span data-ttu-id="e1df5-197">如果内部 Lync 客户端无法为两方或对等调用的其他内部 Lync 客户端建立直接媒体流，则它将回退到通过 Lync Edge 服务器中继的路径，从而导致延迟问题，并增加损失和抖动。</span><span class="sxs-lookup"><span data-stu-id="e1df5-197">If an internal Lync client cannot establish a direct media stream to another internal Lync client for a two-party or peer-to-peer call, it will fall back to a path that relays through a Lync Edge server, again leading to latency issues as well as increased potential for loss and jitter.</span></span> <span data-ttu-id="e1df5-198">我们建议你通过 VPN 定义质量指标0% 的媒体。</span><span class="sxs-lookup"><span data-stu-id="e1df5-198">We suggest you define a quality metric of 0% Media over VPN.</span></span> <span data-ttu-id="e1df5-199">在你更正以实现你设置的目标时，请确定问题子网并调查防火墙规则、数据包 shapers 和其他相关网络设备配置。</span><span class="sxs-lookup"><span data-stu-id="e1df5-199">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

<span data-ttu-id="e1df5-200">IP 数据包可以使用 "传输控制协议（TCP）" 或 "用户数据报协议（UDP）"。</span><span class="sxs-lookup"><span data-stu-id="e1df5-200">IP Packets can use either Transmission Control Protocol (TCP) or User Datagram Protocol (UDP).</span></span> <span data-ttu-id="e1df5-201">TCP 对于数据流而言是最佳的。</span><span class="sxs-lookup"><span data-stu-id="e1df5-201">TCP is optimal for data streams.</span></span> <span data-ttu-id="e1df5-202">UDP 是无连接的，并且更高效地适用于媒体，因为 TCP 恢复机制无法以实时媒体的损失解决。</span><span class="sxs-lookup"><span data-stu-id="e1df5-202">UDP is connectionless and is more efficient for media since TCP recovery mechanisms cannot address loss in real time media.</span></span> <span data-ttu-id="e1df5-203">Lync 始终首选 UDP，但如果无法建立 UDP 会话，则将还原为 TCP。</span><span class="sxs-lookup"><span data-stu-id="e1df5-203">Lync always prefers UDP, but will revert to TCP if a UDP session cannot be established.</span></span> <span data-ttu-id="e1df5-204">通过 TCP 的媒体会话将表现出比通过 UDP 更差的质量。</span><span class="sxs-lookup"><span data-stu-id="e1df5-204">Media sessions over TCP will exhibit poorer quality than over UDP.</span></span> <span data-ttu-id="e1df5-205">我们建议通过 TCP 的0% 连接的质量定义。</span><span class="sxs-lookup"><span data-stu-id="e1df5-205">We recommend a quality definition of 0% connections over TCP.</span></span> <span data-ttu-id="e1df5-206">在你更正以实现你设置的目标时，请确定问题子网并调查防火墙规则、数据包 shapers 和其他相关网络设备配置。</span><span class="sxs-lookup"><span data-stu-id="e1df5-206">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a><span data-ttu-id="e1df5-207">服务管理</span><span class="sxs-lookup"><span data-stu-id="e1df5-207">Service Management</span></span>

<span data-ttu-id="e1df5-208">服务管理是 CQM 的结束状态，所有三条道路的目的地。</span><span class="sxs-lookup"><span data-stu-id="e1df5-208">Service management is the end state of CQM, and the destination for all three roads.</span></span> <span data-ttu-id="e1df5-209">若要保持高级别的通话质量，请监视以下方面：</span><span class="sxs-lookup"><span data-stu-id="e1df5-209">To maintain high levels of call quality, monitor these areas:</span></span>

1.  <span data-ttu-id="e1df5-210">**用户**-补救活动应显示用户满意度的显著增加。</span><span class="sxs-lookup"><span data-stu-id="e1df5-210">**Users** - Remediation activities should show a measurable increase in user satisfaction.</span></span> <span data-ttu-id="e1df5-211">你可以通过问题票证或其他反馈机制来衡量此问题。</span><span class="sxs-lookup"><span data-stu-id="e1df5-211">You can measure this by problem tickets or other feedback mechanisms.</span></span> <span data-ttu-id="e1df5-212">您还可以发布质量指标。</span><span class="sxs-lookup"><span data-stu-id="e1df5-212">You can also publish quality metrics.</span></span>

2.  <span data-ttu-id="e1df5-213">**流程**-定义 operationalize CQM 的每天、每周和每月流程。</span><span class="sxs-lookup"><span data-stu-id="e1df5-213">**Process** - define daily, weekly and monthly processes to operationalize CQM.</span></span> <span data-ttu-id="e1df5-214">在你进行补救时（每天），监视节奏将以更高的频率启动，并随着你的稳定而移动到较低频率（每月）。</span><span class="sxs-lookup"><span data-stu-id="e1df5-214">Monitoring rhythm starts at a higher frequency while you are remediating (daily) and moves to a lower frequency (monthly) as you stabilize.</span></span>

3.  <span data-ttu-id="e1df5-215">**工具**-确定用于测量和修正的工具。</span><span class="sxs-lookup"><span data-stu-id="e1df5-215">**Tools** - identify tools to both measure and remediate.</span></span> <span data-ttu-id="e1df5-216">你可能会发现自动运行 CQM 查询以支持你的进程非常有用。</span><span class="sxs-lookup"><span data-stu-id="e1df5-216">You may find it useful to automate running the CQM queries to support your processes.</span></span> <span data-ttu-id="e1df5-217">补救措施可能需要其他工具，例如，在网络元素上强制实施标准化配置或在不良流中排除损失。</span><span class="sxs-lookup"><span data-stu-id="e1df5-217">Remediation may require additional tools for example to enforce standardized configurations on network elements or troubleshooting loss in poor streams.</span></span>

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a><span data-ttu-id="e1df5-218">董事会游戏规则</span><span class="sxs-lookup"><span data-stu-id="e1df5-218">Board Game Rules</span></span>

<span data-ttu-id="e1df5-219">你可以将此海报用作对 CQM 实现的引用或用作练习概念的游戏。</span><span class="sxs-lookup"><span data-stu-id="e1df5-219">You can use this poster either as a reference to a CQM implementation or as a game to practice the concepts.</span></span> <span data-ttu-id="e1df5-220">要玩游戏，您需要 1 6 面片和所提供的卡。</span><span class="sxs-lookup"><span data-stu-id="e1df5-220">To play, you will need one six-sided die and the cards provided.</span></span> <span data-ttu-id="e1df5-221">可在标准 Avery 5871 名片上打印可下载版本的卡。</span><span class="sxs-lookup"><span data-stu-id="e1df5-221">A downloadable version of the cards is available to print on standard Avery 5871 business cards.</span></span>

<span data-ttu-id="e1df5-222">游戏适用于3个玩家。</span><span class="sxs-lookup"><span data-stu-id="e1df5-222">The game is for 3 players.</span></span> <span data-ttu-id="e1df5-223">玩家可以使用三条路径来达到所需质量并达到中心服务管理状态：服务器植物、终点和上一英里。</span><span class="sxs-lookup"><span data-stu-id="e1df5-223">There are three paths the players can use to achieve the desired quality and reach the center Service Management state: Server Plant, End Point, and Last Mile.</span></span> <span data-ttu-id="e1df5-224">每个路径在断言质量目标、实现目标和维护系统方面的方式上都有停止。</span><span class="sxs-lookup"><span data-stu-id="e1df5-224">Each path has stops along the way where you Assert quality targets, Achieve goals, and Maintain an aspect of your system.</span></span> <span data-ttu-id="e1df5-225">将卡放在上面的指定区域，然后绘制5张卡片。</span><span class="sxs-lookup"><span data-stu-id="e1df5-225">Place the cards in the indicated area above, and then draw 5 cards.</span></span> <span data-ttu-id="e1df5-226">查看你绘制的卡片并将其放在相关的版块段上。</span><span class="sxs-lookup"><span data-stu-id="e1df5-226">Review the cards you’ve drawn and place them on the relevant board segment.</span></span> <span data-ttu-id="e1df5-227">每个玩家通过其路线中的卡片逐个移动，断言质量目标，实现这些目标，以及维护服务级别。</span><span class="sxs-lookup"><span data-stu-id="e1df5-227">Each player moves through the cards on their path step by step, asserting quality targets, achieving those targets, and maintaining the service levels.</span></span> <span data-ttu-id="e1df5-228">当所有玩家都达到中心服务管理状态时，游戏就完成了。</span><span class="sxs-lookup"><span data-stu-id="e1df5-228">The game is completed when all players reach the center Service Management state.</span></span> <span data-ttu-id="e1df5-229">游戏卡下载中提供了更详细的规则。</span><span class="sxs-lookup"><span data-stu-id="e1df5-229">More detailed rules are provided with the game card download.</span></span>

<span data-ttu-id="e1df5-230">若要**断言**质量目标，请查看适用于该目标的参数，并向您发送的内容提供相关内容，并不会选择接受。</span><span class="sxs-lookup"><span data-stu-id="e1df5-230">To **Assert** a quality target, review the parameters applicable to that target, and state out loud what you will and won’t choose to accept.</span></span> <span data-ttu-id="e1df5-231">我们推荐了起始点，但您必须进行最后的通话。</span><span class="sxs-lookup"><span data-stu-id="e1df5-231">We have recommended beginning points, but you must make the final call.</span></span> <span data-ttu-id="e1df5-232">此异常是 KHI 数据，应使用 Microsoft 建立的标准。</span><span class="sxs-lookup"><span data-stu-id="e1df5-232">The exception is KHI data, where the standards established by Microsoft should be used.</span></span> <span data-ttu-id="e1df5-233">请参阅随附的 KHI 海报。</span><span class="sxs-lookup"><span data-stu-id="e1df5-233">See the accompanying KHI poster.</span></span>

<span data-ttu-id="e1df5-234">若要在游戏中**实现**，请使用提供的卡来代替 KHI 数据和系统查询。</span><span class="sxs-lookup"><span data-stu-id="e1df5-234">To **Achieve** in the game, use the cards provided in place of KHI data and system queries.</span></span> <span data-ttu-id="e1df5-235">如果在游戏开始时未绘制与给定方位有关的卡，则可以继续使用它。</span><span class="sxs-lookup"><span data-stu-id="e1df5-235">If at the start of the game you did not draw a card relating to a given aspect, you can continue past it.</span></span> <span data-ttu-id="e1df5-236">如果有相关卡，请滚动骰子。</span><span class="sxs-lookup"><span data-stu-id="e1df5-236">If there is a relevant card, roll the die.</span></span> <span data-ttu-id="e1df5-237">如果您在卡上显示的数字下滚动，则您已成功。</span><span class="sxs-lookup"><span data-stu-id="e1df5-237">If you rolled under the number indicated on the card, you have succeeded.</span></span> <span data-ttu-id="e1df5-238">如果你在指定的数字上滚动，则必须从该幻灯片中绘制另一个卡片。</span><span class="sxs-lookup"><span data-stu-id="e1df5-238">If you roll at or over the indicated number, you must draw another card from the deck.</span></span> <span data-ttu-id="e1df5-239">如果该卡指示两个或更多玩家需要滚动，则它们必须全部成功滚动。</span><span class="sxs-lookup"><span data-stu-id="e1df5-239">If the card indicates two or more players need to roll, they must all roll successfully.</span></span>

<span data-ttu-id="e1df5-240">要在游戏中**维护**，请将有关 Lync 环境的服务管理计划更高的状态。</span><span class="sxs-lookup"><span data-stu-id="e1df5-240">To **Maintain** in the game, state out loud the service management plan regarding that aspect of the Lync environment.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e1df5-241">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1df5-241">See Also</span></span>


[<span data-ttu-id="e1df5-242">Lync Server 网络指南</span><span class="sxs-lookup"><span data-stu-id="e1df5-242">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="e1df5-243">关键运行状况指示器：用于维护正常 Lync 服务器的基础</span><span class="sxs-lookup"><span data-stu-id="e1df5-243">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="e1df5-244">Lync 通话质量方法</span><span class="sxs-lookup"><span data-stu-id="e1df5-244">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

