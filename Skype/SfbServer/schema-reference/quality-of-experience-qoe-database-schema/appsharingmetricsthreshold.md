---
title: AppSharingMetricsThreshold 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold 表包含与应用程序共享一起使用的体验质量指标的最佳值和可接受值。 这些阈值用于确定应用程序共享体验是否应归类为较差。
ms.openlocfilehash: 3639d9f2783b6433353f23d15e6ce063fb8ec49f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811380"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold 表
 
AppSharingMetricsThreshold 表包含与应用程序共享一起使用的体验质量指标的最佳值和可接受值。 这些阈值用于确定应用程序共享体验是否应归类为较差。
  
此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |所发出通话的类型。  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||应用程序共享的最佳带宽限制。 默认值为1000000。  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||应用程序共享的可接受带宽限制。 默认值为500000。  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |十进制（5，2）  <br/> ||用于对应用程序共享质量进行分类的 "损坏" 图块的最佳百分比费率。 此值表示来自共享者的未到达查看者的内容百分比。 当共享者丢弃来自图形源或 ASMCU 磁贴的磁贴时，可能会放弃内容（或损坏）。 默认值为11%。  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |十进制（5，2）  <br/> ||用于对应用程序共享质量进行分类的 "损坏" 图块的可接受百分比费率。 此值表示来自共享者的未到达查看者的内容百分比。 当共享者丢弃来自图形源或 ASMCU 磁贴的磁贴时，可能会放弃内容（或损坏）。 默认值为36%。  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。 这是单跃点延迟度量。 默认值为1.0 秒。  <br/> 在 Microsoft Lync Server 2013 中引入了该列。  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。 这是单跃点延迟度量。 默认值为1.75 秒。  <br/> 在 Microsoft Lync Server 2013 中引入了该列。  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||在查看会话期间作为会议服务器中的平均 RDP 磁贴处理延迟的最佳值。 滞后时间是在服务器上编码起始帧时的时间差（共享者或 MCU 取决于方案），并且在查看器上对同一开始帧进行解码。  <br/> 高平均值反映了查看体验中的延迟较长。 过载的会议服务器可能会遇到更长的平均延迟。 默认值为200ms。  <br/> 在 Microsoft Lync Server 2013 中引入了该列。  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||在查看会话期间作为会议服务器中的平均 RDP 磁贴处理延迟的可接受值。 滞后时间是在服务器上编码起始帧时的时间差（共享者或 MCU 取决于方案），并且在查看器上对同一开始帧进行解码。  <br/> 高平均值反映了查看体验中的延迟较长。 过载的会议服务器可能会遇到更长的平均延迟。 默认值为200ms。  <br/> 在 Microsoft Lync Server 2013 中引入了该列。  <br/> |
   

