---
title: 呼叫诊断摘要报告Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 摘要：了解呼叫诊断摘要报告Skype for Business Server。
ms.openlocfilehash: b3da3315566db66876329ab257ff6fa8d78f81b3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585076"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>呼叫诊断摘要报告Skype for Business Server
 
**摘要：** 了解呼叫诊断摘要报告在 Skype for Business Server。
  
呼叫诊断摘要报告提供失败的点对点会话和会议会话的整体情况。该报告显示了两种类型的会话的整体故障率，并按以下会话形式类型进一步为故障信息分类：
  
- 即时消息
    
- 应用程序共享
    
- 文件传输
    
- 音频
    
- 视频
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>访问呼叫诊断摘要报告

呼叫诊断摘要报告是从监控报告主页访问的。 从呼叫诊断摘要报告中，可以通过单击报告的点对点会话摘要部分下的故障率指标来访问[Skype for Business Server](peer-to-peer-activity-diagnostic-report.md)中的点对点活动诊断报告。 您还可以通过单击以下任[](conference-diagnostic-report.md)一会议Skype for Business Server访问会议诊断报告：
  
- 总体会话故障率
    
- 焦点故障率
    
- MCU 故障率
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>充分利用呼叫诊断摘要报告

呼叫诊断摘要报告包括比较呼叫摘要中使用的各种形式的失败率Skype for Business Server。 这些图中的列实际上是热链接;例如，如果单击对等会话的"即时消息"列，您将深入到[Skype for Business Server](peer-to-peer-activity-diagnostic-report.md)中的对等活动诊断报告的实例，该报告提供有关呼叫诊断摘要报告中包括的所有即时消息会话的其他详细信息。
  
## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，呼叫诊断摘要报告允许您依据会话中使用的注册器池或边缘服务器等条件进行筛选。您还可以选择数据的分组方式。在此示例中，将按小时、天、周或月对呼叫进行分组。
  
下表列出了可用于呼叫诊断摘要报告的筛选器。
  
**呼叫诊断摘要报告筛选器**

|**名称**|**说明**|
|:-----|:-----|
|**From** <br/> |时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**To** <br/> |时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**Interval** <br/> | 时间间隔。选择下列选项之一： <br/>  每小时（最多可显示 25 个小时） <br/>  每天（最多可显示 31 天） <br/>  每周（最多可显示 12 周） <br/>  每月（最多可显示 12 个月） <br/>  如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。 例如，如果您选择开始日期为 2015/7/7 和结束日期为 2015/2/28 的"每天"间隔， 显示 2015 年 8 月 7 日上午 12：00 到 2015 年 9 月 7 日上午 12：00 (即总共 31 天的数据) 。 <br/> |
|**Pool** <br/> |注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>点对点会话的指标

下表列出了点对点会话（即，只涉及两个参与者的会话）的呼叫诊断摘要报告中提供的信息。
  
**点对点会话的指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**会话总数** <br/> |否  <br/> |发起的点对点会话总数。  <br/> |
|**故障率** <br/> |否  <br/> |失败的点对点会话百分比。单击此项时，报告将显示点对点活动诊断报告，其中显示有关失败的点对点会话的详细信息。  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>会议会话的指标

下表列出了会议会话（即，涉及三个或更多参与者的会话）的呼叫诊断报告中提供的信息。
  
**会议会话的指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**会议总数** <br/> |否  <br/> |举行的会议总数。  <br/> |
|**会议会话总数** <br/> |否  <br/> |发起的会议会话总数。  <br/> |
|**总体会话故障率** <br/> |否  <br/> |失败的会议会话百分比。  <br/> |
|**焦点会话** <br/> |否  <br/> |失败的基于会议状态中心的会议会话总数。  <br/> |
|**焦点故障率** <br/> |否  <br/> |失败的基于会议状态中心的会议会话百分比。  <br/> |
|**MCU 会话** <br/> |否  <br/> |失败的基于会议服务器（以前称为多点控制单元，简称 MCU）的会议总数。  <br/> |
|**MCU 故障率** <br/> |否  <br/> |失败的基于会议服务器（以前称为多点控制单元，简称 MCU）的会议百分比。  <br/> |
   

