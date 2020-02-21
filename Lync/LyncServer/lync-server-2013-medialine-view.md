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
ms.openlocfilehash: 21fa89b5afe53937ee515dac45053dbd84ae12ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="4f9ce-102">Lync Server 2013 中的 MediaLine 视图</span><span class="sxs-lookup"><span data-stu-id="4f9ce-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f9ce-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4f9ce-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4f9ce-104">媒体行视图存储有关数据库中每个媒体行的信息。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="4f9ce-105">一个音频会话通常包含一个音频媒体行。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="4f9ce-106">一个音频与视频 (A/V) 会话通常包含一个音频媒体行和一个视频媒体行；但是，如果使用了会议设备或库视图，则会话可能包含两个视频媒体行。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="4f9ce-107">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f9ce-108">列</span><span class="sxs-lookup"><span data-stu-id="4f9ce-108">Column</span></span></th>
<th><span data-ttu-id="4f9ce-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="4f9ce-109">Data Type</span></span></th>
<th><span data-ttu-id="4f9ce-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="4f9ce-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="4f9ce-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4f9ce-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-113"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="4f9ce-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-115">int</span><span class="sxs-lookup"><span data-stu-id="4f9ce-115">int</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-116"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="4f9ce-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f9ce-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-119"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4f9ce-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-121">int</span><span class="sxs-lookup"><span data-stu-id="4f9ce-121">int</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p102">关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4f9ce-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-125">int</span><span class="sxs-lookup"><span data-stu-id="4f9ce-125">int</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p103">关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-128">安全性</span><span class="sxs-lookup"><span data-stu-id="4f9ce-128">Security</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f9ce-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p104">正在使用的安全配置文件。0 为无，1 为 SRTP，2 为 V1。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-132">Transport</span><span class="sxs-lookup"><span data-stu-id="4f9ce-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f9ce-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p105">传输类型。0 为 UDP，1 为 TCP。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f9ce-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-137">var （50）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p106">呼叫者的 IP 地址。可为 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="4f9ce-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-141">int</span><span class="sxs-lookup"><span data-stu-id="4f9ce-141">int</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-142">呼叫者使用的端口。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="4f9ce-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-144">位</span><span class="sxs-lookup"><span data-stu-id="4f9ce-144">bit</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p107">指示呼叫者是否在组织网络内。1 表示呼叫者在企业网络内。0 表示呼叫者在网络外。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="4f9ce-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-149">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-150">呼叫者使用的网络接口的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f9ce-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-152">var （50）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-153">呼叫者所使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="4f9ce-154">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="4f9ce-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-156">int</span><span class="sxs-lookup"><span data-stu-id="4f9ce-156">int</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-157">呼叫者在 A/V 边缘服务中使用的端口。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f9ce-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-159">var （50）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-160">A/V 边缘服务报告的呼叫者的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="4f9ce-161">如果客户端位于 NAT 之后，则此地址可能与 CallerIPAddr 不同。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="4f9ce-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-163">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-164">呼叫者的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="4f9ce-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-166">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-167">呼叫者的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="4f9ce-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-169">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-170">呼叫者的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="4f9ce-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-172">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-173">呼叫者的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="4f9ce-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-175">varchar （256</span><span class="sxs-lookup"><span data-stu-id="4f9ce-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-176">呼叫者的 Wifi 驱动程序描述。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="4f9ce-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-178">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-179">呼叫者的 Wifi 驱动程序版本。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="4f9ce-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-181">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-182">呼叫者的网络连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-182">Details of caller’s network connection.</span></span> <span data-ttu-id="4f9ce-183">有关详细信息，请参阅<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="4f9ce-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-185">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-186">呼叫者 WiFi 连接使用的基本服务集标识符。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="4f9ce-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-188">位</span><span class="sxs-lookup"><span data-stu-id="4f9ce-188">bit</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p111">指示呼叫者是否通过虚拟专用网连接。1 是虚拟专用网 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f9ce-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-192">var （50）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-193">被叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-193">IP address of the callee.</span></span> <span data-ttu-id="4f9ce-194">可为 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="4f9ce-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-196">int</span><span class="sxs-lookup"><span data-stu-id="4f9ce-196">int</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-197">被叫方所使用的端口。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="4f9ce-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-199">位</span><span class="sxs-lookup"><span data-stu-id="4f9ce-199">bit</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p113">指示被叫方是否在企业网络内。1 表示被叫方在企业网络内，0 表示被叫方在该网络外。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="4f9ce-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-203">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-204">被叫方使用的网络接口的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f9ce-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-206">var （50）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-207">被叫方使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="4f9ce-208">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="4f9ce-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-210">int</span><span class="sxs-lookup"><span data-stu-id="4f9ce-210">int</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-211">被叫方在 A/V 边缘服务中使用的端口。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="4f9ce-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-213">var （50）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-214">A/V 边缘服务报告的被叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="4f9ce-215">如果客户端位于 NAT 之后，则此地址可能与 CalleeIPAddr 不同。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="4f9ce-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-217">var （50）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-218">被叫方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="4f9ce-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-220">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-221">被叫方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="4f9ce-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-223">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-224">被叫方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="4f9ce-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-226">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-227">被叫方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="4f9ce-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-229">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-230">被叫方的 Wifi 驱动程序描述。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="4f9ce-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-232">varchar （256</span><span class="sxs-lookup"><span data-stu-id="4f9ce-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-233">被叫方的 Wifi 驱动程序版本。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="4f9ce-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-235">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-236">被叫方的网络连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-236">Details of callee’s network connection.</span></span> <span data-ttu-id="4f9ce-237">有关详细信息，请参阅<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="4f9ce-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-239">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-240">被叫方 WiFi 连接使用的基本服务集标识符。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="4f9ce-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-242">位</span><span class="sxs-lookup"><span data-stu-id="4f9ce-242">bit</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p117">指示被叫方是否通过虚拟专用网连接。1 是虚拟专用网 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="4f9ce-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-246">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-247">音频会话的窄带交谈 MOS（基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="4f9ce-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-249">int</span><span class="sxs-lookup"><span data-stu-id="4f9ce-249">int</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p118">这是应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不应将其与有效带宽混淆，因为根据带宽预估的不同，有效带宽可能会减少。这基本上是发送流可禁止带宽预估设定的限制的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="4f9ce-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-254">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="4f9ce-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-p119">所设定的带宽限制的来源。它描述带宽限制源自的位置（例如，“策略服务器”、“TURN 服务器”或“形式”）。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-257">Caller</span><span class="sxs-lookup"><span data-stu-id="4f9ce-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-258">位</span><span class="sxs-lookup"><span data-stu-id="4f9ce-258">bit</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-259">指示是否已收到来自呼叫者的度量；1 为是，0 为否。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-260">约定</span><span class="sxs-lookup"><span data-stu-id="4f9ce-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-261">位</span><span class="sxs-lookup"><span data-stu-id="4f9ce-261">bit</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-262">指示是否已收到来自呼叫接收者的度量；1 为是，0 为否。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="4f9ce-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-264">位</span><span class="sxs-lookup"><span data-stu-id="4f9ce-264">bit</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-265">指示报告用于呼叫的一部分还是用于整个呼叫。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="4f9ce-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-267">位</span><span class="sxs-lookup"><span data-stu-id="4f9ce-267">bit</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-268">指示呼叫被分类为质量欠佳的呼叫 (1) 还是质量良好的呼叫 (0)。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f9ce-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="4f9ce-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f9ce-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-271">指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f9ce-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="4f9ce-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f9ce-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f9ce-274">指示被呼叫的用户是否使用 ICE 协议（Internet 连接建立）连接至网络。</span><span class="sxs-lookup"><span data-stu-id="4f9ce-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

