---
title: Skype for Business Server 中的位置趋势报告
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
ms.assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
description: 摘要：了解 Skype for Business Server 中的位置趋势报告。
ms.openlocfilehash: cde443757da903daa261d12fd34f50a9288870d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827882"
---
# <a name="location-trend-report-in-skype-for-business-server"></a>Skype for Business Server 中的位置趋势报告
 
**摘要：** 了解 Skype for Business Server 中的位置趋势报告。
  
位置趋势报告提供网络位置的呼叫质量趋势信息。
  
## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，位置趋势报告使您能够按访问类型（即内部访问与外部访问）或有线/无线网络连接等条件来筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日或周对呼叫进行分组。
  
下表列出了可用于位置趋势报告的筛选器。 
  
**位置趋势报告筛选器**

|**名称**|**说明**|
|:-----|:-----|
|**From** <br/> |时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|"自" <br/> |时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**Interval** <br/> | 时间间隔。选择下列选项之一： <br/>  每小时（最多可显示 25 个小时） <br/>  每天（最多可显示 31 天） <br/>  每周（最多可显示 12 周） <br/>  如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/1/2011、结束日期为 9/28/2011、间隔为“每天”，则显示从 8/1/2011 12:00 AM 到 9/1/2011 12:00 AM 这些天的数据（即总共 31 天的数据）。 <br/> |
|**访问类型** <br/> | 指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一： <br/>  [全部] <br/>  内部 <br/>  外部 <br/> |
|**网络类型** <br/> | 指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一： <br/>  [全部] <br/>  有线 <br/>  无线 <br/> |
|**VPN** <br/> | 指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一： <br/>  [全部] <br/>  VPN <br/>  非 VPN <br/> |
   

