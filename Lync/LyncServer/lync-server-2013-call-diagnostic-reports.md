---
title: 'Lync Server 2013: 呼叫诊断报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 342c1727985418930a333c723962da2bb276692f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="8a763-102">在 Lync Server 2013 中呼叫诊断报告</span><span class="sxs-lookup"><span data-stu-id="8a763-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a763-103">_**主题上次修改时间:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="8a763-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="8a763-104">呼叫诊断报告提供失败的对等会话和会议会话的摘要信息及诊断数据。</span><span class="sxs-lookup"><span data-stu-id="8a763-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8a763-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="8a763-105">In This Section</span></span>

  - <span data-ttu-id="8a763-106">[Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   中的呼叫诊断摘要报告提供了失败的对等会话和会议会话的总体摘要。</span><span class="sxs-lookup"><span data-stu-id="8a763-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="8a763-107">对等会话是仅涉及两个参与者的会话。</span><span class="sxs-lookup"><span data-stu-id="8a763-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="8a763-108">会议会话涉及三个或更多参与者。</span><span class="sxs-lookup"><span data-stu-id="8a763-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="8a763-109">[Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   中的对等活动诊断报告提供失败的对等会话的整体趋势视图。</span><span class="sxs-lookup"><span data-stu-id="8a763-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="8a763-110">对等会话只涉及两个参与者。</span><span class="sxs-lookup"><span data-stu-id="8a763-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="8a763-111">[Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   中的会议诊断报告为每个会议模态提供了失败的会议会话和趋势视图的整体趋势视图。</span><span class="sxs-lookup"><span data-stu-id="8a763-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="8a763-112">会议会话至少涉及三个参与者。</span><span class="sxs-lookup"><span data-stu-id="8a763-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="8a763-113">[Lync Server 2013](lync-server-2013-top-failures-report.md)   中的 "热门故障" 报表提供一系列最常见的失败及其随时间变化的趋势。</span><span class="sxs-lookup"><span data-stu-id="8a763-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="8a763-114">[Lync Server 2013](lync-server-2013-failure-distribution-report.md)   中的失败分配报告可分析失败的会话。</span><span class="sxs-lookup"><span data-stu-id="8a763-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="8a763-115">[Lync Server 2013](lync-server-2013-failure-list-report.md)   中的 "故障列表" 报告提供有关失败的会议中涉及的单个参与者的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8a763-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="8a763-116">[Lync Server 2013](lync-server-2013-diagnostic-report.md)   中的诊断报告为失败的会话提供诊断和疑难解答信息 (包括 SIP 响应代码和诊断头和 id)。</span><span class="sxs-lookup"><span data-stu-id="8a763-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

