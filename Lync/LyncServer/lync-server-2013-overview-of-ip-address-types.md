---
title: Lync Server 2013： IP 地址类型概述
description: Lync Server 2013： IP 地址类型概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559218"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="1dea8-103">Lync Server 2013 的 IP 地址类型概述</span><span class="sxs-lookup"><span data-stu-id="1dea8-103">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dea8-104">_**上次修改的主题：** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="1dea8-104">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="1dea8-105">在 Lync Server 2013 中配置 IP 地址时有三个选项。</span><span class="sxs-lookup"><span data-stu-id="1dea8-105">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="1dea8-106">您可以将 Lync Server 2013 配置为仅支持 IP 版本 4 (IPv4) 、仅 IP 版本 6 (IPv6) ，或者 () 称为 *双堆栈* 的组合。</span><span class="sxs-lookup"><span data-stu-id="1dea8-106">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="1dea8-107">对于每种类型的配置，都需要考虑一些问题：</span><span class="sxs-lookup"><span data-stu-id="1dea8-107">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="1dea8-108">**仅 IPv4**    由于世界耗尽了 IPv4 地址，因此已创建 IPv6。</span><span class="sxs-lookup"><span data-stu-id="1dea8-108">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="1dea8-109">最终，IPv6 将会在世界范围内得到完全支持，但现在有很多您的企业可能需要与之通信的公司和设备尚不支持 IPv6，并且在一段时间内可能也不会支持。</span><span class="sxs-lookup"><span data-stu-id="1dea8-109">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="1dea8-110">仅 IPv4 配置将有助于确保你的 Lync Server 实现能够与大多数现有设备通信。</span><span class="sxs-lookup"><span data-stu-id="1dea8-110">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="1dea8-111">**仅限 IPv6**    相反，完整的 IPv6 实现现在将排除与许多现有设备的通信。</span><span class="sxs-lookup"><span data-stu-id="1dea8-111">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="1dea8-112">**双栈**    双栈是启用 IPv4 和 IPv6 地址的网络。</span><span class="sxs-lookup"><span data-stu-id="1dea8-112">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="1dea8-113">Lync Server 2013 支持此配置，因为在大多数情况下，从完整 IPv4 到完整 IPv6 的转换需要几年时间。</span><span class="sxs-lookup"><span data-stu-id="1dea8-113">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="1dea8-114">以下各节概述了各种 Lync Server 功能在这三种配置中的兼容性。</span><span class="sxs-lookup"><span data-stu-id="1dea8-114">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1dea8-p104">仅 IPv6 的客户端或服务器配置只受选项卡或验证的支持。仅 IPv6 配置在生产部署中不受支持。</span><span class="sxs-lookup"><span data-stu-id="1dea8-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="1dea8-117">客户端注册</span><span class="sxs-lookup"><span data-stu-id="1dea8-117">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dea8-118">客户端终结点网络</span><span class="sxs-lookup"><span data-stu-id="1dea8-118">Client endpoint network</span></span></th>
<th><span data-ttu-id="1dea8-119">服务器网络</span><span class="sxs-lookup"><span data-stu-id="1dea8-119">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-120">IPv4</span></span></p></td>
<td><p><span data-ttu-id="1dea8-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-121">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-122">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-122">IPv4</span></span></p></td>
<td><p><span data-ttu-id="1dea8-123">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-123">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-124">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-124">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-125">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-125">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-126">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-126">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-127">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-127">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-128">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-128">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-129">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-130">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-130">IPv6</span></span></p></td>
<td><p><span data-ttu-id="1dea8-131">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-131">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-132">IPv6</span></span></p></td>
<td><p><span data-ttu-id="1dea8-133">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-133">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="1dea8-134">对等客户端</span><span class="sxs-lookup"><span data-stu-id="1dea8-134">Peer-to-Peer Client</span></span>

<span data-ttu-id="1dea8-p105">对等通信包括音频、音频/视频、应用程序共享和文件传输。两个客户端均注册成功后，将支持以下组合。</span><span class="sxs-lookup"><span data-stu-id="1dea8-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dea8-137">客户端终结点 1</span><span class="sxs-lookup"><span data-stu-id="1dea8-137">Client endpoint 1</span></span></th>
<th><span data-ttu-id="1dea8-138">客户端终结点 2</span><span class="sxs-lookup"><span data-stu-id="1dea8-138">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-139">IPv4</span></span></p></td>
<td><p><span data-ttu-id="1dea8-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-140">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-141">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-141">IPv4</span></span></p></td>
<td><p><span data-ttu-id="1dea8-142">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-142">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-143">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-143">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-144">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-144">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-145">IPv6</span></span></p></td>
<td><p><span data-ttu-id="1dea8-146">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-146">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-147">IPv6</span></span></p></td>
<td><p><span data-ttu-id="1dea8-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-148">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="1dea8-149">会议</span><span class="sxs-lookup"><span data-stu-id="1dea8-149">Conferencing</span></span>

<span data-ttu-id="1dea8-150">会议包括音频/视频、应用程序共享和数据协作（白板和文件共享）。</span><span class="sxs-lookup"><span data-stu-id="1dea8-150">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dea8-151">客户端终结点网络</span><span class="sxs-lookup"><span data-stu-id="1dea8-151">Client endpoint network</span></span></th>
<th><span data-ttu-id="1dea8-152">服务器网络</span><span class="sxs-lookup"><span data-stu-id="1dea8-152">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-153">IPv4</span></span></p></td>
<td><p><span data-ttu-id="1dea8-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-154">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-155">IPv4</span></span></p></td>
<td><p><span data-ttu-id="1dea8-156">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-156">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-157">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-157">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-158">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-158">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-159">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-159">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-160">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-160">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-161">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-161">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-162">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-163">IPv6</span></span></p></td>
<td><p><span data-ttu-id="1dea8-164">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-164">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-165">IPv6</span></span></p></td>
<td><p><span data-ttu-id="1dea8-166">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-166">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="1dea8-167">中介服务器/PSTN</span><span class="sxs-lookup"><span data-stu-id="1dea8-167">Mediation Server/PSTN</span></span>

<span data-ttu-id="1dea8-168">如果流量通过 IPv6 接口，Lync Server 2013 不支持公用交换电话网络 (PSTN) 呼叫的媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="1dea8-168">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="1dea8-169">如果需要媒体旁路，则我们建议将 PSTN 网关配置为 IPv4。</span><span class="sxs-lookup"><span data-stu-id="1dea8-169">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dea8-170">主要接口\*</span><span class="sxs-lookup"><span data-stu-id="1dea8-170">Primary interface\*</span></span></th>
<th><span data-ttu-id="1dea8-171">PSTN 接口（位于中介服务器上）</span><span class="sxs-lookup"><span data-stu-id="1dea8-171">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="1dea8-172">PSTN 网关设置</span><span class="sxs-lookup"><span data-stu-id="1dea8-172">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-173">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-173">IPv4</span></span></p></td>
<td><p><span data-ttu-id="1dea8-174">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-174">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-175">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-176">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-177">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-177">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-178">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-178">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-179">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-180">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-180">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-181">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-181">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1dea8-182">\* 主接口是与 Lync Server 组件进行通信的接口。</span><span class="sxs-lookup"><span data-stu-id="1dea8-182">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="1dea8-183">远程用户对等通信</span><span class="sxs-lookup"><span data-stu-id="1dea8-183">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="1dea8-184">与远程用户的对等通信包括即时消息、音频/视频、应用程序共享和文件传输。</span><span class="sxs-lookup"><span data-stu-id="1dea8-184">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dea8-185">远程用户网络</span><span class="sxs-lookup"><span data-stu-id="1dea8-185">Remote user network</span></span></th>
<th><span data-ttu-id="1dea8-186">边缘服务器（外部边缘）</span><span class="sxs-lookup"><span data-stu-id="1dea8-186">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-187">IPv4</span></span></p></td>
<td><p><span data-ttu-id="1dea8-188">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-188">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-189">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-189">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-190">IPv4</span><span class="sxs-lookup"><span data-stu-id="1dea8-190">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-191">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-191">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="1dea8-192">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-192">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-193">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-193">IPv6</span></span></p></td>
<td><p><span data-ttu-id="1dea8-194">双协议栈</span><span class="sxs-lookup"><span data-stu-id="1dea8-194">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-195">IPv6</span></span></p></td>
<td><p><span data-ttu-id="1dea8-196">IPv6</span><span class="sxs-lookup"><span data-stu-id="1dea8-196">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="1dea8-197">前端池和边缘池配置</span><span class="sxs-lookup"><span data-stu-id="1dea8-197">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="1dea8-198">下表显示了前端服务器池和内部边缘服务器池之间的支持列表。</span><span class="sxs-lookup"><span data-stu-id="1dea8-198">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="1dea8-199">前端池和边缘池（内部边缘）矩阵</span><span class="sxs-lookup"><span data-stu-id="1dea8-199">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="1dea8-200"><strong>边缘池：IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-200"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-201"><strong>边缘池：双协议栈</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-201"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-202"><strong>边缘池：IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-202"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-203"><strong>前端池：IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-203"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-204">是</span><span class="sxs-lookup"><span data-stu-id="1dea8-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="1dea8-205">是</span><span class="sxs-lookup"><span data-stu-id="1dea8-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="1dea8-206">否</span><span class="sxs-lookup"><span data-stu-id="1dea8-206">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-207"><strong>前端池：双协议栈</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-207"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-208">是</span><span class="sxs-lookup"><span data-stu-id="1dea8-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="1dea8-209">是</span><span class="sxs-lookup"><span data-stu-id="1dea8-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="1dea8-210">否</span><span class="sxs-lookup"><span data-stu-id="1dea8-210">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-211"><strong>前端池：IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-211"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-212">否</span><span class="sxs-lookup"><span data-stu-id="1dea8-212">No</span></span></p></td>
<td><p><span data-ttu-id="1dea8-213">否</span><span class="sxs-lookup"><span data-stu-id="1dea8-213">No</span></span></p></td>
<td><p><span data-ttu-id="1dea8-214">是\*</span><span class="sxs-lookup"><span data-stu-id="1dea8-214">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1dea8-215">\* 仅在实验室环境中使用此组合。</span><span class="sxs-lookup"><span data-stu-id="1dea8-215">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="1dea8-216">下表是内部和外部边缘接口支持的组合矩阵。</span><span class="sxs-lookup"><span data-stu-id="1dea8-216">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="1dea8-217">边缘池（内部边缘）和边缘池（外部边缘）矩阵</span><span class="sxs-lookup"><span data-stu-id="1dea8-217">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="1dea8-218"><strong>边缘池（外部边缘）：IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-218"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-219"><strong>边缘池（外部边缘）：双协议栈</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-219"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-220"><strong>边缘池（外部边缘）：IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-220"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-221"><strong>边缘池（内部边缘）：IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-221"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-222">是</span><span class="sxs-lookup"><span data-stu-id="1dea8-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="1dea8-223">是</span><span class="sxs-lookup"><span data-stu-id="1dea8-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="1dea8-224">否</span><span class="sxs-lookup"><span data-stu-id="1dea8-224">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dea8-225"><strong>边缘池（内部边缘）：双协议栈</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-225"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-226">否</span><span class="sxs-lookup"><span data-stu-id="1dea8-226">No</span></span></p></td>
<td><p><span data-ttu-id="1dea8-227">是</span><span class="sxs-lookup"><span data-stu-id="1dea8-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="1dea8-228">否</span><span class="sxs-lookup"><span data-stu-id="1dea8-228">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dea8-229"><strong>边缘池（内部边缘）：IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="1dea8-229"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="1dea8-230">否</span><span class="sxs-lookup"><span data-stu-id="1dea8-230">No</span></span></p></td>
<td><p><span data-ttu-id="1dea8-231">否</span><span class="sxs-lookup"><span data-stu-id="1dea8-231">No</span></span></p></td>
<td><p><span data-ttu-id="1dea8-232">是\*</span><span class="sxs-lookup"><span data-stu-id="1dea8-232">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1dea8-233">\* 仅在实验室环境中使用此组合。</span><span class="sxs-lookup"><span data-stu-id="1dea8-233">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="1dea8-234">IPv6 的高级企业语音支持</span><span class="sxs-lookup"><span data-stu-id="1dea8-234">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="1dea8-235">包括呼叫许可控制 (CAC)、增强型 9-1-1 (E9-1-1) 或媒体旁路的部署必须配置为仅 IPv4 或双协议栈实现。</span><span class="sxs-lookup"><span data-stu-id="1dea8-235">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1dea8-236">在双堆栈部署中，即使 Lync 客户端使用 IPv6 连接到 Lync Server，Lync 也将尽力映射合适的 IPv4 地址以支持 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="1dea8-236">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="1dea8-237">不支持使用 IPv6 地址的位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="1dea8-237">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="1dea8-p107">Exchange 统一消息 (UM) 不支持 IPv6。对于 Exchange UM，请确保 DNS 解析不会返回 IPv6 地址。使用 IPv6 可能会在将呼叫发送至语音信箱时导致失败。</span><span class="sxs-lookup"><span data-stu-id="1dea8-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="1dea8-241">适用于 IPv6 的其他 Lync Server 2013 功能支持</span><span class="sxs-lookup"><span data-stu-id="1dea8-241">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="1dea8-242">除了前面提到的功能和组件，Lync Server 2013 还支持 IPv6 以实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="1dea8-242">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="1dea8-243">**持久聊天**</span><span class="sxs-lookup"><span data-stu-id="1dea8-243">**Persistent Chat**</span></span>
    
    <span data-ttu-id="1dea8-244">您可以使用拓扑生成器为持久聊天配置 IPv6。</span><span class="sxs-lookup"><span data-stu-id="1dea8-244">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="1dea8-245">有关配置持久聊天的详细信息，请参阅部署持久聊天服务器文档。</span><span class="sxs-lookup"><span data-stu-id="1dea8-245">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="1dea8-246">**用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 报告**</span><span class="sxs-lookup"><span data-stu-id="1dea8-246">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="1dea8-247">监视报告将会包括 IP 地址，因为该地址存储在监视服务器数据库中（无论类型为 IPv4 还是 IPv6）。</span><span class="sxs-lookup"><span data-stu-id="1dea8-247">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

