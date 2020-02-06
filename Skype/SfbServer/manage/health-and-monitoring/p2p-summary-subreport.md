---
title: Skype for Business 服务器中的 P2P 摘要子报表
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
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 摘要：了解 Skype for Business 服务器中的 P2P 摘要子报告。
ms.openlocfilehash: 31e17aaff8d449c49a7c51d3dba484e7fab48d55
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817791"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Skype for Business 服务器中的 P2P 摘要子报表
 
**摘要：** 了解 Skype for Business 服务器中的 P2P 摘要子报告。
  
P2P 摘要子报表对失败对等通信会话提供一个总体视图。
  
## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于 P2P 摘要子报表的筛选器。
  
**P2P 摘要子报表筛选器**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**说明**|
|:-----|:-----|
|**从** <br/> |时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：  <br/> 2015/7/7 13:00  <br/> 如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：  <br/> 2015/7/7  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 2015/7/3  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**到** <br/> |时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：  <br/> 2015/7/7 13:00  <br/> 如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：  <br/> 2015/7/7  <br/> 若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：  <br/> 2015/7/3  <br/> 一周始终是从星期日开始至星期六结束。  <br/> |
|**池** <br/> |注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“**[所有]**”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。<br/> |
   
## <a name="metrics"></a>指标

下表列出了 P2P 摘要子报表中提供的信息。
  
**P2P 摘要子报告指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**会话总数** <br/> |否  <br/> |会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。  <br/> |
|**故障率** <br/> |否  <br/> |失败的对等会话百分比。  <br/> |
|**按形式列出的会话** <br/> |否  <br/> |按形式分组的会话总数（例如，即时消息）。  <br/> |
|**按形式列出的故障率** <br/> |否  <br/> |按形式分组的失败会话总数（例如，即时消息）。  <br/> |
   

