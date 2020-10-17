---
title: Lync Server 2013：媒体质量诊断报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 058c12ed9f1b07df885e9e7b90f43780043cdf56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500688"
---
# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="2b13c-102">Lync Server 2013 中的媒体质量诊断报告</span><span class="sxs-lookup"><span data-stu-id="2b13c-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b13c-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2b13c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2b13c-104">媒体质量诊断报告提供有关呼叫质量的信息以及失败的呼叫的诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="2b13c-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2b13c-105">本部分内容</span><span class="sxs-lookup"><span data-stu-id="2b13c-105">In This Section</span></span>

  - <span data-ttu-id="2b13c-106">[Lync Server 2013](lync-server-2013-media-quality-summary-report.md)     中的媒体质量摘要报告为不同的终结点类型（包括企业语音对等呼叫、企业语音会议呼叫以及在公开交换的电话网络 (PSTN) 上至少依赖的呼叫提供总体质量数据。</span><span class="sxs-lookup"><span data-stu-id="2b13c-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="2b13c-107">[Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)     中的媒体质量比较报告对不同类型的音频呼叫的通话质量值进行比较 (例如，通过无线网络进行的呼叫与通过有线连接进行的呼叫) 。</span><span class="sxs-lookup"><span data-stu-id="2b13c-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="2b13c-108">[Lync server 2013](lync-server-2013-server-performance-report.md)     中的服务器性能报告列出遇到最多问题的服务器，具体取决于此类关键质量指标在性能下降、数据包丢失和抖动等方面的度量。</span><span class="sxs-lookup"><span data-stu-id="2b13c-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="2b13c-109">[Lync Server 2013](lync-server-2013-location-report.md)     中的位置报告提供网络位置的列表，以及每个位置上发生的呼叫的媒体质量摘要。</span><span class="sxs-lookup"><span data-stu-id="2b13c-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="2b13c-110">出于此报告的目的，位置基于 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="2b13c-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="2b13c-111">[Lync Server 2013](lync-server-2013-device-report.md)     中的设备报告提供用于企业语音呼叫的设备的摘要，并包括设备呼叫的平均媒体质量。</span><span class="sxs-lookup"><span data-stu-id="2b13c-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="2b13c-112">[Lync Server 2013](lync-server-2013-call-list-report.md)     中的呼叫列表报告提供有关在贵组织中拨打或接收的电话呼叫的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2b13c-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="2b13c-113">[Lync Server 2013](lync-server-2013-call-detail-report.md)     中的呼叫详细信息报告提供有关在贵组织中拨打或接收的电话呼叫的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2b13c-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="2b13c-114">[Lync server 2013 中的服务器媒体质量趋势报告](lync-server-2013-server-media-quality-trend-report.md)    提供了一种方式，以图形方式比较最大5台服务器的体验质量指标，如呼叫量、较差的呼叫百分比、数据包丢失和抖动等。</span><span class="sxs-lookup"><span data-stu-id="2b13c-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="2b13c-115">[Lync Server 2013 中的媒体质量指标分布报告](lync-server-2013-media-quality-metrics-distribution-report.md)    提供显示 "体验质量" 指标（如抖动或数据包丢失）的分布值的图。</span><span class="sxs-lookup"><span data-stu-id="2b13c-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="2b13c-116">[Lync Server 2013](lync-server-2013-location-trend-report.md)     中的位置趋势报告提供网络位置的呼叫质量趋势信息。</span><span class="sxs-lookup"><span data-stu-id="2b13c-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

