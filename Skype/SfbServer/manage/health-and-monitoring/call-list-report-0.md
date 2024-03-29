---
title: 呼叫列表中的呼叫Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 摘要：了解呼叫列表中用于Skype for Business Server。
ms.openlocfilehash: 986e107c88210b8abedc44641ce2f13a1db315d8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388160"
---
# <a name="call-list-report-in-skype-for-business-server"></a>呼叫列表中的呼叫Skype for Business Server
 
**摘要：** 了解在呼叫列表中使用的呼叫Skype for Business Server。
  
呼叫列表报告提供了针对您组织中发出和接收的单个呼叫的用户体验质量 (QoE) 指标。 请注意，报告的实际指标将取决于您访问呼叫列表报告的方式。 例如，如果在 Skype for Business Server 中打开设备报告中的报告，[](device-report.md)你将看到诸如以下的指标，设备报告中也报告了这些指标：
  
- 呼叫者的麦克风
    
- 呼叫者的扬声器
    
- 被叫方的麦克风
    
- 被叫方的扬声器
    
- 语音切换时间比率 
    
但是，如果您从 [Skype for Business Server](location-report.md) 中的位置报告中打开呼叫列表报告，您将看不到其中任何指标;相反，您将看到类似以下的指标：
  
- 来回行程(毫秒)
    
- 性能降低(MOS)
    
- 数据包丢失
    
- 抖动(毫秒)
    
这些是在位置报告上报告的指标。但是，您始终能够从呼叫列表报告中单击“详细信息”指标来提供任何呼叫的完整 QoE 信息。
  
## <a name="accessing-the-call-list-report"></a>访问呼叫列表报告

可从以下任一报告访问呼叫列表报告：
  
- 通过[单击"呼叫量Skype for Business Server](location-report.md) (质量欠佳的呼叫百分比"指标，可单击"呼叫量"或"质量欠佳的呼叫百分比"指标) 
    
- 通过[单击呼叫量Skype for Business Server (](device-report.md)质量欠佳的呼叫百分比"指标，可单击"呼叫量"或"质量欠佳的呼叫百分比"指标) 
    
- 通过[单击呼叫量](summary.md)或质量欠佳的呼叫百分比指标Skype for Business Server (报告中的媒体质量摘要报告) 
    
- 通过[单击"呼叫量"](server-performance.md)或"质量欠佳的呼叫百分比"指标Skype for Business Server (中的服务器性能报告) 
    
从呼叫列表报告中，可以通过单击"详细信息"指标[Skype for Business Server报告中的](call-detail-report.md)呼叫详细信息报告。
  
## <a name="making-the-best-use-of-the-call-list-report"></a>最充分地利用呼叫列表报告

如果您记不住实际度量哪些呼叫列表报告指标（例如语音切换时间比率），请将鼠标指针悬停在指标标签的上方；这将显示一个工具提示，它为您简述了此指标。
  
## <a name="filters"></a>筛选器

无。您无法筛选呼叫列表报告。
  
## <a name="metrics"></a>度量标准

下表列出了呼叫列表报告中提供的有关每个呼叫的信息。
  
**呼叫列表报告指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**详细信息** <br/> |否  <br/> |单击此项时，报告将显示有关呼叫的其他信息。  <br/> |
|**Caller** <br/> |是  <br/> |发起呼叫的人的 SIP 地址。  <br/> |
|**被叫方** <br/> |是  <br/> |被呼叫的人的 SIP 地址。  <br/> |
|**开始时间** <br/> |是  <br/> |呼叫开始的日期和时间。  <br/> |
|**结束时间** <br/> |是  <br/> |呼叫结束的日期和时间。  <br/> |
|**呼叫者用户代理** <br/> |是  <br/> |发出呼叫的人的终结点使用的软件。  <br/> |
|**被叫方用户代理** <br/> |是  <br/> |被呼叫的人的终结点使用的软件。  <br/> |
|**来回行程(毫秒)** <br/> |是  <br/> |实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**性能降低(MOS)** <br/> |是  <br/> |呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。 性能降低值的范围介于 0.0 和 5.0 之间。 该值小于或等于 0.5 表示可接受的性能降低。 过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。 在Skype for Business Server，一组算法预测用户如何对呼叫进行评分。  <br/> 高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。  <br/> |
|**数据包丢失** <br/> |是  <br/> |平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。  <br/> |
|**抖动** <br/> |是  <br/> |在 RTP 数据包到达之间检查到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。  <br/> |
|**修复程序隐藏比率** <br/> |是  <br/> |隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。  <br/> |
|**修复程序拉伸比率** <br/> |是  <br/> |拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。  <br/> |
|**修复程序压缩比率** <br/> |是  <br/> |压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。  <br/> |
|**连接性** <br/> |是  <br/> | 无线通信链路的类型。通常，这是以下选项之一： <br/>  中继 <br/>  直接 <br/> |
   

