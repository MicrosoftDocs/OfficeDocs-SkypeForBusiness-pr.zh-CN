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
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="06d1c-102">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="06d1c-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06d1c-103">_**主题上次修改时间：** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="06d1c-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="06d1c-104">对于 Internet 协议安全（IPsec）（请参阅 IETF RFC 4301-4309）已部署的企业网络，必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="06d1c-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="06d1c-105">提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。</span><span class="sxs-lookup"><span data-stu-id="06d1c-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="06d1c-106">下表介绍了建议采用的 IPsec 例外设置。</span><span class="sxs-lookup"><span data-stu-id="06d1c-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="06d1c-107">建议采用的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="06d1c-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="06d1c-108">规则名称</span><span class="sxs-lookup"><span data-stu-id="06d1c-108">Rule name</span></span></th>
<th><span data-ttu-id="06d1c-109">源 IP</span><span class="sxs-lookup"><span data-stu-id="06d1c-109">Source IP</span></span></th>
<th><span data-ttu-id="06d1c-110">目标 IP</span><span class="sxs-lookup"><span data-stu-id="06d1c-110">Destination IP</span></span></th>
<th><span data-ttu-id="06d1c-111">协议</span><span class="sxs-lookup"><span data-stu-id="06d1c-111">Protocol</span></span></th>
<th><span data-ttu-id="06d1c-112">源端口</span><span class="sxs-lookup"><span data-stu-id="06d1c-112">Source port</span></span></th>
<th><span data-ttu-id="06d1c-113">目标端口</span><span class="sxs-lookup"><span data-stu-id="06d1c-113">Destination port</span></span></th>
<th><span data-ttu-id="06d1c-114">身份验证要求</span><span class="sxs-lookup"><span data-stu-id="06d1c-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06d1c-115">A/V 边缘服务器内部入站</span><span class="sxs-lookup"><span data-stu-id="06d1c-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-116">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-116">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-117">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="06d1c-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="06d1c-118">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-119">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-119">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-120">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-120">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-121">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d1c-122">A/V 边缘服务器外部入站</span><span class="sxs-lookup"><span data-stu-id="06d1c-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-123">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-123">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-124">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="06d1c-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="06d1c-125">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-126">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-126">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-127">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-127">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-128">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d1c-129">A/V 边缘服务器内部出站</span><span class="sxs-lookup"><span data-stu-id="06d1c-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-130">A/V 边缘服务器内部</span><span class="sxs-lookup"><span data-stu-id="06d1c-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="06d1c-131">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-131">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-133">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-133">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-134">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-134">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-135">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d1c-136">A/V 边缘服务器外部出站</span><span class="sxs-lookup"><span data-stu-id="06d1c-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-137">A/V 边缘服务器外部</span><span class="sxs-lookup"><span data-stu-id="06d1c-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="06d1c-138">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-138">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-139">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-140">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-140">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-141">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-141">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-142">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d1c-143">中介服务器入站</span><span class="sxs-lookup"><span data-stu-id="06d1c-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-144">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-144">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-145">中介</span><span class="sxs-lookup"><span data-stu-id="06d1c-145">Mediation</span></span></p>
<p><span data-ttu-id="06d1c-146">服务器</span><span class="sxs-lookup"><span data-stu-id="06d1c-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="06d1c-147">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-148">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-148">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-149">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-149">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-150">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d1c-151">中介服务器出站</span><span class="sxs-lookup"><span data-stu-id="06d1c-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-152">中介</span><span class="sxs-lookup"><span data-stu-id="06d1c-152">Mediation</span></span></p>
<p><span data-ttu-id="06d1c-153">服务器</span><span class="sxs-lookup"><span data-stu-id="06d1c-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="06d1c-154">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-154">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-155">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-156">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-156">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-157">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-157">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-158">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d1c-159">会议助理入站</span><span class="sxs-lookup"><span data-stu-id="06d1c-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-160">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-160">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-161">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="06d1c-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="06d1c-162">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-163">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-163">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-164">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-164">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-165">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d1c-166">会议助理出站</span><span class="sxs-lookup"><span data-stu-id="06d1c-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-167">运行会议助理的前端服务器</span><span class="sxs-lookup"><span data-stu-id="06d1c-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="06d1c-168">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-168">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-169">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-170">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-170">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-171">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-171">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-172">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d1c-173">A/V 会议入站</span><span class="sxs-lookup"><span data-stu-id="06d1c-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-174">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-174">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-175">前端服务器</span><span class="sxs-lookup"><span data-stu-id="06d1c-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="06d1c-176">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-177">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-177">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-178">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-178">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-179">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d1c-180">A/V 会议出站</span><span class="sxs-lookup"><span data-stu-id="06d1c-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-181">前端服务器</span><span class="sxs-lookup"><span data-stu-id="06d1c-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="06d1c-182">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-182">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-183">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-184">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-184">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-185">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-185">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-186">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d1c-187">Exchange 入站</span><span class="sxs-lookup"><span data-stu-id="06d1c-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-188">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-188">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-189">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="06d1c-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="06d1c-190">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-191">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-191">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-192">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-192">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-193">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d1c-194">应用程序共享服务器入站</span><span class="sxs-lookup"><span data-stu-id="06d1c-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-195">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-195">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-196">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="06d1c-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="06d1c-197">TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-198">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-198">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-199">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-199">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-200">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d1c-201">应用程序共享服务器出站</span><span class="sxs-lookup"><span data-stu-id="06d1c-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-202">应用程序共享服务器</span><span class="sxs-lookup"><span data-stu-id="06d1c-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="06d1c-203">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-203">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-204">TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-205">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-205">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-206">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-206">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-207">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d1c-208">Exchange 出站</span><span class="sxs-lookup"><span data-stu-id="06d1c-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="06d1c-209">Exchange 统一消息</span><span class="sxs-lookup"><span data-stu-id="06d1c-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="06d1c-210">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-210">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-211">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="06d1c-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-212">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-212">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-213">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-213">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-214">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d1c-215">客户端</span><span class="sxs-lookup"><span data-stu-id="06d1c-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="06d1c-216">任何</span><span class="sxs-lookup"><span data-stu-id="06d1c-216">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-217">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-217">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-218">UDP</span><span class="sxs-lookup"><span data-stu-id="06d1c-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="06d1c-219">指定的媒体端口范围</span><span class="sxs-lookup"><span data-stu-id="06d1c-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="06d1c-220">任意</span><span class="sxs-lookup"><span data-stu-id="06d1c-220">Any</span></span></p></td>
<td><p><span data-ttu-id="06d1c-221">不进行身份验证</span><span class="sxs-lookup"><span data-stu-id="06d1c-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

