---
title: ProgressReport 视图
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 视图存储有关已完成会话的信息。 将仅写入 Lync Server 2013 确定可能对诊断目的有用的通话和会话的进度报告。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814980"
---
# <a name="progressreport-view"></a>ProgressReport 视图
 
ProgressReport 视图存储有关已完成会话的信息。 将仅写入 Lync Server 2013 确定可能对诊断目的有用的通话和会话的进度报告。 此视图已在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> "ErrorTime"、"ErrorReportSeq" 和 "ProgressReportSeq" 字段不一定是指错误，而是指示调用状态或消息的消息。 
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |出现错误的时间。 与 ErrorReportSeq 结合使用以唯一标识错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |标识错误的 ID 号。 与 ErrorTime 结合使用以唯一标识错误。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |标识进度报表的 ID。 用于区分同一错误报告的进度报告。  <br/> |
|**MsDiagId** <br/> |int  <br/> |错误报告的诊断 ID。  <br/> |
|**来源** <br/> |nvarchar(256)  <br/> |产生错误的服务器的名称（如果报表是从服务器组件发送的）。  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |发出错误的应用程序的名称（如果报表是从服务器组件发送的）。  <br/> |
|**TelemetryId** <br/> |标识符  <br/> |关联会议中涉及的不同组件的加入时间信息的唯一标识符。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |特定组件加入会议所需的时间（以毫秒为单位）。  <br/> |
|**MsDiagHeader** <br/> |varchar （max）  <br/> |其他错误信息。  <br/> |
   

