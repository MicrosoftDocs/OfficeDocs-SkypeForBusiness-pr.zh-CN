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
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="c2972-102">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="c2972-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2972-103">_**上次修改的主题：** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="c2972-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="c2972-p101">对于已经部署了 Internet 协议安全性 (IPsec)（请参阅 IETF RFC 4301-4309）的企业网络，必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。</span><span class="sxs-lookup"><span data-stu-id="c2972-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="c2972-106">下表介绍了建议采用的 IPsec 例外设置。</span><span class="sxs-lookup"><span data-stu-id="c2972-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="c2972-107">建议采用的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="c2972-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="c2972-108">规则名称</span><span class="sxs-lookup"><span data-stu-id="c2972-108">Rule name</span></span></th>
<th><span data-ttu-id="c2972-109">源 IP</span><span class="sxs-lookup"><span data-stu-id="c2972-109">Source IP</span></span></th>
<th><span data-ttu-id="c2972-110">目标 IP</span><span class="sxs-lookup"><span data-stu-id="c2972-110">Destination IP</span></span></th>
<th><span data-ttu-id="c2972-111">协议</span><span class="sxs-lookup"><span data-stu-id="c2972-111">Protocol</span></span></th>
<th><span data-ttu-id="c2972-112">源端口</span><span class="sxs-lookup"><span data-stu-id="c2972-112">Source port</span></span></th>
<th><span data-ttu-id="c2972-113">目标端口</span><span class="sxs-lookup"><span data-stu-id="c2972-113">Destination port</span></span></th>
<th><span data-ttu-id="c2972-114">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="c2972-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2972-115">A/V 边缘服务器内部入站</span><span class="sxs-lookup"><span data-stu-id="c2972-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-116">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-116">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-117">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="c2972-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="c2972-118">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-119">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-119">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-120">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-120">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-121">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2972-122">A/V 边缘服务器外部入站</span><span class="sxs-lookup"><span data-stu-id="c2972-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-123">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-123">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-124">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="c2972-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="c2972-125">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-126">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-126">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-127">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-127">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-128">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2972-129">A/V 边缘服务器内部出站</span><span class="sxs-lookup"><span data-stu-id="c2972-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-130">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="c2972-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="c2972-131">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-131">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-133">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-133">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-134">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-134">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-135">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2972-136">A/V 边缘服务器外部出站</span><span class="sxs-lookup"><span data-stu-id="c2972-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-137">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="c2972-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="c2972-138">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-138">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-139">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-140">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-140">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-141">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-141">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-142">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2972-143">中介服务器入站</span><span class="sxs-lookup"><span data-stu-id="c2972-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-144">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-144">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-145">中介</span><span class="sxs-lookup"><span data-stu-id="c2972-145">Mediation</span></span></p>
<p><span data-ttu-id="c2972-146">服务器（s）</span><span class="sxs-lookup"><span data-stu-id="c2972-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="c2972-147">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-148">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-148">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-149">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-149">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-150">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2972-151">中介服务器出站</span><span class="sxs-lookup"><span data-stu-id="c2972-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-152">中介</span><span class="sxs-lookup"><span data-stu-id="c2972-152">Mediation</span></span></p>
<p><span data-ttu-id="c2972-153">服务器（s）</span><span class="sxs-lookup"><span data-stu-id="c2972-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="c2972-154">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-154">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-155">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-156">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-156">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-157">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-157">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-158">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2972-159">会议助理入站</span><span class="sxs-lookup"><span data-stu-id="c2972-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-160">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-160">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-161">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="c2972-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="c2972-162">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-163">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-163">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-164">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-164">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-165">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2972-166">会议助理出站</span><span class="sxs-lookup"><span data-stu-id="c2972-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-167">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="c2972-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="c2972-168">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-168">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-169">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-170">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-170">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-171">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-171">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-172">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2972-173">A/V 会议入站</span><span class="sxs-lookup"><span data-stu-id="c2972-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-174">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-174">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-175">前端服务器</span><span class="sxs-lookup"><span data-stu-id="c2972-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="c2972-176">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-177">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-177">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-178">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-178">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-179">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2972-180">A/V 会议出站</span><span class="sxs-lookup"><span data-stu-id="c2972-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-181">前端服务器</span><span class="sxs-lookup"><span data-stu-id="c2972-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="c2972-182">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-182">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-183">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-184">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-184">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-185">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-185">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-186">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2972-187">Exchange 入站</span><span class="sxs-lookup"><span data-stu-id="c2972-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-188">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-188">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-189">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="c2972-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="c2972-190">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-191">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-191">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-192">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-192">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-193">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2972-194">应用程序共享服务器入站</span><span class="sxs-lookup"><span data-stu-id="c2972-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-195">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-195">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-196">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="c2972-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="c2972-197">TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-198">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-198">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-199">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-199">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-200">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2972-201">应用程序共享服务器出站</span><span class="sxs-lookup"><span data-stu-id="c2972-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-202">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="c2972-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="c2972-203">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-203">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-204">TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-205">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-205">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-206">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-206">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-207">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2972-208">Exchange 出站</span><span class="sxs-lookup"><span data-stu-id="c2972-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="c2972-209">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="c2972-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="c2972-210">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-210">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-211">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="c2972-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c2972-212">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-212">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-213">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-213">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-214">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2972-215">客户端</span><span class="sxs-lookup"><span data-stu-id="c2972-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="c2972-216">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-216">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-217">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-217">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-218">UDP</span><span class="sxs-lookup"><span data-stu-id="c2972-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="c2972-219">指定的媒体端口范围</span><span class="sxs-lookup"><span data-stu-id="c2972-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="c2972-220">任意</span><span class="sxs-lookup"><span data-stu-id="c2972-220">Any</span></span></p></td>
<td><p><span data-ttu-id="c2972-221">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="c2972-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

