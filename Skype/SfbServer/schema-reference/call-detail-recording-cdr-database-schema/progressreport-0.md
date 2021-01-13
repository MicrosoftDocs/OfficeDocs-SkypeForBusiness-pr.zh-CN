---
title: ProgressReport 视图
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 视图会存储有关已完成的会话的信息。 只会针对 Lync Server 2013 判定可能对诊断有用的呼叫和会话编写进度报告。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823182"
---
# <a name="progressreport-view"></a>ProgressReport 视图
 
ProgressReport 视图会存储有关已完成的会话的信息。 只会针对 Lync Server 2013 判定可能对诊断有用的呼叫和会话编写进度报告。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
> [!NOTE]
> ErrorTime、ErrorReportSeq 和 ProgressReportSeq 字段不一定指错误，而是指指示呼叫或消息状态的消息。 
  
|**列**|**数据类型**|**Details**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |发生错误的时间。与 ErrorReportSeq 结合使用来唯一地标识错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |用于标识错误的 ID 号。与 ErrorTime 结合使用来唯一地标识错误。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |用于标识进度报告的 ID。 用来区分相同错误报告的进度报告。  <br/> |
|**MsDiagId** <br/> |int  <br/> |错误报告的诊断 ID。  <br/> |
|**Source** <br/> |nvarchar (256)   <br/> |导致出错的服务器的名称（如果报告发送自服务器组件）。  <br/> |
|**应用程序** <br/> |nvarchar (256)   <br/> |产生错误的应用程序的名称（如果报告是从服务器组件发送的）。  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |关联会议中所涉及不同组件的加入时间信息的唯一标识符。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |特定组件加入会议所需的时间（以毫秒为单位）。  <br/> |
|**MsDiagHeader** <br/> |varchar (max)   <br/> |其他错误信息。  <br/> |
   

