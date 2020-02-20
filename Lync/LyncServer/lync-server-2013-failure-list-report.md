---
title: Lync Server 2013：故障列表报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc3d74e6613f54f346e00328f1fae929f7def27
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="de011-102">Lync Server 2013 中的故障列表报告</span><span class="sxs-lookup"><span data-stu-id="de011-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de011-103">_**上次修改的主题：** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="de011-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="de011-104">故障列表报告提供了有关在发生故障的对等会话或会议会话中参与的各个参与者的信息。</span><span class="sxs-lookup"><span data-stu-id="de011-104">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="de011-105">此信息包括遇到问题的用户的 URI，以及与故障相关联的 SIP 响应代码和诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="de011-105">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="de011-106">访问故障列表报告</span><span class="sxs-lookup"><span data-stu-id="de011-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="de011-107">可通过[在 Lync Server 2013 的故障分布报告中](lync-server-2013-failure-distribution-report.md)单击以下任一指标来访问故障列表报告：</span><span class="sxs-lookup"><span data-stu-id="de011-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="de011-108">主要诊断原因（会话）</span><span class="sxs-lookup"><span data-stu-id="de011-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="de011-109">主要形式（会话）</span><span class="sxs-lookup"><span data-stu-id="de011-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="de011-110">主要池（会话）</span><span class="sxs-lookup"><span data-stu-id="de011-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="de011-111">主要来源（会话）</span><span class="sxs-lookup"><span data-stu-id="de011-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="de011-112">主要组件（会话）</span><span class="sxs-lookup"><span data-stu-id="de011-112">Top components (sessions)</span></span>

  - <span data-ttu-id="de011-113">主要来源用户（会话）</span><span class="sxs-lookup"><span data-stu-id="de011-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="de011-114">主要目标用户（会话）</span><span class="sxs-lookup"><span data-stu-id="de011-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="de011-115">主要来源用户代理（会话）</span><span class="sxs-lookup"><span data-stu-id="de011-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="de011-116">从故障列表报告中，您可以通过单击对等会话的会话详细信息指标，[在 Lync Server 2013 中访问对等会话详细信息报告](lync-server-2013-peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="de011-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="de011-117">您还可以通过单击会议的会议指标来访问会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="de011-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="de011-118">充分利用故障列表报告</span><span class="sxs-lookup"><span data-stu-id="de011-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="de011-119">在故障列表报告中，您只需将鼠标悬停在此值上即可查看每个响应代码或每个诊断 ID 的说明。</span><span class="sxs-lookup"><span data-stu-id="de011-119">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="de011-120">例如，如果将鼠标悬停在诊断 ID 7025 上，则会看到工具提示中显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="de011-120">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="de011-121">为用户创建媒体时出现内部服务器错误。</span><span class="sxs-lookup"><span data-stu-id="de011-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="de011-122">请务必注意，故障列表报告不提供直接检索至少参与一个失败会话的所有用户的列表的简单方法，也不会提供一种方法来确定哪些用户在发生故障时最常参与本次.</span><span class="sxs-lookup"><span data-stu-id="de011-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="de011-123">（一件事，故障列表报告没有筛选功能。）但是，如果导出数据，然后将其转换为逗号分隔值文件，则可以使用 Windows PowerShell 查找类似问题的答案。</span><span class="sxs-lookup"><span data-stu-id="de011-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="de011-124">例如，假设您将数据保存到。名为 C：\\数据\\故障\_列表 .csv 的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="de011-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="de011-125">根据保存在该文件中的数据，此命令将列出至少一个失败的会话中涉及的所有用户：</span><span class="sxs-lookup"><span data-stu-id="de011-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="de011-126">该命令将返回类似于以下的列表：</span><span class="sxs-lookup"><span data-stu-id="de011-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="de011-127">这两个命令返回每个用户参与的失败会话总数：</span><span class="sxs-lookup"><span data-stu-id="de011-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="de011-128">这将返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="de011-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="de011-129">筛选器</span><span class="sxs-lookup"><span data-stu-id="de011-129">Filters</span></span>

<span data-ttu-id="de011-130">无。</span><span class="sxs-lookup"><span data-stu-id="de011-130">None.</span></span> <span data-ttu-id="de011-131">无法筛选故障列表报告。</span><span class="sxs-lookup"><span data-stu-id="de011-131">You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="de011-132">指标</span><span class="sxs-lookup"><span data-stu-id="de011-132">Metrics</span></span>

<span data-ttu-id="de011-133">下表列出了每个失败呼叫的故障列表报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="de011-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="de011-134">故障列表报告指标</span><span class="sxs-lookup"><span data-stu-id="de011-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de011-135">名称</span><span class="sxs-lookup"><span data-stu-id="de011-135">Name</span></span></th>
<th><span data-ttu-id="de011-136">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="de011-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="de011-137">说明</span><span class="sxs-lookup"><span data-stu-id="de011-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de011-138"><strong>报告时间</strong></span><span class="sxs-lookup"><span data-stu-id="de011-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="de011-139">否</span><span class="sxs-lookup"><span data-stu-id="de011-139">No</span></span></p></td>
<td><p><span data-ttu-id="de011-140">记录报告的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="de011-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de011-141"><strong>请求</strong></span><span class="sxs-lookup"><span data-stu-id="de011-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="de011-142">否</span><span class="sxs-lookup"><span data-stu-id="de011-142">No</span></span></p></td>
<td><p><span data-ttu-id="de011-143">失败的 SIP 请求类型。</span><span class="sxs-lookup"><span data-stu-id="de011-143">SIP request type that failed.</span></span> <span data-ttu-id="de011-144">例如 INVITE 或 BYE。</span><span class="sxs-lookup"><span data-stu-id="de011-144">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de011-145"><strong>响应代码</strong></span><span class="sxs-lookup"><span data-stu-id="de011-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="de011-146">否</span><span class="sxs-lookup"><span data-stu-id="de011-146">No</span></span></p></td>
<td><p><span data-ttu-id="de011-147">会议失败时发送的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="de011-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de011-148"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="de011-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="de011-149">否</span><span class="sxs-lookup"><span data-stu-id="de011-149">No</span></span></p></td>
<td><p><span data-ttu-id="de011-150">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="de011-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de011-151"><strong>加入成本时间（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="de011-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="de011-152">否</span><span class="sxs-lookup"><span data-stu-id="de011-152">No</span></span></p></td>
<td><p><span data-ttu-id="de011-153">用户加入会议所需的时间量（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="de011-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de011-154"><strong>来源用户</strong></span><span class="sxs-lookup"><span data-stu-id="de011-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="de011-155">否</span><span class="sxs-lookup"><span data-stu-id="de011-155">No</span></span></p></td>
<td><p><span data-ttu-id="de011-156">发起呼叫的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="de011-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de011-157"><strong>源用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="de011-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="de011-158">否</span><span class="sxs-lookup"><span data-stu-id="de011-158">No</span></span></p></td>
<td><p><span data-ttu-id="de011-159">启动呼叫的用户的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="de011-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de011-160"><strong>目标用户</strong></span><span class="sxs-lookup"><span data-stu-id="de011-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="de011-161">否</span><span class="sxs-lookup"><span data-stu-id="de011-161">No</span></span></p></td>
<td><p><span data-ttu-id="de011-162">被呼叫的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="de011-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

