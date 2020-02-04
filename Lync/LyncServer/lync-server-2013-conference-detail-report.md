---
title: Lync Server 2013：会议详细信息报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e2cd992e83adb29c43935d4b4c7f223580d53
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="0703d-102">Lync Server 2013 中的 "会议详细信息" 报表</span><span class="sxs-lookup"><span data-stu-id="0703d-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0703d-103">_**主题上次修改时间：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="0703d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0703d-p101">会议详细信息报告提供有关参与会议的所有用户的详细信息。例如，您可以查看用户加入会议的日期和时间、用户离开会议的日期和时间以及用于将该用户连接到会议的端点的用户代理等信息。还可以查看用户在每个会议中的角色的信息（例如，演示者或与会者）。可能最重要的是，您可以快速查看哪些用户成功加入和完成会议，哪些用户无法成功加入和完成会议。</span><span class="sxs-lookup"><span data-stu-id="0703d-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="0703d-108">访问会议详细信息报告</span><span class="sxs-lookup"><span data-stu-id="0703d-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="0703d-109">可从以下报告中访问会议详细信息报告：</span><span class="sxs-lookup"><span data-stu-id="0703d-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="0703d-110">[Lync Server 2013 中的呼叫许可控制报告](lync-server-2013-call-admission-control-report.md)（通过单击会议的详细信息指标）</span><span class="sxs-lookup"><span data-stu-id="0703d-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="0703d-111">[Lync Server 2013 中的 "失败列表" 报表](lync-server-2013-failure-list-report.md)（通过单击会议跃点数）</span><span class="sxs-lookup"><span data-stu-id="0703d-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="0703d-112">[Lync Server 2013 中的用户活动报表](lync-server-2013-user-activity-report.md)（通过单击会议 URI 跃点数）</span><span class="sxs-lookup"><span data-stu-id="0703d-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="0703d-113">在 "会议详细信息报告" 中，可以通过单击诊断报告（详细信息）指标来访问[Lync Server 2013 中的诊断报告](lync-server-2013-diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="0703d-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0703d-114">筛选器</span><span class="sxs-lookup"><span data-stu-id="0703d-114">Filters</span></span>

<span data-ttu-id="0703d-p102">无。您无法筛选会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="0703d-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0703d-117">指标</span><span class="sxs-lookup"><span data-stu-id="0703d-117">Metrics</span></span>

<span data-ttu-id="0703d-118">下表列出了会议详细信息报告的“会议信息”部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0703d-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="0703d-119">会议信息指标</span><span class="sxs-lookup"><span data-stu-id="0703d-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0703d-120">名称</span><span class="sxs-lookup"><span data-stu-id="0703d-120">Name</span></span></th>
<th><span data-ttu-id="0703d-121">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0703d-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0703d-122">描述</span><span class="sxs-lookup"><span data-stu-id="0703d-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0703d-123"><strong>会议 URI</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-p103">分配给会议的 URI。例如：</span><span class="sxs-lookup"><span data-stu-id="0703d-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="0703d-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="0703d-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0703d-127"><strong>池 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-128">会话中涉及的注册器池或边缘服务器的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="0703d-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0703d-129"><strong>开始时间</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-130">会议开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0703d-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0703d-131"><strong>组织者</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-132">组织会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="0703d-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0703d-133"><strong>结束时间</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-134">会议结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0703d-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0703d-135">下表列出了会议详细信息报告的“会议参与”部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0703d-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="0703d-136">会议参与指标</span><span class="sxs-lookup"><span data-stu-id="0703d-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0703d-137">名称</span><span class="sxs-lookup"><span data-stu-id="0703d-137">Name</span></span></th>
<th><span data-ttu-id="0703d-138">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0703d-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0703d-139">描述</span><span class="sxs-lookup"><span data-stu-id="0703d-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0703d-140"><strong>用户</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-141">参与会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="0703d-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0703d-142"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-143">会议参与者扮演的角色（例如“演示者”）。</span><span class="sxs-lookup"><span data-stu-id="0703d-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0703d-144"><strong>连接</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-145">参与者的网络连接（通常为“来自内部”或“来自外部”）。</span><span class="sxs-lookup"><span data-stu-id="0703d-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0703d-146">加入时间</span><span class="sxs-lookup"><span data-stu-id="0703d-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-147">参与者加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0703d-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0703d-148"><strong>离开时间</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-149">参与者离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0703d-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0703d-150"><strong>用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-151">参与者的端点所使用软件的标识符。</span><span class="sxs-lookup"><span data-stu-id="0703d-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0703d-152"><strong>诊断报告</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-p104">提供诊断和故障排除信息。包括 SIP 响应代码、诊断标题、会议加入时间和失败会话的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="0703d-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0703d-155">下表列出了会议详细信息报表的 "会议形式" 部分中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0703d-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="0703d-156">会议形式指标</span><span class="sxs-lookup"><span data-stu-id="0703d-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0703d-157">名称</span><span class="sxs-lookup"><span data-stu-id="0703d-157">Name</span></span></th>
<th><span data-ttu-id="0703d-158">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0703d-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0703d-159">描述</span><span class="sxs-lookup"><span data-stu-id="0703d-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0703d-160"><strong>用户</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-161">参与会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="0703d-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0703d-162"><strong>加入时间</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-163">参与者加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0703d-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0703d-164"><strong>离开时间</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-165">参与者离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0703d-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0703d-166"><strong>会议服务器 URI</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-167">会议中使用的会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="0703d-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0703d-168"><strong>诊断报告</strong></span><span class="sxs-lookup"><span data-stu-id="0703d-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0703d-p105">提供诊断和故障排除信息。包括 SIP 响应代码、诊断标题、会议加入时间和失败会话的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="0703d-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

