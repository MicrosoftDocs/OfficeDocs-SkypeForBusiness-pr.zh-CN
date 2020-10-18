---
title: Lync Server 2013 IPsec 例外
description: Lync Server 2013 IPsec 例外。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574998"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="2e17f-103">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="2e17f-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e17f-104">_**上次修改的主题：** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="2e17f-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="2e17f-p101">对于已经部署了 Internet 协议安全性 (IPsec)（请参阅 IETF RFC 4301-4309）的企业网络，必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。</span><span class="sxs-lookup"><span data-stu-id="2e17f-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="2e17f-107">下表介绍了建议采用的 IPsec 例外设置。</span><span class="sxs-lookup"><span data-stu-id="2e17f-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="2e17f-108">建议采用的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="2e17f-108">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="2e17f-109">规则名称</span><span class="sxs-lookup"><span data-stu-id="2e17f-109">Rule name</span></span></th>
<th><span data-ttu-id="2e17f-110">源 IP</span><span class="sxs-lookup"><span data-stu-id="2e17f-110">Source IP</span></span></th>
<th><span data-ttu-id="2e17f-111">目标 IP</span><span class="sxs-lookup"><span data-stu-id="2e17f-111">Destination IP</span></span></th>
<th><span data-ttu-id="2e17f-112">协议</span><span class="sxs-lookup"><span data-stu-id="2e17f-112">Protocol</span></span></th>
<th><span data-ttu-id="2e17f-113">源端口</span><span class="sxs-lookup"><span data-stu-id="2e17f-113">Source port</span></span></th>
<th><span data-ttu-id="2e17f-114">目标端口</span><span class="sxs-lookup"><span data-stu-id="2e17f-114">Destination port</span></span></th>
<th><span data-ttu-id="2e17f-115">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="2e17f-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e17f-116">A/V 边缘服务器内部入站</span><span class="sxs-lookup"><span data-stu-id="2e17f-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-117">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-117">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-118">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="2e17f-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="2e17f-119">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-120">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-120">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-121">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-121">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-122">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e17f-123">A/V 边缘服务器外部入站</span><span class="sxs-lookup"><span data-stu-id="2e17f-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-124">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-124">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-125">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="2e17f-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="2e17f-126">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-127">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-127">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-128">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-128">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-129">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e17f-130">A/V 边缘服务器内部出站</span><span class="sxs-lookup"><span data-stu-id="2e17f-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-131">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="2e17f-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="2e17f-132">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-132">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-133">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-134">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-134">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-135">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-135">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-136">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e17f-137">A/V 边缘服务器外部出站</span><span class="sxs-lookup"><span data-stu-id="2e17f-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-138">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="2e17f-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="2e17f-139">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-139">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-140">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-141">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-141">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-142">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-142">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-143">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e17f-144">中介服务器入站</span><span class="sxs-lookup"><span data-stu-id="2e17f-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-145">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-145">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-146">中介</span><span class="sxs-lookup"><span data-stu-id="2e17f-146">Mediation</span></span></p>
<p><span data-ttu-id="2e17f-147">服务器 (s) </span><span class="sxs-lookup"><span data-stu-id="2e17f-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="2e17f-148">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-149">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-149">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-150">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-150">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-151">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e17f-152">中介服务器出站</span><span class="sxs-lookup"><span data-stu-id="2e17f-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-153">中介</span><span class="sxs-lookup"><span data-stu-id="2e17f-153">Mediation</span></span></p>
<p><span data-ttu-id="2e17f-154">服务器 (s) </span><span class="sxs-lookup"><span data-stu-id="2e17f-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="2e17f-155">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-155">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-156">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-157">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-157">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-158">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-158">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-159">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e17f-160">会议助理入站</span><span class="sxs-lookup"><span data-stu-id="2e17f-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-161">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-161">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-162">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="2e17f-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="2e17f-163">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-164">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-164">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-165">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-165">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-166">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e17f-167">会议助理出站</span><span class="sxs-lookup"><span data-stu-id="2e17f-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-168">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="2e17f-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="2e17f-169">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-169">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-170">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-171">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-171">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-172">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-172">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-173">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e17f-174">A/V 会议入站</span><span class="sxs-lookup"><span data-stu-id="2e17f-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-175">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-175">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-176">前端服务器</span><span class="sxs-lookup"><span data-stu-id="2e17f-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2e17f-177">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-178">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-178">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-179">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-179">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-180">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e17f-181">A/V 会议出站</span><span class="sxs-lookup"><span data-stu-id="2e17f-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-182">前端服务器</span><span class="sxs-lookup"><span data-stu-id="2e17f-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2e17f-183">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-183">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-184">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-185">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-185">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-186">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-186">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-187">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e17f-188">Exchange 入站</span><span class="sxs-lookup"><span data-stu-id="2e17f-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-189">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-189">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-190">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="2e17f-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="2e17f-191">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-192">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-192">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-193">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-193">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-194">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e17f-195">应用程序共享服务器入站</span><span class="sxs-lookup"><span data-stu-id="2e17f-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-196">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-196">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-197">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="2e17f-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="2e17f-198">TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-199">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-199">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-200">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-200">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-201">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e17f-202">应用程序共享服务器出站</span><span class="sxs-lookup"><span data-stu-id="2e17f-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-203">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="2e17f-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="2e17f-204">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-204">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-205">TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-206">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-206">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-207">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-207">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-208">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e17f-209">Exchange 出站</span><span class="sxs-lookup"><span data-stu-id="2e17f-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="2e17f-210">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="2e17f-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="2e17f-211">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-211">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-212">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2e17f-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-213">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-213">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-214">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-214">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-215">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e17f-216">客户端</span><span class="sxs-lookup"><span data-stu-id="2e17f-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="2e17f-217">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-217">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-218">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-218">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-219">UDP</span><span class="sxs-lookup"><span data-stu-id="2e17f-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="2e17f-220">指定的媒体端口范围</span><span class="sxs-lookup"><span data-stu-id="2e17f-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="2e17f-221">任何</span><span class="sxs-lookup"><span data-stu-id="2e17f-221">Any</span></span></p></td>
<td><p><span data-ttu-id="2e17f-222">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2e17f-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

