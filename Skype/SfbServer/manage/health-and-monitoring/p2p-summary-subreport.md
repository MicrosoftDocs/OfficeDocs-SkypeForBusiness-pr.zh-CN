---
title: P2P 摘要子报表Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 摘要：了解 P2P 摘要子报表Skype for Business Server。
ms.openlocfilehash: e8296604626b143bb143ea2acbdf8e6875e1acf6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861319"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>P2P 摘要子报表Skype for Business Server
 
**摘要：** 了解 P2P 摘要子报表Skype for Business Server。
  
P2P 摘要子报表对失败点对点通信会话提供一个总体视图。
  
## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于 P2P 摘要子报表的筛选器。
  
**P2P 摘要子报表筛选器**

|**名称**|**说明**|
|:-----|:-----|
|**From** <br/> |时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**To** <br/> |时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 7/7/2015 1：00 PM  <br/> 如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 7/7/2015  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 7/3/2015  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**Pool** <br/> |注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。<br/> |
   
## <a name="metrics"></a>度量标准

下表列出了 P2P 摘要子报表中提供的信息。
  
**P2P 摘要子报告指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**会话总数** <br/> |否  <br/> |会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。  <br/> |
|**故障率** <br/> |否  <br/> |失败的点对点会话百分比。  <br/> |
|**按形式列出的会话** <br/> |否  <br/> |按形式分组的会话总数（例如，即时消息）。  <br/> |
|**按形式列出的故障率** <br/> |否  <br/> |按形式分组的失败会话总数（例如，即时消息）。  <br/> |
   

