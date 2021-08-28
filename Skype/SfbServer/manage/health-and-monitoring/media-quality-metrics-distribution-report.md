---
title: 媒体质量指标分布报告Skype for Business Server
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
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 摘要：了解 Skype for Business Server 中的媒体质量指标分布Skype for Business Server。
ms.openlocfilehash: 0ba1bfadee22d731a6ef6c523ba22261a8f22202
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606181"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>媒体质量指标分布报告Skype for Business Server 
 
**摘要：** 了解 Skype for Business Server 中的媒体质量指标分布Skype for Business Server。
  
通过媒体质量指标分布报告，你可以查看显示用户体验质量指标（如抖动或数据包丢失）的分布值的图形。 例如，假设用户总共拨打了 10 个电话;这 10 个呼叫报告以下往返时间：
  
|**呼叫号码**|**往返时间 (毫秒)**|
|:-----|:-----|
|1   <br/> |50  <br/> |
|2   <br/> |50  <br/> |
|3   <br/> |50  <br/> |
|4   <br/> |50  <br/> |
|5   <br/> |50  <br/> |
|6   <br/> |50  <br/> |
|7   <br/> |50  <br/> |
|8   <br/> |4550  <br/> |
|9   <br/> |50  <br/> |
|10   <br/> |50  <br/> |
   
这些往返时间的平均时间为 500 毫秒 (5000 除以 10) 。 500 毫秒是一个非常大的往返时间;因此，你可能会认为网络拥塞是一个严重问题。  (往返时间长通常是网络过载的结果。) 
  
当然，实际上，90% 的呼叫具有出色的往返时间;您只有一个扭曲总体结果的错误调用。 如果您只查看平均往返时间，您可能会得出一个非常错误的结果。
  
媒体质量指标分布报告通过向用户显示指定指标（如往返时间 (的图形分布，帮助您避免做出错误) 。 这些图形可帮助你清楚地了解你拥有九个非常好的呼叫和一个非常坏的呼叫。 不可否认，您可能仍希望进一步调查该呼叫;但是，10 次呼叫中的 9 次非常好，表明没有理由对网络进行重大更改，至少此时没有更改。
  
## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。 下表列出了可用于媒体质量指标分布报告的筛选器。
  
**媒体质量指标分布报告筛选器**

|**名称**|**说明**|
|:-----|:-----|
|**From** <br/> |时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**To** <br/> |时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**x 轴中的最小值** <br/> |要显示在图形 X 轴上的最低值。  <br/> |
|**x 轴中的最大值** <br/> |要显示在图形 X 轴上的最高值。  <br/> |
|**访问类型** <br/> | 指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一： <br/>  [All] <br/>  内部 <br/>  外部 <br/> |
|**VPN** <br/> | 指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一： <br/>  [All] <br/>  VPN <br/>  非 VPN <br/> |
|**网络类型** <br/> | 指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一： <br/>  [All] <br/>  有线 <br/>  无线 <br/> |
   

