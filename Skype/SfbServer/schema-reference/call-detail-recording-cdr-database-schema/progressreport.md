---
title: ProgressReport 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 进度报告基于呼叫或会话结束后客户端上载到数据库的数据。 仅针对 2015 年 2015 Skype for Business Server确定可用于诊断目的的呼叫和会话编写进度报告。
ms.openlocfilehash: 666320d64e319816666404dff3afd4f27b7413f4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740278"
---
# <a name="progressreport-table"></a>ProgressReport 表
 
进度报告基于呼叫或会话结束后客户端上载到数据库的数据。 仅针对 2015 年 2015 Skype for Business Server确定可用于诊断目的的呼叫和会话编写进度报告。
  
ErrorTime、ErrorReportSeq 和 ProgressReportSeq 字段不一定指错误，而是指指示呼叫或消息状态的消息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |主、外  <br/> |包含此进度报告的进度错误报告的日期和时间。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ErrorReport](errorreport.md)表。 <br/> |
|**ErrorId** <br/> |int  <br/> |主、外  <br/> |与 ErrorTime 和 ProgressReportSeq 结合使用唯一地标识进度报告的 ID 号。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ErrorReport](errorreport.md)表。 <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |主、外  <br/> |标识错误报告的 ID 号。 ErrorReporSeq 与 ErrorTime 结合使用来唯一地标识错误报告。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ErrorReport](errorreport.md)表 <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |主  <br/> |标识进度报告的 ID 号。与 ErrorTime 和 ErrorReportSeq 结合使用可唯一地标识进度报告。  <br/> |
|**MsDiagId** <br/> |int  <br/> ||进度报告的诊断 ID。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SourceId** <br/> |int  <br/> |Foreign  <br/> |发送错误报告的服务器 (报告是否从服务器组件发送) 。 有关详细信息 [，请参阅 Servers](servers.md) 表。此字段在 Microsoft Lync Server 2013 中引入。 <br/> |
|**ApplicationId** <br/> |int  <br/> ||报告涉及的 Lync Server 进程。有关详细信息，请参阅 Application 表。  <br/> |
|**详细信息** <br/> |image  <br/> ||为节省空间而以二进制格式存储的进度报告详细信息。使用以下语法可将此数据转换为文本格式：  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||与会议中所涉及不同组件的加入时间信息关联的唯一标识符。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定组件加入会议的时间（以毫秒计）。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
   

