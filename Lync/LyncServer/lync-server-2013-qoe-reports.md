---
title: Lync Server 2013： QoE 报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 958c67b1b10b25e44805d2582ffe2e9fab575568
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="0a4a3-102">Lync Server 2013 中的 QoE 报告</span><span class="sxs-lookup"><span data-stu-id="0a4a3-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a4a3-103">_**上次修改的主题：** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="0a4a3-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="0a4a3-104">QoE 摘要/趋势报告</span><span class="sxs-lookup"><span data-stu-id="0a4a3-104">QoE summary/trend reports</span></span>

<span data-ttu-id="0a4a3-105">QoE 摘要/趋势报告可用于查找一天的高峰使用时间，并在这些时间内检查媒体质量，以帮助确保组织的网络资源足够。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="0a4a3-106">您的组织还可以使用报告中提供的多个筛选器来隔离特定位置、客户端和设备类型以及服务器的性能号码。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="0a4a3-107">QoE 摘要/趋势报告包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="0a4a3-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="0a4a3-108">UC 到 UC 摘要/趋势报告</span><span class="sxs-lookup"><span data-stu-id="0a4a3-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="0a4a3-109">PSTN 摘要/趋势报告</span><span class="sxs-lookup"><span data-stu-id="0a4a3-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="0a4a3-110">会议摘要/趋势报告</span><span class="sxs-lookup"><span data-stu-id="0a4a3-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="0a4a3-111">QoE 性能报告</span><span class="sxs-lookup"><span data-stu-id="0a4a3-111">QoE performance reports</span></span>

<span data-ttu-id="0a4a3-112">QoE 性能报告提供了有关三个报告的详细信息，这些报告集中在中介服务器、A/V 会议服务器和终结点位置的 QoE 性能上。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="0a4a3-113">中介服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="0a4a3-113">Mediation server performance report</span></span>

<span data-ttu-id="0a4a3-114">中介服务器性能报告列出了在指定时间段内由一个或多个中介实现的指标。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="0a4a3-115">统一通信（UC）到中介服务器腿的指标和每个呼叫的中介服务器到网关的线路分别报告。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="0a4a3-116">使用此报告可比较组织的各种中介服务器的容量和性能。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="0a4a3-117">对于每个中介服务器（和每个呼叫腿），报告将显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="0a4a3-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="0a4a3-118">呼叫数</span><span class="sxs-lookup"><span data-stu-id="0a4a3-118">Number of calls</span></span>

  - <span data-ttu-id="0a4a3-119">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="0a4a3-119">Packet Loss</span></span>

  - <span data-ttu-id="0a4a3-120">往返时间</span><span class="sxs-lookup"><span data-stu-id="0a4a3-120">Round Trip Time</span></span>

  - <span data-ttu-id="0a4a3-121">抖动</span><span class="sxs-lookup"><span data-stu-id="0a4a3-121">Jitter</span></span>

  - <span data-ttu-id="0a4a3-122">会话平均意见得分（MOS）</span><span class="sxs-lookup"><span data-stu-id="0a4a3-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="0a4a3-123">发送 MOS</span><span class="sxs-lookup"><span data-stu-id="0a4a3-123">Sending MOS</span></span>

  - <span data-ttu-id="0a4a3-124">侦听 MOS</span><span class="sxs-lookup"><span data-stu-id="0a4a3-124">Listening MOS</span></span>

  - <span data-ttu-id="0a4a3-125">网络 MOS</span><span class="sxs-lookup"><span data-stu-id="0a4a3-125">Network MOS</span></span>

  - <span data-ttu-id="0a4a3-126">网络 MOS 降级</span><span class="sxs-lookup"><span data-stu-id="0a4a3-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="0a4a3-127">回显返回</span><span class="sxs-lookup"><span data-stu-id="0a4a3-127">Echo Return</span></span>

  - <span data-ttu-id="0a4a3-128">信号级别</span><span class="sxs-lookup"><span data-stu-id="0a4a3-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="0a4a3-129">A/V 会议服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="0a4a3-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="0a4a3-130">A/V 会议服务器性能报告提供了在指定时间段内由一个或多个 A/V 会议服务器实现的指标的列表。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="0a4a3-131">此报告可用于比较组织的各种 A/V 会议服务器的容量和性能。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="0a4a3-132">您的组织还可以隔离报告以仅显示特定客户端类型（如 Lync 客户端或 PSTN 客户端）的体验。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="0a4a3-133">对于每个 A/V 会议服务器，报告将显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="0a4a3-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="0a4a3-134">会议数</span><span class="sxs-lookup"><span data-stu-id="0a4a3-134">Number of conferences</span></span>

  - <span data-ttu-id="0a4a3-135">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="0a4a3-135">Packet Loss</span></span>

  - <span data-ttu-id="0a4a3-136">往返时间</span><span class="sxs-lookup"><span data-stu-id="0a4a3-136">Round Trip Time</span></span>

  - <span data-ttu-id="0a4a3-137">抖动</span><span class="sxs-lookup"><span data-stu-id="0a4a3-137">Jitter</span></span>

  - <span data-ttu-id="0a4a3-138">会话平均意见得分（MOS）</span><span class="sxs-lookup"><span data-stu-id="0a4a3-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="0a4a3-139">发送 MOS</span><span class="sxs-lookup"><span data-stu-id="0a4a3-139">Sending MOS</span></span>

  - <span data-ttu-id="0a4a3-140">侦听 MOS</span><span class="sxs-lookup"><span data-stu-id="0a4a3-140">Listening MOS</span></span>

  - <span data-ttu-id="0a4a3-141">网络 MOS</span><span class="sxs-lookup"><span data-stu-id="0a4a3-141">Network MOS</span></span>

  - <span data-ttu-id="0a4a3-142">网络 MOS 降级</span><span class="sxs-lookup"><span data-stu-id="0a4a3-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="0a4a3-143">回显返回</span><span class="sxs-lookup"><span data-stu-id="0a4a3-143">Echo Return</span></span>

  - <span data-ttu-id="0a4a3-144">信号级别</span><span class="sxs-lookup"><span data-stu-id="0a4a3-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="0a4a3-145">基于位置的性能报告</span><span class="sxs-lookup"><span data-stu-id="0a4a3-145">Location-based performance report</span></span>

<span data-ttu-id="0a4a3-146">基于位置的性能报告提供了网络位置的列表，每个位置都显示了每个预先确定的质量范围内的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="0a4a3-147">此报告的目标是提供对各种位置的组织电话呼叫的媒体质量的深入了解，以便您能够识别出性能不佳的位置，并在组织中查看不同等级的媒体质量不同的位置。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="0a4a3-148">显示报表时，将显示不同的指标表，即组织决定报告的每个指标的一个表。</span><span class="sxs-lookup"><span data-stu-id="0a4a3-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="0a4a3-149">您可以从此报告的以下指标中进行选择：</span><span class="sxs-lookup"><span data-stu-id="0a4a3-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="0a4a3-150">会话平均意见得分（MOS）</span><span class="sxs-lookup"><span data-stu-id="0a4a3-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="0a4a3-151">网络 MOS</span><span class="sxs-lookup"><span data-stu-id="0a4a3-151">Network MOS</span></span>

  - <span data-ttu-id="0a4a3-152">网络 MOS 降级</span><span class="sxs-lookup"><span data-stu-id="0a4a3-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="0a4a3-153">发送 MOS</span><span class="sxs-lookup"><span data-stu-id="0a4a3-153">Sending MOS</span></span>

  - <span data-ttu-id="0a4a3-154">侦听 MOS</span><span class="sxs-lookup"><span data-stu-id="0a4a3-154">Listening MOS</span></span>

  - <span data-ttu-id="0a4a3-155">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="0a4a3-155">Packet Loss</span></span>

  - <span data-ttu-id="0a4a3-156">抖动</span><span class="sxs-lookup"><span data-stu-id="0a4a3-156">Jitter</span></span>

  - <span data-ttu-id="0a4a3-157">延迟</span><span class="sxs-lookup"><span data-stu-id="0a4a3-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

