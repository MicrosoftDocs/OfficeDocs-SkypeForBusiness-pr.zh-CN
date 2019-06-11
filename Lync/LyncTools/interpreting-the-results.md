---
title: 解释结果
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="85dee-102">解释结果</span><span class="sxs-lookup"><span data-stu-id="85dee-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85dee-103">_**主题上次修改时间:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="85dee-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="85dee-104">Lync Server 2013 应力和性能工具 (LyncPerfTool) 具有许多计数器, 你可以使用这些计数器来了解客户端正在执行的操作以及它是否会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="85dee-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="85dee-105">客户端计数器</span><span class="sxs-lookup"><span data-stu-id="85dee-105">Client Counters</span></span>

<span data-ttu-id="85dee-106">正在运行的 LyncPerfTool 的每个实例都具有计数器的单独实例。</span><span class="sxs-lookup"><span data-stu-id="85dee-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="85dee-107">每个实例均按其进程 ID 命名。</span><span class="sxs-lookup"><span data-stu-id="85dee-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="85dee-108">如果客户端超载, 可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="85dee-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="85dee-109">若要防止这些问题, 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="85dee-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="85dee-110">监视客户端计算机上的 CPU 和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="85dee-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="85dee-111">如果 CPU 持续超过 90%, 请减少用户数。</span><span class="sxs-lookup"><span data-stu-id="85dee-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="85dee-112">如果内存占用量较高, 则当页面文件不够大时, 可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="85dee-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="85dee-113">验证确认费用未达到计算机的限制。</span><span class="sxs-lookup"><span data-stu-id="85dee-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="85dee-114">如果您运行的是内存限制, 请考虑增加页面文件大小或减少用户数</span><span class="sxs-lookup"><span data-stu-id="85dee-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="85dee-115">下表列出了关键 LyncPerfTool 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="85dee-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="85dee-116">**常规信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-117"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-118"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-119">分钟花费的时间</span><span class="sxs-lookup"><span data-stu-id="85dee-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="85dee-120">启动流程后所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="85dee-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-121">活动终结点</span><span class="sxs-lookup"><span data-stu-id="85dee-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="85dee-122">当前连接到服务器的终结点的数量。</span><span class="sxs-lookup"><span data-stu-id="85dee-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-123">失败的登录</span><span class="sxs-lookup"><span data-stu-id="85dee-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="85dee-124">终结点登录失败总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-125">登录尝试</span><span class="sxs-lookup"><span data-stu-id="85dee-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="85dee-126">终结点登录尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-127">终结点断开连接</span><span class="sxs-lookup"><span data-stu-id="85dee-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="85dee-128">已断开连接的终结点的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-129">**状态信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-130"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-131"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-132">SetPresence 通话</span><span class="sxs-lookup"><span data-stu-id="85dee-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="85dee-133">联机状态更改尝试总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-133">Total number of presence change attempts.</span></span> <span data-ttu-id="85dee-134">对于不同类型的状态更改, 请参阅 SetPresence (状态类型) 调用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="85dee-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-135">SetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="85dee-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="85dee-136">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-137">GetPresence 通话</span><span class="sxs-lookup"><span data-stu-id="85dee-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="85dee-138">获取状态请求尝试的总次数。</span><span class="sxs-lookup"><span data-stu-id="85dee-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-139">GetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="85dee-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="85dee-140">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-141">**通讯簿服务信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-141">**Address Book service Information**</span></span>

<span data-ttu-id="85dee-142">此类别包括用于监视通讯簿服务 (ABS) 文件下载和通讯簿 Web 查询服务请求的计数器。</span><span class="sxs-lookup"><span data-stu-id="85dee-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-143"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-144"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-145">已尝试绝对值完整/增量文件下载</span><span class="sxs-lookup"><span data-stu-id="85dee-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="85dee-146">已尝试的完整或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-147">ABS 完整/增量文件下载成功</span><span class="sxs-lookup"><span data-stu-id="85dee-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="85dee-148">已尝试的完整或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-149">通讯簿 Web 查询服务相关计数器</span><span class="sxs-lookup"><span data-stu-id="85dee-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="85dee-150">通讯簿文件下载相关计数器。</span><span class="sxs-lookup"><span data-stu-id="85dee-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-151">尝试进行 ABS WS 呼叫</span><span class="sxs-lookup"><span data-stu-id="85dee-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="85dee-152">尝试的通讯簿 Web 查询服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-153">ABS WS 呼叫成功</span><span class="sxs-lookup"><span data-stu-id="85dee-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="85dee-154">返回成功响应代码的通讯簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-155">ABS WS 呼叫失败</span><span class="sxs-lookup"><span data-stu-id="85dee-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="85dee-156">返回错误响应代码的通讯簿 Web 查询服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-157">**通讯组列表 (DL) 信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-158"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-159"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-160">已尝试呼叫</span><span class="sxs-lookup"><span data-stu-id="85dee-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="85dee-161">尝试的通讯组列表展开 (DLX) web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-162">通话成功</span><span class="sxs-lookup"><span data-stu-id="85dee-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="85dee-163">返回成功响应代码的 DLX web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-164">呼叫失败</span><span class="sxs-lookup"><span data-stu-id="85dee-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="85dee-165">返回了错误响应代码的 DLX web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-166">**VoIP 基本信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="85dee-167">以下列出的性能计数器将在启用这些方案时针对所有 IP 语音 (VoIP) 呼叫 (包括中介服务器、A/V 会议服务器、边缘服务器、响应组应用程序和会议自动助理) 的报告编号。</span><span class="sxs-lookup"><span data-stu-id="85dee-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-168"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-169"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-170">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="85dee-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="85dee-171">当前正在进行的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-172">通话终止</span><span class="sxs-lookup"><span data-stu-id="85dee-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="85dee-173">已终止的传入/传出语音通话总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-174">通话被拒绝</span><span class="sxs-lookup"><span data-stu-id="85dee-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="85dee-175">已拒绝的传入语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-176">已尝试拨入/拨出电话</span><span class="sxs-lookup"><span data-stu-id="85dee-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="85dee-177">已尝试传入/传出语音通话的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-178">已建立传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="85dee-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="85dee-179">已建立的传入/传出语音通话的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-180">呼叫接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="85dee-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="85dee-181">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-182">VoIP 传递率 (%)</span><span class="sxs-lookup"><span data-stu-id="85dee-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="85dee-183">已建立通话总次数/尝试的通话总次数。</span><span class="sxs-lookup"><span data-stu-id="85dee-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-184">**响应组服务呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-185"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-186"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-187">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="85dee-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="85dee-188">对响应组应用程序的活动呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-189">已尝试呼叫</span><span class="sxs-lookup"><span data-stu-id="85dee-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="85dee-190">尝试的通话总次数。</span><span class="sxs-lookup"><span data-stu-id="85dee-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-191">**即时消息 (IM) 呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-192"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-193"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-194">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="85dee-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="85dee-195">正在进行的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-196">通话终止</span><span class="sxs-lookup"><span data-stu-id="85dee-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="85dee-197">已终止的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-198">呼叫接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="85dee-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="85dee-199">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-200">接收/发送的 IM 消息</span><span class="sxs-lookup"><span data-stu-id="85dee-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="85dee-201">所有会话的已接收或已发送邮件的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-202">已尝试拨入/拨出电话</span><span class="sxs-lookup"><span data-stu-id="85dee-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="85dee-203">尝试的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-204">已建立传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="85dee-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="85dee-205">已建立的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-206">**应用共享呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-207"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-208"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-209">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="85dee-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="85dee-210">正在进行的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-211">通话终止</span><span class="sxs-lookup"><span data-stu-id="85dee-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="85dee-212">已终止的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-213">呼叫接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="85dee-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="85dee-214">从服务器接收的 nnn 响应代码的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-215">已尝试拨入/拨出电话</span><span class="sxs-lookup"><span data-stu-id="85dee-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="85dee-216">尝试的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-217">已建立传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="85dee-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="85dee-218">已建立的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-219">**CAA 通话信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-220"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-221"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-222">通话处于活动状态</span><span class="sxs-lookup"><span data-stu-id="85dee-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="85dee-223">当前正在进行的传入/传出公共交换电话网络 (PSTN) 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-224">通话终止</span><span class="sxs-lookup"><span data-stu-id="85dee-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="85dee-225">已终止的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-226">已尝试拨入/拨出电话</span><span class="sxs-lookup"><span data-stu-id="85dee-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="85dee-227">尝试的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-228">已建立传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="85dee-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="85dee-229">已建立的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-230">**会议信息**</span><span class="sxs-lookup"><span data-stu-id="85dee-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-231"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-232"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-233">活动即时消息会议</span><span class="sxs-lookup"><span data-stu-id="85dee-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="85dee-234">正在进行的即时消息会议总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-235">活动音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="85dee-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="85dee-236">正在进行的音频/视频 (A/V) 会议总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-237">活动应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="85dee-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="85dee-238">正在进行的应用程序共享会议总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-239">参与者的人数</span><span class="sxs-lookup"><span data-stu-id="85dee-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="85dee-240">当前连接到会议的参与者总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85dee-241">会议计划失败</span><span class="sxs-lookup"><span data-stu-id="85dee-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="85dee-242">尝试安排会议时失败的总次数。</span><span class="sxs-lookup"><span data-stu-id="85dee-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-243">加入会议失败</span><span class="sxs-lookup"><span data-stu-id="85dee-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="85dee-244">尝试连接到会议时失败的总次数。</span><span class="sxs-lookup"><span data-stu-id="85dee-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85dee-245">**UCWA 客户端计数器**</span><span class="sxs-lookup"><span data-stu-id="85dee-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85dee-246"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="85dee-247"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="85dee-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85dee-248">已成功联接的 IMMCU 总数</span><span class="sxs-lookup"><span data-stu-id="85dee-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="85dee-249">已加入的即时消息会议的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85dee-250">已成功联接的 DMCU 总数</span><span class="sxs-lookup"><span data-stu-id="85dee-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="85dee-251">已加入/V 会议的总数。</span><span class="sxs-lookup"><span data-stu-id="85dee-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

