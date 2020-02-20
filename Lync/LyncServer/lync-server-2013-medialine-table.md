---
title: Lync Server 2013： MediaLine 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf0e216d90af0d32a0e700661a653a13028e01a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="eb6c7-102">Lync Server 2013 中的 MediaLine 表</span><span class="sxs-lookup"><span data-stu-id="eb6c7-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb6c7-103">_**上次修改的主题：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="eb6c7-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="eb6c7-104">每个记录代表一个媒体行。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-104">Each record represents one media line.</span></span> <span data-ttu-id="eb6c7-105">（一个音频会话通常包含一个音频媒体线。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="eb6c7-106">一个音频和视频（A/V）会话通常包含一个音频媒体线和一个视频媒体线，但如果使用了会议设备或者使用了库视图，则会话可能包含两个视频媒体线路。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb6c7-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="eb6c7-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="eb6c7-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="eb6c7-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="eb6c7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-113">主</span><span class="sxs-lookup"><span data-stu-id="eb6c7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-114">从<a href="lync-server-2013-session-table.md">Lync Server 2013 中的会话表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-116">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-116">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-117">主</span><span class="sxs-lookup"><span data-stu-id="eb6c7-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-118">从<a href="lync-server-2013-session-table.md">Lync Server 2013 中的会话表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="eb6c7-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-121">主</span><span class="sxs-lookup"><span data-stu-id="eb6c7-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-122">0是主要音频，1是主要视频，2是全景视频，3是应用程序/桌面共享。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="eb6c7-123">此标签在单个会话中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="eb6c7-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-126">此列存在，但在 Microsoft Lync Server 2013 中未使用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="eb6c7-127">CallerConnectivityICE 和 CalleeConnectivityICE 列中捕获了用于媒体行的连接的相关信息。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-129">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-130">有关 bits 标志中所述的交互式连接建立（ICE）过程的信息。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="eb6c7-131">有关详细信息，请参阅可供下载的<em>经验丰富的监视服务器协议规范的质量</em>。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-133">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-134">与 CallerIceWarningFlags 相同，但在被叫方的一侧。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="eb6c7-135">有关详细信息，请参阅可供下载的<em>经验丰富的监视服务器协议规范的质量</em>。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-136"><strong>安全</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="eb6c7-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-138">正在使用的安全配置文件。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-138">The security profile in use.</span></span> <span data-ttu-id="eb6c7-139">0 为无，1 为 SRTP，2 为 V1。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="eb6c7-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-142">0 为 UDP，1 为 TCP。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-144">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-144">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-145">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-146">呼叫者的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-146">IP Address of the caller.</span></span> <span data-ttu-id="eb6c7-147">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-149">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-150">呼叫者使用的端口。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-152">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-152">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-153"> 对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-154">呼叫者的子网。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-154">The subnet of the caller.</span></span> <span data-ttu-id="eb6c7-155">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-157">位</span><span class="sxs-lookup"><span data-stu-id="eb6c7-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-158">1 表示呼叫者位于企业网络内部，0 表示呼叫者位于该网络外部。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-160">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-160">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-161">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-162">呼叫者的 mac 地址，从<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-164">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-164">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-165">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-166">呼叫者使用的 Lync Server A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="eb6c7-167">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-169">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-170">呼叫者在 A/V 边缘服务上使用的端口。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-172">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-172">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-173">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-174">呼叫者使用的捕获设备。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-174">Capture device used by the caller.</span></span> <span data-ttu-id="eb6c7-175">从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-177">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-177">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-178">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-179">呈现由呼叫者使用的设备。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-179">Render device used by caller.</span></span> <span data-ttu-id="eb6c7-180">从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-182">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-182">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-183">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-184">呼叫者捕获设备的驱动程序，从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-186">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-186">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-187">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-188">呼叫者的呈现设备的驱动程序，从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="eb6c7-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-191">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-192">指示呼叫者如何连接到网络。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="eb6c7-193">值是从<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表中</a>获取的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="eb6c7-194">对于 WiFi 连接，典型值为0（对于 WiFi 连接，为1）;对于以太网连接，为3。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-196">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-196">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-197">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-198">呼叫者的 BSSID （如果使用无线）。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="eb6c7-199"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中从 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-201">位</span><span class="sxs-lookup"><span data-stu-id="eb6c7-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb6c7-202">呼叫者的链接。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-202">The caller's link.</span></span> <span data-ttu-id="eb6c7-203">1 是虚拟专用网 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-205">小数（18，0）</span><span class="sxs-lookup"><span data-stu-id="eb6c7-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb6c7-206">呼叫者终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-208">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-208">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-209">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-210">呼叫接收器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-210">IP Address of the call receiver.</span></span> <span data-ttu-id="eb6c7-211">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-213">位</span><span class="sxs-lookup"><span data-stu-id="eb6c7-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb6c7-214">呼叫接收器使用的端口。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-216">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-216">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-217">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-218">被叫方的子网。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-218">Subnet of callee.</span></span> <span data-ttu-id="eb6c7-219">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-221">位</span><span class="sxs-lookup"><span data-stu-id="eb6c7-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-222">1表示呼叫接收器位于企业网络内，0表示呼叫接收器在网络外部。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-224">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-224">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-225">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-226">被叫方 Mac 地址。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-226">Callee Mac address.</span></span> <span data-ttu-id="eb6c7-227"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中从 MacAddress 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-229">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-229">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-230">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-231">呼叫接收器使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="eb6c7-232">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-234">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-235">呼叫接收器在 A/V 边缘服务上使用的端口。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-237">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-237">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-238">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-239">由呼叫接收器使用的捕获设备。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="eb6c7-240">从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-242">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-242">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-243">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-244">呈现呼叫接收器使用的设备。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-244">Render device used by the call receiver.</span></span> <span data-ttu-id="eb6c7-245">从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-247">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-247">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-248">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-249">呼叫接收器的捕获设备的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="eb6c7-250"><a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中从 DeviceDriver 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-252">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="eb6c7-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-253">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-254">呼叫接收器的呈现设备的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="eb6c7-255"><a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中从 DeviceDriver 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="eb6c7-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-258">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-259">指示被叫方如何连接到网络。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="eb6c7-260">值是从<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表中</a>获取的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="eb6c7-261">对于 WiFi 连接，典型值为0（对于 WiFi 连接，为1）;对于以太网连接，为3。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-263">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-263">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-264">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-265">被呼叫者的 BSSID （如果使用无线）。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="eb6c7-266"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中从 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-268">位</span><span class="sxs-lookup"><span data-stu-id="eb6c7-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-269">呼叫接收器的链接;1是虚拟专用网络（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-271">小数（18，0）</span><span class="sxs-lookup"><span data-stu-id="eb6c7-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-272">呼叫接收器终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-274">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="eb6c7-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-275">音频会话的窄带交谈 MOS（基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-277">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb6c7-278">这是在给定各种策略设置（TURN、API、SDP、策略服务器等）时应用于给定发送方流的实际带宽。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="eb6c7-279">不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="eb6c7-280">这基本上是发送流可禁止带宽预估设定的限制的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-282">smallint</span><span class="sxs-lookup"><span data-stu-id="eb6c7-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb6c7-283">这是所设定的带宽限制的来源。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="eb6c7-284">它描述带宽限制来自何处（"策略服务器"、"轮流服务器"、"模态" 等）。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="eb6c7-285"><a href="lync-server-2013-appliedbandwidthsource-table.md">在 Lync Server 2013 中从 AppliedBandwidthSource 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-287">位</span><span class="sxs-lookup"><span data-stu-id="eb6c7-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-288">指示是否收到来自呼叫者的指标;1为 "是"，null 值为 "否"。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-289"><strong>约定</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-290">位</span><span class="sxs-lookup"><span data-stu-id="eb6c7-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eb6c7-291">指示是否已收到来自呼叫接收器的指标;1为 "是"，null 值为 "否"。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-293">位</span><span class="sxs-lookup"><span data-stu-id="eb6c7-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb6c7-294">指示报表是针对会话的一部分还是完整会话。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="eb6c7-295">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-297">位</span><span class="sxs-lookup"><span data-stu-id="eb6c7-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb6c7-298">指示呼叫是否分类为较差呼叫（值为1）或正常呼叫（0）。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="eb6c7-299">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="eb6c7-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb6c7-302">指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="eb6c7-303">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="eb6c7-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb6c7-306">指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="eb6c7-307">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-309">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-309">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-310">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-311">发出呼叫的用户的反身 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="eb6c7-312">在使用 NAT （网络地址转换）的组织中，反身 IP 地址是代理服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="eb6c7-313">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-315">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-315">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-316">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-317">发出呼叫的用户所采用的 WiFi 驱动程序的设备说明。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="eb6c7-318">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-320">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-320">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-321">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-322">发出呼叫的用户所采用的 WiFi 驱动程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="eb6c7-323">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-325">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-325">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-326">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-327">接收呼叫的用户的反身 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="eb6c7-328">在使用 NAT （网络地址转换）的组织中，反身 IP 地址是代理服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="eb6c7-329">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6c7-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-331">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-331">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-332">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-333">接收呼叫的用户所使用的 WiFi 驱动程序的设备说明。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="eb6c7-334">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6c7-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="eb6c7-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="eb6c7-336">int</span><span class="sxs-lookup"><span data-stu-id="eb6c7-336">int</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-337">对外</span><span class="sxs-lookup"><span data-stu-id="eb6c7-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eb6c7-338">接收呼叫的用户所采用的 WiFi 驱动程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="eb6c7-339">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="eb6c7-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

