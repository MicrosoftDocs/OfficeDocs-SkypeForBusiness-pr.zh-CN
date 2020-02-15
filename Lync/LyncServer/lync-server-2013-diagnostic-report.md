---
title: Lync Server 2013：诊断报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a906e131329df1b59c4ac6067a4696871f0bebfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="ebc35-102">Lync Server 2013 中的诊断报告</span><span class="sxs-lookup"><span data-stu-id="ebc35-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebc35-103">_**上次修改的主题：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="ebc35-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="ebc35-104">诊断报告提供失败的会话的诊断和故障排除信息。</span><span class="sxs-lookup"><span data-stu-id="ebc35-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="ebc35-105">此信息包括在会话失败时所报告的诊断 ID 和诊断标头。</span><span class="sxs-lookup"><span data-stu-id="ebc35-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="ebc35-106">诊断 ID 是附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），而诊断标头提供诊断 ID 的附带说明。</span><span class="sxs-lookup"><span data-stu-id="ebc35-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="ebc35-107">该报告可能还包含报告组件所了解的有价值的故障排除详细信息。</span><span class="sxs-lookup"><span data-stu-id="ebc35-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="ebc35-108">例如：</span><span class="sxs-lookup"><span data-stu-id="ebc35-108">For example:</span></span>

  - <span data-ttu-id="ebc35-p102">由生成故障的 PSTN 网关提供的原因代码。在 PSTN 网络上，传出呼叫失败时，会自动生成 ISDN 用户部分 (ISUP) 原因代码。例如，PSTN 网关可能会发送原因代码 34，指示不存在可用于完成呼叫的任何电路或信道。</span><span class="sxs-lookup"><span data-stu-id="ebc35-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="ebc35-112">针对连接失败的对等方 FQDN、端口和 Winsock 错误。</span><span class="sxs-lookup"><span data-stu-id="ebc35-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="ebc35-p103">针对 DNS 解析失败所查找的名称。每次客户端联系名称服务器并请求与指定的设备名称相对应的 IP 地址时，都会进行 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="ebc35-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="ebc35-115">访问诊断报告</span><span class="sxs-lookup"><span data-stu-id="ebc35-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="ebc35-116">可以通过单击 Lync Server 2013 或会议详细信息报告[中的对等会话详细信息报告](lync-server-2013-peer-to-peer-session-detail-report.md)上的 "诊断报告（详细信息）" 指标来访问诊断报告。</span><span class="sxs-lookup"><span data-stu-id="ebc35-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ebc35-117">筛选器</span><span class="sxs-lookup"><span data-stu-id="ebc35-117">Filters</span></span>

<span data-ttu-id="ebc35-p104">无。您不能对诊断报告进行筛选。</span><span class="sxs-lookup"><span data-stu-id="ebc35-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ebc35-120">指标</span><span class="sxs-lookup"><span data-stu-id="ebc35-120">Metrics</span></span>

<span data-ttu-id="ebc35-121">下表列出了各会话的诊断报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="ebc35-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="ebc35-122">诊断报告指标</span><span class="sxs-lookup"><span data-stu-id="ebc35-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebc35-123">名称</span><span class="sxs-lookup"><span data-stu-id="ebc35-123">Name</span></span></th>
<th><span data-ttu-id="ebc35-124">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="ebc35-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ebc35-125">说明</span><span class="sxs-lookup"><span data-stu-id="ebc35-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebc35-126"><strong>报告时间</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-127">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-127">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-128">记录报告的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ebc35-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebc35-129"><strong>响应代码</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-130">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-130">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-131">会话失败时发送的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="ebc35-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebc35-132"><strong>请求类型</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-133">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-133">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-p105">失败的 SIP 请求类型。例如，INVITE、BYE 或 SERVICE。</span><span class="sxs-lookup"><span data-stu-id="ebc35-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebc35-136"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-137">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-137">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-138">错误的来源。</span><span class="sxs-lookup"><span data-stu-id="ebc35-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebc35-139"><strong>源用户 URI</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-140">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-140">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-141">发起会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="ebc35-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebc35-142"><strong>源用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-143">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-143">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-144">发起会话的用户的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="ebc35-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebc35-145"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-146">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-146">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-147">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="ebc35-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebc35-148"><strong>内容类型</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-149">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-149">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-p106">失败的媒体内容类型。例如，常见内容类型为 Application/sdp。会话描述协议 (SDP) 是用于会话公告、会话邀请及其他形式的多媒体会话启动的标准 Internet 协议。</span><span class="sxs-lookup"><span data-stu-id="ebc35-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebc35-153"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-154">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-154">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-155">错误涉及的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ebc35-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebc35-156"><strong>目标用户 URI</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-157">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-157">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-158">受邀加入会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="ebc35-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebc35-159">会议加入时间（毫秒）</span><span class="sxs-lookup"><span data-stu-id="ebc35-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="ebc35-160">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-160">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-161">用户加入会议所需的时间量（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="ebc35-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebc35-162"><strong>诊断标头</strong></span><span class="sxs-lookup"><span data-stu-id="ebc35-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="ebc35-163">否</span><span class="sxs-lookup"><span data-stu-id="ebc35-163">No</span></span></p></td>
<td><p><span data-ttu-id="ebc35-164">诊断 ID 描述</span><span class="sxs-lookup"><span data-stu-id="ebc35-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ebc35-165">可以在 " [Ms-诊断" 标头页](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx)上找到诊断错误列表。</span><span class="sxs-lookup"><span data-stu-id="ebc35-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

