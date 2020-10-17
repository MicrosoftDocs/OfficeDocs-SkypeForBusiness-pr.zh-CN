---
title: Lync Server 2013： QoE 报告
description: Lync Server 2013： QoE 报告。
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
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571398"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="21d70-103">Lync Server 2013 中的 QoE 报告</span><span class="sxs-lookup"><span data-stu-id="21d70-103">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d70-104">_**上次修改的主题：** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="21d70-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="21d70-105">QoE 摘要/趋势报告</span><span class="sxs-lookup"><span data-stu-id="21d70-105">QoE summary/trend reports</span></span>

<span data-ttu-id="21d70-106">QoE 摘要/趋势报告可用于查找一天的高峰使用时间，并在这些时间内检查媒体质量，以帮助确保组织的网络资源足够。</span><span class="sxs-lookup"><span data-stu-id="21d70-106">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="21d70-107">您的组织还可以使用报告中提供的多个筛选器来隔离特定位置、客户端和设备类型以及服务器的性能号码。</span><span class="sxs-lookup"><span data-stu-id="21d70-107">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="21d70-108">QoE 摘要/趋势报告包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="21d70-108">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="21d70-109">UC 到 UC 摘要/趋势报告</span><span class="sxs-lookup"><span data-stu-id="21d70-109">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="21d70-110">PSTN 摘要/趋势报告</span><span class="sxs-lookup"><span data-stu-id="21d70-110">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="21d70-111">会议摘要/趋势报告</span><span class="sxs-lookup"><span data-stu-id="21d70-111">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="21d70-112">QoE 性能报告</span><span class="sxs-lookup"><span data-stu-id="21d70-112">QoE performance reports</span></span>

<span data-ttu-id="21d70-113">QoE 性能报告提供了有关三个报告的详细信息，这些报告集中在中介服务器、A/V 会议服务器和终结点位置的 QoE 性能上。</span><span class="sxs-lookup"><span data-stu-id="21d70-113">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="21d70-114">中介服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="21d70-114">Mediation server performance report</span></span>

<span data-ttu-id="21d70-115">中介服务器性能报告列出了在指定时间段内由一个或多个中介实现的指标。</span><span class="sxs-lookup"><span data-stu-id="21d70-115">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="21d70-116">统一通信 (UC) 到中介服务器腿的指标和每个呼叫的中介服务器到网关腿分别报告。</span><span class="sxs-lookup"><span data-stu-id="21d70-116">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="21d70-117">使用此报告可比较组织的各种中介服务器的容量和性能。</span><span class="sxs-lookup"><span data-stu-id="21d70-117">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="21d70-118">对于每个中介服务器 (和每个呼叫腿) ，报告将显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="21d70-118">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="21d70-119">呼叫数</span><span class="sxs-lookup"><span data-stu-id="21d70-119">Number of calls</span></span>

  - <span data-ttu-id="21d70-120">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="21d70-120">Packet Loss</span></span>

  - <span data-ttu-id="21d70-121">往返时间</span><span class="sxs-lookup"><span data-stu-id="21d70-121">Round Trip Time</span></span>

  - <span data-ttu-id="21d70-122">抖动</span><span class="sxs-lookup"><span data-stu-id="21d70-122">Jitter</span></span>

  - <span data-ttu-id="21d70-123">会话平均意见分数 (MOS) </span><span class="sxs-lookup"><span data-stu-id="21d70-123">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="21d70-124">发送 MOS</span><span class="sxs-lookup"><span data-stu-id="21d70-124">Sending MOS</span></span>

  - <span data-ttu-id="21d70-125">侦听 MOS</span><span class="sxs-lookup"><span data-stu-id="21d70-125">Listening MOS</span></span>

  - <span data-ttu-id="21d70-126">网络 MOS</span><span class="sxs-lookup"><span data-stu-id="21d70-126">Network MOS</span></span>

  - <span data-ttu-id="21d70-127">网络 MOS 降级</span><span class="sxs-lookup"><span data-stu-id="21d70-127">Network MOS Degradation</span></span>

  - <span data-ttu-id="21d70-128">回显返回</span><span class="sxs-lookup"><span data-stu-id="21d70-128">Echo Return</span></span>

  - <span data-ttu-id="21d70-129">信号级别</span><span class="sxs-lookup"><span data-stu-id="21d70-129">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="21d70-130">A/V 会议服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="21d70-130">A/V conferencing server performance report</span></span>

<span data-ttu-id="21d70-131">A/V 会议服务器性能报告提供了在指定时间段内由一个或多个 A/V 会议服务器实现的指标的列表。</span><span class="sxs-lookup"><span data-stu-id="21d70-131">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="21d70-132">此报告可用于比较组织的各种 A/V 会议服务器的容量和性能。</span><span class="sxs-lookup"><span data-stu-id="21d70-132">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="21d70-133">您的组织还可以隔离报告以仅显示特定客户端类型（如 Lync 客户端或 PSTN 客户端）的体验。</span><span class="sxs-lookup"><span data-stu-id="21d70-133">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="21d70-134">对于每个 A/V 会议服务器，报告将显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="21d70-134">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="21d70-135">会议数</span><span class="sxs-lookup"><span data-stu-id="21d70-135">Number of conferences</span></span>

  - <span data-ttu-id="21d70-136">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="21d70-136">Packet Loss</span></span>

  - <span data-ttu-id="21d70-137">往返时间</span><span class="sxs-lookup"><span data-stu-id="21d70-137">Round Trip Time</span></span>

  - <span data-ttu-id="21d70-138">抖动</span><span class="sxs-lookup"><span data-stu-id="21d70-138">Jitter</span></span>

  - <span data-ttu-id="21d70-139">会话平均意见分数 (MOS) </span><span class="sxs-lookup"><span data-stu-id="21d70-139">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="21d70-140">发送 MOS</span><span class="sxs-lookup"><span data-stu-id="21d70-140">Sending MOS</span></span>

  - <span data-ttu-id="21d70-141">侦听 MOS</span><span class="sxs-lookup"><span data-stu-id="21d70-141">Listening MOS</span></span>

  - <span data-ttu-id="21d70-142">网络 MOS</span><span class="sxs-lookup"><span data-stu-id="21d70-142">Network MOS</span></span>

  - <span data-ttu-id="21d70-143">网络 MOS 降级</span><span class="sxs-lookup"><span data-stu-id="21d70-143">Network MOS Degradation</span></span>

  - <span data-ttu-id="21d70-144">回显返回</span><span class="sxs-lookup"><span data-stu-id="21d70-144">Echo Return</span></span>

  - <span data-ttu-id="21d70-145">信号级别</span><span class="sxs-lookup"><span data-stu-id="21d70-145">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="21d70-146">基于位置的性能报告</span><span class="sxs-lookup"><span data-stu-id="21d70-146">Location-based performance report</span></span>

<span data-ttu-id="21d70-147">Location-Based 性能报告提供了一个网络位置列表，每个位置都显示了每个预先确定的质量范围内的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="21d70-147">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="21d70-148">此报告的目标是提供对各种位置的组织电话呼叫的媒体质量的深入了解，以便您能够识别出性能不佳的位置，并在组织的不同位置查看不同的媒体质量等级。</span><span class="sxs-lookup"><span data-stu-id="21d70-148">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="21d70-149">显示报表时，将显示不同的指标表，即组织决定报告的每个指标的一个表。</span><span class="sxs-lookup"><span data-stu-id="21d70-149">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="21d70-150">您可以从此报告的以下指标中进行选择：</span><span class="sxs-lookup"><span data-stu-id="21d70-150">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="21d70-151">会话平均意见分数 (MOS) </span><span class="sxs-lookup"><span data-stu-id="21d70-151">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="21d70-152">网络 MOS</span><span class="sxs-lookup"><span data-stu-id="21d70-152">Network MOS</span></span>

  - <span data-ttu-id="21d70-153">网络 MOS 降级</span><span class="sxs-lookup"><span data-stu-id="21d70-153">Network MOS Degradation</span></span>

  - <span data-ttu-id="21d70-154">发送 MOS</span><span class="sxs-lookup"><span data-stu-id="21d70-154">Sending MOS</span></span>

  - <span data-ttu-id="21d70-155">侦听 MOS</span><span class="sxs-lookup"><span data-stu-id="21d70-155">Listening MOS</span></span>

  - <span data-ttu-id="21d70-156">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="21d70-156">Packet Loss</span></span>

  - <span data-ttu-id="21d70-157">抖动</span><span class="sxs-lookup"><span data-stu-id="21d70-157">Jitter</span></span>

  - <span data-ttu-id="21d70-158">延迟</span><span class="sxs-lookup"><span data-stu-id="21d70-158">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

