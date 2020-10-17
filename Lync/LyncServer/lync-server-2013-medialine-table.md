---
title: Lync Server 2013： MediaLine 表
description: Lync Server 2013： MediaLine 表。
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
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572108"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="e64c5-103">Lync Server 2013 中的 MediaLine 表</span><span class="sxs-lookup"><span data-stu-id="e64c5-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e64c5-104">_**上次修改的主题：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="e64c5-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="e64c5-105">每个记录代表一个媒体行。</span><span class="sxs-lookup"><span data-stu-id="e64c5-105">Each record represents one media line.</span></span> <span data-ttu-id="e64c5-106"> (一个音频会话通常包含一个音频媒体线。</span><span class="sxs-lookup"><span data-stu-id="e64c5-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="e64c5-107">一个音频和视频 (A/V) 会话通常包含一个音频媒体线和一个视频媒体线，但如果使用了会议设备或使用了 "库视图"，则该会话可能包含两个视频媒体线路。</span><span class="sxs-lookup"><span data-stu-id="e64c5-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e64c5-108"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e64c5-109"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e64c5-110"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e64c5-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e64c5-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="e64c5-114">主</span><span class="sxs-lookup"><span data-stu-id="e64c5-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="e64c5-115">从 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的会话表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-117">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-117">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-118">主</span><span class="sxs-lookup"><span data-stu-id="e64c5-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="e64c5-119">从 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的会话表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-120"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-121">tinyint</span><span class="sxs-lookup"><span data-stu-id="e64c5-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e64c5-122">主</span><span class="sxs-lookup"><span data-stu-id="e64c5-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="e64c5-123">0是主要音频，1是主要视频，2是全景视频，3是应用程序/桌面共享。</span><span class="sxs-lookup"><span data-stu-id="e64c5-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="e64c5-124">此标签在单个会话中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-125"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-126">tinyint</span><span class="sxs-lookup"><span data-stu-id="e64c5-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-127">此列存在，但在 Microsoft Lync Server 2013 中未使用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e64c5-128">CallerConnectivityICE 和 CalleeConnectivityICE 列中捕获了用于媒体行的连接的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e64c5-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-129"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-130">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-131">有关交互式连接建立 (ICE) 过程的信息，如 bits 标志中所述。</span><span class="sxs-lookup"><span data-stu-id="e64c5-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="e64c5-132">有关详细信息，请参阅可供下载的 <em>经验丰富的监视服务器协议规范的质量</em>。</span><span class="sxs-lookup"><span data-stu-id="e64c5-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-133"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-134">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-135">与 CallerIceWarningFlags 相同，但在被叫方的一侧。</span><span class="sxs-lookup"><span data-stu-id="e64c5-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="e64c5-136">有关详细信息，请参阅可供下载的 <em>经验丰富的监视服务器协议规范的质量</em>。</span><span class="sxs-lookup"><span data-stu-id="e64c5-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-137"><strong>安全性</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-138">tinyint</span><span class="sxs-lookup"><span data-stu-id="e64c5-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-139">正在使用的安全配置文件。</span><span class="sxs-lookup"><span data-stu-id="e64c5-139">The security profile in use.</span></span> <span data-ttu-id="e64c5-140">0 为无，1 为 SRTP，2 为 V1。</span><span class="sxs-lookup"><span data-stu-id="e64c5-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-141"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-142">tinyint</span><span class="sxs-lookup"><span data-stu-id="e64c5-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-143">0 为 UDP，1 为 TCP。</span><span class="sxs-lookup"><span data-stu-id="e64c5-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-144"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-145">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-145">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-146">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-147">呼叫者的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e64c5-147">IP Address of the caller.</span></span> <span data-ttu-id="e64c5-148">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e64c5-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-149"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-150">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-151">呼叫者使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e64c5-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-152"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-153">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-153">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-154"> 对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-155">呼叫者的子网。</span><span class="sxs-lookup"><span data-stu-id="e64c5-155">The subnet of the caller.</span></span> <span data-ttu-id="e64c5-156">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e64c5-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-157"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-158">位</span><span class="sxs-lookup"><span data-stu-id="e64c5-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-159">1 表示呼叫者位于企业网络内部，0 表示呼叫者位于该网络外部。</span><span class="sxs-lookup"><span data-stu-id="e64c5-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-160"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-161">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-161">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-162">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-163">呼叫者的 mac 地址，从 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-164"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-165">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-165">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-166">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-167">呼叫者使用的 Lync Server A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e64c5-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="e64c5-168">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e64c5-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-169"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-170">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-171">呼叫者在 A/V 边缘服务上使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e64c5-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-172"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-173">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-173">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-174">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-175">呼叫者使用的捕获设备。</span><span class="sxs-lookup"><span data-stu-id="e64c5-175">Capture device used by the caller.</span></span> <span data-ttu-id="e64c5-176">从 <a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-177"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-178">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-178">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-179">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-180">呈现由呼叫者使用的设备。</span><span class="sxs-lookup"><span data-stu-id="e64c5-180">Render device used by caller.</span></span> <span data-ttu-id="e64c5-181">从 <a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-182"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-183">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-183">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-184">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-185">呼叫者捕获设备的驱动程序，从 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-186"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-187">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-187">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-188">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-189">呼叫者的呈现设备的驱动程序，从 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-190"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="e64c5-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e64c5-192">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-193">指示呼叫者如何连接到网络。</span><span class="sxs-lookup"><span data-stu-id="e64c5-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="e64c5-194">值是从 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表中</a>获取的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="e64c5-195">对于 WiFi 连接，典型值为0（对于 WiFi 连接，为1）;对于以太网连接，为3。</span><span class="sxs-lookup"><span data-stu-id="e64c5-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-196"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-197">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-197">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-198">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-199">呼叫者的 BSSID （如果使用无线）。</span><span class="sxs-lookup"><span data-stu-id="e64c5-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="e64c5-200"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中从 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-201"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-202">位</span><span class="sxs-lookup"><span data-stu-id="e64c5-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e64c5-203">呼叫者的链接。</span><span class="sxs-lookup"><span data-stu-id="e64c5-203">The caller's link.</span></span> <span data-ttu-id="e64c5-204">1 是虚拟专用网 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="e64c5-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-205"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-206">十进制 (18，0) </span><span class="sxs-lookup"><span data-stu-id="e64c5-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e64c5-207">呼叫者终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="e64c5-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-208"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-209">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-209">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-210">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-211">呼叫接收器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e64c5-211">IP Address of the call receiver.</span></span> <span data-ttu-id="e64c5-212">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e64c5-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-213"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-214">位</span><span class="sxs-lookup"><span data-stu-id="e64c5-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e64c5-215">呼叫接收器使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e64c5-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-216"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-217">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-217">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-218">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-219">被叫方的子网。</span><span class="sxs-lookup"><span data-stu-id="e64c5-219">Subnet of callee.</span></span> <span data-ttu-id="e64c5-220">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e64c5-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-221"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-222">位</span><span class="sxs-lookup"><span data-stu-id="e64c5-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-223">1表示呼叫接收器位于企业网络内，0表示呼叫接收器在网络外部。</span><span class="sxs-lookup"><span data-stu-id="e64c5-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-224"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-225">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-225">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-226">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-227">被叫方 Mac 地址。</span><span class="sxs-lookup"><span data-stu-id="e64c5-227">Callee Mac address.</span></span> <span data-ttu-id="e64c5-228"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中从 MacAddress 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-229"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-230">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-230">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-231">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-232">呼叫接收器使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e64c5-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="e64c5-233">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e64c5-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-234"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-235">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-236">呼叫接收器在 A/V 边缘服务上使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e64c5-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-237"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-238">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-238">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-239">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-240">由呼叫接收器使用的捕获设备。</span><span class="sxs-lookup"><span data-stu-id="e64c5-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="e64c5-241">从 <a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-242"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-243">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-243">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-244">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-245">呈现呼叫接收器使用的设备。</span><span class="sxs-lookup"><span data-stu-id="e64c5-245">Render device used by the call receiver.</span></span> <span data-ttu-id="e64c5-246">从 <a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-247"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-248">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-248">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-249">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-250">呼叫接收器的捕获设备的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e64c5-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="e64c5-251"><a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中从 DeviceDriver 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-252"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-253">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="e64c5-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e64c5-254">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-255">呼叫接收器的呈现设备的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e64c5-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="e64c5-256"><a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中从 DeviceDriver 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-257"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-258">tinyint</span><span class="sxs-lookup"><span data-stu-id="e64c5-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e64c5-259">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-260">指示被叫方如何连接到网络。</span><span class="sxs-lookup"><span data-stu-id="e64c5-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="e64c5-261">值是从 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表中</a>获取的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="e64c5-262">对于 WiFi 连接，典型值为0（对于 WiFi 连接，为1）;对于以太网连接，为3。</span><span class="sxs-lookup"><span data-stu-id="e64c5-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-263"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-264">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-264">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-265">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-266">被呼叫者的 BSSID （如果使用无线）。</span><span class="sxs-lookup"><span data-stu-id="e64c5-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="e64c5-267"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中从 MacAddress 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-268"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-269">位</span><span class="sxs-lookup"><span data-stu-id="e64c5-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-270">呼叫接收器的链接;1是虚拟专用网络 (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="e64c5-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-271"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-272">十进制 (18，0) </span><span class="sxs-lookup"><span data-stu-id="e64c5-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-273">呼叫接收器终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="e64c5-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-274"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-275">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e64c5-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-276">音频会话的窄带交谈 MOS（基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="e64c5-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-277"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-278">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e64c5-279">这是在给定各种策略设置 (TURN、API、SDP、策略服务器等) 的情况下应用于给定发送方流的实际带宽。</span><span class="sxs-lookup"><span data-stu-id="e64c5-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="e64c5-280">不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。</span><span class="sxs-lookup"><span data-stu-id="e64c5-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="e64c5-281">这基本上是发送流可禁止带宽预估设定的限制的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="e64c5-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-282"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-283">smallint</span><span class="sxs-lookup"><span data-stu-id="e64c5-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e64c5-284">这是所设定的带宽限制的来源。</span><span class="sxs-lookup"><span data-stu-id="e64c5-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="e64c5-285">它描述带宽限制来自 ( "策略服务器"、"轮流服务器"、"模态"，等等) 。</span><span class="sxs-lookup"><span data-stu-id="e64c5-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="e64c5-286"><a href="lync-server-2013-appliedbandwidthsource-table.md">在 Lync Server 2013 中从 AppliedBandwidthSource 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e64c5-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-287"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-288">位</span><span class="sxs-lookup"><span data-stu-id="e64c5-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-289">指示是否收到来自呼叫者的指标;1为 "是"，null 值为 "否"。</span><span class="sxs-lookup"><span data-stu-id="e64c5-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-290"><strong>约定</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-291">位</span><span class="sxs-lookup"><span data-stu-id="e64c5-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e64c5-292">指示是否已收到来自呼叫接收器的指标;1为 "是"，null 值为 "否"。</span><span class="sxs-lookup"><span data-stu-id="e64c5-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-293"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-294">位</span><span class="sxs-lookup"><span data-stu-id="e64c5-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e64c5-295">指示报表是针对会话的一部分还是完整会话。</span><span class="sxs-lookup"><span data-stu-id="e64c5-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="e64c5-296">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-297"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-298">位</span><span class="sxs-lookup"><span data-stu-id="e64c5-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e64c5-299">指示是否将呼叫分类为较差的呼叫 (值为 1) 或 (0) 的正常呼叫。</span><span class="sxs-lookup"><span data-stu-id="e64c5-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="e64c5-300">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-301"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-302">tinyInt</span><span class="sxs-lookup"><span data-stu-id="e64c5-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e64c5-303">指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。</span><span class="sxs-lookup"><span data-stu-id="e64c5-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="e64c5-304">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-305"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-306">tinyint</span><span class="sxs-lookup"><span data-stu-id="e64c5-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e64c5-307">指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。</span><span class="sxs-lookup"><span data-stu-id="e64c5-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="e64c5-308">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-309"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-310">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-310">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-311">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-312">发出呼叫的用户的反身 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e64c5-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="e64c5-313">在使用 NAT (网络地址转换) 的组织中，反身 IP 地址是代理服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e64c5-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="e64c5-314">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-315"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-316">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-316">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-317">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-318">发出呼叫的用户所采用的 WiFi 驱动程序的设备说明。</span><span class="sxs-lookup"><span data-stu-id="e64c5-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="e64c5-319">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-320"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-321">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-321">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-322">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-323">发出呼叫的用户所采用的 WiFi 驱动程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="e64c5-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="e64c5-324">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-325"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-326">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-326">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-327">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-328">接收呼叫的用户的反身 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e64c5-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="e64c5-329">在使用 NAT (网络地址转换) 的组织中，反身 IP 地址是代理服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e64c5-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="e64c5-330">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e64c5-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-332">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-332">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-333">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-334">接收呼叫的用户所使用的 WiFi 驱动程序的设备说明。</span><span class="sxs-lookup"><span data-stu-id="e64c5-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="e64c5-335">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e64c5-336"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e64c5-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e64c5-337">int</span><span class="sxs-lookup"><span data-stu-id="e64c5-337">int</span></span></p></td>
<td><p><span data-ttu-id="e64c5-338">对外</span><span class="sxs-lookup"><span data-stu-id="e64c5-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e64c5-339">接收呼叫的用户所采用的 WiFi 驱动程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="e64c5-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="e64c5-340">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e64c5-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

