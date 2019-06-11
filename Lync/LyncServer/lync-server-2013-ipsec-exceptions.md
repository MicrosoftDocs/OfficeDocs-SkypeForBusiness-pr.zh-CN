---
title: Lync Server 2013 IPsec 例外
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="edec7-102">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="edec7-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edec7-103">_**主题上次修改时间:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="edec7-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="edec7-104">对于 Internet 协议安全 (IPsec) (请参阅 IETF RFC 4301-4309) 已部署的企业网络, 必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="edec7-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="edec7-105">提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。</span><span class="sxs-lookup"><span data-stu-id="edec7-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="edec7-106">下表介绍了建议采用的 IPsec 例外设置。</span><span class="sxs-lookup"><span data-stu-id="edec7-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="edec7-107">建议采用的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="edec7-107">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edec7-108">规则名称</span><span class="sxs-lookup"><span data-stu-id="edec7-108">Rule name</span></span></th>
<th><span data-ttu-id="edec7-109">源 IP</span><span class="sxs-lookup"><span data-stu-id="edec7-109">Source IP</span></span></th>
<th><span data-ttu-id="edec7-110">目标 IP</span><span class="sxs-lookup"><span data-stu-id="edec7-110">Destination IP</span></span></th>
<th><span data-ttu-id="edec7-111">协议</span><span class="sxs-lookup"><span data-stu-id="edec7-111">Protocol</span></span></th>
<th><span data-ttu-id="edec7-112">源端口</span><span class="sxs-lookup"><span data-stu-id="edec7-112">Source port</span></span></th>
<th><span data-ttu-id="edec7-113">目标端口</span><span class="sxs-lookup"><span data-stu-id="edec7-113">Destination port</span></span></th>
<th><span data-ttu-id="edec7-114">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="edec7-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edec7-115">A/V 边缘服务器内部入站</span><span class="sxs-lookup"><span data-stu-id="edec7-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-116">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-116">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-117">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="edec7-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="edec7-118">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-119">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-119">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-120">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-120">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-121">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edec7-122">A/V 边缘服务器外部入站</span><span class="sxs-lookup"><span data-stu-id="edec7-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-123">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-123">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-124">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="edec7-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="edec7-125">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-126">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-126">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-127">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-127">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-128">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edec7-129">A/V 边缘服务器内部出站</span><span class="sxs-lookup"><span data-stu-id="edec7-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-130">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="edec7-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="edec7-131">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-131">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-133">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-133">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-134">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-134">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-135">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edec7-136">A/V 边缘服务器外部出站</span><span class="sxs-lookup"><span data-stu-id="edec7-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-137">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="edec7-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="edec7-138">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-138">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-139">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-140">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-140">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-141">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-141">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-142">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edec7-143">中介服务器入站</span><span class="sxs-lookup"><span data-stu-id="edec7-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-144">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-144">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-145">中介</span><span class="sxs-lookup"><span data-stu-id="edec7-145">Mediation</span></span></p>
<p><span data-ttu-id="edec7-146">服务器</span><span class="sxs-lookup"><span data-stu-id="edec7-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="edec7-147">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-148">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-148">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-149">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-149">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-150">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edec7-151">中介服务器出站</span><span class="sxs-lookup"><span data-stu-id="edec7-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-152">中介</span><span class="sxs-lookup"><span data-stu-id="edec7-152">Mediation</span></span></p>
<p><span data-ttu-id="edec7-153">服务器</span><span class="sxs-lookup"><span data-stu-id="edec7-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="edec7-154">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-154">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-155">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-156">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-156">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-157">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-157">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-158">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edec7-159">会议助理入站</span><span class="sxs-lookup"><span data-stu-id="edec7-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-160">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-160">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-161">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="edec7-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="edec7-162">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-163">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-163">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-164">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-164">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-165">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edec7-166">会议助理出站</span><span class="sxs-lookup"><span data-stu-id="edec7-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-167">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="edec7-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="edec7-168">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-168">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-169">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-170">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-170">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-171">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-171">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-172">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edec7-173">A/V 会议入站</span><span class="sxs-lookup"><span data-stu-id="edec7-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-174">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-174">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-175">前端服务器</span><span class="sxs-lookup"><span data-stu-id="edec7-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="edec7-176">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-177">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-177">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-178">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-178">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-179">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edec7-180">A/V 会议出站</span><span class="sxs-lookup"><span data-stu-id="edec7-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-181">前端服务器</span><span class="sxs-lookup"><span data-stu-id="edec7-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="edec7-182">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-182">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-183">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-184">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-184">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-185">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-185">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-186">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edec7-187">Exchange 入站</span><span class="sxs-lookup"><span data-stu-id="edec7-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-188">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-188">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-189">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="edec7-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="edec7-190">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-191">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-191">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-192">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-192">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-193">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edec7-194">应用程序共享服务器入站</span><span class="sxs-lookup"><span data-stu-id="edec7-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-195">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-195">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-196">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="edec7-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="edec7-197">TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-198">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-198">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-199">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-199">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-200">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edec7-201">应用程序共享服务器出站</span><span class="sxs-lookup"><span data-stu-id="edec7-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-202">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="edec7-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="edec7-203">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-203">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-204">TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-205">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-205">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-206">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-206">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-207">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edec7-208">Exchange 出站</span><span class="sxs-lookup"><span data-stu-id="edec7-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="edec7-209">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="edec7-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="edec7-210">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-210">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-211">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="edec7-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="edec7-212">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-212">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-213">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-213">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-214">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edec7-215">客户端</span><span class="sxs-lookup"><span data-stu-id="edec7-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="edec7-216">任何</span><span class="sxs-lookup"><span data-stu-id="edec7-216">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-217">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-217">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-218">UDP</span><span class="sxs-lookup"><span data-stu-id="edec7-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="edec7-219">指定的媒体端口范围</span><span class="sxs-lookup"><span data-stu-id="edec7-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="edec7-220">任意</span><span class="sxs-lookup"><span data-stu-id="edec7-220">Any</span></span></p></td>
<td><p><span data-ttu-id="edec7-221">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="edec7-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

