---
title: Skype for Business Server 中的媒体质量诊断报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: 摘要：了解 Skype for Business 服务器中的媒体质量诊断报告。
ms.openlocfilehash: e02ea51681b31b524bf87005e7c4b4fcf48bef62
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817861"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="6ceb2-103">Skype for Business Server 中的媒体质量诊断报告</span><span class="sxs-lookup"><span data-stu-id="6ceb2-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="6ceb2-104">**摘要：** 了解 Skype for Business 服务器中的媒体质量诊断报告。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="6ceb2-105">媒体质量诊断报告提供有关呼叫质量的信息以及失败的呼叫的诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="6ceb2-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="6ceb2-106">In this section</span></span>

- <span data-ttu-id="6ceb2-107">[Skype For Business 服务器中的 "媒体质量摘要" 报表](summary.md)提供不同终结点类型的总体质量数据，包括企业语音对等呼叫、企业语音会议呼叫以及在公共交换电话网络（PSTN）上至少部分的通话。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="6ceb2-108">[Skype For Business Server 中的媒体质量比较报告](comparison.md)比较不同类型的音频呼叫的通话质量值（例如，通过无线网络进行的通话与通过有线连接拨打的电话）。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="6ceb2-109">[Skype For Business 服务器中的服务器性能报告](server-performance.md)基于性能下降、数据包丢失和抖动等关键质量指标的度量，列出遇到最多问题的服务器。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="6ceb2-110">[Skype For Business 服务器中的位置报告](location-report.md)提供网络位置列表，以及每个位置上出现的通话的媒体质量摘要。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="6ceb2-111">出于此报告的目的，位置基于 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="6ceb2-112">[Skype For Business 服务器中的设备报告](device-report.md)提供用于企业语音通话的设备摘要，其中包括设备通话的平均媒体质量。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="6ceb2-113">[Skype For Business 服务器中的通话清单报告](call-list-report-0.md)提供有关在您的组织内拨打或接听电话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="6ceb2-114">[Skype For Business 服务器中的呼叫详细报告](call-detail-report.md)提供有关在您的组织内拨打或接收电话的电话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="6ceb2-115">[Skype For Business server 中的服务器媒体质量趋势报表](server-media-quality-trend-report.md)提供了一种以图形方式比较多达五台服务器的体验，如呼叫音量、通话百分比差、数据包丢失和抖动等。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="6ceb2-116">[Skype For Business 服务器中的媒体质量指标分布报告](media-quality-metrics-distribution-report.md)提供显示经验指标（如抖动或数据包丢失）的分布值的图表。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="6ceb2-117">[Skype For Business 服务器中的位置趋势报告](location-trend-report.md)提供网络位置的通话质量趋势信息。</span><span class="sxs-lookup"><span data-stu-id="6ceb2-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

