---
title: Lync Server 2013：MediaLine 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="52d5f-102">Lync Server 2013 中的 MediaLine 表</span><span class="sxs-lookup"><span data-stu-id="52d5f-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52d5f-103">_**主题上次修改时间:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="52d5f-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="52d5f-104">每条记录表示一个媒体行。</span><span class="sxs-lookup"><span data-stu-id="52d5f-104">Each record represents one media line.</span></span> <span data-ttu-id="52d5f-105">(一个音频会话通常包含一个音频媒体行。</span><span class="sxs-lookup"><span data-stu-id="52d5f-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="52d5f-106">一个音频和视频 (A/V) 会话通常包含一个音频媒体线和一个视频媒体行, 但如果使用了会议设备或使用了库视图, 则该会话可能包含两个视频媒体线。</span><span class="sxs-lookup"><span data-stu-id="52d5f-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52d5f-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="52d5f-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="52d5f-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="52d5f-110"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="52d5f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="52d5f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="52d5f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="52d5f-114">从<a href="lync-server-2013-session-table.md">Lync Server 2013 中的会话表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-116">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-116">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-117">Primary</span><span class="sxs-lookup"><span data-stu-id="52d5f-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="52d5f-118">从<a href="lync-server-2013-session-table.md">Lync Server 2013 中的会话表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="52d5f-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="52d5f-121">Primary</span><span class="sxs-lookup"><span data-stu-id="52d5f-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="52d5f-122">0是主音频, 1 是主视频, 2 是全景视频, 3 是应用程序/桌面共享。</span><span class="sxs-lookup"><span data-stu-id="52d5f-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="52d5f-123">此标签在单个会话中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="52d5f-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="52d5f-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-126">此列存在, 但未在 Microsoft Lync Server 2013 中使用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="52d5f-127">在 "CallerConnectivityICE" 和 "CalleeConnectivityICE" 列中捕获有关用于媒体行的连接的信息。</span><span class="sxs-lookup"><span data-stu-id="52d5f-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-129">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-130">有关在 bits 标志中描述的交互式连接建立 (ICE) 流程的信息。</span><span class="sxs-lookup"><span data-stu-id="52d5f-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="52d5f-131">有关详细信息, 请参阅可供下载的<em>体验质量监视服务器协议规范</em>。</span><span class="sxs-lookup"><span data-stu-id="52d5f-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-133">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-134">与 CallerIceWarningFlags 相同, 但在被调用方。</span><span class="sxs-lookup"><span data-stu-id="52d5f-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="52d5f-135">有关详细信息, 请参阅可供下载的<em>体验质量监视服务器协议规范</em>。</span><span class="sxs-lookup"><span data-stu-id="52d5f-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-136"><strong>安全性</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="52d5f-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-138">正在使用的安全配置文件。</span><span class="sxs-lookup"><span data-stu-id="52d5f-138">The security profile in use.</span></span> <span data-ttu-id="52d5f-139">0为 NONE, 1 为 SRTP, 2 为 V1。</span><span class="sxs-lookup"><span data-stu-id="52d5f-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="52d5f-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-142">0是 UDP, 1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="52d5f-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-144">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-144">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-145">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-146">呼叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52d5f-146">IP Address of the caller.</span></span> <span data-ttu-id="52d5f-147">有关详细信息, 请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="52d5f-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-149">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-150">呼叫方使用的端口。</span><span class="sxs-lookup"><span data-stu-id="52d5f-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-152">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-152">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-153"> 外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-154">呼叫方的子网。</span><span class="sxs-lookup"><span data-stu-id="52d5f-154">The subnet of the caller.</span></span> <span data-ttu-id="52d5f-155">有关详细信息, 请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="52d5f-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-157">bit</span><span class="sxs-lookup"><span data-stu-id="52d5f-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-158">1表示呼叫方位于企业网络内, 0 表示呼叫方位于网络外部。</span><span class="sxs-lookup"><span data-stu-id="52d5f-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-160">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-160">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-161">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-162">呼叫者的 mac 地址, 从<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-164">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-164">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-165">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-166">呼叫者使用的 Lync Server A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52d5f-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="52d5f-167">有关详细信息, 请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="52d5f-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-169">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-170">由呼叫者在 A/V 边缘服务上使用的端口。</span><span class="sxs-lookup"><span data-stu-id="52d5f-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-172">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-172">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-173">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-174">由呼叫者使用的捕获设备。</span><span class="sxs-lookup"><span data-stu-id="52d5f-174">Capture device used by the caller.</span></span> <span data-ttu-id="52d5f-175">从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-177">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-177">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-178">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-179">由呼叫者使用的渲染设备。</span><span class="sxs-lookup"><span data-stu-id="52d5f-179">Render device used by caller.</span></span> <span data-ttu-id="52d5f-180">从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-182">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-182">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-183">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-184">呼叫者捕获设备的驱动程序, 从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-186">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-186">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-187">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-188">呼叫者的呈现设备的驱动程序, 从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="52d5f-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="52d5f-191">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-192">指示呼叫者如何连接到网络。</span><span class="sxs-lookup"><span data-stu-id="52d5f-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="52d5f-193">从<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表中</a>获取值。</span><span class="sxs-lookup"><span data-stu-id="52d5f-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="52d5f-194">用于 WiFi 连接的有线连接 "1" 的典型值为 0;对于以太网连接, 请使用3。</span><span class="sxs-lookup"><span data-stu-id="52d5f-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-196">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-196">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-197">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-198">呼叫者的 BSSID (如果使用无线)。</span><span class="sxs-lookup"><span data-stu-id="52d5f-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="52d5f-199">从<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-201">bit</span><span class="sxs-lookup"><span data-stu-id="52d5f-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52d5f-202">呼叫者的链接。</span><span class="sxs-lookup"><span data-stu-id="52d5f-202">The caller's link.</span></span> <span data-ttu-id="52d5f-203">1是虚拟专用网络 (VPN), 0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="52d5f-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-205">十进制 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="52d5f-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52d5f-206">呼叫方终结点的网络链接速度 (以 bps 为的)。</span><span class="sxs-lookup"><span data-stu-id="52d5f-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-208">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-208">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-209">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-210">呼叫接收器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52d5f-210">IP Address of the call receiver.</span></span> <span data-ttu-id="52d5f-211">有关详细信息, 请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="52d5f-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-213">bit</span><span class="sxs-lookup"><span data-stu-id="52d5f-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52d5f-214">呼叫接收器使用的端口。</span><span class="sxs-lookup"><span data-stu-id="52d5f-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-216">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-216">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-217">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-218">被调用的子网。</span><span class="sxs-lookup"><span data-stu-id="52d5f-218">Subnet of callee.</span></span> <span data-ttu-id="52d5f-219">有关详细信息, 请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="52d5f-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-221">bit</span><span class="sxs-lookup"><span data-stu-id="52d5f-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-222">1表示呼叫接收器位于企业网络内, 0 表示呼叫接收器位于网络外部。</span><span class="sxs-lookup"><span data-stu-id="52d5f-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-224">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-224">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-225">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-226">被呼叫方 Mac 地址。</span><span class="sxs-lookup"><span data-stu-id="52d5f-226">Callee Mac address.</span></span> <span data-ttu-id="52d5f-227">从<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-229">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-229">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-230">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-231">呼叫接收器使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52d5f-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="52d5f-232">有关详细信息, 请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="52d5f-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-234">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-235">由呼叫接收器在 A/V 边缘服务上使用的端口。</span><span class="sxs-lookup"><span data-stu-id="52d5f-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-237">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-237">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-238">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-239">由呼叫接收器使用的捕获设备。</span><span class="sxs-lookup"><span data-stu-id="52d5f-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="52d5f-240">从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-242">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-242">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-243">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-244">由呼叫接收器使用的呈现设备。</span><span class="sxs-lookup"><span data-stu-id="52d5f-244">Render device used by the call receiver.</span></span> <span data-ttu-id="52d5f-245">从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-247">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-247">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-248">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-249">呼叫接收器的捕获设备的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="52d5f-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="52d5f-250">从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="52d5f-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="52d5f-253">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-254">呼叫接收器的呈现设备的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="52d5f-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="52d5f-255">从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="52d5f-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="52d5f-258">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-259">指明被呼叫方如何连接到网络。</span><span class="sxs-lookup"><span data-stu-id="52d5f-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="52d5f-260">从<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表中</a>获取值。</span><span class="sxs-lookup"><span data-stu-id="52d5f-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="52d5f-261">用于 WiFi 连接的有线连接 "1" 的典型值为 0;对于以太网连接, 请使用3。</span><span class="sxs-lookup"><span data-stu-id="52d5f-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-263">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-263">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-264">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-265">如果使用无线, 则被呼叫者的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="52d5f-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="52d5f-266">从<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-268">bit</span><span class="sxs-lookup"><span data-stu-id="52d5f-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-269">呼叫接收器的链接;1是虚拟专用网络 (VPN), 0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="52d5f-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-271">十进制 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="52d5f-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-272">呼叫接收器终结点的网络链接速度 (以 bps 为 bps)。</span><span class="sxs-lookup"><span data-stu-id="52d5f-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-274">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="52d5f-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-275">音频会话的 Narrowband 对话 MOS (基于两个音频流)。</span><span class="sxs-lookup"><span data-stu-id="52d5f-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-277">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52d5f-278">这是在给定各种策略设置 (TURN、API、SDP、策略服务器等) 上应用到给定发送端流的实际带宽。</span><span class="sxs-lookup"><span data-stu-id="52d5f-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="52d5f-279">此操作不会与有效的带宽混淆, 因为根据带宽估计, 可能会有较低的有效带宽。</span><span class="sxs-lookup"><span data-stu-id="52d5f-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="52d5f-280">这基本上是发送流可以通过带宽估计限制限制的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="52d5f-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-282">smallint</span><span class="sxs-lookup"><span data-stu-id="52d5f-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52d5f-283">这是所强加的带宽上限的来源。</span><span class="sxs-lookup"><span data-stu-id="52d5f-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="52d5f-284">它介绍带宽限制的来源 ("策略服务器"、"打开服务器"、"模态" 等)。</span><span class="sxs-lookup"><span data-stu-id="52d5f-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="52d5f-285">从<a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 中的 AppliedBandwidthSource 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="52d5f-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-286"><strong>呼叫者</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-287">bit</span><span class="sxs-lookup"><span data-stu-id="52d5f-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-288">指示是否收到来自呼叫方的指标;1为 "是", null 值为 "否"。</span><span class="sxs-lookup"><span data-stu-id="52d5f-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-289"><strong>被叫方</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-290">bit</span><span class="sxs-lookup"><span data-stu-id="52d5f-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52d5f-291">指示是否收到来自呼叫接收器的指标;1为 "是", null 值为 "否"。</span><span class="sxs-lookup"><span data-stu-id="52d5f-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-293">bit</span><span class="sxs-lookup"><span data-stu-id="52d5f-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52d5f-294">指示报表是用于会话的一部分还是整个会话。</span><span class="sxs-lookup"><span data-stu-id="52d5f-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="52d5f-295">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-297">bit</span><span class="sxs-lookup"><span data-stu-id="52d5f-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52d5f-298">指示呼叫是否分类为不太好的通话 (值为 1) 或正常呼叫 (0)。</span><span class="sxs-lookup"><span data-stu-id="52d5f-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="52d5f-299">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="52d5f-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52d5f-302">指示呼叫者是否使用 ICE 协议 (Internet 连接建立) 连接到网络。</span><span class="sxs-lookup"><span data-stu-id="52d5f-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="52d5f-303">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="52d5f-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52d5f-306">指示呼叫者是否使用 ICE 协议 (Internet 连接建立) 连接到网络。</span><span class="sxs-lookup"><span data-stu-id="52d5f-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="52d5f-307">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-309">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-309">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-310">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-311">发出呼叫的用户的自身 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52d5f-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="52d5f-312">在使用 NAT (网络地址转换) 的组织中, 自身 IP 地址是代理服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52d5f-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="52d5f-313">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-315">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-315">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-316">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-317">发出呼叫的用户所使用的 WiFi 驱动程序的设备说明。</span><span class="sxs-lookup"><span data-stu-id="52d5f-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="52d5f-318">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-320">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-320">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-321">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-322">发出呼叫的用户所使用的 WiFi 驱动程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="52d5f-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="52d5f-323">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-325">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-325">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-326">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-327">接收呼叫的用户的自身 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52d5f-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="52d5f-328">在使用 NAT (网络地址转换) 的组织中, 自身 IP 地址是代理服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52d5f-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="52d5f-329">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52d5f-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-331">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-331">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-332">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-333">接收呼叫的用户所使用的 WiFi 驱动程序的设备说明。</span><span class="sxs-lookup"><span data-stu-id="52d5f-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="52d5f-334">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52d5f-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="52d5f-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="52d5f-336">int</span><span class="sxs-lookup"><span data-stu-id="52d5f-336">int</span></span></p></td>
<td><p><span data-ttu-id="52d5f-337">外表</span><span class="sxs-lookup"><span data-stu-id="52d5f-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="52d5f-338">接收呼叫的用户所使用的 WiFi 驱动程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="52d5f-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="52d5f-339">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d5f-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

