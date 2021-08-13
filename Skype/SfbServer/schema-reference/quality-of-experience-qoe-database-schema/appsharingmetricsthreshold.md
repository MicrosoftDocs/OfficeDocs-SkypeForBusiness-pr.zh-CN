---
title: AppSharingMetricsThreshold 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold 表包含用于应用程序共享的用户体验质量指标的最佳值和可接受的值。这些阈值用于确定是否应将应用程序共享体验归类为质量欠佳。
ms.openlocfilehash: c3ee6c9742935cf7fc076c809a7aa3e09706391a58a6b1cc8025f5c5044dc5d5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344591"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold 表
 
AppSharingMetricsThreshold 表包含用于应用程序共享的用户体验质量指标的最佳值和可接受的值。这些阈值用于确定是否应将应用程序共享体验归类为质量欠佳。
  
此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |主  <br/> |已发出的呼叫的类型。  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||应用程序共享的最佳带宽限制。默认值为 1000000。  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||应用程序共享的可接受带宽限制。默认值为 500000。  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal (5，2)   <br/> ||用于对应用程序共享质量进行分类的"损坏"图块的最佳百分比。 此值是共享方中未到达查看方的内容的百分比。 当共享方丢弃图形源中的图块或 ASMCU 图块丢弃共享方中的图块时，内容可能被丢弃（或被损坏）。 默认值为 11%。  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal (5，2)   <br/> ||用于对应用程序共享质量进行分类的"损坏"图块的可接受百分比。 此值是共享方中未到达查看方的内容的百分比。 当共享方丢弃图形源中的图块或 ASMCU 图块丢弃共享方中的图块时，内容可能被丢弃（或被损坏）。 默认值为 36%。  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||此列不用于 Microsoft Lync Server 2013。  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||此列不用于 Microsoft Lync Server 2013。  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||此列不用于 Microsoft Lync Server 2013。  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||此列不用于 Microsoft Lync Server 2013。  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||此列不用于 Microsoft Lync Server 2013。  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||此列不用于 Microsoft Lync Server 2013。  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。这是单跃点延迟度量。默认值为 1.0 秒。  <br/> 该列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。这是单跃点延迟度量。默认值为 1.75 秒。  <br/> 该列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟的最佳值。 延迟是在服务器 (共享者或 MCU 上对"开始帧"进行编码（具体取决于方案) 且在查看器上解码同一个"开始帧"时）之间的时间差。  <br/> 高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。默认值为 200 毫秒。  <br/> 该列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟的可接受值。 延迟是在服务器 (共享者或 MCU 上对"开始帧"进行编码（具体取决于方案) 且在查看器上解码同一个"开始帧"时）之间的时间差。  <br/> 高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。默认值为 200 毫秒。  <br/> 该列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

