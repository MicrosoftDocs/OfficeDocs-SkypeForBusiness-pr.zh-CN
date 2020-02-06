---
title: Skype for Business Server 中的对等 IM 报表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 摘要：了解 Skype for Business 服务器中的对等 IM 报表。
ms.openlocfilehash: 7775e7dc4a6fc3cd36283decd12971ac0e0f780a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817912"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Skype for Business Server 中的对等 IM 报表
 
**摘要：** 了解 Skype for Business 服务器中的对等 IM 报表。
  
对等 IM 报告提供了有关按池和身份验证类型分类的对等即时消息 (IM) 会话的趋势信息。该报告可以显示在指定时间段内（例如，每天或每小时）进行的会话总数或显示在该时间段内发送的即时消息总数。
  
## <a name="accessing-the-peer-to-peer-im-report"></a>访问对等 IM 报告

只有[在 Skype For Business Server 中打开对等活动摘要报告](peer-to-peer-activity-summary-report.md)，然后单击以下任一指标，才能访问对等 IM 报告：
  
- 对等 IM 会话总数
    
- 对等 IM 消息总数
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>充分利用对等 IM 报告

默认情况下，对等 IM 报告显示每小时（或每天，具体取决于设置）的消息计数。但是，还可以选择按每小时会话数来查看日期。为此，请单击“报告”窗口右上角的“**隐藏/显示参数**”，然后从“**报告依据**”列表中单击“**会话计数**”。
  
## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于对等 IM 报告的筛选器。
  
**对等 IM 报告筛选器**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**说明**|
|:-----|:-----|
|**从** <br/> |时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 2015/7/7 13:00  <br/> 如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 2015/7/7  <br/> 若要按周或按月查看，请输入周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 2015/7/3  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**到** <br/> |时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 2015/7/7 13:00  <br/> 如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 2015/7/7  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 2015/7/3  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**间隔** <br/> | 时间间隔。选择下列选项之一： <br/>  每小时（最多可显示 25 个小时） <br/>  每天（最多可显示 31 天） <br/>  每周（最多可显示 12 周） <br/>  每月（最多可显示 12 个月） <br/>  如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 2015/7/7、结束日期为 2015/2/28、间隔为“每天”，则显示从 2015/8/7 12:00 AM 到 2015/9/7 12:00 AM 这些天的数据（即总共 31 天的数据）。 <br/> |
|**报告依据** <br/> | 指示要在报告中使用的值。选择下列选项之一： <br/>  会话计数 <br/>  消息计数 <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>按池列出的对等 IM 会话的指标

下表列出了对等 IM 报告中提供的信息。
  
**按池列出的对等 IM 会话的指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**池** <br/> |否  <br/> |注册机构池或边缘服务器的名称。  <br/> |
|**日期/时间** <br/> |否  <br/> |会话发生的日期和时间。  <br/> |
|**总计** <br/> |否  <br/> |会话总数或消息总数。  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>按身份验证类型列出的对等 IM 会话的指标

下表列出了对等会话中的参与者所用各个身份验证类型的对等 IM 报告中提供的信息。
  
**按身份验证类型列出的对等 IM 会话的指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**身份验证类型** <br/> |否  <br/> | 会话参与者使用的身份验证的类型。通常可指定下列值之一： <br/>  Enterprise <br/>  Federated <br/>  PIC <br/> |
|**日期/时间** <br/> |否  <br/> |会话发生的日期和时间。  <br/> |
|**总计** <br/> |否  <br/> |会话总数或消息总数。  <br/> |
   

