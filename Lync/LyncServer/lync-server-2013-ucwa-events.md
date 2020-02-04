---
title: Lync Server 2013： UCWA 事件
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
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="4290b-102">Lync Server 2013 中的 UCWA 事件</span><span class="sxs-lookup"><span data-stu-id="4290b-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4290b-103">_**主题上次修改时间：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="4290b-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="4290b-104">Lync Server 2013 使用统一通信 Web API （UCWA）来实现许多用途，从访问 Microsoft Exchange 到联系人搜索以更新移动客户端的状态。</span><span class="sxs-lookup"><span data-stu-id="4290b-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="4290b-p101">UCWA 将运行行为的记录编写成“信息”、“警告”和“错误”事件类型。下表介绍了可由 UCWA 组件编写的事件。</span><span class="sxs-lookup"><span data-stu-id="4290b-p101">UCWA will write records of operational behavior as event types Informational, Warning, and Error. The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4290b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4290b-107">Event ID</span></span></th>
<th><span data-ttu-id="4290b-108">事件类型</span><span class="sxs-lookup"><span data-stu-id="4290b-108">Event Type</span></span></th>
<th><span data-ttu-id="4290b-109">摘要</span><span class="sxs-lookup"><span data-stu-id="4290b-109">Summary</span></span></th>
<th><span data-ttu-id="4290b-110">原因和解决方法</span><span class="sxs-lookup"><span data-stu-id="4290b-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4290b-111">20001</span><span class="sxs-lookup"><span data-stu-id="4290b-111">20001</span></span></p></td>
<td><p><span data-ttu-id="4290b-112">信息</span><span class="sxs-lookup"><span data-stu-id="4290b-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="4290b-113">UCWA 已初始化</span><span class="sxs-lookup"><span data-stu-id="4290b-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="4290b-114">不适用</span><span class="sxs-lookup"><span data-stu-id="4290b-114">N/A</span></span></p>
<p><span data-ttu-id="4290b-115">不适用</span><span class="sxs-lookup"><span data-stu-id="4290b-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-116">20002</span><span class="sxs-lookup"><span data-stu-id="4290b-116">20002</span></span></p></td>
<td><p><span data-ttu-id="4290b-117">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-117">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-118">UCWA 在初始化期间遇到意外异常</span><span class="sxs-lookup"><span data-stu-id="4290b-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="4290b-119">初始化期间出现意外错误</span><span class="sxs-lookup"><span data-stu-id="4290b-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="4290b-120">检查相关事件日志条目中的异常详细信息以确定可能的原因</span><span class="sxs-lookup"><span data-stu-id="4290b-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-121">20003</span><span class="sxs-lookup"><span data-stu-id="4290b-121">20003</span></span></p></td>
<td><p><span data-ttu-id="4290b-122">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-122">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-123">UCWA 遇到未经处理的异常</span><span class="sxs-lookup"><span data-stu-id="4290b-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="4290b-124">出现未经处理的异常</span><span class="sxs-lookup"><span data-stu-id="4290b-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="4290b-p102">重新启动服务器。如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="4290b-p102">Restart the server. If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-127">20004</span><span class="sxs-lookup"><span data-stu-id="4290b-127">20004</span></span></p></td>
<td><p><span data-ttu-id="4290b-128">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-128">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-129">无法访问 Exchange 获取高清照片</span><span class="sxs-lookup"><span data-stu-id="4290b-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="4290b-130">与 Exchange 的连接不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="4290b-131">确保与 Exchange 的连接可用</span><span class="sxs-lookup"><span data-stu-id="4290b-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-132">20005</span><span class="sxs-lookup"><span data-stu-id="4290b-132">20005</span></span></p></td>
<td><p><span data-ttu-id="4290b-133">信息</span><span class="sxs-lookup"><span data-stu-id="4290b-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="4290b-134">从无法访问 Exchange 获取高清照片的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="4290b-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="4290b-135">不适用</span><span class="sxs-lookup"><span data-stu-id="4290b-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-136">20006</span><span class="sxs-lookup"><span data-stu-id="4290b-136">20006</span></span></p></td>
<td><p><span data-ttu-id="4290b-137">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-137">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-138">无法访问 Exchange 进行联系人搜索</span><span class="sxs-lookup"><span data-stu-id="4290b-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="4290b-139">与 Exchange 的连接不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="4290b-140">确保与 Exchange 的连接可用</span><span class="sxs-lookup"><span data-stu-id="4290b-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-141">20007</span><span class="sxs-lookup"><span data-stu-id="4290b-141">20007</span></span></p></td>
<td><p><span data-ttu-id="4290b-142">信息</span><span class="sxs-lookup"><span data-stu-id="4290b-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="4290b-143">从无法在 Exchange 中搜索联系人的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="4290b-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="4290b-144">不适用</span><span class="sxs-lookup"><span data-stu-id="4290b-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-145">20008</span><span class="sxs-lookup"><span data-stu-id="4290b-145">20008</span></span></p></td>
<td><p><span data-ttu-id="4290b-146">警告</span><span class="sxs-lookup"><span data-stu-id="4290b-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="4290b-147">尝试订阅超过每应用程序允许的状态订阅数量</span><span class="sxs-lookup"><span data-stu-id="4290b-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="4290b-148">尝试订阅超过每应用程序允许的状态订阅数量</span><span class="sxs-lookup"><span data-stu-id="4290b-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="4290b-149">检查客户端中不必要的订阅</span><span class="sxs-lookup"><span data-stu-id="4290b-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-150">20009</span><span class="sxs-lookup"><span data-stu-id="4290b-150">20009</span></span></p></td>
<td><p><span data-ttu-id="4290b-151">警告</span><span class="sxs-lookup"><span data-stu-id="4290b-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="4290b-152">尝试订阅超过每批允许的状态订阅数量</span><span class="sxs-lookup"><span data-stu-id="4290b-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="4290b-153">尝试订阅超过每批允许的状态订阅数量</span><span class="sxs-lookup"><span data-stu-id="4290b-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="4290b-154">检查客户端中不必要的订阅</span><span class="sxs-lookup"><span data-stu-id="4290b-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-155">20010</span><span class="sxs-lookup"><span data-stu-id="4290b-155">20010</span></span></p></td>
<td><p><span data-ttu-id="4290b-156">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-156">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-157">无法检索带内数据</span><span class="sxs-lookup"><span data-stu-id="4290b-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="4290b-158">无法检索带内数据</span><span class="sxs-lookup"><span data-stu-id="4290b-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="4290b-159">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="4290b-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-160">20011</span><span class="sxs-lookup"><span data-stu-id="4290b-160">20011</span></span></p></td>
<td><p><span data-ttu-id="4290b-161">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-161">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-162">无法订阅状态</span><span class="sxs-lookup"><span data-stu-id="4290b-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="4290b-163">无法订阅状态</span><span class="sxs-lookup"><span data-stu-id="4290b-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="4290b-164">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="4290b-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-165">20012</span><span class="sxs-lookup"><span data-stu-id="4290b-165">20012</span></span></p></td>
<td><p><span data-ttu-id="4290b-166">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-166">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-167">未能注册终结点</span><span class="sxs-lookup"><span data-stu-id="4290b-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="4290b-168">未能注册终结点</span><span class="sxs-lookup"><span data-stu-id="4290b-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="4290b-169">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="4290b-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-170">20013</span><span class="sxs-lookup"><span data-stu-id="4290b-170">20013</span></span></p></td>
<td><p><span data-ttu-id="4290b-171">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-171">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-172">IM MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4290b-173">IM MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="4290b-174">查看 IM MCU 是否在运行</span><span class="sxs-lookup"><span data-stu-id="4290b-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-175">20014</span><span class="sxs-lookup"><span data-stu-id="4290b-175">20014</span></span></p></td>
<td><p><span data-ttu-id="4290b-176">信息</span><span class="sxs-lookup"><span data-stu-id="4290b-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="4290b-177">从无法连接 IM MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="4290b-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="4290b-178">不适用</span><span class="sxs-lookup"><span data-stu-id="4290b-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-179">20015</span><span class="sxs-lookup"><span data-stu-id="4290b-179">20015</span></span></p></td>
<td><p><span data-ttu-id="4290b-180">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-180">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-181">AV MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4290b-182">AV MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="4290b-183">查看 AV MCU 是否在运行</span><span class="sxs-lookup"><span data-stu-id="4290b-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-184">20016</span><span class="sxs-lookup"><span data-stu-id="4290b-184">20016</span></span></p></td>
<td><p><span data-ttu-id="4290b-185">信息</span><span class="sxs-lookup"><span data-stu-id="4290b-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="4290b-186">从无法连接 AV MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="4290b-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="4290b-187">不适用</span><span class="sxs-lookup"><span data-stu-id="4290b-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-188">20017</span><span class="sxs-lookup"><span data-stu-id="4290b-188">20017</span></span></p></td>
<td><p><span data-ttu-id="4290b-189">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-189">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-190">AS MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4290b-191">AS MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="4290b-192">查看 AS MCU 是否在运行</span><span class="sxs-lookup"><span data-stu-id="4290b-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-193">20018</span><span class="sxs-lookup"><span data-stu-id="4290b-193">20018</span></span></p></td>
<td><p><span data-ttu-id="4290b-194">信息</span><span class="sxs-lookup"><span data-stu-id="4290b-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="4290b-195">从无法连接 AS MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="4290b-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="4290b-196">不适用</span><span class="sxs-lookup"><span data-stu-id="4290b-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-197">20019</span><span class="sxs-lookup"><span data-stu-id="4290b-197">20019</span></span></p></td>
<td><p><span data-ttu-id="4290b-198">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-198">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-199">Data MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4290b-200">Data MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="4290b-201">查看 Data MCU 是否在运行</span><span class="sxs-lookup"><span data-stu-id="4290b-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-202">20020</span><span class="sxs-lookup"><span data-stu-id="4290b-202">20020</span></span></p></td>
<td><p><span data-ttu-id="4290b-203">信息</span><span class="sxs-lookup"><span data-stu-id="4290b-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="4290b-204">从无法连接 Data MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="4290b-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="4290b-205">不适用</span><span class="sxs-lookup"><span data-stu-id="4290b-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-206">20021</span><span class="sxs-lookup"><span data-stu-id="4290b-206">20021</span></span></p></td>
<td><p><span data-ttu-id="4290b-207">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-207">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-208">无法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="4290b-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="4290b-209">无法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="4290b-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="4290b-210">查看 IM MCU 是否在运行</span><span class="sxs-lookup"><span data-stu-id="4290b-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-211">20022</span><span class="sxs-lookup"><span data-stu-id="4290b-211">20022</span></span></p></td>
<td><p><span data-ttu-id="4290b-212">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-212">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-213">无法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="4290b-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="4290b-214">无法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="4290b-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="4290b-215">查看 AV MCU 是否在运行</span><span class="sxs-lookup"><span data-stu-id="4290b-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-216">20023</span><span class="sxs-lookup"><span data-stu-id="4290b-216">20023</span></span></p></td>
<td><p><span data-ttu-id="4290b-217">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-217">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-218">无法加入 AS MCU</span><span class="sxs-lookup"><span data-stu-id="4290b-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="4290b-219">无法加入 AS MCU</span><span class="sxs-lookup"><span data-stu-id="4290b-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="4290b-220">查看 AS MCU 是否在运行</span><span class="sxs-lookup"><span data-stu-id="4290b-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-221">20024</span><span class="sxs-lookup"><span data-stu-id="4290b-221">20024</span></span></p></td>
<td><p><span data-ttu-id="4290b-222">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-222">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-223">无法加入 Data MCU</span><span class="sxs-lookup"><span data-stu-id="4290b-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="4290b-224">无法加入 Data MCU</span><span class="sxs-lookup"><span data-stu-id="4290b-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="4290b-225">查看 Data MCU 是否在运行</span><span class="sxs-lookup"><span data-stu-id="4290b-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-226">20025</span><span class="sxs-lookup"><span data-stu-id="4290b-226">20025</span></span></p></td>
<td><p><span data-ttu-id="4290b-227">错误</span><span class="sxs-lookup"><span data-stu-id="4290b-227">Error</span></span></p></td>
<td><p><span data-ttu-id="4290b-228">无法访问 Active Directory 获取照片</span><span class="sxs-lookup"><span data-stu-id="4290b-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="4290b-229">与 Active Directory 的连接不可用</span><span class="sxs-lookup"><span data-stu-id="4290b-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="4290b-230">确保与 Active Directory 的连接可用</span><span class="sxs-lookup"><span data-stu-id="4290b-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4290b-231">20026</span><span class="sxs-lookup"><span data-stu-id="4290b-231">20026</span></span></p></td>
<td><p><span data-ttu-id="4290b-232">信息</span><span class="sxs-lookup"><span data-stu-id="4290b-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="4290b-233">从无法访问 Active Directory 获取照片的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="4290b-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="4290b-234">不适用</span><span class="sxs-lookup"><span data-stu-id="4290b-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4290b-235">20027</span><span class="sxs-lookup"><span data-stu-id="4290b-235">20027</span></span></p></td>
<td><p><span data-ttu-id="4290b-236">警告</span><span class="sxs-lookup"><span data-stu-id="4290b-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="4290b-237">无法反序列化</span><span class="sxs-lookup"><span data-stu-id="4290b-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="4290b-238">无法反序列化</span><span class="sxs-lookup"><span data-stu-id="4290b-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="4290b-239">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="4290b-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

