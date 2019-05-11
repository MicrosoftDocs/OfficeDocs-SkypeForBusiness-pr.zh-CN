---
title: ProgressReport 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 视图存储有关已完成会话的信息。 仅对呼叫和 Lync Server 2013 确定用于进行诊断下可能有用的会话将写入进度报告。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 4508b2f1772a3b21d51d561c310b31f00740973d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930628"
---
# <a name="progressreport-view"></a>ProgressReport 视图
 
ProgressReport 视图存储有关已完成会话的信息。 仅对呼叫和 Lync Server 2013 确定用于进行诊断下可能有用的会话将写入进度报告。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
> [!NOTE]
> ErrorTime、 ErrorReportSeq 和 ProgressReportSeq 字段不一定引用，而对错误消息，以表明的呼叫或消息状态。 
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |发生的错误的时间。 与 ErrorReportSeq 结合使用，来唯一地标识错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |若要确定错误的 ID 号。 与 ErrorTime 结合使用，来唯一地标识错误。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |若要确定进度报告的 ID。 用于区分相同的错误报告的进度报告。  <br/> |
|**MsDiagId** <br/> |int  <br/> |错误报告的诊断 ID。  <br/> |
|**来源** <br/> |nvarchar(256)  <br/> |产生错误 （如果报告发送自服务器组件） 的服务器的名称。  <br/> |
|**应用程序** <br/> |nvarchar(256)  <br/> |产生错误 （如果报告发送自服务器组件） 的应用程序的名称。  <br/> |
|**TelemetryId** <br/> |唯一标识符  <br/> |关联会议中所涉及的不同组件的加入时间信息的唯一标识符。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |时间 （以毫秒为单位） 所需的特定组件加入会议。  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |其他错误信息。  <br/> |
   

