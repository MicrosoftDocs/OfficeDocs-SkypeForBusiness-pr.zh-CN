---
title: Lync Server 2013：对等会话详细信息报告
description: Lync Server 2013：对等会话详细信息报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e712225fddabb646cc3b862f59601857a7df8eff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557278"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="2853c-103">Lync Server 2013 中的对等会话详细信息报告</span><span class="sxs-lookup"><span data-stu-id="2853c-103">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2853c-104">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="2853c-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="2853c-p101">点对点会话详细信息报告返回有关点对点会话的详细信息。例如，如果您选择即时消息会话，则此报告将告知您会话中两个用户各自发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="2853c-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="2853c-107">访问点对点会话详细信息报告</span><span class="sxs-lookup"><span data-stu-id="2853c-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="2853c-108">可以从下列任一报告（可从监控报告主页中访问所有这些报告）访问点对点会话详细信息报告：</span><span class="sxs-lookup"><span data-stu-id="2853c-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="2853c-109">IP 电话清单报告</span><span class="sxs-lookup"><span data-stu-id="2853c-109">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="2853c-110">用户活动报告</span><span class="sxs-lookup"><span data-stu-id="2853c-110">User Activity Report</span></span>

  - <span data-ttu-id="2853c-111">呼叫允许控制报告</span><span class="sxs-lookup"><span data-stu-id="2853c-111">Call Admission Control Report</span></span>

  - <span data-ttu-id="2853c-112">故障列表报告</span><span class="sxs-lookup"><span data-stu-id="2853c-112">Failure List Report</span></span>

<span data-ttu-id="2853c-113">在对等会话详细信息报告中，可通过单击 "诊断报告 (详细信息") 指标来访问 [Lync Server 2013 中的诊断报告](lync-server-2013-diagnostic-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="2853c-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="2853c-114">此外，还可以通过单击这两个指标之一来访问主要故障报告：</span><span class="sxs-lookup"><span data-stu-id="2853c-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="2853c-115">响应</span><span class="sxs-lookup"><span data-stu-id="2853c-115">Response</span></span>

  - <span data-ttu-id="2853c-116">诊断 ID</span><span class="sxs-lookup"><span data-stu-id="2853c-116">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="2853c-117">最充分地利用点对点会话详细信息报告</span><span class="sxs-lookup"><span data-stu-id="2853c-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="2853c-p103">点对点会话详细信息报告包括大量指标，其中有许多指标是系统管理员所不熟悉的。不过，通常您只需将鼠标指针悬停在指标标签的上方即可查看提供了指标的简要说明的工具提示。</span><span class="sxs-lookup"><span data-stu-id="2853c-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="2853c-p104">请注意，给定报告上显示的实际指标将取决于您所选的点对点会话的类型。音频/视频会话将报告一组与即时消息会话不同的指标。</span><span class="sxs-lookup"><span data-stu-id="2853c-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="2853c-122">还可以将鼠标指针悬停在响应代码和诊断 ID 指标的上方来获取这些值的描述：</span><span class="sxs-lookup"><span data-stu-id="2853c-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2853c-123">筛选器</span><span class="sxs-lookup"><span data-stu-id="2853c-123">Filters</span></span>

<span data-ttu-id="2853c-p105">无。无法筛选点对点会话详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="2853c-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="2853c-126">会话信息指标</span><span class="sxs-lookup"><span data-stu-id="2853c-126">Session Information Metrics</span></span>

<span data-ttu-id="2853c-127">下表列出了每个会话的点对点会话详细信息报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="2853c-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="2853c-128">会话信息指标</span><span class="sxs-lookup"><span data-stu-id="2853c-128">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2853c-129">名称</span><span class="sxs-lookup"><span data-stu-id="2853c-129">Name</span></span></th>
<th><span data-ttu-id="2853c-130">说明</span><span class="sxs-lookup"><span data-stu-id="2853c-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2853c-131"><strong>池 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-131"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-132">会话中涉及的注册器池或边缘服务器的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="2853c-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-133"><strong>邀请时间</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-133"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-134">最初发送会话邀请的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2853c-134">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-135"><strong>响应时间</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-135"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-136">收到邀请接受函的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2853c-136">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-137"><strong>来源用户</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-137"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-138">发起会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="2853c-138">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-139"><strong>源用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-139"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-140">发起会话的用户的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="2853c-140">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-141"><strong>源用户为内部用户</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-141"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-142">指示启动会话的用户是否登录到内部网络。</span><span class="sxs-lookup"><span data-stu-id="2853c-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-143"><strong>源用户与桌面电话集成</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-143"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-144">指示启动会话的用户使用的终结点是否与其桌面电话集成。</span><span class="sxs-lookup"><span data-stu-id="2853c-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-145"><strong>会话优先级</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-145"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-p106">分配给会话的优先级。有效优先级有：未知、非紧急、正常和紧急。</span><span class="sxs-lookup"><span data-stu-id="2853c-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-148"><strong>响应代码</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-148"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-149">会话失败时发送的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="2853c-149">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-150"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-150"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-151">会议中使用的前端服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="2853c-151">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-152"><strong>捕获时间</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-152"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-153">记录会话信息的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2853c-153">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-154"><strong>结束时间</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-154"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-155">会话结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2853c-155">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-156"><strong>目标用户</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-156"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-157">受邀加入会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="2853c-157">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-158"><strong>目标用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-158"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-159">受邀加入会话的用户的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="2853c-159">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-160"><strong>目标用户为内部用户</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-160"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-161">指示受邀加入会话的用户是否登录到内部网络。</span><span class="sxs-lookup"><span data-stu-id="2853c-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-162"><strong>目标用户与桌面电话集成</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-162"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-163">指示受邀加入会话的用户使用的终结点是否与其桌面电话集成。</span><span class="sxs-lookup"><span data-stu-id="2853c-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-164"><strong>为重试会话</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-164"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-165">指示会话是否是在尝试重试以前失败的会话。</span><span class="sxs-lookup"><span data-stu-id="2853c-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-166"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-166"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-p107">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。将光标停留在 ID 号上可查看有关该 ID 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="2853c-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="2853c-169">形式指标</span><span class="sxs-lookup"><span data-stu-id="2853c-169">Metrics for Modalities</span></span>

<span data-ttu-id="2853c-170">下表列出了每种会话形式的点对点会话详细信息报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="2853c-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="2853c-171">形式指标</span><span class="sxs-lookup"><span data-stu-id="2853c-171">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2853c-172">名称</span><span class="sxs-lookup"><span data-stu-id="2853c-172">Name</span></span></th>
<th><span data-ttu-id="2853c-173">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="2853c-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2853c-174">说明</span><span class="sxs-lookup"><span data-stu-id="2853c-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2853c-175"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-175"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-176">否</span><span class="sxs-lookup"><span data-stu-id="2853c-176">No</span></span></p></td>
<td><p><span data-ttu-id="2853c-p108">会话中使用的形式。例如，即时消息 (IM) 或文件传输。</span><span class="sxs-lookup"><span data-stu-id="2853c-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-179"><strong>源用户消息</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-179"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-180">否</span><span class="sxs-lookup"><span data-stu-id="2853c-180">No</span></span></p></td>
<td><p><span data-ttu-id="2853c-181">启动会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="2853c-181">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-182"><strong>目标用户消息</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-182"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-183">否</span><span class="sxs-lookup"><span data-stu-id="2853c-183">No</span></span></p></td>
<td><p><span data-ttu-id="2853c-184">受邀加入会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="2853c-184">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="2853c-185">诊断报告指标</span><span class="sxs-lookup"><span data-stu-id="2853c-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="2853c-186">下表列出了每个诊断报告的点对点会话详细信息报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="2853c-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="2853c-187">诊断报告指标</span><span class="sxs-lookup"><span data-stu-id="2853c-187">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2853c-188">名称</span><span class="sxs-lookup"><span data-stu-id="2853c-188">Name</span></span></th>
<th><span data-ttu-id="2853c-189">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="2853c-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2853c-190">说明</span><span class="sxs-lookup"><span data-stu-id="2853c-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2853c-191"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-191"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-192">否</span><span class="sxs-lookup"><span data-stu-id="2853c-192">No</span></span></p></td>
<td><p><span data-ttu-id="2853c-193">当您单击此项时，报告显示会话的诊断报告。</span><span class="sxs-lookup"><span data-stu-id="2853c-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-194"><strong>报告时间</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-194"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-195">否</span><span class="sxs-lookup"><span data-stu-id="2853c-195">No</span></span></p></td>
<td><p><span data-ttu-id="2853c-196">记录报告的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2853c-196">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-197"><strong>请求</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-197"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-198">否</span><span class="sxs-lookup"><span data-stu-id="2853c-198">No</span></span></p></td>
<td><p><span data-ttu-id="2853c-p109">SIP 请求类型。例如 INVITE 或 BYE。</span><span class="sxs-lookup"><span data-stu-id="2853c-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-201"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-201"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-202">否</span><span class="sxs-lookup"><span data-stu-id="2853c-202">No</span></span></p></td>
<td><p><span data-ttu-id="2853c-203">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="2853c-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2853c-204"><strong>内容类型</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-204"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-205">否</span><span class="sxs-lookup"><span data-stu-id="2853c-205">No</span></span></p></td>
<td><p><span data-ttu-id="2853c-p110">会议中使用的媒体内容的类型。例如，常见内容类型为 Application/sdp。会话描述协议 (SDP) 是用于会话公告、会话邀请及其他形式的多媒体会话启动的标准 Internet 协议。</span><span class="sxs-lookup"><span data-stu-id="2853c-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2853c-209"><strong>报告者</strong></span><span class="sxs-lookup"><span data-stu-id="2853c-209"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="2853c-210">否</span><span class="sxs-lookup"><span data-stu-id="2853c-210">No</span></span></p></td>
<td><p><span data-ttu-id="2853c-211">报告问题的计算机（即客户端或服务器）。</span><span class="sxs-lookup"><span data-stu-id="2853c-211">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

