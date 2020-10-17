---
title: Lync Server 2013： MediaLine 视图
description: Lync Server 2013： MediaLine 视图。
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
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568678"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="648c8-103">Lync Server 2013 中的 MediaLine 视图</span><span class="sxs-lookup"><span data-stu-id="648c8-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="648c8-104">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="648c8-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="648c8-105">媒体行视图存储有关数据库中每个媒体行的信息。</span><span class="sxs-lookup"><span data-stu-id="648c8-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="648c8-106">一个音频会话通常包含一个音频媒体行。</span><span class="sxs-lookup"><span data-stu-id="648c8-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="648c8-107">一个音频与视频 (A/V) 会话通常包含一个音频媒体行和一个视频媒体行；但是，如果使用了会议设备或库视图，则会话可能包含两个视频媒体行。</span><span class="sxs-lookup"><span data-stu-id="648c8-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="648c8-108">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="648c8-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="648c8-109">列</span><span class="sxs-lookup"><span data-stu-id="648c8-109">Column</span></span></th>
<th><span data-ttu-id="648c8-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="648c8-110">Data Type</span></span></th>
<th><span data-ttu-id="648c8-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="648c8-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="648c8-112">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="648c8-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="648c8-113">datetime</span><span class="sxs-lookup"><span data-stu-id="648c8-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="648c8-114"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="648c8-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-115">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="648c8-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="648c8-116">int</span><span class="sxs-lookup"><span data-stu-id="648c8-116">int</span></span></p></td>
<td><p><span data-ttu-id="648c8-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="648c8-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-118">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="648c8-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="648c8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="648c8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="648c8-120"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="648c8-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-121">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="648c8-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="648c8-122">int</span><span class="sxs-lookup"><span data-stu-id="648c8-122">int</span></span></p></td>
<td><p><span data-ttu-id="648c8-p102">关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="648c8-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-125">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="648c8-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="648c8-126">int</span><span class="sxs-lookup"><span data-stu-id="648c8-126">int</span></span></p></td>
<td><p><span data-ttu-id="648c8-p103">关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="648c8-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-129">安全性</span><span class="sxs-lookup"><span data-stu-id="648c8-129">Security</span></span></p></td>
<td><p><span data-ttu-id="648c8-130">tinyint</span><span class="sxs-lookup"><span data-stu-id="648c8-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="648c8-p104">正在使用的安全配置文件。0 为无，1 为 SRTP，2 为 V1。</span><span class="sxs-lookup"><span data-stu-id="648c8-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-133">Transport</span><span class="sxs-lookup"><span data-stu-id="648c8-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="648c8-134">tinyint</span><span class="sxs-lookup"><span data-stu-id="648c8-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="648c8-p105">传输类型。0 为 UDP，1 为 TCP。</span><span class="sxs-lookup"><span data-stu-id="648c8-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-137">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="648c8-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="648c8-138">var (50) </span><span class="sxs-lookup"><span data-stu-id="648c8-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="648c8-p106">呼叫者的 IP 地址。可为 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="648c8-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-141">CallerPort</span><span class="sxs-lookup"><span data-stu-id="648c8-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="648c8-142">int</span><span class="sxs-lookup"><span data-stu-id="648c8-142">int</span></span></p></td>
<td><p><span data-ttu-id="648c8-143">呼叫者使用的端口。</span><span class="sxs-lookup"><span data-stu-id="648c8-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-144">CallerInside</span><span class="sxs-lookup"><span data-stu-id="648c8-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="648c8-145">位</span><span class="sxs-lookup"><span data-stu-id="648c8-145">bit</span></span></p></td>
<td><p><span data-ttu-id="648c8-p107">指示呼叫者是否在组织网络内。1 表示呼叫者在企业网络内。0 表示呼叫者在网络外。</span><span class="sxs-lookup"><span data-stu-id="648c8-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-149">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="648c8-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="648c8-150">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-151">呼叫者使用的网络接口的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="648c8-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-152">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="648c8-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="648c8-153">var (50) </span><span class="sxs-lookup"><span data-stu-id="648c8-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="648c8-154">呼叫者所使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="648c8-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="648c8-155">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="648c8-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-156">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="648c8-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="648c8-157">int</span><span class="sxs-lookup"><span data-stu-id="648c8-157">int</span></span></p></td>
<td><p><span data-ttu-id="648c8-158">呼叫者在 A/V 边缘服务中使用的端口。</span><span class="sxs-lookup"><span data-stu-id="648c8-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-159">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="648c8-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="648c8-160">var (50) </span><span class="sxs-lookup"><span data-stu-id="648c8-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="648c8-161">A/V 边缘服务报告的呼叫者的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="648c8-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="648c8-162">如果客户端位于 NAT 之后，则此地址可能与 CallerIPAddr 不同。</span><span class="sxs-lookup"><span data-stu-id="648c8-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-163">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="648c8-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="648c8-164">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-165">呼叫者的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="648c8-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-166">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="648c8-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="648c8-167">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-168">呼叫者的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="648c8-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-169">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="648c8-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="648c8-170">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-171">呼叫者的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="648c8-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-172">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="648c8-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="648c8-173">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-174">呼叫者的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="648c8-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-175">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="648c8-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="648c8-176">varchar (256</span><span class="sxs-lookup"><span data-stu-id="648c8-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="648c8-177">呼叫者的 Wifi 驱动程序描述。</span><span class="sxs-lookup"><span data-stu-id="648c8-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-178">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="648c8-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="648c8-179">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-180">呼叫者的 Wifi 驱动程序版本。</span><span class="sxs-lookup"><span data-stu-id="648c8-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-181">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="648c8-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="648c8-182">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-183">呼叫者的网络连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="648c8-183">Details of caller’s network connection.</span></span> <span data-ttu-id="648c8-184">有关详细信息，请参阅 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="648c8-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-185">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="648c8-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="648c8-186">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-187">呼叫者 WiFi 连接使用的基本服务集标识符。</span><span class="sxs-lookup"><span data-stu-id="648c8-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-188">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="648c8-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="648c8-189">位</span><span class="sxs-lookup"><span data-stu-id="648c8-189">bit</span></span></p></td>
<td><p><span data-ttu-id="648c8-p111">指示呼叫者是否通过虚拟专用网连接。1 是虚拟专用网 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="648c8-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-192">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="648c8-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="648c8-193">var (50) </span><span class="sxs-lookup"><span data-stu-id="648c8-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="648c8-194">被叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="648c8-194">IP address of the callee.</span></span> <span data-ttu-id="648c8-195">可为 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="648c8-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-196">CalleePort</span><span class="sxs-lookup"><span data-stu-id="648c8-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="648c8-197">int</span><span class="sxs-lookup"><span data-stu-id="648c8-197">int</span></span></p></td>
<td><p><span data-ttu-id="648c8-198">被叫方所使用的端口。</span><span class="sxs-lookup"><span data-stu-id="648c8-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-199">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="648c8-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="648c8-200">位</span><span class="sxs-lookup"><span data-stu-id="648c8-200">bit</span></span></p></td>
<td><p><span data-ttu-id="648c8-p113">指示被叫方是否在企业网络内。1 表示被叫方在企业网络内，0 表示被叫方在该网络外。</span><span class="sxs-lookup"><span data-stu-id="648c8-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-203">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="648c8-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="648c8-204">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-205">被叫方使用的网络接口的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="648c8-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-206">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="648c8-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="648c8-207">var (50) </span><span class="sxs-lookup"><span data-stu-id="648c8-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="648c8-208">被叫方使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="648c8-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="648c8-209">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="648c8-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-210">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="648c8-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="648c8-211">int</span><span class="sxs-lookup"><span data-stu-id="648c8-211">int</span></span></p></td>
<td><p><span data-ttu-id="648c8-212">被叫方在 A/V 边缘服务中使用的端口。</span><span class="sxs-lookup"><span data-stu-id="648c8-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-213">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="648c8-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="648c8-214">var (50) </span><span class="sxs-lookup"><span data-stu-id="648c8-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="648c8-215">A/V 边缘服务报告的被叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="648c8-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="648c8-216">如果客户端位于 NAT 之后，则此地址可能与 CalleeIPAddr 不同。</span><span class="sxs-lookup"><span data-stu-id="648c8-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-217">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="648c8-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="648c8-218">var (50) </span><span class="sxs-lookup"><span data-stu-id="648c8-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="648c8-219">被叫方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="648c8-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-220">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="648c8-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="648c8-221">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-222">被叫方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="648c8-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-223">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="648c8-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="648c8-224">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-225">被叫方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="648c8-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-226">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="648c8-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="648c8-227">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-228">被叫方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="648c8-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-229">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="648c8-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="648c8-230">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-231">被叫方的 Wifi 驱动程序描述。</span><span class="sxs-lookup"><span data-stu-id="648c8-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-232">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="648c8-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="648c8-233">varchar (256</span><span class="sxs-lookup"><span data-stu-id="648c8-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="648c8-234">被叫方的 Wifi 驱动程序版本。</span><span class="sxs-lookup"><span data-stu-id="648c8-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-235">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="648c8-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="648c8-236">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-237">被叫方的网络连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="648c8-237">Details of callee’s network connection.</span></span> <span data-ttu-id="648c8-238">有关详细信息，请参阅 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="648c8-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-239">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="648c8-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="648c8-240">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-241">被叫方 WiFi 连接使用的基本服务集标识符。</span><span class="sxs-lookup"><span data-stu-id="648c8-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-242">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="648c8-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="648c8-243">位</span><span class="sxs-lookup"><span data-stu-id="648c8-243">bit</span></span></p></td>
<td><p><span data-ttu-id="648c8-p117">指示被叫方是否通过虚拟专用网连接。1 是虚拟专用网 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="648c8-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-246">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="648c8-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="648c8-247">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="648c8-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="648c8-248">音频会话的窄带交谈 MOS（基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="648c8-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-249">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="648c8-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="648c8-250">int</span><span class="sxs-lookup"><span data-stu-id="648c8-250">int</span></span></p></td>
<td><p><span data-ttu-id="648c8-p118">这是应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不应将其与有效带宽混淆，因为根据带宽预估的不同，有效带宽可能会减少。这基本上是发送流可禁止带宽预估设定的限制的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="648c8-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="648c8-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="648c8-255">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="648c8-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="648c8-p119">所设定的带宽限制的来源。它描述带宽限制源自的位置（例如，“策略服务器”、“TURN 服务器”或“形式”）。</span><span class="sxs-lookup"><span data-stu-id="648c8-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-258">Caller</span><span class="sxs-lookup"><span data-stu-id="648c8-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="648c8-259">位</span><span class="sxs-lookup"><span data-stu-id="648c8-259">bit</span></span></p></td>
<td><p><span data-ttu-id="648c8-260">指示是否已收到来自呼叫者的度量；1 为是，0 为否。</span><span class="sxs-lookup"><span data-stu-id="648c8-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-261">约定</span><span class="sxs-lookup"><span data-stu-id="648c8-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="648c8-262">位</span><span class="sxs-lookup"><span data-stu-id="648c8-262">bit</span></span></p></td>
<td><p><span data-ttu-id="648c8-263">指示是否已收到来自呼叫接收者的度量；1 为是，0 为否。</span><span class="sxs-lookup"><span data-stu-id="648c8-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-264">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="648c8-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="648c8-265">位</span><span class="sxs-lookup"><span data-stu-id="648c8-265">bit</span></span></p></td>
<td><p><span data-ttu-id="648c8-266">指示报告用于呼叫的一部分还是用于整个呼叫。</span><span class="sxs-lookup"><span data-stu-id="648c8-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-267">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="648c8-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="648c8-268">位</span><span class="sxs-lookup"><span data-stu-id="648c8-268">bit</span></span></p></td>
<td><p><span data-ttu-id="648c8-269">指示呼叫被分类为质量欠佳的呼叫 (1) 还是质量良好的呼叫 (0)。</span><span class="sxs-lookup"><span data-stu-id="648c8-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648c8-270">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="648c8-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="648c8-271">tinyint</span><span class="sxs-lookup"><span data-stu-id="648c8-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="648c8-272">指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。</span><span class="sxs-lookup"><span data-stu-id="648c8-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648c8-273">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="648c8-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="648c8-274">tinyint</span><span class="sxs-lookup"><span data-stu-id="648c8-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="648c8-275">指示被呼叫的用户是否使用 ICE 协议（Internet 连接建立）连接至网络。</span><span class="sxs-lookup"><span data-stu-id="648c8-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

