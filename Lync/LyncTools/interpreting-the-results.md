---
title: 解释结果
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
ms.openlocfilehash: 4d02f69f8ea1c8eb7df004e063dba39f03bbe8b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="edcd4-102">解释结果</span><span class="sxs-lookup"><span data-stu-id="edcd4-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edcd4-103">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="edcd4-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="edcd4-104">Lync Server 2013 压力和性能工具（LyncPerfTool.exe）具有许多计数器，您可以使用这些计数器来了解客户端正在执行的操作以及它是否遇到问题。</span><span class="sxs-lookup"><span data-stu-id="edcd4-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="edcd4-105">客户端计数器</span><span class="sxs-lookup"><span data-stu-id="edcd4-105">Client Counters</span></span>

<span data-ttu-id="edcd4-106">运行的每个 LyncPerfTool.exe 实例都有一个单独的计数器实例。</span><span class="sxs-lookup"><span data-stu-id="edcd4-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="edcd4-107">每个实例都按其进程 ID 命名。</span><span class="sxs-lookup"><span data-stu-id="edcd4-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="edcd4-108">如果客户端过载，则可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="edcd4-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="edcd4-109">若要避免这些问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="edcd4-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="edcd4-110">监视客户端计算机上的 CPU 和内存使用率。</span><span class="sxs-lookup"><span data-stu-id="edcd4-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="edcd4-111">如果 CPU 的使用率持续高于90%，则减少用户数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="edcd4-112">如果内存占用量较高，则在页面文件不够大的情况下可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="edcd4-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="edcd4-113">确认确认费用未超出计算机上的限制。</span><span class="sxs-lookup"><span data-stu-id="edcd4-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="edcd4-114">如果您正在运行内存限制，请考虑增加页面文件大小或减少用户数</span><span class="sxs-lookup"><span data-stu-id="edcd4-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="edcd4-115">下表列出了关键 LyncPerfTool 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="edcd4-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="edcd4-116">**常规信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-117"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-118"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-119">花费的时间（分钟）</span><span class="sxs-lookup"><span data-stu-id="edcd4-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="edcd4-120">启动进程后所用的时间。</span><span class="sxs-lookup"><span data-stu-id="edcd4-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-121">活动终结点</span><span class="sxs-lookup"><span data-stu-id="edcd4-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="edcd4-122">当前连接到服务器的终结点的数目。</span><span class="sxs-lookup"><span data-stu-id="edcd4-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-123">失败登录</span><span class="sxs-lookup"><span data-stu-id="edcd4-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="edcd4-124">总的终结点登录失败次数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-125">登录尝试</span><span class="sxs-lookup"><span data-stu-id="edcd4-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="edcd4-126">尝试登录尝试的总次数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-127">终结点断开</span><span class="sxs-lookup"><span data-stu-id="edcd4-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="edcd4-128">已断开连接的终结点总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-129">**状态信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-130"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-131"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-132">SetPresence 调用</span><span class="sxs-lookup"><span data-stu-id="edcd4-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="edcd4-133">状态更改尝试的总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-133">Total number of presence change attempts.</span></span> <span data-ttu-id="edcd4-134">有关不同类型的状态更改，请参阅 SetPresence （状态类型）调用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="edcd4-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-135">SetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="edcd4-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="edcd4-136">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-137">GetPresence 调用</span><span class="sxs-lookup"><span data-stu-id="edcd4-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="edcd4-138">Get 状态请求尝试总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-139">GetPresence 的 NNN 响应</span><span class="sxs-lookup"><span data-stu-id="edcd4-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="edcd4-140">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-141">**通讯簿服务信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-141">**Address Book service Information**</span></span>

<span data-ttu-id="edcd4-142">此类别包括用于监视通讯簿服务（ABS）文件下载和通讯簿 Web 查询服务请求的计数器。</span><span class="sxs-lookup"><span data-stu-id="edcd4-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-143"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-144"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-145">试图进行的 ABS 完全/增量文件下载</span><span class="sxs-lookup"><span data-stu-id="edcd4-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="edcd4-146">尝试的完整或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-147">ABS 完全/增量文件下载成功</span><span class="sxs-lookup"><span data-stu-id="edcd4-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="edcd4-148">尝试的完整或增量文件下载请求的总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-149">通讯簿 Web 查询服务相关计数器</span><span class="sxs-lookup"><span data-stu-id="edcd4-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="edcd4-150">通讯簿文件下载相关计数器。</span><span class="sxs-lookup"><span data-stu-id="edcd4-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-151">尝试的 ABS WS 调用</span><span class="sxs-lookup"><span data-stu-id="edcd4-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="edcd4-152">尝试的通讯簿 Web 查询服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-153">ABS WS 调用成功</span><span class="sxs-lookup"><span data-stu-id="edcd4-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="edcd4-154">返回成功响应代码的通讯簿 Web 查询服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-155">ABS WS 调用失败</span><span class="sxs-lookup"><span data-stu-id="edcd4-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="edcd4-156">返回错误响应代码的通讯簿 Web 查询服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-157">**通讯组列表（DL）信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-158"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-159"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-160">尝试的呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="edcd4-161">尝试的通讯组列表展开（DLX） web 服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-162">呼叫成功</span><span class="sxs-lookup"><span data-stu-id="edcd4-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="edcd4-163">返回成功响应代码的 DLX web 服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-164">调用失败</span><span class="sxs-lookup"><span data-stu-id="edcd4-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="edcd4-165">返回错误响应代码的 DLX web 服务请求总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-166">**VoIP 基本信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="edcd4-167">在启用这些方案时，下面列出了所有 IP 语音（VoIP）呼叫的报告编号，包括对中介服务器、A/V 会议服务器、边缘服务器、响应组应用程序和会议自动助理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="edcd4-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-168"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-169"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-170">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="edcd4-171">当前正在进行的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-172">呼叫已终止</span><span class="sxs-lookup"><span data-stu-id="edcd4-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="edcd4-173">已终止的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-174">呼叫被拒绝</span><span class="sxs-lookup"><span data-stu-id="edcd4-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="edcd4-175">已拒绝的传入语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-176">尝试传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="edcd4-177">尝试的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-178">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="edcd4-179">建立的传入/传出语音呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-180">呼叫收到的 NNN</span><span class="sxs-lookup"><span data-stu-id="edcd4-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="edcd4-181">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-182">VoIP 传递率（%）</span><span class="sxs-lookup"><span data-stu-id="edcd4-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="edcd4-183">已建立的呼叫总数/尝试的总呼叫数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-184">**响应组服务调用信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-185"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-186"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-187">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="edcd4-188">对响应组应用程序的活动呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-189">尝试的呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="edcd4-190">尝试的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-191">**即时消息（IM）呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-192"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-193"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-194">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="edcd4-195">正在进行的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-196">呼叫已终止</span><span class="sxs-lookup"><span data-stu-id="edcd4-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="edcd4-197">已终止的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-198">呼叫收到的 NNN</span><span class="sxs-lookup"><span data-stu-id="edcd4-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="edcd4-199">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-200">接收/发送的 IM 消息</span><span class="sxs-lookup"><span data-stu-id="edcd4-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="edcd4-201">所有会话接收或发送的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-202">尝试传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="edcd4-203">尝试的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-204">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="edcd4-205">已建立的传入/传出即时消息呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-206">**应用程序共享呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-207"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-208"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-209">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="edcd4-210">正在进行的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-211">呼叫已终止</span><span class="sxs-lookup"><span data-stu-id="edcd4-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="edcd4-212">已终止的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-213">呼叫收到的 NNN</span><span class="sxs-lookup"><span data-stu-id="edcd4-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="edcd4-214">从服务器接收的 nnn 响应代码总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-215">尝试传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="edcd4-216">尝试的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-217">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="edcd4-218">已建立的传入/传出应用程序共享呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-219">**CAA 呼叫信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-220"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-221"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-222">活动呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="edcd4-223">当前正在进行的传入/传出公用电话交换网（PSTN）呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-224">呼叫已终止</span><span class="sxs-lookup"><span data-stu-id="edcd4-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="edcd4-225">已终止的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-226">尝试传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="edcd4-227">尝试的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-228">建立的传入/传出呼叫</span><span class="sxs-lookup"><span data-stu-id="edcd4-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="edcd4-229">已建立的传入/传出 PSTN 呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-230">**会议信息**</span><span class="sxs-lookup"><span data-stu-id="edcd4-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-231"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-232"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-233">活动即时消息会议</span><span class="sxs-lookup"><span data-stu-id="edcd4-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="edcd4-234">正在进行的即时消息会议总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-235">活动的音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="edcd4-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="edcd4-236">正在进行的音频/视频（A/V）会议总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-237">活动应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="edcd4-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="edcd4-238">正在进行的应用程序共享会议总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-239">参与者数量</span><span class="sxs-lookup"><span data-stu-id="edcd4-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="edcd4-240">当前连接到会议的参与者总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-241">会议日程安排失败</span><span class="sxs-lookup"><span data-stu-id="edcd4-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="edcd4-242">尝试安排会议时出现的失败总次数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-243">加入会议失败</span><span class="sxs-lookup"><span data-stu-id="edcd4-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="edcd4-244">尝试连接到会议时出现的失败总次数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edcd4-245">**UCWA 客户端计数器**</span><span class="sxs-lookup"><span data-stu-id="edcd4-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edcd4-246"><strong>性能计数器</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="edcd4-247"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="edcd4-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edcd4-248">成功的 IMMCU 联接总数</span><span class="sxs-lookup"><span data-stu-id="edcd4-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="edcd4-249">加入的即时消息会议总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edcd4-250">成功的 DMCU 联接总数</span><span class="sxs-lookup"><span data-stu-id="edcd4-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="edcd4-251">加入的 A/V 会议总数。</span><span class="sxs-lookup"><span data-stu-id="edcd4-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

