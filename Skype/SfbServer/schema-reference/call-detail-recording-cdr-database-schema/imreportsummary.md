---
title: Skype for Business Server 2015 中的 IMReportSummary 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 提供有关组织中进行的即时消息会话的总体报告。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 204aeb21037f69eb34c2e12ee642d2ed6495111f8ae68d8c8f3786eb49a957fa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341717"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 IMReportSummary 表
 
IMReportSummaryTable 提供有关组织中进行的即时消息会话的总体报告。 此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |主  <br/> |即时消息会话开始的日期和时间。  <br/> |
|**TimePeriod** <br/> |char (1)   <br/> |主  <br/> ||
|**PoolFQDN** <br/> |nvarchar (257)   <br/> |主  <br/> |承载会话的池的完全限定域名。  <br/> |
|**AuthType** <br/> |int  <br/> |主  <br/> |呼叫的优先级（例如，紧急或非紧急）。 优先级信息存储在 Skype for Business Server [2015 中的 CallPriorities 表中](callpriorities.md)。  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||会话期间交换的即时消息总数。  <br/> |
   

