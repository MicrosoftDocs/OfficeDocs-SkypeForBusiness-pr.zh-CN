---
title: Lync Server 2013：呼叫诊断报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 692c3e3baa564b2276be678b48e67b5f2a4abd56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="420bd-102">在 Lync Server 2013 中呼叫诊断报告</span><span class="sxs-lookup"><span data-stu-id="420bd-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="420bd-103">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="420bd-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="420bd-104">呼叫诊断报告提供失败的点对点会话和会议会话的摘要信息及诊断数据。</span><span class="sxs-lookup"><span data-stu-id="420bd-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="420bd-105">本部分内容</span><span class="sxs-lookup"><span data-stu-id="420bd-105">In This Section</span></span>

  - <span data-ttu-id="420bd-106">[Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   中的呼叫诊断摘要报告提供失败的对等会话和会议会话的总体摘要。</span><span class="sxs-lookup"><span data-stu-id="420bd-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="420bd-107">对等会话是仅涉及两个参与者的会话。</span><span class="sxs-lookup"><span data-stu-id="420bd-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="420bd-108">会议会话涉及三个或更多参与者。</span><span class="sxs-lookup"><span data-stu-id="420bd-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="420bd-109">[Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   中的对等活动诊断报告提供失败的对等会话的总体趋势视图。</span><span class="sxs-lookup"><span data-stu-id="420bd-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="420bd-110">对等会话仅涉及两个参与者。</span><span class="sxs-lookup"><span data-stu-id="420bd-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="420bd-111">[Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   中的会议诊断报告提供了每个会议模态的失败会议会话和趋势视图的总体趋势视图。</span><span class="sxs-lookup"><span data-stu-id="420bd-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="420bd-112">会议会话至少涉及三个参与者。</span><span class="sxs-lookup"><span data-stu-id="420bd-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="420bd-113">[Lync Server 2013](lync-server-2013-top-failures-report.md)   中的热门故障报告提供了一系列最常见的故障及其随时间发展的趋势。</span><span class="sxs-lookup"><span data-stu-id="420bd-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="420bd-114">[Lync Server 2013](lync-server-2013-failure-distribution-report.md)   中的故障分布报告提供了失败会话的分析。</span><span class="sxs-lookup"><span data-stu-id="420bd-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="420bd-115">[Lync Server 2013](lync-server-2013-failure-list-report.md)   中的 "故障列表报告" 提供有关失败的会议中涉及的各个参与者的详细信息。</span><span class="sxs-lookup"><span data-stu-id="420bd-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="420bd-116">[Lync Server 2013](lync-server-2013-diagnostic-report.md)   中的诊断报告为失败的会话提供诊断和疑难解答信息（包括 SIP 响应代码和诊断头和 id）。</span><span class="sxs-lookup"><span data-stu-id="420bd-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

