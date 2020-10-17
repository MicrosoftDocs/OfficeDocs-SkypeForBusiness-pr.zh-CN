---
title: 解释结果
description: 解释结果。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8342a1ec1e15e42852fc5293f87342e98587a60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565338"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="88492-103">解释结果</span><span class="sxs-lookup"><span data-stu-id="88492-103">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88492-104">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="88492-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="88492-105">Lync Server 2013 的压力和性能工具 ( # A0) 具有许多计数器，您可以使用这些计数器来了解客户端正在执行的操作以及它是否遇到问题。</span><span class="sxs-lookup"><span data-stu-id="88492-105">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="88492-106">客户端计数器</span><span class="sxs-lookup"><span data-stu-id="88492-106">Client Counters</span></span>

<span data-ttu-id="88492-107">运行的每个 LyncPerfTool.exe 实例都有一个单独的计数器实例。</span><span class="sxs-lookup"><span data-stu-id="88492-107">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="88492-108">每个实例都按其进程 ID 命名。</span><span class="sxs-lookup"><span data-stu-id="88492-108">Each instance is named by its process ID.</span></span>

<span data-ttu-id="88492-109">如果客户端过载，则可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="88492-109">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="88492-110">若要避免这些问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="88492-110">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="88492-111">监视客户端计算机上的 CPU 和内存使用率。</span><span class="sxs-lookup"><span data-stu-id="88492-111">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="88492-112">如果 CPU 的使用率持续高于90%，则减少用户数。</span><span class="sxs-lookup"><span data-stu-id="88492-112">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="88492-113">如果内存占用量较高，则在页面文件不够大的情况下可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="88492-113">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="88492-114">确认确认费用未超出计算机上的限制。</span><span class="sxs-lookup"><span data-stu-id="88492-114">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="88492-115">如果您正在运行内存限制，请考虑增加页面文件大小或减少用户数</span><span class="sxs-lookup"><span data-stu-id="88492-115">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="88492-116">下表列出了关键 LyncPerfTool 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="88492-116">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="88492-117">**常规信息**</span><span class="sxs-lookup"><span data-stu-id="88492-117">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-118"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-118"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-119"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-119"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-120">花费的时间（分钟）</span><span class="sxs-lookup"><span data-stu-id="88492-120">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="88492-121">启动进程后所用的时间。</span><span class="sxs-lookup"><span data-stu-id="88492-121">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-122">活动终结点</span><span class="sxs-lookup"><span data-stu-id="88492-122">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="88492-123">当前连接到服务器的终结点的数目。</span><span class="sxs-lookup"><span data-stu-id="88492-123">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-124">失败登录</span><span class="sxs-lookup"><span data-stu-id="88492-124">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="88492-125">总的终结点登录失败次数。</span><span class="sxs-lookup"><span data-stu-id="88492-125">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-126">登录尝试</span><span class="sxs-lookup"><span data-stu-id="88492-126">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="88492-127">尝试登录尝试的总次数。</span><span class="sxs-lookup"><span data-stu-id="88492-127">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-128">终结点断开</span><span class="sxs-lookup"><span data-stu-id="88492-128">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="88492-129">已断开连接的终结点总数。</span><span class="sxs-lookup"><span data-stu-id="88492-129">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-130">**状态信息**</span><span class="sxs-lookup"><span data-stu-id="88492-130">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-131"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-131"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-132"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-132"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-133">SetPresence 调用</span><span class="sxs-lookup"><span data-stu-id="88492-133">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="88492-134">状态更改尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="88492-134">Total number of presence change attempts.</span></span> <span data-ttu-id="88492-135">有关不同类型的状态更改，请参阅 SetPresence (状态类型) Calls Performance Counter。</span><span class="sxs-lookup"><span data-stu-id="88492-135">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-136">SetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="88492-136">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="88492-137">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="88492-137">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-138">GetPresence 调用</span><span class="sxs-lookup"><span data-stu-id="88492-138">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="88492-139">Get 状态请求尝试总数。</span><span class="sxs-lookup"><span data-stu-id="88492-139">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-140">GetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="88492-140">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="88492-141">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="88492-141">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-142">**通讯簿服务信息**</span><span class="sxs-lookup"><span data-stu-id="88492-142">**Address Book service Information**</span></span>

<span data-ttu-id="88492-143">此类别包括用于监视通讯簿服务 (ABS) 文件下载和通讯簿 Web 查询服务请求的计数器。</span><span class="sxs-lookup"><span data-stu-id="88492-143">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-144"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-144"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-145"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-145"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-146">试图进行的 ABS 完全/增量文件下载</span><span class="sxs-lookup"><span data-stu-id="88492-146">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="88492-147">尝试的完整或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="88492-147">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-148">ABS 完全/增量文件下载成功</span><span class="sxs-lookup"><span data-stu-id="88492-148">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="88492-149">尝试的完整或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="88492-149">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-150">通讯簿 Web 查询服务相关计数器</span><span class="sxs-lookup"><span data-stu-id="88492-150">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="88492-151">通讯簿文件下载相关计数器。</span><span class="sxs-lookup"><span data-stu-id="88492-151">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-152">尝试的 ABS WS 调用</span><span class="sxs-lookup"><span data-stu-id="88492-152">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="88492-153">尝试的通讯簿 Web 查询服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="88492-153">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-154">ABS WS 调用成功</span><span class="sxs-lookup"><span data-stu-id="88492-154">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="88492-155">返回成功响应代码的通讯簿 Web 查询服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="88492-155">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-156">ABS WS 调用失败</span><span class="sxs-lookup"><span data-stu-id="88492-156">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="88492-157">返回错误响应代码的通讯簿 Web 查询服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="88492-157">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-158">**通讯组列表 (DL) 信息**</span><span class="sxs-lookup"><span data-stu-id="88492-158">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-159"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-159"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-160"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-160"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-161">尝试的呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-161">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="88492-162">尝试的通讯组列表展开 (DLX) web 服务请求的总数。</span><span class="sxs-lookup"><span data-stu-id="88492-162">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-163">呼叫成功</span><span class="sxs-lookup"><span data-stu-id="88492-163">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="88492-164">返回成功响应代码的 DLX web 服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="88492-164">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-165">调用失败</span><span class="sxs-lookup"><span data-stu-id="88492-165">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="88492-166">返回错误响应代码的 DLX web 服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="88492-166">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-167">**VoIP 基本信息**</span><span class="sxs-lookup"><span data-stu-id="88492-167">**VoIP Basic Information**</span></span>

<span data-ttu-id="88492-168">在启用这些方案时，以下列出的性能计数器将列出所有 IP 语音 (VoIP) 呼叫的报告编号，包括对中介服务器、A/V 会议服务器、边缘服务器、响应组应用程序和会议自动助理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="88492-168">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-169"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-169"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-170"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-170"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-171">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-171">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="88492-172">当前正在进行的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-172">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-173">呼叫已终止</span><span class="sxs-lookup"><span data-stu-id="88492-173">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="88492-174">已终止的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-174">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-175">呼叫被拒绝</span><span class="sxs-lookup"><span data-stu-id="88492-175">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="88492-176">已拒绝的传入语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-176">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-177">尝试传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-177">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="88492-178">尝试的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-178">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-179">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-179">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="88492-180">建立的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-180">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-181">呼叫收到的 NNN</span><span class="sxs-lookup"><span data-stu-id="88492-181">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="88492-182">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="88492-182">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-183">VoIP 传递速率 (% ) </span><span class="sxs-lookup"><span data-stu-id="88492-183">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="88492-184">已建立的呼叫总数/尝试的总呼叫数。</span><span class="sxs-lookup"><span data-stu-id="88492-184">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-185">**响应组服务调用信息**</span><span class="sxs-lookup"><span data-stu-id="88492-185">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-186"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-186"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-187"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-187"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-188">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-188">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="88492-189">对响应组应用程序的活动呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-189">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-190">尝试的呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-190">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="88492-191">尝试的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-191">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-192">**即时消息 (IM) 呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="88492-192">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-193"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-193"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-194"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-194"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-195">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-195">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="88492-196">正在进行的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-196">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-197">呼叫已终止</span><span class="sxs-lookup"><span data-stu-id="88492-197">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="88492-198">已终止的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-198">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-199">呼叫收到的 NNN</span><span class="sxs-lookup"><span data-stu-id="88492-199">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="88492-200">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="88492-200">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-201">接收/发送的 IM 消息</span><span class="sxs-lookup"><span data-stu-id="88492-201">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="88492-202">所有会话接收或发送的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="88492-202">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-203">尝试传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-203">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="88492-204">尝试的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-204">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-205">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-205">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="88492-206">已建立的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-206">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-207">**应用程序共享呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="88492-207">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-208"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-208"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-209"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-209"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-210">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-210">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="88492-211">正在进行的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-211">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-212">呼叫已终止</span><span class="sxs-lookup"><span data-stu-id="88492-212">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="88492-213">已终止的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-213">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-214">呼叫收到的 NNN</span><span class="sxs-lookup"><span data-stu-id="88492-214">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="88492-215">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="88492-215">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-216">尝试传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-216">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="88492-217">尝试的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-217">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-218">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-218">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="88492-219">已建立的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-219">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-220">**CAA 呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="88492-220">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-221"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-221"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-222"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-222"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-223">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-223">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="88492-224">当前正在进行的 (PSTN) 呼叫的传入/传出公用交换电话网络总数。</span><span class="sxs-lookup"><span data-stu-id="88492-224">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-225">呼叫已终止</span><span class="sxs-lookup"><span data-stu-id="88492-225">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="88492-226">已终止的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-226">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-227">尝试传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-227">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="88492-228">尝试的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-228">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-229">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="88492-229">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="88492-230">已建立的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="88492-230">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-231">**会议信息**</span><span class="sxs-lookup"><span data-stu-id="88492-231">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-232"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-232"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-233"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-233"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-234">活动即时消息会议</span><span class="sxs-lookup"><span data-stu-id="88492-234">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="88492-235">正在进行的即时消息会议总数。</span><span class="sxs-lookup"><span data-stu-id="88492-235">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-236">活动的音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="88492-236">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="88492-237"> (A/V) 会议的现行音频/视频总数。</span><span class="sxs-lookup"><span data-stu-id="88492-237">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-238">活动应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="88492-238">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="88492-239">正在进行的应用程序共享会议总数。</span><span class="sxs-lookup"><span data-stu-id="88492-239">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-240">参与者数量</span><span class="sxs-lookup"><span data-stu-id="88492-240">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="88492-241">当前连接到会议的参与者总数。</span><span class="sxs-lookup"><span data-stu-id="88492-241">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88492-242">会议日程安排失败</span><span class="sxs-lookup"><span data-stu-id="88492-242">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="88492-243">尝试安排会议时出现的失败总次数。</span><span class="sxs-lookup"><span data-stu-id="88492-243">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-244">加入会议失败</span><span class="sxs-lookup"><span data-stu-id="88492-244">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="88492-245">尝试连接到会议时出现的失败总次数。</span><span class="sxs-lookup"><span data-stu-id="88492-245">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88492-246">**UCWA 客户端计数器**</span><span class="sxs-lookup"><span data-stu-id="88492-246">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88492-247"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="88492-247"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="88492-248"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="88492-248"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88492-249">成功的 IMMCU 联接总数</span><span class="sxs-lookup"><span data-stu-id="88492-249">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="88492-250">加入的即时消息会议总数。</span><span class="sxs-lookup"><span data-stu-id="88492-250">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88492-251">成功的 DMCU 联接总数</span><span class="sxs-lookup"><span data-stu-id="88492-251">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="88492-252">加入的 A/V 会议总数。</span><span class="sxs-lookup"><span data-stu-id="88492-252">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

