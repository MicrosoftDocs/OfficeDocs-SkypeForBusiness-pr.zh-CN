---
title: Skype 业务服务器中的媒体质量诊断报告
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: 摘要： 了解业务服务器的媒体质量诊断报告中 Skype。
ms.openlocfilehash: a7861d60e9108dcf599c5cecee9a678248715e44
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889187"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="240f6-103">Skype 业务服务器中的媒体质量诊断报告</span><span class="sxs-lookup"><span data-stu-id="240f6-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="240f6-104">**摘要：** 了解业务服务器媒体质量诊断报告中 Skype。</span><span class="sxs-lookup"><span data-stu-id="240f6-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="240f6-105">媒体质量诊断报告提供有关呼叫质量的信息以及失败的呼叫的诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="240f6-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="240f6-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="240f6-106">In this section</span></span>

- <span data-ttu-id="240f6-107">[Skype 业务服务器中的媒体质量摘要报告](summary.md)提供总体质量数据对于不同的终结点类型，包括企业语音对等呼叫、 企业语音会议呼叫和依赖，呼叫至少部分，在公共公用电话交换网 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="240f6-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="240f6-108">[Skype 业务服务器中的媒体质量比较报告](comparison.md)提供的不同类型的音频呼叫 （例如，通过无线网络与有线连接进行呼叫的呼叫） 的呼叫的比较质量值。</span><span class="sxs-lookup"><span data-stu-id="240f6-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="240f6-109">[Skype 业务服务器中的服务器性能报告](server-performance.md)列出遇到最多问题，测量诸如降级、 数据包丢失和抖动的关键质量指标的服务器。</span><span class="sxs-lookup"><span data-stu-id="240f6-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="240f6-110">[Skype 业务服务器中的位置报告](location-report.md)提供网络位置和在每个位置发生的呼叫的媒体质量摘要的列表。</span><span class="sxs-lookup"><span data-stu-id="240f6-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="240f6-111">对于此报告的目的，基于 IP 子网位置。</span><span class="sxs-lookup"><span data-stu-id="240f6-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="240f6-112">[Skype 业务服务器中的设备报告](device-report.md)提供的用于企业语音呼叫，它的设备的摘要包含按设备列出的呼叫的平均媒体质量。</span><span class="sxs-lookup"><span data-stu-id="240f6-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="240f6-113">[呼叫列表报告中的业务服务器 Skype](call-list-report-0.md)提供有关组织中拨打或接收的电话呼叫的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="240f6-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="240f6-114">[呼叫详情报告中的业务服务器 Skype](call-detail-report.md)提供有关在中您的组织中拨打或接收的电话呼叫的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="240f6-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="240f6-115">[Skype 业务服务器中的服务器媒体质量趋势报告](server-media-quality-trend-report.md)提供一种方法，以图形方式比较最多五个服务器上呼叫量、 质量欠佳的呼叫百分比、 数据包丢失和抖动等的用户体验质量指标。</span><span class="sxs-lookup"><span data-stu-id="240f6-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="240f6-116">[在 Skype 业务服务器媒体质量标准分发报告](media-quality-metrics-distribution-report.md)提供该图显示如抖动或数据包丢失的用户体验质量指标的通讯组值。</span><span class="sxs-lookup"><span data-stu-id="240f6-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="240f6-117">[Skype 业务服务器中的位置趋势报告](location-trend-report.md)提供网络位置的呼叫质量趋势信息。</span><span class="sxs-lookup"><span data-stu-id="240f6-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

