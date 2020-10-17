---
title: Lync Server 2013：移动性能计数器
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
ms.openlocfilehash: 37e36b4492814043317fcafb2612a28c9f4d7b91
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513599"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="f09f4-102">Lync Server 2013 中的移动性能计数器</span><span class="sxs-lookup"><span data-stu-id="f09f4-102">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f09f4-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f09f4-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f09f4-104">下表列出了可用于监视运行统一通信 Web API (UCWA) 和 Lync Server 2013 Mcx 移动服务的服务器的性能计数器的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="f09f4-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="f09f4-105">UCWA 表中的计数器的类别名称为 **LS： WEB – UCWA**。</span><span class="sxs-lookup"><span data-stu-id="f09f4-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="f09f4-106">Mcx 移动服务表中的计数器的类别名称为 **LS： WEB-移动通信服务**。</span><span class="sxs-lookup"><span data-stu-id="f09f4-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="f09f4-107">UCWA 的性能计数器</span><span class="sxs-lookup"><span data-stu-id="f09f4-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f09f4-108">计数器</span><span class="sxs-lookup"><span data-stu-id="f09f4-108">Counter</span></span></th>
<th><span data-ttu-id="f09f4-109">描述</span><span class="sxs-lookup"><span data-stu-id="f09f4-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-110">活动应用程序计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-111">当前的应用程序数</span><span class="sxs-lookup"><span data-stu-id="f09f4-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-112">活动应用程序共享模态计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-113">当前的应用程序共享模态数量</span><span class="sxs-lookup"><span data-stu-id="f09f4-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-114">主动音频模态计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-115">音频模态的当前数量</span><span class="sxs-lookup"><span data-stu-id="f09f4-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-116">主动数据协作的模态计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-117">当前的数据协作模态数量</span><span class="sxs-lookup"><span data-stu-id="f09f4-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-118">Active Directory 照片获取延迟 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="f09f4-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="f09f4-119">此计数器显示从 active directory 检索照片的平均时间（以毫秒为单位） () </span><span class="sxs-lookup"><span data-stu-id="f09f4-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-120">活动邮件模态计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-121">当前邮件模态的数量</span><span class="sxs-lookup"><span data-stu-id="f09f4-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-122">活动全景视频模态计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-123">当前的全景视频模态数</span><span class="sxs-lookup"><span data-stu-id="f09f4-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-124">活动挂起获取计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-125">当前处于活动状态的挂起获取的数目;与服务器的长时间保持连接</span><span class="sxs-lookup"><span data-stu-id="f09f4-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-126">活动会话计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-127">每个应用程序的 UCWA 中注册的当前终结点数和总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-128">活动用户实例计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-129">当前用户实例数</span><span class="sxs-lookup"><span data-stu-id="f09f4-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-130">没有应用程序的活动用户实例</span><span class="sxs-lookup"><span data-stu-id="f09f4-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="f09f4-131">当前不包含应用程序的用户实例数</span><span class="sxs-lookup"><span data-stu-id="f09f4-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-132">活动视频模态计数</span><span class="sxs-lookup"><span data-stu-id="f09f4-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-133">视频模态的当前数量</span><span class="sxs-lookup"><span data-stu-id="f09f4-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-134">收到的应用程序创建请求数/秒</span><span class="sxs-lookup"><span data-stu-id="f09f4-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-135">每秒收到应用程序创建请求的速率</span><span class="sxs-lookup"><span data-stu-id="f09f4-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-136">作为 MCU 联接失败</span><span class="sxs-lookup"><span data-stu-id="f09f4-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-137">作为 MCU 联接失败的次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-138">AV MCU 联接失败</span><span class="sxs-lookup"><span data-stu-id="f09f4-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-139">AV MCU 联接失败的次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-140"> (毫秒的平均应用程序启动时间) </span><span class="sxs-lookup"><span data-stu-id="f09f4-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="f09f4-141">应用程序的平均启动时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="f09f4-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-142">会话 (ms 的平均生存期) </span><span class="sxs-lookup"><span data-stu-id="f09f4-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="f09f4-143">会话的平均生存时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="f09f4-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-144">数据 MCU 联接失败</span><span class="sxs-lookup"><span data-stu-id="f09f4-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-145">数据 MCU 联接失败次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-146">Exchange 联系人搜索延迟 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="f09f4-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="f09f4-147">此计数器显示在 Exchange 中搜索联系人的平均时间 (（以毫秒为单位）) </span><span class="sxs-lookup"><span data-stu-id="f09f4-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-148">Exchange HD 照片获取延迟 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="f09f4-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="f09f4-149">此计数器显示从 Exchange 检索照片的平均时间（以毫秒为单位） () </span><span class="sxs-lookup"><span data-stu-id="f09f4-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-150">HTTP 4xx 响应数/秒</span><span class="sxs-lookup"><span data-stu-id="f09f4-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-151">HTTP 4xx 代码的每秒响应速率</span><span class="sxs-lookup"><span data-stu-id="f09f4-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-152">HTTP 5xx 响应数/秒</span><span class="sxs-lookup"><span data-stu-id="f09f4-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-153">HTTP 5xx 代码的每秒响应速率</span><span class="sxs-lookup"><span data-stu-id="f09f4-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-154">IM MCU 联接失败</span><span class="sxs-lookup"><span data-stu-id="f09f4-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-155">IM MCU 联接失败的次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-156">Active Directory 照片获取失败的次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-157">从 Active Directory 检索照片的失败总次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-158">联系人搜索失败的次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-159">在 Exchange 中搜索联系人的失败总次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-160">反序列化失败次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-161">反序列化失败总次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-162">HD 照片获取失败的次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-163">从 Exchange 检索 HD 照片的失败总次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-164">在每个应用程序的最大订阅数</span><span class="sxs-lookup"><span data-stu-id="f09f4-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="f09f4-165">每个应用程序允许的最大订阅请求数</span><span class="sxs-lookup"><span data-stu-id="f09f4-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-166">在每批的最大订阅数</span><span class="sxs-lookup"><span data-stu-id="f09f4-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="f09f4-167">每个批处理允许的最大订阅请求数</span><span class="sxs-lookup"><span data-stu-id="f09f4-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-168">状态订阅失败</span><span class="sxs-lookup"><span data-stu-id="f09f4-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-169">订阅状态失败的次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-170">注册终结点故障</span><span class="sxs-lookup"><span data-stu-id="f09f4-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="f09f4-171">注册终结点的失败次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-172">Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-173">每秒收到的请求数</span><span class="sxs-lookup"><span data-stu-id="f09f4-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-174">Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-175">每秒成功请求 (HTTP 2xx/3xx 响应代码的速率) </span><span class="sxs-lookup"><span data-stu-id="f09f4-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-176">已成功创建应用程序请求/秒</span><span class="sxs-lookup"><span data-stu-id="f09f4-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-177">每秒成功的应用程序创建请求的速率</span><span class="sxs-lookup"><span data-stu-id="f09f4-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-178">挂起 Get Count 超时</span><span class="sxs-lookup"><span data-stu-id="f09f4-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-179">超时的挂起获取数</span><span class="sxs-lookup"><span data-stu-id="f09f4-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-180">收到的应用程序创建请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="f09f4-181">自启动服务以来收到的应用程序创建请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-182">HTTP 4xx 响应总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="f09f4-183">HTTP 4xx 响应总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-184">HTTP 5xx 响应总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="f09f4-185">HTTP 5xx 响应总次数</span><span class="sxs-lookup"><span data-stu-id="f09f4-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-186">在命令通道上收到的请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="f09f4-187">命令通道上收到的请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-188">Total Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="f09f4-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="f09f4-189">成功的请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-190">启动的会话总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="f09f4-191">启动服务后启动的会话总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-192">由于空闲超时而终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="f09f4-193">因用户空闲超时终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-194">限制的应用程序总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="f09f4-195">限制的应用程序数</span><span class="sxs-lookup"><span data-stu-id="f09f4-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="f09f4-196">Mcx 移动服务的性能计数器</span><span class="sxs-lookup"><span data-stu-id="f09f4-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f09f4-197">计数器</span><span class="sxs-lookup"><span data-stu-id="f09f4-197">Counter</span></span></th>
<th><span data-ttu-id="f09f4-198">描述</span><span class="sxs-lookup"><span data-stu-id="f09f4-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-199">Average Lifetime for a Session in Milliseconds</span><span class="sxs-lookup"><span data-stu-id="f09f4-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="f09f4-200">会话的平均生存时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="f09f4-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-201">Current Push Notification Subscriptions</span><span class="sxs-lookup"><span data-stu-id="f09f4-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="f09f4-202">当前推送通知订阅数。</span><span class="sxs-lookup"><span data-stu-id="f09f4-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="f09f4-203">此数字与当前活动会话计数联合在一起表示为 Windows Mobile 或 iPhone 设备注册的当前活动会话的子集。</span><span class="sxs-lookup"><span data-stu-id="f09f4-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-204">Currently Active Network Timeout Poll Count</span><span class="sxs-lookup"><span data-stu-id="f09f4-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-205">超时的网络投票数</span><span class="sxs-lookup"><span data-stu-id="f09f4-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-206">Currently Active Poll Count</span><span class="sxs-lookup"><span data-stu-id="f09f4-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-207">当前活动投票数（与服务器的长期连接）</span><span class="sxs-lookup"><span data-stu-id="f09f4-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-208">Currently Active Session Count</span><span class="sxs-lookup"><span data-stu-id="f09f4-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-209">当前注册到 Mobility Service 中的终结点的数目</span><span class="sxs-lookup"><span data-stu-id="f09f4-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-210">Currently Active Session Count with Active Presence Subscriptions</span><span class="sxs-lookup"><span data-stu-id="f09f4-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="f09f4-211">包含活动状态订阅的当前活动会话的数目</span><span class="sxs-lookup"><span data-stu-id="f09f4-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-212">Push Notification Requests Failed/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-213">每秒失败的推送通知数</span><span class="sxs-lookup"><span data-stu-id="f09f4-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-214">Push Notification Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-215">每秒成功的推送通知数</span><span class="sxs-lookup"><span data-stu-id="f09f4-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-216">Push Notification Requests Throttled/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-217">每秒阻止的推送通知数</span><span class="sxs-lookup"><span data-stu-id="f09f4-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-218">Push Notification Requests/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-219">每秒发送的推送通知数</span><span class="sxs-lookup"><span data-stu-id="f09f4-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-220">Requests Failed/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-221">每秒失败的请求数</span><span class="sxs-lookup"><span data-stu-id="f09f4-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-222">Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-223">每秒收到的请求数</span><span class="sxs-lookup"><span data-stu-id="f09f4-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-224">Requests Rejected/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-225">每秒拒绝的请求数</span><span class="sxs-lookup"><span data-stu-id="f09f4-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-226">Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-227">每秒成功的请求数</span><span class="sxs-lookup"><span data-stu-id="f09f4-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-228">Succeeded Initiate Session Requests/Second</span><span class="sxs-lookup"><span data-stu-id="f09f4-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="f09f4-p102">每秒成功的 Get Location 请求数。启动会话的请求占用了服务器上大部分 CPU。支持的峰值负载为 12/秒。可持续性依赖于服务器上的其他负载。启动会话通常意味着用户登录已注销很长一段时间。</span><span class="sxs-lookup"><span data-stu-id="f09f4-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-234">Total Declined Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="f09f4-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="f09f4-235">拒绝的入站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-236">Total Failed Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="f09f4-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="f09f4-237">失败的入站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-238">Total Failed Outbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="f09f4-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="f09f4-239">失败的出站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-240">Total number of sessions terminated by user</span><span class="sxs-lookup"><span data-stu-id="f09f4-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="f09f4-241">用户终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-242">Total Push Notification Requests</span><span class="sxs-lookup"><span data-stu-id="f09f4-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="f09f4-243">推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-244">Total Push Notification Requests Failed</span><span class="sxs-lookup"><span data-stu-id="f09f4-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="f09f4-245">失败的推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-246">Total Push Notification Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="f09f4-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="f09f4-247">成功的推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-248">Total Push Notification Requests Throttled</span><span class="sxs-lookup"><span data-stu-id="f09f4-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="f09f4-249">阻止的推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-250">Total Requests Failed</span><span class="sxs-lookup"><span data-stu-id="f09f4-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="f09f4-251">失败的请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-252">Total Requests received on the Command Channel</span><span class="sxs-lookup"><span data-stu-id="f09f4-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="f09f4-253">命令通道上收到的请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-254">Total Requests Rejected</span><span class="sxs-lookup"><span data-stu-id="f09f4-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="f09f4-255">拒绝的请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-256">Total Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="f09f4-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="f09f4-257">成功发送给 Mobility Service 的请求总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-258">Total Session Initiated Count</span><span class="sxs-lookup"><span data-stu-id="f09f4-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="f09f4-259">自启动 Mobility Service 后启动的会话总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-260">Total Sessions Terminated Because of User Idle Timeout</span><span class="sxs-lookup"><span data-stu-id="f09f4-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="f09f4-261">因用户空闲超时终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f09f4-262">Total Successful Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="f09f4-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="f09f4-263">成功的入站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f09f4-264">Total Successful Outbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="f09f4-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="f09f4-265">成功的出站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="f09f4-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

