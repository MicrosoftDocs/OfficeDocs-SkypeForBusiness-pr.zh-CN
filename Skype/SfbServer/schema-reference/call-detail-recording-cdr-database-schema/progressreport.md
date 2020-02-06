---
title: ProgressReport 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 进度报告基于客户端在通话或会话完成后上载到数据库的数据。 进度报告将仅写入 Skype for Business Server 2015 确定可能对诊断用途有用的通话和会话。
ms.openlocfilehash: a6cd89d7ba7f8cc03b25dc9310bdb408c85b50cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814970"
---
# <a name="progressreport-table"></a>ProgressReport 表
 
进度报告基于客户端在通话或会话完成后上载到数据库的数据。 进度报告将仅写入 Skype for Business Server 2015 确定可能对诊断用途有用的通话和会话。
  
"ErrorTime"、"ErrorReportSeq" 和 "ProgressReportSeq" 字段不一定是指错误，而是指示调用状态或消息的消息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |主、外部  <br/> |包含此进度报表的 "进度错误" 报表的日期和时间。 有关详细信息，请参阅[Skype For Business Server 2015 中的 ErrorReport 表](errorreport.md)。 <br/> |
|**ErrorId** <br/> |int  <br/> |主、外部  <br/> |与 ErrorTime 和 ProgressReportSeq 结合使用的 ID 号，用于唯一标识进度报告。 有关详细信息，请参阅[Skype For Business Server 2015 中的 ErrorReport 表](errorreport.md)。 <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |主、外部  <br/> |标识错误报告的 ID 号。 ErrorReporSeq 与 ErrorTime 结合使用，以唯一标识错误报告。 有关详细信息，请参阅[Skype For Business Server 2015 中的 ErrorReport 表](errorreport.md)。 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |标识进度报表的 ID 号。 与 ErrorTime 和 ErrorReportSeq 结合使用，以唯一标识进度报表。  <br/> |
|**MsDiagId** <br/> |int  <br/> ||进度报表的诊断 ID。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SourceId** <br/> |int  <br/> |外表  <br/> |发送错误报告的服务器（如果报表是从服务器组件发送的）。 有关详细信息，请参阅[服务器表](servers.md)。此字段是在 Microsoft Lync Server 2013 中引入的。 <br/> |
|**ApplicationId** <br/> |int  <br/> ||报表所针对的 Lync Server 进程。 有关详细信息，请参阅应用程序表。  <br/> |
|**详情** <br/> |图像  <br/> ||进度报告详细信息，以二进制格式存储以节省空间。此数据可以使用以下语法转换为文本格式：  <br/> 转换（cast （作为 varbinary （max）的详细信息）作为 varchar （max））  <br/> |
|**TelemetryId** <br/> |标识符  <br/> ||关联会议中涉及的不同组件的联接时间信息的唯一标识符。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定组件加入会议的时间（以毫秒为单位）。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

