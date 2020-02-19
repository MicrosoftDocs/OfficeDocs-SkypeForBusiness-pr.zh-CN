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
ms.openlocfilehash: 717f4e9686574a04434889f2c44a029a02e75768
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="44684-102">Lync Server 2013 中的 UCWA 事件</span><span class="sxs-lookup"><span data-stu-id="44684-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44684-103">_**上次修改的主题：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="44684-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="44684-104">Lync Server 2013 使用统一通信 Web API （UCWA）来实现多种用途，从访问 Microsoft Exchange 以进行联系人搜索，以更新移动客户端的状态。</span><span class="sxs-lookup"><span data-stu-id="44684-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="44684-105">UCWA 会将操作行为的记录编写为事件类型信息、警告和错误。</span><span class="sxs-lookup"><span data-stu-id="44684-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="44684-106">下表介绍了 UCWA 组件可以编写的事件。</span><span class="sxs-lookup"><span data-stu-id="44684-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44684-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44684-107">Event ID</span></span></th>
<th><span data-ttu-id="44684-108">事件类型</span><span class="sxs-lookup"><span data-stu-id="44684-108">Event Type</span></span></th>
<th><span data-ttu-id="44684-109">总结</span><span class="sxs-lookup"><span data-stu-id="44684-109">Summary</span></span></th>
<th><span data-ttu-id="44684-110">原因和解决方法</span><span class="sxs-lookup"><span data-stu-id="44684-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44684-111">20001</span><span class="sxs-lookup"><span data-stu-id="44684-111">20001</span></span></p></td>
<td><p><span data-ttu-id="44684-112">之</span><span class="sxs-lookup"><span data-stu-id="44684-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="44684-113">UCWA 已初始化</span><span class="sxs-lookup"><span data-stu-id="44684-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="44684-114">不适用</span><span class="sxs-lookup"><span data-stu-id="44684-114">N/A</span></span></p>
<p><span data-ttu-id="44684-115">不适用</span><span class="sxs-lookup"><span data-stu-id="44684-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-116">20002</span><span class="sxs-lookup"><span data-stu-id="44684-116">20002</span></span></p></td>
<td><p><span data-ttu-id="44684-117">Error</span><span class="sxs-lookup"><span data-stu-id="44684-117">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-118">UCWA 在初始化期间遇到意外异常</span><span class="sxs-lookup"><span data-stu-id="44684-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="44684-119">初始化过程中出现意外错误</span><span class="sxs-lookup"><span data-stu-id="44684-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="44684-120">在关联的事件日志条目中检查异常详细信息，以确定可能的原因</span><span class="sxs-lookup"><span data-stu-id="44684-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-121">20003</span><span class="sxs-lookup"><span data-stu-id="44684-121">20003</span></span></p></td>
<td><p><span data-ttu-id="44684-122">Error</span><span class="sxs-lookup"><span data-stu-id="44684-122">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-123">UCWA 遇到未经处理的异常</span><span class="sxs-lookup"><span data-stu-id="44684-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="44684-124">发生未处理的异常</span><span class="sxs-lookup"><span data-stu-id="44684-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="44684-125">重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="44684-125">Restart the server.</span></span> <span data-ttu-id="44684-126">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="44684-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-127">20004</span><span class="sxs-lookup"><span data-stu-id="44684-127">20004</span></span></p></td>
<td><p><span data-ttu-id="44684-128">Error</span><span class="sxs-lookup"><span data-stu-id="44684-128">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-129">无法访问 HD 照片的 Exchange</span><span class="sxs-lookup"><span data-stu-id="44684-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="44684-130">与 Exchange 的连接不可用</span><span class="sxs-lookup"><span data-stu-id="44684-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="44684-131">请确保与 Exchange 的连接可用</span><span class="sxs-lookup"><span data-stu-id="44684-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-132">20005</span><span class="sxs-lookup"><span data-stu-id="44684-132">20005</span></span></p></td>
<td><p><span data-ttu-id="44684-133">之</span><span class="sxs-lookup"><span data-stu-id="44684-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="44684-134">从无法访问 Exchange for HD 照片的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="44684-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="44684-135">不适用</span><span class="sxs-lookup"><span data-stu-id="44684-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-136">20006</span><span class="sxs-lookup"><span data-stu-id="44684-136">20006</span></span></p></td>
<td><p><span data-ttu-id="44684-137">Error</span><span class="sxs-lookup"><span data-stu-id="44684-137">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-138">无法访问联系人搜索的 Exchange</span><span class="sxs-lookup"><span data-stu-id="44684-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="44684-139">与 Exchange 的连接不可用</span><span class="sxs-lookup"><span data-stu-id="44684-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="44684-140">请确保与 Exchange 的连接可用</span><span class="sxs-lookup"><span data-stu-id="44684-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-141">20007</span><span class="sxs-lookup"><span data-stu-id="44684-141">20007</span></span></p></td>
<td><p><span data-ttu-id="44684-142">之</span><span class="sxs-lookup"><span data-stu-id="44684-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="44684-143">从 Exchange 中的搜索联系人故障中恢复</span><span class="sxs-lookup"><span data-stu-id="44684-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="44684-144">不适用</span><span class="sxs-lookup"><span data-stu-id="44684-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-145">20008</span><span class="sxs-lookup"><span data-stu-id="44684-145">20008</span></span></p></td>
<td><p><span data-ttu-id="44684-146">警告</span><span class="sxs-lookup"><span data-stu-id="44684-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="44684-147">尝试为每个应用程序订阅多于允许的状态订阅</span><span class="sxs-lookup"><span data-stu-id="44684-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="44684-148">尝试为每个应用程序订阅多于允许的状态订阅</span><span class="sxs-lookup"><span data-stu-id="44684-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="44684-149">检查客户端是否有不必要的订阅</span><span class="sxs-lookup"><span data-stu-id="44684-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-150">20009</span><span class="sxs-lookup"><span data-stu-id="44684-150">20009</span></span></p></td>
<td><p><span data-ttu-id="44684-151">警告</span><span class="sxs-lookup"><span data-stu-id="44684-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="44684-152">每批次尝试订阅的订阅数超过允许的状态订阅数</span><span class="sxs-lookup"><span data-stu-id="44684-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="44684-153">每批次尝试订阅的订阅数超过允许的状态订阅数</span><span class="sxs-lookup"><span data-stu-id="44684-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="44684-154">检查客户端是否有不必要的订阅</span><span class="sxs-lookup"><span data-stu-id="44684-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-155">20010</span><span class="sxs-lookup"><span data-stu-id="44684-155">20010</span></span></p></td>
<td><p><span data-ttu-id="44684-156">Error</span><span class="sxs-lookup"><span data-stu-id="44684-156">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-157">无法检索带内数据</span><span class="sxs-lookup"><span data-stu-id="44684-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="44684-158">无法检索带内数据</span><span class="sxs-lookup"><span data-stu-id="44684-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="44684-159">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="44684-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-160">20011</span><span class="sxs-lookup"><span data-stu-id="44684-160">20011</span></span></p></td>
<td><p><span data-ttu-id="44684-161">Error</span><span class="sxs-lookup"><span data-stu-id="44684-161">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-162">无法订阅状态</span><span class="sxs-lookup"><span data-stu-id="44684-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="44684-163">无法订阅状态</span><span class="sxs-lookup"><span data-stu-id="44684-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="44684-164">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="44684-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-165">20012</span><span class="sxs-lookup"><span data-stu-id="44684-165">20012</span></span></p></td>
<td><p><span data-ttu-id="44684-166">Error</span><span class="sxs-lookup"><span data-stu-id="44684-166">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-167">无法注册终结点</span><span class="sxs-lookup"><span data-stu-id="44684-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="44684-168">无法注册终结点</span><span class="sxs-lookup"><span data-stu-id="44684-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="44684-169">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="44684-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-170">20013</span><span class="sxs-lookup"><span data-stu-id="44684-170">20013</span></span></p></td>
<td><p><span data-ttu-id="44684-171">Error</span><span class="sxs-lookup"><span data-stu-id="44684-171">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-172">IM MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="44684-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="44684-173">IM MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="44684-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="44684-174">查看 IM MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="44684-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-175">20014</span><span class="sxs-lookup"><span data-stu-id="44684-175">20014</span></span></p></td>
<td><p><span data-ttu-id="44684-176">之</span><span class="sxs-lookup"><span data-stu-id="44684-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="44684-177">从无法连接到 IM MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="44684-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="44684-178">不适用</span><span class="sxs-lookup"><span data-stu-id="44684-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-179">20015</span><span class="sxs-lookup"><span data-stu-id="44684-179">20015</span></span></p></td>
<td><p><span data-ttu-id="44684-180">Error</span><span class="sxs-lookup"><span data-stu-id="44684-180">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-181">AV MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="44684-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="44684-182">AV MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="44684-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="44684-183">查看 AV MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="44684-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-184">20016</span><span class="sxs-lookup"><span data-stu-id="44684-184">20016</span></span></p></td>
<td><p><span data-ttu-id="44684-185">之</span><span class="sxs-lookup"><span data-stu-id="44684-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="44684-186">从无法连接到 AV MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="44684-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="44684-187">不适用</span><span class="sxs-lookup"><span data-stu-id="44684-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-188">20017</span><span class="sxs-lookup"><span data-stu-id="44684-188">20017</span></span></p></td>
<td><p><span data-ttu-id="44684-189">Error</span><span class="sxs-lookup"><span data-stu-id="44684-189">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-190">AS MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="44684-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="44684-191">AS MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="44684-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="44684-192">查看 AS MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="44684-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-193">20018</span><span class="sxs-lookup"><span data-stu-id="44684-193">20018</span></span></p></td>
<td><p><span data-ttu-id="44684-194">之</span><span class="sxs-lookup"><span data-stu-id="44684-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="44684-195">从无法连接到 MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="44684-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="44684-196">不适用</span><span class="sxs-lookup"><span data-stu-id="44684-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-197">20019</span><span class="sxs-lookup"><span data-stu-id="44684-197">20019</span></span></p></td>
<td><p><span data-ttu-id="44684-198">Error</span><span class="sxs-lookup"><span data-stu-id="44684-198">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-199">数据 MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="44684-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="44684-200">数据 MCU 不可用</span><span class="sxs-lookup"><span data-stu-id="44684-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="44684-201">查看数据 MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="44684-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-202">20020</span><span class="sxs-lookup"><span data-stu-id="44684-202">20020</span></span></p></td>
<td><p><span data-ttu-id="44684-203">之</span><span class="sxs-lookup"><span data-stu-id="44684-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="44684-204">从无法连接到数据 MCU 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="44684-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="44684-205">不适用</span><span class="sxs-lookup"><span data-stu-id="44684-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-206">20021</span><span class="sxs-lookup"><span data-stu-id="44684-206">20021</span></span></p></td>
<td><p><span data-ttu-id="44684-207">Error</span><span class="sxs-lookup"><span data-stu-id="44684-207">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-208">无法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="44684-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="44684-209">无法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="44684-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="44684-210">查看 IM MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="44684-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-211">20022</span><span class="sxs-lookup"><span data-stu-id="44684-211">20022</span></span></p></td>
<td><p><span data-ttu-id="44684-212">Error</span><span class="sxs-lookup"><span data-stu-id="44684-212">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-213">无法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="44684-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="44684-214">无法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="44684-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="44684-215">查看 AV MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="44684-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-216">20023</span><span class="sxs-lookup"><span data-stu-id="44684-216">20023</span></span></p></td>
<td><p><span data-ttu-id="44684-217">Error</span><span class="sxs-lookup"><span data-stu-id="44684-217">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-218">无法作为 MCU 加入</span><span class="sxs-lookup"><span data-stu-id="44684-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="44684-219">无法作为 MCU 加入</span><span class="sxs-lookup"><span data-stu-id="44684-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="44684-220">查看 AS MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="44684-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-221">20024</span><span class="sxs-lookup"><span data-stu-id="44684-221">20024</span></span></p></td>
<td><p><span data-ttu-id="44684-222">Error</span><span class="sxs-lookup"><span data-stu-id="44684-222">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-223">无法加入数据 MCU</span><span class="sxs-lookup"><span data-stu-id="44684-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="44684-224">无法加入数据 MCU</span><span class="sxs-lookup"><span data-stu-id="44684-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="44684-225">查看数据 MCU 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="44684-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-226">20025</span><span class="sxs-lookup"><span data-stu-id="44684-226">20025</span></span></p></td>
<td><p><span data-ttu-id="44684-227">Error</span><span class="sxs-lookup"><span data-stu-id="44684-227">Error</span></span></p></td>
<td><p><span data-ttu-id="44684-228">无法访问 active directory 中的照片</span><span class="sxs-lookup"><span data-stu-id="44684-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="44684-229">Active directory 的连接不可用</span><span class="sxs-lookup"><span data-stu-id="44684-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="44684-230">请确保与 active directory 的连接可用</span><span class="sxs-lookup"><span data-stu-id="44684-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44684-231">20026</span><span class="sxs-lookup"><span data-stu-id="44684-231">20026</span></span></p></td>
<td><p><span data-ttu-id="44684-232">之</span><span class="sxs-lookup"><span data-stu-id="44684-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="44684-233">从无法访问 active directory for photo 的故障中恢复</span><span class="sxs-lookup"><span data-stu-id="44684-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="44684-234">不适用</span><span class="sxs-lookup"><span data-stu-id="44684-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44684-235">20027</span><span class="sxs-lookup"><span data-stu-id="44684-235">20027</span></span></p></td>
<td><p><span data-ttu-id="44684-236">警告</span><span class="sxs-lookup"><span data-stu-id="44684-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="44684-237">无法反序列化</span><span class="sxs-lookup"><span data-stu-id="44684-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="44684-238">无法反序列化</span><span class="sxs-lookup"><span data-stu-id="44684-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="44684-239">如果问题仍然存在，请联系产品支持人员</span><span class="sxs-lookup"><span data-stu-id="44684-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

