---
title: 'Lync Server 2013: 媒体质量诊断报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05836ea853c89b132d39eaaba1b66056fa958072
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="db55e-102">Lync Server 2013 中的媒体质量诊断报告</span><span class="sxs-lookup"><span data-stu-id="db55e-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db55e-103">_**主题上次修改时间:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="db55e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="db55e-104">媒体质量诊断报告提供有关呼叫质量的信息以及失败的呼叫的诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="db55e-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="db55e-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="db55e-105">In This Section</span></span>

  - <span data-ttu-id="db55e-106">[Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   中的 "媒体质量摘要" 报表提供不同终结点类型的总体质量数据, 包括企业语音对等调用、企业语音会议呼叫和在公共客户端上至少依赖的通话交换式电话网络 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="db55e-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="db55e-107">[Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   中的 "媒体质量比较" 报表可比较不同类型的音频呼叫的通话质量值 (例如, 通过无线网络进行的通话以及通过有线连接拨打的通话)。</span><span class="sxs-lookup"><span data-stu-id="db55e-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="db55e-108">[Lync server 2013](lync-server-2013-server-performance-report.md)   中的服务器性能报告列出了遇到最多问题的服务器, 这些指标基于性能下降、数据包丢失和抖动等关键质量指标的测量。</span><span class="sxs-lookup"><span data-stu-id="db55e-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="db55e-109">[Lync Server 2013](lync-server-2013-location-report.md)   中的位置报告提供了网络位置列表, 以及每个位置上出现的通话的媒体质量摘要。</span><span class="sxs-lookup"><span data-stu-id="db55e-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="db55e-110">出于此报告的目的, 位置基于 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="db55e-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="db55e-111">[Lync Server 2013](lync-server-2013-device-report.md)   中的设备报表提供用于企业语音呼叫的设备摘要, 其中包括设备通话的平均媒体质量。</span><span class="sxs-lookup"><span data-stu-id="db55e-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="db55e-112">[Lync Server 2013](lync-server-2013-call-list-report.md)   中的通话清单报告提供有关在您的组织内拨打或接收电话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="db55e-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="db55e-113">[Lync Server 2013](lync-server-2013-call-detail-report.md)   中的 "呼叫详细信息" 报告提供有关在您的组织内拨打或接收电话的电话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="db55e-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="db55e-114">[Lync server 2013](lync-server-2013-server-media-quality-trend-report.md)   中的服务器媒体质量趋势报表提供了一种以图形方式比较多达5台服务器的方式, 如呼叫音量、通话百分比差、数据包丢失和抖动等。</span><span class="sxs-lookup"><span data-stu-id="db55e-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="db55e-115">[Lync Server 2013 中的 "媒体质量指标分布" 报表](lync-server-2013-media-quality-metrics-distribution-report.md)   提供了一个图形, 其中显示了质量指标 (如抖动或数据包丢失) 的分布值。</span><span class="sxs-lookup"><span data-stu-id="db55e-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="db55e-116">[Lync Server 2013](lync-server-2013-location-trend-report.md)   中的 "位置趋势" 报表提供网络位置的通话质量趋势信息。</span><span class="sxs-lookup"><span data-stu-id="db55e-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

