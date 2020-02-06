---
title: Skype for Business Server 2015 中的 IMReportSummary 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 提供组织中的即时消息会话的整体报告。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815140"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 IMReportSummary 表
 
IMReportSummaryTable 提供组织中的即时消息会话的整体报告。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |即时消息会话开始的日期和时间。  <br/> |
|**TimePeriod** <br/> |char （1）  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar （257）  <br/> |Primary  <br/> |托管会话的池的完全限定的域名。  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |通话的优先级（例如，紧急或非紧急）。 优先级信息存储在[Skype For Business Server 2015 的 CallPriorities 表中](callpriorities.md)。  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||会话期间交换的即时消息总数。  <br/> |
   

