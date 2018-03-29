---
title: 在业务服务器 2015年的 Skype 的 IMReportSummary 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 提供即时消息会话保存在一个组织的总体报告。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: f716a7406f4cf3562e2fa9244e8a766ef8537f53
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 IMReportSummary 表
 
IMReportSummaryTable 提供即时消息会话保存在一个组织的总体报告。 在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**开始时间** <br/> |datetime  <br/> |Primary  <br/> |日期和即时消息会话开始的时间。  <br/> |
|**TimePeriod** <br/> |char （1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |发起会话池的完全限定的域名。  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |调用的 （例如，紧急或非紧急） 优先级。 优先级信息存储[在业务服务器 2015年的 Skype 的 CallPriorities 表](callpriorities.md)中。  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||在会话期间交换的即时消息总数。  <br/> |
   

