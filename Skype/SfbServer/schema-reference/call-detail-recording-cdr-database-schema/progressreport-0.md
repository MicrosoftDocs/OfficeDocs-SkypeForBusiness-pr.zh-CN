---
title: ProgressReport 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 视图存储有关已完成的会话信息。 进度报告将仅对呼叫和 Lync Server 2013 确定可用于诊断目的的会话写入。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 7dab41202eb098e2e49e5d4960b0c7b4e4c6570d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="progressreport-view"></a>ProgressReport 视图
 
ProgressReport 视图存储有关已完成的会话信息。 进度报告将仅对呼叫和 Lync Server 2013 确定可用于诊断目的的会话写入。 在 Microsoft Lync Server 2013 引入了此视图。
  
> [!NOTE]
> ErrorTime、 ErrorReportSeq 和 ProgressReportSeq 字段一定不请而对错误消息，以表明通话或邮件的状态。 
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |发生错误的时间。 与 ErrorReportSeq 配合使用，以唯一地标识错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |若要确定错误的 ID 号。 与 ErrorTime 配合使用，以唯一地标识错误。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID 来标识进度报表。 用于区分同一错误报告的进度报告。  <br/> |
|**MsDiagId** <br/> |int  <br/> |有关错误报告的诊断 ID。  <br/> |
|**来源** <br/> |nvarchar(256)  <br/> |（如果报表的服务器组件发送） 发出了错误的服务器的名称。  <br/> |
|**应用程序** <br/> |nvarchar(256)  <br/> |（如果报表的服务器组件发送） 发出了错误的应用程序的名称。  <br/> |
|**TelemetryId** <br/> |唯一标识符  <br/> |将在会议中所涉及的不同部分的加入时间信息关联起来的唯一标识符。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |时间 （以毫秒为单位） 所需的特定组件加入会议。  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |其他错误的信息。  <br/> |
   

