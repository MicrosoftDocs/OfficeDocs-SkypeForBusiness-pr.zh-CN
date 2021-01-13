---
title: Skype for Business Server 中的媒体质量诊断报告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: 摘要：了解 Skype for Business Server 中的媒体质量诊断报告。
ms.openlocfilehash: a00084605941af80435dd5da73efbfea89a6272f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827832"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="547c1-103">Skype for Business Server 中的媒体质量诊断报告</span><span class="sxs-lookup"><span data-stu-id="547c1-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="547c1-104">**摘要：** 了解 Skype for Business Server 中的媒体质量诊断报告。</span><span class="sxs-lookup"><span data-stu-id="547c1-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="547c1-105">媒体质量诊断报告提供有关呼叫质量的信息以及失败的呼叫的诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="547c1-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="547c1-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="547c1-106">In this section</span></span>

- <span data-ttu-id="547c1-107">[Skype for Business Server 中的媒体质量摘要报告](summary.md) 提供不同终结点类型的整体质量数据，包括 企业语音 对等呼叫、企业语音 电话会议和至少部分依赖公用电话交换网 (PSTN) 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="547c1-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="547c1-108">[Skype for Business Server 中的媒体质量比较报告](comparison.md) 提供不同类型的音频呼叫的呼叫质量值的比较 (例如，通过无线网络拨打的呼叫与通过有线连接网络) 。</span><span class="sxs-lookup"><span data-stu-id="547c1-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="547c1-109">[Skype for Business Server 中的服务器性能报告](server-performance.md) 根据诸如降级、数据包丢失和抖动等关键质量指标的度量，列出遇到最多问题的服务器。</span><span class="sxs-lookup"><span data-stu-id="547c1-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="547c1-110">[Skype for Business Server 中的位置报告](location-report.md) 提供网络位置的列表以及每个位置发生的呼叫的媒体质量摘要。</span><span class="sxs-lookup"><span data-stu-id="547c1-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="547c1-111">对于此报告，位置基于 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="547c1-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="547c1-112">[Skype for Business Server 中的设备报告](device-report.md) 提供用于呼叫的设备的摘要企业语音包括按设备表示的呼叫的平均媒体质量。</span><span class="sxs-lookup"><span data-stu-id="547c1-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="547c1-113">[Skype for Business Server 中的呼叫列表报告](call-list-report-0.md) 提供有关在组织中拨打或接听的电话呼叫的详细信息。</span><span class="sxs-lookup"><span data-stu-id="547c1-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="547c1-114">[Skype for Business Server 中的呼叫详细信息报告](call-detail-report.md) 提供有关从组织内部拨打或接听的电话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="547c1-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="547c1-115">[Skype for Business Server 中的服务器媒体质量趋势报告](server-media-quality-trend-report.md) 提供了一种在用户体验质量指标（如呼叫量、质量欠佳的呼叫百分比、数据包丢失和抖动）上以图形方式比较最多五台服务器的方法。</span><span class="sxs-lookup"><span data-stu-id="547c1-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="547c1-116">[Skype for Business Server 中的媒体质量指标分布报告](media-quality-metrics-distribution-report.md) 提供显示用户体验质量指标（如抖动或数据包丢失）的分布值的图形。</span><span class="sxs-lookup"><span data-stu-id="547c1-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="547c1-117">[Skype for Business Server 中的位置趋势报告](location-trend-report.md) 提供网络位置的呼叫质量趋势信息。</span><span class="sxs-lookup"><span data-stu-id="547c1-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

