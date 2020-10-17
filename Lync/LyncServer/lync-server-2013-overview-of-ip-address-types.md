---
title: Lync Server 2013： IP 地址类型概述
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
ms.openlocfilehash: 9663f7ee8b57ceba27e1a1892c30bb92a1c86ffc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520999"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="15dfe-102">Lync Server 2013 的 IP 地址类型概述</span><span class="sxs-lookup"><span data-stu-id="15dfe-102">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15dfe-103">_**上次修改的主题：** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="15dfe-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="15dfe-104">在 Lync Server 2013 中配置 IP 地址时有三个选项。</span><span class="sxs-lookup"><span data-stu-id="15dfe-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="15dfe-105">您可以将 Lync Server 2013 配置为仅支持 IP 版本 4 (IPv4) 、仅 IP 版本 6 (IPv6) ，或者 () 称为 *双堆栈* 的组合。</span><span class="sxs-lookup"><span data-stu-id="15dfe-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="15dfe-106">对于每种类型的配置，都需要考虑一些问题：</span><span class="sxs-lookup"><span data-stu-id="15dfe-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="15dfe-107">**仅 IPv4**    由于世界耗尽了 IPv4 地址，因此已创建 IPv6。</span><span class="sxs-lookup"><span data-stu-id="15dfe-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="15dfe-108">最终，IPv6 将会在世界范围内得到完全支持，但现在有很多您的企业可能需要与之通信的公司和设备尚不支持 IPv6，并且在一段时间内可能也不会支持。</span><span class="sxs-lookup"><span data-stu-id="15dfe-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="15dfe-109">仅 IPv4 配置将有助于确保你的 Lync Server 实现能够与大多数现有设备通信。</span><span class="sxs-lookup"><span data-stu-id="15dfe-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="15dfe-110">**仅限 IPv6**    相反，完整的 IPv6 实现现在将排除与许多现有设备的通信。</span><span class="sxs-lookup"><span data-stu-id="15dfe-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="15dfe-111">**双栈**    双栈是启用 IPv4 和 IPv6 地址的网络。</span><span class="sxs-lookup"><span data-stu-id="15dfe-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="15dfe-112">Lync Server 2013 支持此配置，因为在大多数情况下，从完整 IPv4 到完整 IPv6 的转换需要几年时间。</span><span class="sxs-lookup"><span data-stu-id="15dfe-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="15dfe-113">以下各节概述了各种 Lync Server 功能在这三种配置中的兼容性。</span><span class="sxs-lookup"><span data-stu-id="15dfe-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15dfe-p104">仅 IPv6 的客户端或服务器配置只受选项卡或验证的支持。仅 IPv6 配置在生产部署中不受支持。</span><span class="sxs-lookup"><span data-stu-id="15dfe-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="15dfe-116">客户端注册</span><span class="sxs-lookup"><span data-stu-id="15dfe-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15dfe-117">客户端终结点网络</span><span class="sxs-lookup"><span data-stu-id="15dfe-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="15dfe-118">服务器网络</span><span class="sxs-lookup"><span data-stu-id="15dfe-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="15dfe-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="15dfe-122">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-123">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-125">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-126">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-127">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="15dfe-130">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="15dfe-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="15dfe-133">对等客户端</span><span class="sxs-lookup"><span data-stu-id="15dfe-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="15dfe-p105">对等通信包括音频、音频/视频、应用程序共享和文件传输。两个客户端均注册成功后，将支持以下组合。</span><span class="sxs-lookup"><span data-stu-id="15dfe-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15dfe-136">客户端终结点 1</span><span class="sxs-lookup"><span data-stu-id="15dfe-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="15dfe-137">客户端终结点 2</span><span class="sxs-lookup"><span data-stu-id="15dfe-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="15dfe-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="15dfe-141">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-142">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-143">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="15dfe-145">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="15dfe-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="15dfe-148">会议</span><span class="sxs-lookup"><span data-stu-id="15dfe-148">Conferencing</span></span>

<span data-ttu-id="15dfe-149">会议包括音频/视频、应用程序共享和数据协作（白板和文件共享）。</span><span class="sxs-lookup"><span data-stu-id="15dfe-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15dfe-150">客户端终结点网络</span><span class="sxs-lookup"><span data-stu-id="15dfe-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="15dfe-151">服务器网络</span><span class="sxs-lookup"><span data-stu-id="15dfe-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="15dfe-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="15dfe-155">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-156">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-158">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-159">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-160">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="15dfe-163">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="15dfe-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="15dfe-166">中介服务器/PSTN</span><span class="sxs-lookup"><span data-stu-id="15dfe-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="15dfe-167">如果流量通过 IPv6 接口，Lync Server 2013 不支持公用交换电话网络 (PSTN) 呼叫的媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="15dfe-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="15dfe-168">如果需要媒体旁路，则我们建议将 PSTN 网关配置为 IPv4。</span><span class="sxs-lookup"><span data-stu-id="15dfe-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15dfe-169">主要接口\*</span><span class="sxs-lookup"><span data-stu-id="15dfe-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="15dfe-170">PSTN 接口（位于中介服务器上）</span><span class="sxs-lookup"><span data-stu-id="15dfe-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="15dfe-171">PSTN 网关设置</span><span class="sxs-lookup"><span data-stu-id="15dfe-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="15dfe-173">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-175">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-176">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-178">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-179">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="15dfe-181">\* 主接口是与 Lync Server 组件进行通信的接口。</span><span class="sxs-lookup"><span data-stu-id="15dfe-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="15dfe-182">远程用户对等通信</span><span class="sxs-lookup"><span data-stu-id="15dfe-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="15dfe-183">与远程用户的对等通信包括即时消息、音频/视频、应用程序共享和文件传输。</span><span class="sxs-lookup"><span data-stu-id="15dfe-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15dfe-184">远程用户网络</span><span class="sxs-lookup"><span data-stu-id="15dfe-184">Remote user network</span></span></th>
<th><span data-ttu-id="15dfe-185">边缘服务器（外部边缘）</span><span class="sxs-lookup"><span data-stu-id="15dfe-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="15dfe-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-188">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="15dfe-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-190">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="15dfe-191">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="15dfe-193">双协议栈</span><span class="sxs-lookup"><span data-stu-id="15dfe-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="15dfe-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="15dfe-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="15dfe-196">前端池和边缘池配置</span><span class="sxs-lookup"><span data-stu-id="15dfe-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="15dfe-197">下表显示了前端服务器池和内部边缘服务器池之间的支持列表。</span><span class="sxs-lookup"><span data-stu-id="15dfe-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="15dfe-198">前端池和边缘池（内部边缘）矩阵</span><span class="sxs-lookup"><span data-stu-id="15dfe-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="15dfe-199"><strong>边缘池：IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-200"><strong>边缘池：双协议栈</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-201"><strong>边缘池：IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-202"><strong>前端池：IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-203">是</span><span class="sxs-lookup"><span data-stu-id="15dfe-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="15dfe-204">是</span><span class="sxs-lookup"><span data-stu-id="15dfe-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="15dfe-205">否</span><span class="sxs-lookup"><span data-stu-id="15dfe-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-206"><strong>前端池：双协议栈</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-207">是</span><span class="sxs-lookup"><span data-stu-id="15dfe-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="15dfe-208">是</span><span class="sxs-lookup"><span data-stu-id="15dfe-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="15dfe-209">否</span><span class="sxs-lookup"><span data-stu-id="15dfe-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-210"><strong>前端池：IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-211">否</span><span class="sxs-lookup"><span data-stu-id="15dfe-211">No</span></span></p></td>
<td><p><span data-ttu-id="15dfe-212">否</span><span class="sxs-lookup"><span data-stu-id="15dfe-212">No</span></span></p></td>
<td><p><span data-ttu-id="15dfe-213">是\*</span><span class="sxs-lookup"><span data-stu-id="15dfe-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="15dfe-214">\* 仅在实验室环境中使用此组合。</span><span class="sxs-lookup"><span data-stu-id="15dfe-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="15dfe-215">下表是内部和外部边缘接口支持的组合矩阵。</span><span class="sxs-lookup"><span data-stu-id="15dfe-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="15dfe-216">边缘池（内部边缘）和边缘池（外部边缘）矩阵</span><span class="sxs-lookup"><span data-stu-id="15dfe-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="15dfe-217"><strong>边缘池（外部边缘）：IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-218"><strong>边缘池（外部边缘）：双协议栈</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-219"><strong>边缘池（外部边缘）：IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-220"><strong>边缘池（内部边缘）：IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-221">是</span><span class="sxs-lookup"><span data-stu-id="15dfe-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="15dfe-222">是</span><span class="sxs-lookup"><span data-stu-id="15dfe-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="15dfe-223">否</span><span class="sxs-lookup"><span data-stu-id="15dfe-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15dfe-224"><strong>边缘池（内部边缘）：双协议栈</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-225">否</span><span class="sxs-lookup"><span data-stu-id="15dfe-225">No</span></span></p></td>
<td><p><span data-ttu-id="15dfe-226">是</span><span class="sxs-lookup"><span data-stu-id="15dfe-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="15dfe-227">否</span><span class="sxs-lookup"><span data-stu-id="15dfe-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15dfe-228"><strong>边缘池（内部边缘）：IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="15dfe-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="15dfe-229">否</span><span class="sxs-lookup"><span data-stu-id="15dfe-229">No</span></span></p></td>
<td><p><span data-ttu-id="15dfe-230">否</span><span class="sxs-lookup"><span data-stu-id="15dfe-230">No</span></span></p></td>
<td><p><span data-ttu-id="15dfe-231">是\*</span><span class="sxs-lookup"><span data-stu-id="15dfe-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="15dfe-232">\* 仅在实验室环境中使用此组合。</span><span class="sxs-lookup"><span data-stu-id="15dfe-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="15dfe-233">IPv6 的高级企业语音支持</span><span class="sxs-lookup"><span data-stu-id="15dfe-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="15dfe-234">包括呼叫许可控制 (CAC)、增强型 9-1-1 (E9-1-1) 或媒体旁路的部署必须配置为仅 IPv4 或双协议栈实现。</span><span class="sxs-lookup"><span data-stu-id="15dfe-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15dfe-235">在双堆栈部署中，即使 Lync 客户端使用 IPv6 连接到 Lync Server，Lync 也将尽力映射合适的 IPv4 地址以支持 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="15dfe-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="15dfe-236">不支持使用 IPv6 地址的位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="15dfe-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="15dfe-p107">Exchange 统一消息 (UM) 不支持 IPv6。对于 Exchange UM，请确保 DNS 解析不会返回 IPv6 地址。使用 IPv6 可能会在将呼叫发送至语音信箱时导致失败。</span><span class="sxs-lookup"><span data-stu-id="15dfe-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="15dfe-240">适用于 IPv6 的其他 Lync Server 2013 功能支持</span><span class="sxs-lookup"><span data-stu-id="15dfe-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="15dfe-241">除了前面提到的功能和组件，Lync Server 2013 还支持 IPv6 以实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="15dfe-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="15dfe-242">**持久聊天**</span><span class="sxs-lookup"><span data-stu-id="15dfe-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="15dfe-243">您可以使用拓扑生成器为持久聊天配置 IPv6。</span><span class="sxs-lookup"><span data-stu-id="15dfe-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="15dfe-244">有关配置持久聊天的详细信息，请参阅部署持久聊天服务器文档。</span><span class="sxs-lookup"><span data-stu-id="15dfe-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="15dfe-245">**用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 报告**</span><span class="sxs-lookup"><span data-stu-id="15dfe-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="15dfe-246">监视报告将会包括 IP 地址，因为该地址存储在监视服务器数据库中（无论类型为 IPv4 还是 IPv6）。</span><span class="sxs-lookup"><span data-stu-id="15dfe-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

