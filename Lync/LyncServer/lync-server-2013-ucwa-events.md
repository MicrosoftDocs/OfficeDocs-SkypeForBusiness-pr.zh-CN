---
title: Lync Server 2013： UCWA 事件
description: Lync Server 2013： UCWA 事件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548848"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="2c501-103">Lync Server 2013 中的 UCWA 事件</span><span class="sxs-lookup"><span data-stu-id="2c501-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c501-104">_**上次修改的主题：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="2c501-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="2c501-105">Lync Server 2013 使用统一通信 Web API (UCWA) 进行多种用途，从访问 Microsoft Exchange 以进行联系人搜索，以更新移动客户端的状态。</span><span class="sxs-lookup"><span data-stu-id="2c501-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="2c501-106">UCWA 会将操作行为的记录编写为事件类型信息、警告和错误。</span><span class="sxs-lookup"><span data-stu-id="2c501-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="2c501-107">下表介绍了 UCWA 组件可以编写的事件。</span><span class="sxs-lookup"><span data-stu-id="2c501-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c501-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2c501-108">Event ID</span></span></th>
<th><span data-ttu-id="2c501-109">事件类型</span><span class="sxs-lookup"><span data-stu-id="2c501-109">Event Type</span></span></th>
<th><span data-ttu-id="2c501-110">摘要</span><span class="sxs-lookup"><span data-stu-id="2c501-110">Summary</span></span></th>
<th><span data-ttu-id="2c501-111">原因和解决方法</span><span class="sxs-lookup"><span data-stu-id="2c501-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c501-112">20001</span><span class="sxs-lookup"><span data-stu-id="2c501-112">20001</span></span></p></td>
<td><p><span data-ttu-id="2c501-113">之</span><span class="sxs-lookup"><span data-stu-id="2c501-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="2c501-114">UCWA 已初始化</span><span class="sxs-lookup"><span data-stu-id="2c501-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="2c501-115">不适用</span><span class="sxs-lookup"><span data-stu-id="2c501-115">N/A</span></span></p>
<p><span data-ttu-id="2c501-116">不适用</span><span class="sxs-lookup"><span data-stu-id="2c501-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-117">20002</span><span class="sxs-lookup"><span data-stu-id="2c501-117">20002</span></span></p></td>
<td><p><span data-ttu-id="2c501-118">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-118">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-119">UCWA 在初始化期间遇到意外异常</span><span class="sxs-lookup"><span data-stu-id="2c501-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="2c501-120">初始化过程中出现意外错误</span><span class="sxs-lookup"><span data-stu-id="2c501-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="2c501-121">在关联的事件日志条目中检查异常详细信息，以确定可能的原因</span><span class="sxs-lookup"><span data-stu-id="2c501-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-122">20003</span><span class="sxs-lookup"><span data-stu-id="2c501-122">20003</span></span></p></td>
<td><p><span data-ttu-id="2c501-123">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-123">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-124">UCWA 遇到未经处理的异常</span><span class="sxs-lookup"><span data-stu-id="2c501-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="2c501-125">发生未处理的异常</span><span class="sxs-lookup"><span data-stu-id="2c501-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="2c501-126">重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="2c501-126">Restart the server.</span></span> <span data-ttu-id="2c501-127">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="2c501-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-128">20004</span><span class="sxs-lookup"><span data-stu-id="2c501-128">20004</span></span></p></td>
<td><p><span data-ttu-id="2c501-129">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-129">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-130">无法访问 HD 照片的 Exchange</span><span class="sxs-lookup"><span data-stu-id="2c501-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="2c501-131">与 Exchange 的连接不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="2c501-132">请确保与 Exchange 的连接可用</span><span class="sxs-lookup"><span data-stu-id="2c501-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-133">20005</span><span class="sxs-lookup"><span data-stu-id="2c501-133">20005</span></span></p></td>
<td><p><span data-ttu-id="2c501-134">之</span><span class="sxs-lookup"><span data-stu-id="2c501-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="2c501-135">从无法访问 Exchange for HD 照片的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="2c501-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="2c501-136">不适用</span><span class="sxs-lookup"><span data-stu-id="2c501-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-137">20006</span><span class="sxs-lookup"><span data-stu-id="2c501-137">20006</span></span></p></td>
<td><p><span data-ttu-id="2c501-138">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-138">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-139">无法访问联系人搜索的 Exchange</span><span class="sxs-lookup"><span data-stu-id="2c501-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="2c501-140">与 Exchange 的连接不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="2c501-141">请确保与 Exchange 的连接可用</span><span class="sxs-lookup"><span data-stu-id="2c501-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-142">20007</span><span class="sxs-lookup"><span data-stu-id="2c501-142">20007</span></span></p></td>
<td><p><span data-ttu-id="2c501-143">之</span><span class="sxs-lookup"><span data-stu-id="2c501-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="2c501-144">从 Exchange 中的搜索联系人故障中恢复</span><span class="sxs-lookup"><span data-stu-id="2c501-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="2c501-145">不适用</span><span class="sxs-lookup"><span data-stu-id="2c501-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-146">20008</span><span class="sxs-lookup"><span data-stu-id="2c501-146">20008</span></span></p></td>
<td><p><span data-ttu-id="2c501-147">警告</span><span class="sxs-lookup"><span data-stu-id="2c501-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="2c501-148">尝试为每个应用程序订阅多于允许的状态订阅</span><span class="sxs-lookup"><span data-stu-id="2c501-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="2c501-149">尝试为每个应用程序订阅多于允许的状态订阅</span><span class="sxs-lookup"><span data-stu-id="2c501-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="2c501-150">检查客户端是否有不必要的订阅</span><span class="sxs-lookup"><span data-stu-id="2c501-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-151">20009</span><span class="sxs-lookup"><span data-stu-id="2c501-151">20009</span></span></p></td>
<td><p><span data-ttu-id="2c501-152">警告</span><span class="sxs-lookup"><span data-stu-id="2c501-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="2c501-153">每批次尝试订阅的订阅数超过允许的状态订阅数</span><span class="sxs-lookup"><span data-stu-id="2c501-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="2c501-154">每批次尝试订阅的订阅数超过允许的状态订阅数</span><span class="sxs-lookup"><span data-stu-id="2c501-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="2c501-155">检查客户端是否有不必要的订阅</span><span class="sxs-lookup"><span data-stu-id="2c501-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-156">20010</span><span class="sxs-lookup"><span data-stu-id="2c501-156">20010</span></span></p></td>
<td><p><span data-ttu-id="2c501-157">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-157">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-158">无法检索带内数据</span><span class="sxs-lookup"><span data-stu-id="2c501-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="2c501-159">无法检索带内数据</span><span class="sxs-lookup"><span data-stu-id="2c501-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="2c501-160">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="2c501-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-161">20011</span><span class="sxs-lookup"><span data-stu-id="2c501-161">20011</span></span></p></td>
<td><p><span data-ttu-id="2c501-162">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-162">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-163">无法订阅状态</span><span class="sxs-lookup"><span data-stu-id="2c501-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="2c501-164">无法订阅状态</span><span class="sxs-lookup"><span data-stu-id="2c501-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="2c501-165">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="2c501-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-166">20012</span><span class="sxs-lookup"><span data-stu-id="2c501-166">20012</span></span></p></td>
<td><p><span data-ttu-id="2c501-167">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-167">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-168">无法注册终结点</span><span class="sxs-lookup"><span data-stu-id="2c501-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="2c501-169">无法注册终结点</span><span class="sxs-lookup"><span data-stu-id="2c501-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="2c501-170">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="2c501-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-171">20013</span><span class="sxs-lookup"><span data-stu-id="2c501-171">20013</span></span></p></td>
<td><p><span data-ttu-id="2c501-172">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-172">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-173">IM MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="2c501-174">IM MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="2c501-175">查看 IM MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="2c501-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-176">20014</span><span class="sxs-lookup"><span data-stu-id="2c501-176">20014</span></span></p></td>
<td><p><span data-ttu-id="2c501-177">之</span><span class="sxs-lookup"><span data-stu-id="2c501-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="2c501-178">从无法连接到 IM MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="2c501-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="2c501-179">不适用</span><span class="sxs-lookup"><span data-stu-id="2c501-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-180">20015</span><span class="sxs-lookup"><span data-stu-id="2c501-180">20015</span></span></p></td>
<td><p><span data-ttu-id="2c501-181">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-181">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-182">AV MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="2c501-183">AV MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="2c501-184">查看 AV MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="2c501-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-185">20016</span><span class="sxs-lookup"><span data-stu-id="2c501-185">20016</span></span></p></td>
<td><p><span data-ttu-id="2c501-186">之</span><span class="sxs-lookup"><span data-stu-id="2c501-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="2c501-187">从无法连接到 AV MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="2c501-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="2c501-188">不适用</span><span class="sxs-lookup"><span data-stu-id="2c501-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-189">20017</span><span class="sxs-lookup"><span data-stu-id="2c501-189">20017</span></span></p></td>
<td><p><span data-ttu-id="2c501-190">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-190">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-191">AS MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="2c501-192">AS MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="2c501-193">查看 AS MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="2c501-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-194">20018</span><span class="sxs-lookup"><span data-stu-id="2c501-194">20018</span></span></p></td>
<td><p><span data-ttu-id="2c501-195">之</span><span class="sxs-lookup"><span data-stu-id="2c501-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="2c501-196">从无法连接到 MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="2c501-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="2c501-197">不适用</span><span class="sxs-lookup"><span data-stu-id="2c501-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-198">20019</span><span class="sxs-lookup"><span data-stu-id="2c501-198">20019</span></span></p></td>
<td><p><span data-ttu-id="2c501-199">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-199">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-200">数据 MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="2c501-201">数据 MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="2c501-202">查看数据 MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="2c501-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-203">20020</span><span class="sxs-lookup"><span data-stu-id="2c501-203">20020</span></span></p></td>
<td><p><span data-ttu-id="2c501-204">之</span><span class="sxs-lookup"><span data-stu-id="2c501-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="2c501-205">从无法连接到数据 MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="2c501-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="2c501-206">不适用</span><span class="sxs-lookup"><span data-stu-id="2c501-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-207">20021</span><span class="sxs-lookup"><span data-stu-id="2c501-207">20021</span></span></p></td>
<td><p><span data-ttu-id="2c501-208">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-208">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-209">无法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="2c501-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="2c501-210">无法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="2c501-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="2c501-211">查看 IM MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="2c501-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-212">20022</span><span class="sxs-lookup"><span data-stu-id="2c501-212">20022</span></span></p></td>
<td><p><span data-ttu-id="2c501-213">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-213">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-214">无法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="2c501-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="2c501-215">无法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="2c501-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="2c501-216">查看 AV MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="2c501-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-217">20023</span><span class="sxs-lookup"><span data-stu-id="2c501-217">20023</span></span></p></td>
<td><p><span data-ttu-id="2c501-218">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-218">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-219">无法作为 MCU 加入</span><span class="sxs-lookup"><span data-stu-id="2c501-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="2c501-220">无法作为 MCU 加入</span><span class="sxs-lookup"><span data-stu-id="2c501-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="2c501-221">查看 AS MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="2c501-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-222">20024</span><span class="sxs-lookup"><span data-stu-id="2c501-222">20024</span></span></p></td>
<td><p><span data-ttu-id="2c501-223">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-223">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-224">无法加入数据 MCU</span><span class="sxs-lookup"><span data-stu-id="2c501-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="2c501-225">无法加入数据 MCU</span><span class="sxs-lookup"><span data-stu-id="2c501-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="2c501-226">查看数据 MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="2c501-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-227">20025</span><span class="sxs-lookup"><span data-stu-id="2c501-227">20025</span></span></p></td>
<td><p><span data-ttu-id="2c501-228">错误</span><span class="sxs-lookup"><span data-stu-id="2c501-228">Error</span></span></p></td>
<td><p><span data-ttu-id="2c501-229">无法访问 active directory 中的照片</span><span class="sxs-lookup"><span data-stu-id="2c501-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="2c501-230">Active directory 的连接不可用</span><span class="sxs-lookup"><span data-stu-id="2c501-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="2c501-231">请确保与 active directory 的连接可用</span><span class="sxs-lookup"><span data-stu-id="2c501-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c501-232">20026</span><span class="sxs-lookup"><span data-stu-id="2c501-232">20026</span></span></p></td>
<td><p><span data-ttu-id="2c501-233">之</span><span class="sxs-lookup"><span data-stu-id="2c501-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="2c501-234">从无法访问 active directory for photo 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="2c501-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="2c501-235">不适用</span><span class="sxs-lookup"><span data-stu-id="2c501-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c501-236">20027</span><span class="sxs-lookup"><span data-stu-id="2c501-236">20027</span></span></p></td>
<td><p><span data-ttu-id="2c501-237">警告</span><span class="sxs-lookup"><span data-stu-id="2c501-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="2c501-238">无法反序列化</span><span class="sxs-lookup"><span data-stu-id="2c501-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="2c501-239">无法反序列化</span><span class="sxs-lookup"><span data-stu-id="2c501-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="2c501-240">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="2c501-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

