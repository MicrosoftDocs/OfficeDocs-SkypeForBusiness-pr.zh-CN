---
title: 服务器性能报告Skype for Business Server
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
ms.assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
description: 摘要：了解 Skype for Business Server 中的服务器性能报告。
ms.openlocfilehash: 21bb6dbc462633d3d5620d63389b72a9b4d49a07
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396534"
---
# <a name="server-performance-report-in-skype-for-business-server"></a>服务器性能报告Skype for Business Server
 
**摘要：** 了解 Skype for Business Server 中的服务器性能报告。
  
服务器性能报告提供了遇到质量欠佳Skype for Business Server率最高的服务器的列表。 该报告按服务器类型对服务器进行分解，并报告以下类型的单独统计信息：
  
- 中介服务器
    
- A/V 会议服务器
    
- A/V 边缘服务器
    
- 网关（中介服务器）
    
- 网关 (中介服务器旁路) 
    
- 视频 (包括 A/V 会议服务器和 A/V 边缘服务器的视频) 
    
- 应用程序共享 (包括 A/V 会议服务器和 A/V 边缘服务器的应用程序共享) 
    
需要注意的是，此报告中显示的排名是相对排名。 例如，假设性能最差的服务器在 1，000 个拨打的呼叫中拥有一个质量欠佳的呼叫。 这是 0.1% 的可接受百分比。 但是，如果这是性能最差的服务器， (也就是说，如果所有其他服务器的通话百分比都低于 .1%) ，那么该服务器仍将出现在"服务器性能报告"中。
  
## <a name="accessing-the-server-performance-report"></a>访问服务器性能报告

服务器性能报告从监控报告主页访问。 通过单击以下任一指标[，Skype for Business Server](call-list-report-0.md)中深入到呼叫列表报告：
  
- 呼叫量
    
- 质量欠佳的呼叫百分比
    
此外，可以通过单击以下指标向下钻取到服务器媒体质量趋势报告：
  
- 趋势
    
## <a name="making-the-best-use-of-the-server-performance-report"></a>充分利用服务器性能报告

服务器性能报告提供了多种筛选数据的方法;例如，可以筛选从有线连接进行的网络类型 (呼叫与从无线连接) 和从防火墙内进行的访问类型 (呼叫与从防火墙) 外部拨打的呼叫。 在查看服务器性能报告以使用这些筛选器时，这是一个好主意。 例如，假设有一个中介服务器，其质量欠佳的呼叫百分比为 3.24%。 如果您仅查看无线呼叫，则同一台服务器的较差呼叫百分比可能接近 20%。 这意味着服务器在无线呼叫方面遇到困难，因为服务器没有遇到有线呼叫问题，这一问题被部分遮盖。
  
## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。 例如，服务器性能报告允许您执行如下操作：按服务器类型或按网络类型（即有线或无线 (）筛选返回) 。 您还可以选择数据的分组方式。 在这种情况下，将按小时、日、周或月对数据进行分组。
  
下表列出了可用于服务器性能报告的筛选器。
  
**服务器性能报告筛选器**

|**名称**|**说明**|
|:-----|:-----|
|**From** <br/> |时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**To** <br/> |时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**服务器类型** <br/> |指示应报告其性能的服务器的类型。 选择下列选项之一：  <br/> [All]中介服务器 A/V 会议服务器 A/V 边缘服务器 |
|**前 N 个** <br/> |指示基于每个类别中 (质量欠佳的呼叫百分比) 服务器的数量。 例如，如果选择 **5** ，则显示五个性能最差的服务器。 选择下列选项之一： <br/> [All] 5 10 |
|**访问类型** <br/> |指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：  <br/> [All]内部外部 |
|**网络类型** <br/> |指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：  <br/> [All]有线无线 |
|**VPN** <br/> |指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：  <br/> [All]VPN 非 VPN |
   
## <a name="metrics"></a>度量标准

下表列出了服务器性能报告中提供的信息。
  
**服务器性能报告指标：音频呼叫摘要**

|**名称**|**可排序**|**说明**|
|:-----|:-----|:-----|
|**Server** <br/> |否  <br/> |服务器的名称/IP 地址。  <br/> |
|**呼叫量** <br/> |否  <br/> |已进行呼叫的总数。  <br/> |
|**质量欠佳的呼叫百分比** <br/> |否  <br/> |归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。  <br/> |
|**来回行程(毫秒)** <br/> |是  <br/> |实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**性能降低(MOS)** <br/> |是  <br/> |呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。 性能降低值的范围介于 0.0 和 5.0 之间。 该值小于或等于 0.5 表示可接受的性能降低。 过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。 在Skype for Business Server中，监控服务器使用一组算法来预测用户对呼叫的评分。  <br/> 高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。  <br/> |
|**数据包丢失** <br/> |是  <br/> |RTP 实时传输协议和数据包 (的平均) 率。  (当 RTP 数据包（一种用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时发生数据包丢失。) 高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。 数据包丢失通常导致音频失真或丢失。  <br/> |
|**抖动(毫秒)** <br/> |是  <br/> |在 RTP 数据包到达之间检查到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。  <br/> |
|**修复程序隐藏比率** <br/> |是  <br/> |隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。  <br/> |
|**修复程序拉伸比率** <br/> |是  <br/> |拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。  <br/> |
|**修复程序压缩比率** <br/> |是  <br/> |压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。  <br/> |
   
**服务器性能报告指标：视频呼叫摘要**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**呼叫类型/终结点类型** <br/> |否  <br/> | 当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括： <br/>  UC 对等呼叫 <br/>  UC 会议会话 <br/>  PSTN 会议会话 <br/>  PSTN 呼叫: 媒体旁路 <br/>  PSTN 呼叫(无旁路): UC 线路 <br/>  PSTN 呼叫(无旁路): 网关线路 <br/>  其他呼叫类型 <br/> |
|**呼叫量** <br/> |否  <br/> |每个呼叫类型的呼叫总数。  <br/> |
|**质量欠佳的呼叫百分比** <br/> |否  <br/> |归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。  <br/> |
|**呼叫量(无线呼叫)** <br/> |否  <br/> |使用了无线连接的呼叫的总数。  <br/> |
|**呼叫量(VPN 呼叫)** <br/> |否  <br/> |使用了 VPN 连接的呼叫的总数。  <br/> |
|**呼叫量(外部呼叫)** <br/> |否  <br/> |使用了外部连接（即内部网络外部的连接）的呼叫的总数。  <br/> |
|**平均比特率(Kb/s)** <br/> |否  <br/> |平均视频比特率 (Kb/s)。  <br/> |
|**低比特率百分比** <br/> |否  <br/> |比特率较低的呼叫的百分比。  <br/> |
|**出站数据包丢失** <br/> |否  <br/> |出站数据包的实时传输协议 (RTP) 数据包丢失率。  (当 RTP 数据包（一种用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时发生数据包丢失。) 高丢失率通常是由拥塞造成的;带宽不足;无线拥塞或干扰;或媒体服务器超载。 数据包丢失通常导致音频失真或丢失。  <br/> |
|**冻结帧百分比** <br/> |否  <br/> |"冻结"帧的百分比。 在一个冻结帧中，视频将停止前进，而呼叫的音频部分将继续。  <br/> |
|**出站平均帧速率** <br/> |否  <br/> |呼叫期间的出站传输的平均帧速率。  <br/> |
|**入站平均帧速率** <br/> |否  <br/> |呼叫期间的入站传输的平均帧速率。  <br/> |
|**入站低帧速率(%)** <br/> |否  <br/> |传入视频的比特率较低的呼叫的百分比。  <br/> |
|**客户端健康状态百分比** <br/> ||指示呼叫期间客户端设备的相对健康状态。  <br/> |
   
**服务器性能报告指标：应用程序共享呼叫摘要**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**呼叫类型/终结点类型** <br/> |否  <br/> | 当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括： <br/>  UC 对等呼叫 <br/>  UC 会议会话 <br/>  PSTN 会议会话 <br/>  PSTN 呼叫: 媒体旁路 <br/>  PSTN 呼叫(无旁路): UC 线路 <br/>  PSTN 呼叫(无旁路): 网关线路 <br/>  其他呼叫类型 <br/> |
|**呼叫量** <br/> |否  <br/> |每个呼叫类型的呼叫总数。  <br/> |
|**质量欠佳的呼叫百分比** <br/> |否  <br/> |归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。  <br/> |
|**呼叫量(无线呼叫)** <br/> |否  <br/> |使用了无线连接的呼叫的总数。  <br/> |
|**呼叫量(VPN 呼叫)** <br/> |否  <br/> |使用了 VPN 连接的呼叫的总数。  <br/> |
|**呼叫量(外部呼叫)** <br/> |否  <br/> |使用了外部连接（即内部网络外部的连接）的呼叫的总数。  <br/> |
|**抖动(毫秒)** <br/> |否  <br/> |在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。  <br/> |
|**相对单向平均值** <br/> |否  <br/> |两个媒体终结点之间的平均相对单向延迟。这是单跃点延迟度量。  <br/> |
|**平均 RDP 图块处理延迟** <br/> |否  <br/> |查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟。此指标不涉及网络延迟。高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。  <br/> |
|**总损坏图块百分比** <br/> |否  <br/> |已损坏 RDP 图块的总百分比。  <br/> |
   

