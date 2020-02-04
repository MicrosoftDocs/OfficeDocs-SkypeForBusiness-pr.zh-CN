---
title: Lync Server 2013： MediaLine 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="70543-102">Lync Server 2013 中的 MediaLine 视图</span><span class="sxs-lookup"><span data-stu-id="70543-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70543-103">_**主题上次修改时间：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="70543-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="70543-104">MediaLine 视图存储有关数据库中每个媒体行的信息。</span><span class="sxs-lookup"><span data-stu-id="70543-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="70543-105">一个音频会话通常包含一个音频媒体行。</span><span class="sxs-lookup"><span data-stu-id="70543-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="70543-106">一个音频和视频（A/V）会话通常包含一个音频媒体线和一个视频媒体行;但是，如果使用了会议设备或使用了库视图，则会话可能包含两个视频媒体线。</span><span class="sxs-lookup"><span data-stu-id="70543-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="70543-107">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="70543-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70543-108">列</span><span class="sxs-lookup"><span data-stu-id="70543-108">Column</span></span></th>
<th><span data-ttu-id="70543-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="70543-109">Data Type</span></span></th>
<th><span data-ttu-id="70543-110">更多信息</span><span class="sxs-lookup"><span data-stu-id="70543-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70543-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="70543-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="70543-112">datetime</span><span class="sxs-lookup"><span data-stu-id="70543-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="70543-113">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="70543-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="70543-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="70543-115">int</span><span class="sxs-lookup"><span data-stu-id="70543-115">int</span></span></p></td>
<td><p><span data-ttu-id="70543-116">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="70543-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="70543-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="70543-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="70543-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="70543-119">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="70543-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="70543-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="70543-121">int</span><span class="sxs-lookup"><span data-stu-id="70543-121">int</span></span></p></td>
<td><p><span data-ttu-id="70543-122">有关在呼叫者的位标志中描述的交互式连接建立（ICE）流程的信息。</span><span class="sxs-lookup"><span data-stu-id="70543-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="70543-123">有关详细信息，请参阅体验质量监视服务器协议规范。</span><span class="sxs-lookup"><span data-stu-id="70543-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="70543-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="70543-125">int</span><span class="sxs-lookup"><span data-stu-id="70543-125">int</span></span></p></td>
<td><p><span data-ttu-id="70543-126">有关被调用方的位标志中所述的交互式连接建立（ICE）流程的信息。</span><span class="sxs-lookup"><span data-stu-id="70543-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="70543-127">有关详细信息，请参阅体验质量监视服务器协议规范。</span><span class="sxs-lookup"><span data-stu-id="70543-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-128">安全性</span><span class="sxs-lookup"><span data-stu-id="70543-128">Security</span></span></p></td>
<td><p><span data-ttu-id="70543-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="70543-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="70543-130">安全配置文件正在使用。</span><span class="sxs-lookup"><span data-stu-id="70543-130">Security profile in use.</span></span> <span data-ttu-id="70543-131">0为 NONE，1为 SRTP，2为 V1。</span><span class="sxs-lookup"><span data-stu-id="70543-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-132">Transport</span><span class="sxs-lookup"><span data-stu-id="70543-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="70543-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="70543-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="70543-134">传输类型。</span><span class="sxs-lookup"><span data-stu-id="70543-134">Transport type.</span></span> <span data-ttu-id="70543-135">0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="70543-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="70543-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="70543-137">var （50）</span><span class="sxs-lookup"><span data-stu-id="70543-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="70543-138">呼叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-138">IP address of the caller.</span></span> <span data-ttu-id="70543-139">这可以是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="70543-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="70543-141">int</span><span class="sxs-lookup"><span data-stu-id="70543-141">int</span></span></p></td>
<td><p><span data-ttu-id="70543-142">呼叫方使用的端口。</span><span class="sxs-lookup"><span data-stu-id="70543-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="70543-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="70543-144">bit</span><span class="sxs-lookup"><span data-stu-id="70543-144">bit</span></span></p></td>
<td><p><span data-ttu-id="70543-145">指示呼叫者是否在组织网络内。</span><span class="sxs-lookup"><span data-stu-id="70543-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="70543-146">1表示呼叫方位于企业网络内。</span><span class="sxs-lookup"><span data-stu-id="70543-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="70543-147">0表示呼叫方位于网络外部。</span><span class="sxs-lookup"><span data-stu-id="70543-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="70543-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="70543-149">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-150">呼叫方使用的网络接口的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="70543-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="70543-152">var （50）</span><span class="sxs-lookup"><span data-stu-id="70543-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="70543-153">呼叫方使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="70543-154">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="70543-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="70543-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="70543-156">int</span><span class="sxs-lookup"><span data-stu-id="70543-156">int</span></span></p></td>
<td><p><span data-ttu-id="70543-157">由呼叫方使用的 A/V 边缘服务使用的端口。</span><span class="sxs-lookup"><span data-stu-id="70543-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="70543-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="70543-159">var （50）</span><span class="sxs-lookup"><span data-stu-id="70543-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="70543-160">由 A/V 边缘服务报告的呼叫者的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="70543-161">如果客户端位于 NAT 后面，则该地址可能与 CallerIPAddr 不同，例如。</span><span class="sxs-lookup"><span data-stu-id="70543-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="70543-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="70543-163">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-164">呼叫方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="70543-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="70543-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="70543-166">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-167">调用方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="70543-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="70543-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="70543-169">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-170">呼叫方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="70543-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="70543-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="70543-172">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-173">呼叫方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="70543-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="70543-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="70543-175">varchar （256</span><span class="sxs-lookup"><span data-stu-id="70543-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="70543-176">呼叫方的 Wifi 驱动程序说明。</span><span class="sxs-lookup"><span data-stu-id="70543-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="70543-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="70543-178">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-179">呼叫方的 Wifi 驱动程序版本。</span><span class="sxs-lookup"><span data-stu-id="70543-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="70543-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="70543-181">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-182">呼叫方网络连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="70543-182">Details of caller’s network connection.</span></span> <span data-ttu-id="70543-183">有关详细信息，请参阅<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a>。</span><span class="sxs-lookup"><span data-stu-id="70543-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="70543-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="70543-185">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-186">呼叫方 WiFi 连接使用的基本服务设置标识符。</span><span class="sxs-lookup"><span data-stu-id="70543-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="70543-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="70543-188">bit</span><span class="sxs-lookup"><span data-stu-id="70543-188">bit</span></span></p></td>
<td><p><span data-ttu-id="70543-189">指示呼叫者是否通过虚拟专用网络连接。</span><span class="sxs-lookup"><span data-stu-id="70543-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="70543-190">1是虚拟专用网络（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="70543-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="70543-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="70543-192">var （50）</span><span class="sxs-lookup"><span data-stu-id="70543-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="70543-193">被呼叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-193">IP address of the callee.</span></span> <span data-ttu-id="70543-194">这可以是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="70543-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="70543-196">int</span><span class="sxs-lookup"><span data-stu-id="70543-196">int</span></span></p></td>
<td><p><span data-ttu-id="70543-197">被呼叫方使用的端口。</span><span class="sxs-lookup"><span data-stu-id="70543-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="70543-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="70543-199">bit</span><span class="sxs-lookup"><span data-stu-id="70543-199">bit</span></span></p></td>
<td><p><span data-ttu-id="70543-200">指示被调用方是否位于企业网络内。</span><span class="sxs-lookup"><span data-stu-id="70543-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="70543-201">1表示被呼叫方位于企业网络内，0表示被呼叫方位于网络外部。</span><span class="sxs-lookup"><span data-stu-id="70543-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="70543-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="70543-203">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-204">被呼叫方使用的网络接口的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="70543-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="70543-206">var （50）</span><span class="sxs-lookup"><span data-stu-id="70543-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="70543-207">被呼叫方使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="70543-208">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="70543-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="70543-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="70543-210">int</span><span class="sxs-lookup"><span data-stu-id="70543-210">int</span></span></p></td>
<td><p><span data-ttu-id="70543-211">用于由被呼叫方使用的 A/V 边缘服务的端口。</span><span class="sxs-lookup"><span data-stu-id="70543-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="70543-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="70543-213">var （50）</span><span class="sxs-lookup"><span data-stu-id="70543-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="70543-214">由 A/V 边缘服务报告的被呼叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="70543-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="70543-215">如果客户端位于 NAT 后面，则该地址可能与 CalleeIPAddr 不同，例如。</span><span class="sxs-lookup"><span data-stu-id="70543-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="70543-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="70543-217">var （50）</span><span class="sxs-lookup"><span data-stu-id="70543-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="70543-218">被调用方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="70543-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="70543-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="70543-220">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-221">被调用方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="70543-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="70543-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="70543-223">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-224">被调用方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="70543-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="70543-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="70543-226">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-227">被调用方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="70543-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="70543-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="70543-229">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-230">被呼叫方的 Wifi 驱动程序说明。</span><span class="sxs-lookup"><span data-stu-id="70543-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="70543-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="70543-232">varchar （256</span><span class="sxs-lookup"><span data-stu-id="70543-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="70543-233">被呼叫方的 Wifi 驱动程序版本。</span><span class="sxs-lookup"><span data-stu-id="70543-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="70543-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="70543-235">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-236">被呼叫方的网络连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="70543-236">Details of callee’s network connection.</span></span> <span data-ttu-id="70543-237">有关详细信息，请参阅<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a>。</span><span class="sxs-lookup"><span data-stu-id="70543-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="70543-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="70543-239">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-240">被呼叫方的 WiFi 连接使用的基本服务设置标识符。</span><span class="sxs-lookup"><span data-stu-id="70543-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="70543-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="70543-242">bit</span><span class="sxs-lookup"><span data-stu-id="70543-242">bit</span></span></p></td>
<td><p><span data-ttu-id="70543-243">指示被调用方是否通过虚拟专用网络进行连接。</span><span class="sxs-lookup"><span data-stu-id="70543-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="70543-244">1是虚拟专用网络（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="70543-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="70543-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="70543-246">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="70543-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="70543-247">音频会话的 Narrowband 对话 MOS （基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="70543-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="70543-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="70543-249">int</span><span class="sxs-lookup"><span data-stu-id="70543-249">int</span></span></p></td>
<td><p><span data-ttu-id="70543-250">这是在给定各种策略设置（TURN、API、SDP、策略服务器等）上应用到给定发送端流的实际带宽。</span><span class="sxs-lookup"><span data-stu-id="70543-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="70543-251">不要将这一点与有效的带宽混淆，因为它可以根据带宽估计值降低较低的有效带宽。</span><span class="sxs-lookup"><span data-stu-id="70543-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="70543-252">这基本上是发送流可以通过带宽估计限制限制的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="70543-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="70543-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="70543-254">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="70543-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70543-255">所强加带宽上限的来源。</span><span class="sxs-lookup"><span data-stu-id="70543-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="70543-256">它介绍带宽限制的来源（例如，"策略服务器"、"转换服务器" 或 "模态"）。</span><span class="sxs-lookup"><span data-stu-id="70543-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-257">呼叫者</span><span class="sxs-lookup"><span data-stu-id="70543-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="70543-258">bit</span><span class="sxs-lookup"><span data-stu-id="70543-258">bit</span></span></p></td>
<td><p><span data-ttu-id="70543-259">指示是否收到来自呼叫方的指标;1为 "是"，0为 "否"。</span><span class="sxs-lookup"><span data-stu-id="70543-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-260">被叫方</span><span class="sxs-lookup"><span data-stu-id="70543-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="70543-261">bit</span><span class="sxs-lookup"><span data-stu-id="70543-261">bit</span></span></p></td>
<td><p><span data-ttu-id="70543-262">指示是否收到来自呼叫接收器的指标;1为 "是"，0为 "否"。</span><span class="sxs-lookup"><span data-stu-id="70543-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="70543-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="70543-264">bit</span><span class="sxs-lookup"><span data-stu-id="70543-264">bit</span></span></p></td>
<td><p><span data-ttu-id="70543-265">指示报表是用于部分通话还是完整通话。</span><span class="sxs-lookup"><span data-stu-id="70543-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="70543-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="70543-267">bit</span><span class="sxs-lookup"><span data-stu-id="70543-267">bit</span></span></p></td>
<td><p><span data-ttu-id="70543-268">指示呼叫是否分类为差通话（1）或正常呼叫（0）。</span><span class="sxs-lookup"><span data-stu-id="70543-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70543-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="70543-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="70543-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="70543-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="70543-271">指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接到网络。</span><span class="sxs-lookup"><span data-stu-id="70543-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70543-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="70543-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="70543-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="70543-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="70543-274">指示用户是否使用 ICE 协议（Internet 连接建立）连接到网络。</span><span class="sxs-lookup"><span data-stu-id="70543-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

