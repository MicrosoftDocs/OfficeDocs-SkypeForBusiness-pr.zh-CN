---
title: Lync Server 2013 IPsec 例外
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
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514149"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="9d323-102">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="9d323-102">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d323-103">_**上次修改的主题：** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="9d323-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="9d323-p101">对于已经部署了 Internet 协议安全性 (IPsec)（请参阅 IETF RFC 4301-4309）的企业网络，必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。</span><span class="sxs-lookup"><span data-stu-id="9d323-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="9d323-106">下表介绍了建议采用的 IPsec 例外设置。</span><span class="sxs-lookup"><span data-stu-id="9d323-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="9d323-107">建议采用的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="9d323-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="9d323-108">规则名称</span><span class="sxs-lookup"><span data-stu-id="9d323-108">Rule name</span></span></th>
<th><span data-ttu-id="9d323-109">源 IP</span><span class="sxs-lookup"><span data-stu-id="9d323-109">Source IP</span></span></th>
<th><span data-ttu-id="9d323-110">目标 IP</span><span class="sxs-lookup"><span data-stu-id="9d323-110">Destination IP</span></span></th>
<th><span data-ttu-id="9d323-111">协议</span><span class="sxs-lookup"><span data-stu-id="9d323-111">Protocol</span></span></th>
<th><span data-ttu-id="9d323-112">源端口</span><span class="sxs-lookup"><span data-stu-id="9d323-112">Source port</span></span></th>
<th><span data-ttu-id="9d323-113">目标端口</span><span class="sxs-lookup"><span data-stu-id="9d323-113">Destination port</span></span></th>
<th><span data-ttu-id="9d323-114">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="9d323-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d323-115">A/V 边缘服务器内部入站</span><span class="sxs-lookup"><span data-stu-id="9d323-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-116">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-116">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-117">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="9d323-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="9d323-118">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-119">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-119">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-120">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-120">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-121">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d323-122">A/V 边缘服务器外部入站</span><span class="sxs-lookup"><span data-stu-id="9d323-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-123">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-123">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-124">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="9d323-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="9d323-125">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-126">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-126">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-127">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-127">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-128">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d323-129">A/V 边缘服务器内部出站</span><span class="sxs-lookup"><span data-stu-id="9d323-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-130">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="9d323-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="9d323-131">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-131">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-133">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-133">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-134">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-134">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-135">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d323-136">A/V 边缘服务器外部出站</span><span class="sxs-lookup"><span data-stu-id="9d323-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-137">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="9d323-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="9d323-138">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-138">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-139">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-140">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-140">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-141">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-141">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-142">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d323-143">中介服务器入站</span><span class="sxs-lookup"><span data-stu-id="9d323-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-144">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-144">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-145">中介</span><span class="sxs-lookup"><span data-stu-id="9d323-145">Mediation</span></span></p>
<p><span data-ttu-id="9d323-146">服务器 (s) </span><span class="sxs-lookup"><span data-stu-id="9d323-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="9d323-147">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-148">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-148">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-149">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-149">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-150">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d323-151">中介服务器出站</span><span class="sxs-lookup"><span data-stu-id="9d323-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-152">中介</span><span class="sxs-lookup"><span data-stu-id="9d323-152">Mediation</span></span></p>
<p><span data-ttu-id="9d323-153">服务器 (s) </span><span class="sxs-lookup"><span data-stu-id="9d323-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="9d323-154">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-154">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-155">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-156">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-156">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-157">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-157">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-158">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d323-159">会议助理入站</span><span class="sxs-lookup"><span data-stu-id="9d323-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-160">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-160">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-161">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="9d323-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="9d323-162">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-163">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-163">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-164">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-164">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-165">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d323-166">会议助理出站</span><span class="sxs-lookup"><span data-stu-id="9d323-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-167">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="9d323-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="9d323-168">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-168">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-169">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-170">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-170">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-171">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-171">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-172">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d323-173">A/V 会议入站</span><span class="sxs-lookup"><span data-stu-id="9d323-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-174">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-174">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-175">前端服务器</span><span class="sxs-lookup"><span data-stu-id="9d323-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="9d323-176">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-177">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-177">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-178">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-178">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-179">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d323-180">A/V 会议出站</span><span class="sxs-lookup"><span data-stu-id="9d323-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-181">前端服务器</span><span class="sxs-lookup"><span data-stu-id="9d323-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="9d323-182">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-182">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-183">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-184">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-184">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-185">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-185">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-186">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d323-187">Exchange 入站</span><span class="sxs-lookup"><span data-stu-id="9d323-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-188">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-188">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-189">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="9d323-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="9d323-190">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-191">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-191">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-192">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-192">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-193">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d323-194">应用程序共享服务器入站</span><span class="sxs-lookup"><span data-stu-id="9d323-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-195">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-195">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-196">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="9d323-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="9d323-197">TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-198">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-198">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-199">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-199">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-200">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d323-201">应用程序共享服务器出站</span><span class="sxs-lookup"><span data-stu-id="9d323-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-202">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="9d323-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="9d323-203">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-203">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-204">TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-205">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-205">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-206">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-206">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-207">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d323-208">Exchange 出站</span><span class="sxs-lookup"><span data-stu-id="9d323-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="9d323-209">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="9d323-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="9d323-210">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-210">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-211">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="9d323-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9d323-212">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-212">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-213">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-213">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-214">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d323-215">客户端</span><span class="sxs-lookup"><span data-stu-id="9d323-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="9d323-216">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-216">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-217">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-217">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-218">UDP</span><span class="sxs-lookup"><span data-stu-id="9d323-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="9d323-219">指定的媒体端口范围</span><span class="sxs-lookup"><span data-stu-id="9d323-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="9d323-220">任何</span><span class="sxs-lookup"><span data-stu-id="9d323-220">Any</span></span></p></td>
<td><p><span data-ttu-id="9d323-221">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="9d323-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

