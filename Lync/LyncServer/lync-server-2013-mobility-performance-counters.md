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
ms.openlocfilehash: 439c179476c89de8a5245e80e26586d42f4f6e3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="ccbda-102">Lync Server 2013 中的移动性能计数器</span><span class="sxs-lookup"><span data-stu-id="ccbda-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccbda-103">_**主题上次修改时间：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ccbda-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ccbda-104">下表列出了可用于监视运行统一通信 Web API （UCWA）和 Lync Server 2013 Mcx 移动服务的服务器的性能计数器的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="ccbda-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="ccbda-105">UCWA 表中计数器的类别名称为 **LS:WEB – UCWA**。</span><span class="sxs-lookup"><span data-stu-id="ccbda-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="ccbda-106">Mcx Mobility Service 表中计数器的类别名称为 **LS:WEB - Mobile Communication Service**。</span><span class="sxs-lookup"><span data-stu-id="ccbda-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="ccbda-107">UCWA 性能计数器</span><span class="sxs-lookup"><span data-stu-id="ccbda-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccbda-108">计数器</span><span class="sxs-lookup"><span data-stu-id="ccbda-108">Counter</span></span></th>
<th><span data-ttu-id="ccbda-109">描述</span><span class="sxs-lookup"><span data-stu-id="ccbda-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-110">Active Application Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-111">当前应用程序数目</span><span class="sxs-lookup"><span data-stu-id="ccbda-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-112">Active Application Sharing Modality Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-113">当前应用程序共享形式数目</span><span class="sxs-lookup"><span data-stu-id="ccbda-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-114">Active Audio Modality Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-115">当前音频形式数目</span><span class="sxs-lookup"><span data-stu-id="ccbda-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-116">Active Data Collaboration Modality Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-117">当前数据协作形式数目</span><span class="sxs-lookup"><span data-stu-id="ccbda-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-118">Active Directory Photo Get Latency (ms)</span><span class="sxs-lookup"><span data-stu-id="ccbda-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="ccbda-119">此计数器显示从 Active Directory 检索照片所花的平均时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="ccbda-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-120">Active Messaging Modality Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-121">当前消息传递形式数目</span><span class="sxs-lookup"><span data-stu-id="ccbda-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-122">Active Panoramic Video Modality Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-123">当前全景视频形式数目</span><span class="sxs-lookup"><span data-stu-id="ccbda-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-124">Active Pending Get Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-125">当前活动待处理项数；与服务器长期保持连接</span><span class="sxs-lookup"><span data-stu-id="ccbda-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-126">Active Session Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-127">当前在 UCWA 中按应用程序注册的终结点数和总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-128">Active User Instance Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-129">当前用户实例数</span><span class="sxs-lookup"><span data-stu-id="ccbda-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-130">Active User Instances without Application</span><span class="sxs-lookup"><span data-stu-id="ccbda-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="ccbda-131">当前用户实例数（无应用程序）</span><span class="sxs-lookup"><span data-stu-id="ccbda-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-132">Active Video Modality Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-133">当前视频形式数目</span><span class="sxs-lookup"><span data-stu-id="ccbda-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-134">Application Creation Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-135">应用程序创建请求的每秒接收速率</span><span class="sxs-lookup"><span data-stu-id="ccbda-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-136">AS MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="ccbda-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-137">AS MCU 联接失败数</span><span class="sxs-lookup"><span data-stu-id="ccbda-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-138">AV MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="ccbda-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-139">AV MCU 联接失败数</span><span class="sxs-lookup"><span data-stu-id="ccbda-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-140">Average Application Startup Time (ms)</span><span class="sxs-lookup"><span data-stu-id="ccbda-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="ccbda-141">应用程序平均启动时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="ccbda-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-142">Average Lifetime for Session (ms)</span><span class="sxs-lookup"><span data-stu-id="ccbda-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="ccbda-143">会话的平均生存时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="ccbda-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-144">Data MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="ccbda-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-145">Data MCU 联接失败数</span><span class="sxs-lookup"><span data-stu-id="ccbda-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-146">Exchange Contact Search Latency (ms)</span><span class="sxs-lookup"><span data-stu-id="ccbda-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="ccbda-147">此计数器显示在 Exchange 中搜索联系人所花的平均时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="ccbda-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-148">Exchange HD Photo Get Latency (ms)</span><span class="sxs-lookup"><span data-stu-id="ccbda-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="ccbda-149">此计数器显示从 Exchange 中检索照片所花的平均时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="ccbda-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-150">HTTP 4xx Responses/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-151">HTTP 4xx 代码的每秒响应速率</span><span class="sxs-lookup"><span data-stu-id="ccbda-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-152">HTTP 5xx Responses/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-153">HTTP 5xx 代码的每秒响应速率</span><span class="sxs-lookup"><span data-stu-id="ccbda-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-154">IM MCU Join Failures</span><span class="sxs-lookup"><span data-stu-id="ccbda-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-155">IM MCU 联接失败数</span><span class="sxs-lookup"><span data-stu-id="ccbda-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-156">Number of Active Directory Photo Get Failures</span><span class="sxs-lookup"><span data-stu-id="ccbda-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-157">从 Active Directory 中检索照片的总失败次数</span><span class="sxs-lookup"><span data-stu-id="ccbda-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-158">Number of Contact Search failures</span><span class="sxs-lookup"><span data-stu-id="ccbda-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-159">在 Exchange 中搜索联系人的总失败次数</span><span class="sxs-lookup"><span data-stu-id="ccbda-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-160">Number of Deserialization Failures</span><span class="sxs-lookup"><span data-stu-id="ccbda-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-161">反序列化的总失败次数</span><span class="sxs-lookup"><span data-stu-id="ccbda-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-162">HD 照片获取失败的次数</span><span class="sxs-lookup"><span data-stu-id="ccbda-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-163">从 Exchange 中检索 HD 照片的总失败次数</span><span class="sxs-lookup"><span data-stu-id="ccbda-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-164">Over The Maximum Subscriptions Per Application</span><span class="sxs-lookup"><span data-stu-id="ccbda-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="ccbda-165">允许的每应用程序最大订阅请求数</span><span class="sxs-lookup"><span data-stu-id="ccbda-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-166">Over The Maximum Subscriptions Per Batch</span><span class="sxs-lookup"><span data-stu-id="ccbda-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="ccbda-167">允许的每批次最大订阅请求数</span><span class="sxs-lookup"><span data-stu-id="ccbda-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-168">Presence Subscription Failures</span><span class="sxs-lookup"><span data-stu-id="ccbda-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-169">订阅状态失败次数</span><span class="sxs-lookup"><span data-stu-id="ccbda-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-170">Registering Endpoint Failures</span><span class="sxs-lookup"><span data-stu-id="ccbda-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="ccbda-171">注册终结点的失败次数</span><span class="sxs-lookup"><span data-stu-id="ccbda-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-172">Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-173">每秒收到的请求数</span><span class="sxs-lookup"><span data-stu-id="ccbda-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-174">Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-175">每秒的成功请求数（HTTP 2xx/3xx 响应代码）</span><span class="sxs-lookup"><span data-stu-id="ccbda-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-176">Succeeded Create Application Requests/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-177">成功应用程序创建请求的每秒接收速率</span><span class="sxs-lookup"><span data-stu-id="ccbda-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-178">Timed Out Pending Get Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-179">超时的待处理项数</span><span class="sxs-lookup"><span data-stu-id="ccbda-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-180">Total Application Creation Requests Received</span><span class="sxs-lookup"><span data-stu-id="ccbda-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="ccbda-181">自启动服务以来收到的应用程序创建请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-182">Total HTTP 4xx Responses</span><span class="sxs-lookup"><span data-stu-id="ccbda-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="ccbda-183">HTTP 4xx 响应总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-184">Total HTTP 5xx Responses</span><span class="sxs-lookup"><span data-stu-id="ccbda-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="ccbda-185">HTTP 5xx 响应总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-186">Total Requests Received on the Command Channel</span><span class="sxs-lookup"><span data-stu-id="ccbda-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="ccbda-187">命令通道上收到的请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-188">Total Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="ccbda-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="ccbda-189">成功的请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-190">Total Sessions Initiated</span><span class="sxs-lookup"><span data-stu-id="ccbda-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="ccbda-191">自启动服务以来启动的会话总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-192">Total Sessions Terminated Because of Idle Timeout</span><span class="sxs-lookup"><span data-stu-id="ccbda-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="ccbda-193">因用户空闲超时终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-194">Total Throttled Applications</span><span class="sxs-lookup"><span data-stu-id="ccbda-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="ccbda-195">阻止的应用程序数</span><span class="sxs-lookup"><span data-stu-id="ccbda-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="ccbda-196">Mcx Mobility Service 性能计数器</span><span class="sxs-lookup"><span data-stu-id="ccbda-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccbda-197">计数器</span><span class="sxs-lookup"><span data-stu-id="ccbda-197">Counter</span></span></th>
<th><span data-ttu-id="ccbda-198">描述</span><span class="sxs-lookup"><span data-stu-id="ccbda-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-199">Average Lifetime for a Session in Milliseconds</span><span class="sxs-lookup"><span data-stu-id="ccbda-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="ccbda-200">会话的平均生存时间（以毫秒为单位）</span><span class="sxs-lookup"><span data-stu-id="ccbda-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-201">Current Push Notification Subscriptions</span><span class="sxs-lookup"><span data-stu-id="ccbda-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="ccbda-p101">当前推送通知订阅数。此数目与 Currently Active Session Count 结合在一起表示为 Windows Mobile 或 iPhone 设备注册的当前活动会话的子集。</span><span class="sxs-lookup"><span data-stu-id="ccbda-p101">The current number of push notification subscriptions. This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-204">Currently Active Network Timeout Poll Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-205">超时的网络投票数</span><span class="sxs-lookup"><span data-stu-id="ccbda-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-206">Currently Active Poll Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-207">当前活动投票数（与服务器的长期连接）</span><span class="sxs-lookup"><span data-stu-id="ccbda-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-208">Currently Active Session Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-209">当前注册到 Mobility Service 中的终结点的数目</span><span class="sxs-lookup"><span data-stu-id="ccbda-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-210">Currently Active Session Count with Active Presence Subscriptions</span><span class="sxs-lookup"><span data-stu-id="ccbda-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="ccbda-211">包含活动状态订阅的当前活动会话的数目</span><span class="sxs-lookup"><span data-stu-id="ccbda-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-212">Push Notification Requests Failed/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-213">每秒失败的推送通知数</span><span class="sxs-lookup"><span data-stu-id="ccbda-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-214">Push Notification Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-215">每秒成功的推送通知数</span><span class="sxs-lookup"><span data-stu-id="ccbda-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-216">Push Notification Requests Throttled/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-217">每秒阻止的推送通知数</span><span class="sxs-lookup"><span data-stu-id="ccbda-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-218">Push Notification Requests/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-219">每秒发送的推送通知数</span><span class="sxs-lookup"><span data-stu-id="ccbda-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-220">Requests Failed/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-221">每秒失败的请求数</span><span class="sxs-lookup"><span data-stu-id="ccbda-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-222">Requests Received/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-223">每秒收到的请求数</span><span class="sxs-lookup"><span data-stu-id="ccbda-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-224">Requests Rejected/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-225">每秒拒绝的请求数</span><span class="sxs-lookup"><span data-stu-id="ccbda-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-226">Requests Succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-227">每秒成功的请求数</span><span class="sxs-lookup"><span data-stu-id="ccbda-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-228">Succeeded Initiate Session Requests/Second</span><span class="sxs-lookup"><span data-stu-id="ccbda-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="ccbda-p102">每秒成功的 Get Location 请求数。启动会话的请求占用了服务器上大部分 CPU。支持的峰值负载为 12/秒。可持续性依赖于服务器上的其他负载。启动会话通常意味着用户登录已注销很长一段时间。</span><span class="sxs-lookup"><span data-stu-id="ccbda-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-234">Total Declined Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="ccbda-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="ccbda-235">拒绝的入站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-236">Total Failed Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="ccbda-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="ccbda-237">失败的入站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-238">Total Failed Outbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="ccbda-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="ccbda-239">失败的出站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-240">Total number of sessions terminated by user</span><span class="sxs-lookup"><span data-stu-id="ccbda-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="ccbda-241">用户终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-242">Total Push Notification Requests</span><span class="sxs-lookup"><span data-stu-id="ccbda-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="ccbda-243">推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-244">Total Push Notification Requests Failed</span><span class="sxs-lookup"><span data-stu-id="ccbda-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="ccbda-245">失败的推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-246">Total Push Notification Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="ccbda-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="ccbda-247">成功的推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-248">Total Push Notification Requests Throttled</span><span class="sxs-lookup"><span data-stu-id="ccbda-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="ccbda-249">阻止的推送通知请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-250">Total Requests Failed</span><span class="sxs-lookup"><span data-stu-id="ccbda-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="ccbda-251">失败的请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-252">Total Requests received on the Command Channel</span><span class="sxs-lookup"><span data-stu-id="ccbda-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="ccbda-253">命令通道上收到的请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-254">Total Requests Rejected</span><span class="sxs-lookup"><span data-stu-id="ccbda-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="ccbda-255">拒绝的请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-256">Total Requests Succeeded</span><span class="sxs-lookup"><span data-stu-id="ccbda-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="ccbda-257">成功发送给 Mobility Service 的请求总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-258">Total Session Initiated Count</span><span class="sxs-lookup"><span data-stu-id="ccbda-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="ccbda-259">自启动 Mobility Service 后启动的会话总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-260">Total Sessions Terminated Because of User Idle Timeout</span><span class="sxs-lookup"><span data-stu-id="ccbda-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="ccbda-261">因用户空闲超时终止的会话总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccbda-262">Total Successful Inbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="ccbda-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="ccbda-263">成功的入站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccbda-264">Total Successful Outbound Voice Calls</span><span class="sxs-lookup"><span data-stu-id="ccbda-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="ccbda-265">成功的出站语音呼叫总数</span><span class="sxs-lookup"><span data-stu-id="ccbda-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

