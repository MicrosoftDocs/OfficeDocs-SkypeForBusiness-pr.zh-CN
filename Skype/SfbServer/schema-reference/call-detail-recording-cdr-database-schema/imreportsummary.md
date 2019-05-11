---
title: IMReportSummary 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 的即时消息会话保留在组织中提供的全面报告。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 3611243e49821e5fae211ce55858cdee555dd383
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901043"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>IMReportSummary 表中的业务服务器 2015 Skype
 
IMReportSummaryTable 的即时消息会话保留在组织中提供的全面报告。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |日期和即时消息会话开始的时间。  <br/> |
|**时间段** <br/> |char （1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |承载会话的池的完全限定的域名。  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |呼叫的优先级 （例如，紧急或非紧迫）。 优先级信息存储[中的业务服务器 2015 Skype CallPriorities 表](callpriorities.md)中。  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||在会话期间交换的即时消息的总数。  <br/> |
   

