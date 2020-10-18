---
title: Lync Server 2013：会议详细信息报告
description: Lync Server 2013：会议详细信息报告。
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
ms.openlocfilehash: 07c50b545f4a9ee3308a840fc2aa5a15e617a5bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577628"
---
# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="a481a-103">Lync Server 2013 中的会议详细信息报告</span><span class="sxs-lookup"><span data-stu-id="a481a-103">Conference Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a481a-104">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a481a-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a481a-105">会议详细信息报告提供了参与会议的所有用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a481a-105">The Conference Detail Report provides detailed information about all the users who participated in a conference.</span></span> <span data-ttu-id="a481a-106">例如，您可以查看用户加入会议的日期和时间、用户离开会议的日期和时间以及用于将该用户连接到会议的终结点的用户代理等信息。</span><span class="sxs-lookup"><span data-stu-id="a481a-106">For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference.</span></span> <span data-ttu-id="a481a-107">您还可以查看每个会议中用户角色的信息 (例如，"演示者" 或 "与会者) "。</span><span class="sxs-lookup"><span data-stu-id="a481a-107">You can also see information the user's role in each conference (for example, Presenter or Attendee).</span></span> <span data-ttu-id="a481a-108">最重要的是，您很快就会发现哪些用户成功加入会议并完成会议，哪些用户无法成功加入会议，也无法完成会议。</span><span class="sxs-lookup"><span data-stu-id="a481a-108">Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="a481a-109">访问会议详细信息报告</span><span class="sxs-lookup"><span data-stu-id="a481a-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="a481a-110">可从以下报告访问会议详细信息报告：</span><span class="sxs-lookup"><span data-stu-id="a481a-110">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="a481a-111">[Lync Server 2013 中的呼叫允许控制报告](lync-server-2013-call-admission-control-report.md) (单击会议的详细指标) </span><span class="sxs-lookup"><span data-stu-id="a481a-111">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="a481a-112">[Lync Server 2013 中的 "故障列表报告](lync-server-2013-failure-list-report.md)" (单击 "会议指标") </span><span class="sxs-lookup"><span data-stu-id="a481a-112">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="a481a-113">[Lync Server 2013 中的 "用户活动" 报表](lync-server-2013-user-activity-report.md) (单击 "会议 URI" 指标) </span><span class="sxs-lookup"><span data-stu-id="a481a-113">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="a481a-114">从会议详细信息报告中，您可以通过单击诊断报告 (详细信息) 指标来访问 [Lync Server 2013 中的诊断报告](lync-server-2013-diagnostic-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="a481a-114">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a481a-115">筛选器</span><span class="sxs-lookup"><span data-stu-id="a481a-115">Filters</span></span>

<span data-ttu-id="a481a-116">无。</span><span class="sxs-lookup"><span data-stu-id="a481a-116">None.</span></span> <span data-ttu-id="a481a-117">无法筛选会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="a481a-117">You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a481a-118">指标</span><span class="sxs-lookup"><span data-stu-id="a481a-118">Metrics</span></span>

<span data-ttu-id="a481a-119">下表列出了会议详细信息报告的 "会议信息" 部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="a481a-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="a481a-120">会议信息指标</span><span class="sxs-lookup"><span data-stu-id="a481a-120">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a481a-121">名称</span><span class="sxs-lookup"><span data-stu-id="a481a-121">Name</span></span></th>
<th><span data-ttu-id="a481a-122">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="a481a-122">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a481a-123">说明</span><span class="sxs-lookup"><span data-stu-id="a481a-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a481a-124"><strong>会议 URI</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-124"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-125">分配给会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="a481a-125">URI assigned to the conference.</span></span> <span data-ttu-id="a481a-126">例如：</span><span class="sxs-lookup"><span data-stu-id="a481a-126">For example:</span></span></p>
<p><span data-ttu-id="a481a-127">sip： kmyer@litwareinc; gruu; 不透明 = app：会议：焦点： id： drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="a481a-127">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a481a-128"><strong>池 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-128"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-129">会话中涉及的注册器池或边缘服务器的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="a481a-129">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a481a-130"><strong>开始时间</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-130"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-131">会议开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a481a-131">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a481a-132"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-132"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-133">组织会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="a481a-133">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a481a-134"><strong>结束时间</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-134"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-135">会议结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a481a-135">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a481a-136">下表列出了会议详细信息报告的会议参与部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="a481a-136">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="a481a-137">会议参与指标</span><span class="sxs-lookup"><span data-stu-id="a481a-137">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a481a-138">名称</span><span class="sxs-lookup"><span data-stu-id="a481a-138">Name</span></span></th>
<th><span data-ttu-id="a481a-139">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="a481a-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a481a-140">说明</span><span class="sxs-lookup"><span data-stu-id="a481a-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a481a-141"><strong>用户</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-141"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-142">参与会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="a481a-142">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a481a-143"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-143"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-144">会议参与者扮演的角色（例如“演示者”）。</span><span class="sxs-lookup"><span data-stu-id="a481a-144">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a481a-145"><strong>连接</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-145"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-146">参与者的网络连接（通常为“来自内部”或“来自外部”）。</span><span class="sxs-lookup"><span data-stu-id="a481a-146">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a481a-147">加入时间</span><span class="sxs-lookup"><span data-stu-id="a481a-147">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-148">参与者加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a481a-148">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a481a-149"><strong>离开时间</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-149"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-150">参与者离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a481a-150">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a481a-151"><strong>用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-151"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-152">参与者终结点使用的软件的标识符。</span><span class="sxs-lookup"><span data-stu-id="a481a-152">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a481a-153"><strong>诊断报告</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-153"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-154">提供诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="a481a-154">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="a481a-155">包括 SIP 响应代码、诊断标头、会议加入时间，以及失败会话的诊断 Id。</span><span class="sxs-lookup"><span data-stu-id="a481a-155">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a481a-156">下表列出了会议详细信息报告的 "会议形式" 部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="a481a-156">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="a481a-157">会议形式指标</span><span class="sxs-lookup"><span data-stu-id="a481a-157">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a481a-158">名称</span><span class="sxs-lookup"><span data-stu-id="a481a-158">Name</span></span></th>
<th><span data-ttu-id="a481a-159">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="a481a-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a481a-160">说明</span><span class="sxs-lookup"><span data-stu-id="a481a-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a481a-161"><strong>用户</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-161"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-162">参与会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="a481a-162">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a481a-163"><strong>加入时间</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-163"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-164">参与者加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a481a-164">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a481a-165"><strong>离开时间</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-165"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-166">参与者离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a481a-166">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a481a-167"><strong>会议服务器 URI</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-167"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-168">会议中使用的会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="a481a-168">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a481a-169"><strong>诊断报告</strong></span><span class="sxs-lookup"><span data-stu-id="a481a-169"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a481a-170">提供诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="a481a-170">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="a481a-171">包括 SIP 响应代码、诊断标头、会议加入时间，以及失败会话的诊断 Id。</span><span class="sxs-lookup"><span data-stu-id="a481a-171">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

