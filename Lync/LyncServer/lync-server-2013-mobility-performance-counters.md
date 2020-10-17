---
title: Lync Server 2013：移动性能计数器
description: Lync Server 2013：移动性能计数器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550528"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="e9ff2-103">Lync Server 2013 中的移动性能计数器</span><span class="sxs-lookup"><span data-stu-id="e9ff2-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9ff2-104">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e9ff2-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e9ff2-105">下表列出了可用于监视运行统一通信 Web API (UCWA) 和 Lync Server 2013 Mcx 移动服务的服务器的性能计数器的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e9ff2-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="e9ff2-106">UCWA 表中的计数器的类别名称为 **LS： WEB – UCWA**。</span><span class="sxs-lookup"><span data-stu-id="e9ff2-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="e9ff2-107">Mcx 移动服务表中的计数器的类别名称为 **LS： WEB-移动通信服务**。</span><span class="sxs-lookup"><span data-stu-id="e9ff2-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="e9ff2-108">UCWA 的性能计数器</span><span class="sxs-lookup"><span data-stu-id="e9ff2-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9ff2-109">计数器</span><span class="sxs-lookup"><span data-stu-id="e9ff2-109">Counter</span></span></th>
<th><span data-ttu-id="e9ff2-110">描述</span><span class="sxs-lookup"><span data-stu-id="e9ff2-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-111">活动应用程序计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-112">当前的应用程序数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-113">活动应用程序共享模态计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-114">当前的应用程序共享模态数量</span><span class="sxs-lookup"><span data-stu-id="e9ff2-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-115">主动音频模态计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-116">音频模态的当前数量</span><span class="sxs-lookup"><span data-stu-id="e9ff2-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-117">主动数据协作的模态计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-118">当前的数据协作模态数量</span><span class="sxs-lookup"><span data-stu-id="e9ff2-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-119">Active Directory 照片获取延迟 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="e9ff2-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-120">此计数器显示从 active directory 检索照片的平均时间（以毫秒为单位） () </span><span class="sxs-lookup"><span data-stu-id="e9ff2-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-121">活动邮件模态计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-122">当前邮件模态的数量</span><span class="sxs-lookup"><span data-stu-id="e9ff2-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-123">活动全景视频模态计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-124">当前的全景视频模态数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-125">活动挂起获取计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-126">当前处于活动状态的挂起获取的数目;与服务器的长时间保持连接</span><span class="sxs-lookup"><span data-stu-id="e9ff2-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-127">活动会话计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-128">每个应用程序的 UCWA 中注册的当前终结点数和总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-129">活动用户实例计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-130">当前用户实例数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-131">没有应用程序的活动用户实例</span><span class="sxs-lookup"><span data-stu-id="e9ff2-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-132">当前不包含应用程序的用户实例数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-133">活动视频模态计数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-134">视频模态的当前数量</span><span class="sxs-lookup"><span data-stu-id="e9ff2-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-135">收到的应用程序创建请求数/秒</span><span class="sxs-lookup"><span data-stu-id="e9ff2-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-136">每秒收到应用程序创建请求的速率</span><span class="sxs-lookup"><span data-stu-id="e9ff2-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-137">作为 MCU 联接失败</span><span class="sxs-lookup"><span data-stu-id="e9ff2-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-138">作为 MCU 联接失败的次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-139">AV MCU 联接失败</span><span class="sxs-lookup"><span data-stu-id="e9ff2-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-140">AV MCU 联接失败的次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-141"> (毫秒的平均应用程序启动时间) </span><span class="sxs-lookup"><span data-stu-id="e9ff2-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-142">应用程序的平均启动时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="e9ff2-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-143">会话 (ms 的平均生存期) </span><span class="sxs-lookup"><span data-stu-id="e9ff2-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-144">会话的平均生存时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="e9ff2-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-145">数据 MCU 联接失败</span><span class="sxs-lookup"><span data-stu-id="e9ff2-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-146">数据 MCU 联接失败次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-147">Exchange 联系人搜索延迟 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="e9ff2-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-148">此计数器显示在 Exchange 中搜索联系人的平均时间 (（以毫秒为单位）) </span><span class="sxs-lookup"><span data-stu-id="e9ff2-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-149">Exchange HD 照片获取延迟 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="e9ff2-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-150">此计数器显示从 Exchange 检索照片的平均时间（以毫秒为单位） () </span><span class="sxs-lookup"><span data-stu-id="e9ff2-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-151">HTTP 4xx 响应数/秒</span><span class="sxs-lookup"><span data-stu-id="e9ff2-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-152">HTTP 4xx 代码的每秒响应速率</span><span class="sxs-lookup"><span data-stu-id="e9ff2-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-153">HTTP 5xx 响应数/秒</span><span class="sxs-lookup"><span data-stu-id="e9ff2-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-154">HTTP 5xx 代码的每秒响应速率</span><span class="sxs-lookup"><span data-stu-id="e9ff2-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-155">IM MCU 联接失败</span><span class="sxs-lookup"><span data-stu-id="e9ff2-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-156">IM MCU 联接失败的次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-157">Active Directory 照片获取失败的次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-158">从 Active Directory 检索照片的失败总次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-159">联系人搜索失败的次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-160">在 Exchange 中搜索联系人的失败总次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-161">反序列化失败次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-162">反序列化失败总次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-163">HD 照片获取失败的次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-164">从 Exchange 检索 HD 照片的失败总次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-165">在每个应用程序的最大订阅数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-166">每个应用程序允许的最大订阅请求数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-167">在每批的最大订阅数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-168">每个批处理允许的最大订阅请求数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-169">状态订阅失败</span><span class="sxs-lookup"><span data-stu-id="e9ff2-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-170">订阅状态失败的次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-171">注册终结点故障</span><span class="sxs-lookup"><span data-stu-id="e9ff2-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-172">注册终结点的失败次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-173">Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-174">每秒收到的请求数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-175">Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-176">每秒成功请求 (HTTP 2xx/3xx 响应代码的速率) </span><span class="sxs-lookup"><span data-stu-id="e9ff2-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-177">已成功创建应用程序请求/秒</span><span class="sxs-lookup"><span data-stu-id="e9ff2-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-178">每秒成功的应用程序创建请求的速率</span><span class="sxs-lookup"><span data-stu-id="e9ff2-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-179">挂起 Get Count 超时</span><span class="sxs-lookup"><span data-stu-id="e9ff2-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-180">超时的挂起获取数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-181">收到的应用程序创建请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-182">自启动服务以来收到的应用程序创建请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-183">HTTP 4xx 响应总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-184">HTTP 4xx 响应总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-185">HTTP 5xx 响应总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-186">HTTP 5xx 响应总次数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-187">在命令通道上收到的请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-188">命令通道上收到的请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-189">Total Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="e9ff2-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-190">成功的请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-191">启动的会话总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-192">启动服务后启动的会话总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-193">由于空闲超时而终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-194">因用户空闲超时终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-195">限制的应用程序总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-196">限制的应用程序数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="e9ff2-197">Mcx 移动服务的性能计数器</span><span class="sxs-lookup"><span data-stu-id="e9ff2-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9ff2-198">计数器</span><span class="sxs-lookup"><span data-stu-id="e9ff2-198">Counter</span></span></th>
<th><span data-ttu-id="e9ff2-199">描述</span><span class="sxs-lookup"><span data-stu-id="e9ff2-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-200">Average Lifetime for a Session in Milliseconds</span><span class="sxs-lookup"><span data-stu-id="e9ff2-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-201">会话的平均生存时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="e9ff2-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-202">Current Push Notification Subscriptions</span><span class="sxs-lookup"><span data-stu-id="e9ff2-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-203">当前推送通知订阅数。</span><span class="sxs-lookup"><span data-stu-id="e9ff2-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="e9ff2-204">此数字与当前活动会话计数联合在一起表示为 Windows Mobile 或 iPhone 设备注册的当前活动会话的子集。</span><span class="sxs-lookup"><span data-stu-id="e9ff2-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-205">Currently Active Network Timeout Poll Count</span><span class="sxs-lookup"><span data-stu-id="e9ff2-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-206">超时的网络投票数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-207">Currently Active Poll Count</span><span class="sxs-lookup"><span data-stu-id="e9ff2-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-208">当前活动投票数（与服务器的长期连接）</span><span class="sxs-lookup"><span data-stu-id="e9ff2-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-209">Currently Active Session Count</span><span class="sxs-lookup"><span data-stu-id="e9ff2-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-210">当前注册到 Mobility Service 中的终结点的数目</span><span class="sxs-lookup"><span data-stu-id="e9ff2-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-211">Currently Active Session Count with Active Presence Subscriptions</span><span class="sxs-lookup"><span data-stu-id="e9ff2-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-212">包含活动状态订阅的当前活动会话的数目</span><span class="sxs-lookup"><span data-stu-id="e9ff2-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-213">Push Notification Requests Failed/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-214">每秒失败的推送通知数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-215">Push Notification Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-216">每秒成功的推送通知数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-217">Push Notification Requests Throttled/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-218">每秒阻止的推送通知数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-219">Push Notification Requests/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-220">每秒发送的推送通知数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-221">Requests Failed/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-222">每秒失败的请求数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-223">Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-224">每秒收到的请求数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-225">Requests Rejected/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-226">每秒拒绝的请求数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-227">Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-228">每秒成功的请求数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-229">Succeeded Initiate Session Requests/Second</span><span class="sxs-lookup"><span data-stu-id="e9ff2-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-p102">每秒成功的 Get Location 请求数。启动会话的请求占用了服务器上大部分 CPU。支持的峰值负载为 12/秒。可持续性依赖于服务器上的其他负载。启动会话通常意味着用户登录已注销很长一段时间。</span><span class="sxs-lookup"><span data-stu-id="e9ff2-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-235">Total Declined Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="e9ff2-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-236">拒绝的入站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-237">Total Failed Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="e9ff2-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-238">失败的入站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-239">Total Failed Outbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="e9ff2-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-240">失败的出站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-241">Total number of sessions terminated by user</span><span class="sxs-lookup"><span data-stu-id="e9ff2-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-242">用户终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-243">Total Push Notification Requests</span><span class="sxs-lookup"><span data-stu-id="e9ff2-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-244">推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-245">Total Push Notification Requests Failed</span><span class="sxs-lookup"><span data-stu-id="e9ff2-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-246">失败的推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-247">Total Push Notification Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="e9ff2-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-248">成功的推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-249">Total Push Notification Requests Throttled</span><span class="sxs-lookup"><span data-stu-id="e9ff2-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-250">阻止的推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-251">Total Requests Failed</span><span class="sxs-lookup"><span data-stu-id="e9ff2-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-252">失败的请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-253">Total Requests received on the Command Channel</span><span class="sxs-lookup"><span data-stu-id="e9ff2-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-254">命令通道上收到的请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-255">Total Requests Rejected</span><span class="sxs-lookup"><span data-stu-id="e9ff2-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-256">拒绝的请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-257">Total Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="e9ff2-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-258">成功发送给 Mobility Service 的请求总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-259">Total Session Initiated Count</span><span class="sxs-lookup"><span data-stu-id="e9ff2-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-260">自启动 Mobility Service 后启动的会话总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-261">Total Sessions Terminated Because of User Idle Timeout</span><span class="sxs-lookup"><span data-stu-id="e9ff2-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-262">因用户空闲超时终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9ff2-263">Total Successful Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="e9ff2-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-264">成功的入站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9ff2-265">Total Successful Outbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="e9ff2-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e9ff2-266">成功的出站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="e9ff2-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

