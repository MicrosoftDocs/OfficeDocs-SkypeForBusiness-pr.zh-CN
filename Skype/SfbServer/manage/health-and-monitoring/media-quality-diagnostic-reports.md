---
title: Skype for Business Server 2015 中的媒体质量诊断报告
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: 摘要： 了解媒体在 Skype 的质量诊断报告业务服务器 2015年。
ms.openlocfilehash: 15454020262a02f0028734d98f0bad579a3a5319
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server-2015"></a><span data-ttu-id="2796b-103">Skype for Business Server 2015 中的媒体质量诊断报告</span><span class="sxs-lookup"><span data-stu-id="2796b-103">Media Quality Diagnostic Reports in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2796b-104">**摘要：**了解媒体在 Skype 的质量诊断报告业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="2796b-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2796b-105">媒体质量诊断报告提供有关呼叫质量的信息以及失败的呼叫的诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="2796b-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2796b-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="2796b-106">In this section</span></span>

- <span data-ttu-id="2796b-107">[在 Skype 业务服务器 2015年的媒体质量摘要报告](summary.md)提供总体质量数据不同的终结点类型包括点到点调用企业语音、 企业语音电话会议和调用依赖于，至少部分公用交换电话网络 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="2796b-107">[Media Quality Summary Report in Skype for Business Server 2015](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="2796b-108">[媒体质量比较报告在 Skype 业务服务器 2015](comparison.md)提供不同类型的音频呼叫 （例如，通过无线网络与有线连接上调用进行的调用） 调用比较质量值。</span><span class="sxs-lookup"><span data-stu-id="2796b-108">[Media Quality Comparison Report in Skype for Business Server 2015](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="2796b-109">[服务器性能报告在 Skype 业务服务器 2015](server-performance.md)列出遇到的大多数问题，基于这种主要的质量指标作为降低、 数据包丢失及抖动的测量值的服务器。</span><span class="sxs-lookup"><span data-stu-id="2796b-109">[Server Performance Report in Skype for Business Server 2015](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="2796b-110">[在 Skype 业务服务器 2015年报告位置](location-report.md)提供网络位置，并调用在每个位置发生的媒体质量的摘要的列表。</span><span class="sxs-lookup"><span data-stu-id="2796b-110">[Location Report in Skype for Business Server 2015](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="2796b-111">对于本报告而言，位置基于 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="2796b-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="2796b-112">[设备报告在 Skype 业务服务器 2015](device-report.md)提供了对企业语音呼叫和其使用的设备的摘要设备包括平均媒体质量的调用。</span><span class="sxs-lookup"><span data-stu-id="2796b-112">[Device Report in Skype for Business Server 2015](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="2796b-113">[调用在 Skype 业务服务器 2015年列表报告](call-list-report-0.md)提供有关电话的拨打或接听您的组织中的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="2796b-113">[Call List Report in Skype for Business Server 2015](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="2796b-114">[调用在 Skype 业务服务器 2015年详细信息报告](call-detail-report.md)提供有关从或在您的组织内接收到的电话联络的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="2796b-114">[Call Detail Report in Skype for Business Server 2015](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="2796b-115">[服务器的媒体质量趋势报告在 Skype 业务服务器 2015](server-media-quality-trend-report.md)为提供一种以图形方式比较上体验质量指标，如电话的数量、 较差的呼叫百分比、 数据包丢失和抖动最多五个服务器。</span><span class="sxs-lookup"><span data-stu-id="2796b-115">[Server Media Quality Trend Report in Skype for Business Server 2015](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="2796b-116">[媒体质量指标分发报告在 Skype 业务服务器 2015](media-quality-metrics-distribution-report.md)提供该图显示体验质量指标如抖动或数据包丢失的分布值。</span><span class="sxs-lookup"><span data-stu-id="2796b-116">[The Media Quality Metrics Distribution Report in Skype for Business Server 2015](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="2796b-117">[在 Skype 业务服务器 2015年的位置趋势报告](location-trend-report.md)提供网络位置的呼叫质量趋势的信息。</span><span class="sxs-lookup"><span data-stu-id="2796b-117">[Location Trend Report in Skype for Business Server 2015](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

