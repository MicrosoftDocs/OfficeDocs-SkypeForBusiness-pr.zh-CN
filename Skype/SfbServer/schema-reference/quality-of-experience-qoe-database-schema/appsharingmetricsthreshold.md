---
title: AppSharingMetricsThreshold 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold 表包含用于应用程序共享的用户体验质量指标的最佳和可接受值。 使用这些阈值来确定是否应为差分类应用程序共享体验。
ms.openlocfilehash: bddad99803ab6683985b0f44ed5df509b84344f3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877040"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold 表
 
AppSharingMetricsThreshold 表包含用于应用程序共享的用户体验质量指标的最佳和可接受值。 使用这些阈值来确定是否应为差分类应用程序共享体验。
  
此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |发出的呼叫的类型。  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||应用程序共享的最佳的带宽限制。 默认值为 1000000。  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||应用程序共享的可接受的带宽限制。 默认值为 500000。  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||最佳百分比进行分类应用程序共享的质量"损坏"图块速率。 此值是从没有到达查看共享内容的百分比。 可能会丢弃 （或扰乱了） 内容时共享者放弃从图形源的图块数为单位或 ASMCU 平铺放弃平铺从共享者分别。 默认值为 11%。  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||可接受的百分比进行分类应用程序共享的质量"损坏"图块速率。 此值是从没有到达查看共享内容的百分比。 可能会丢弃 （或扰乱了） 内容时共享者放弃从图形源的图块数为单位或 ASMCU 平铺放弃平铺从共享者分别。 默认值为 36%。  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不使用此列。  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||应用程序共享所涉及的两个媒体终结点之间的相对单向延迟的的最佳值。 这是单跃点延迟度量。 默认值为 1.0 秒。  <br/> 列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||应用程序共享所涉及的两个媒体终结点之间的相对单向延迟的的最佳值。 这是单跃点延迟度量。 默认值为 1.75 秒。  <br/> 列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||通过查看会话的持续时间处理 AS 会议服务器中的延迟的平均 RDP 图块的最佳值。 延迟时之间的时间差异 （共享者或具体取决于该方案的 MCU） 的服务器上启动框架进行编码和同一启动框架进行解码上查看器。  <br/> 高平均值反映了查看体验中的延迟较长。 过载的会议服务器可能会遇到更长的平均延迟。 默认值为 200 毫秒。  <br/> 列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||可接受的平均处理通过查看会话的持续时间延迟以 AS 会议服务器的 RDP 图块的值。 延迟时之间的时间差异 （共享者或具体取决于该方案的 MCU） 的服务器上启动框架进行编码和同一启动框架进行解码上查看器。  <br/> 高平均值反映了查看体验中的延迟较长。 过载的会议服务器可能会遇到更长的平均延迟。 默认值为 200 毫秒。  <br/> 列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

