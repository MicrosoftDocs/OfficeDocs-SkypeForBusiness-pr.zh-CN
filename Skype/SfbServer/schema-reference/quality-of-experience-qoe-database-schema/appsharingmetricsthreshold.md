---
title: AppSharingMetricsThreshold 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold 表包含使用应用程序共享的体验质量指标的最佳状态，并且可接受值。 这些阈值用于确定是否应归应用程序共享体验一样差。
ms.openlocfilehash: 1ccf60fc9668d2ad2943929affad6fd4a078c789
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold 表
 
AppSharingMetricsThreshold 表包含使用应用程序共享的体验质量指标的最佳状态，并且可接受值。 这些阈值用于确定是否应归应用程序共享体验一样差。
  
在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |被放置的呼叫类型。  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||应用程序共享的最佳带宽限制。 默认值为 1000000。  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||应用程序共享的可接受的带宽限制。 默认值为 500000。  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||对于"受损"的图块，进行分类应用程序共享的质量最优的百分比率。 此值是从没有到达查看共享内容的百分比。 可能会丢弃 （或破坏） 内容共享者放弃从图形源的拼贴或 ASMCU 平铺放弃时平铺从共享资源分别。 默认值为 11%。  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||对于"受损"的图块，进行分类应用程序共享的质量可接受的百分比率。 此值是从没有到达查看共享内容的百分比。 可能会丢弃 （或破坏） 内容共享者放弃从图形源的拼贴或 ASMCU 平铺放弃时平铺从共享资源分别。 默认值是 36%。  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||在 Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||在 Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||在 Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||在 Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||在 Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||在 Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||所涉及的应用程序共享媒体两个终结点之间的相对单向延迟的最佳值。 这是单跃点延迟度量。 默认值为 1.0 秒。  <br/> 在 Microsoft Lync Server 2013 引入了列。  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||所涉及的应用程序共享媒体两个终结点之间的相对单向延迟的最佳值。 这是单跃点延迟度量。 默认值为 1.75 秒。  <br/> 在 Microsoft Lync Server 2013 引入了列。  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||查看会话的持续时间内处理中 AS 会议服务器的滞后时间的平均 RDP 平铺的最佳值。 滞后时间时之间的时间差别开始帧进行编码 （共享或根据具体情况的 MCU） 的服务器上，启动同一帧解码播放器上。  <br/> 高平均值反映了查看体验中的延迟较长。 过载的会议服务器可能会遇到更长的平均延迟。 默认值为 200 毫秒。  <br/> 在 Microsoft Lync Server 2013 引入了列。  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||查看会话的持续时间内处理中 AS 会议服务器的滞后时间平均的 RDP 拼贴的可接受的值。 滞后时间时之间的时间差别开始帧进行编码 （共享或根据具体情况的 MCU） 的服务器上，启动同一帧解码播放器上。  <br/> 高平均值反映了查看体验中的延迟较长。 过载的会议服务器可能会遇到更长的平均延迟。 默认值为 200 毫秒。  <br/> 在 Microsoft Lync Server 2013 引入了列。  <br/> |
   

