---
title: ProgressReport 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 进度报告根据调用或会话完成后客户端数据库上载数据。 进度报告将仅用于电话和 Skype 业务服务器 2015年的确定可用于诊断目的的会话写入。
ms.openlocfilehash: 9acf54e7fb00917ad8263d4c40e534beb29b628c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="progressreport-table"></a>ProgressReport 表
 
进度报告根据调用或会话完成后客户端数据库上载数据。 进度报告将仅用于电话和 Skype 业务服务器 2015年的确定可用于诊断目的的会话写入。
  
ErrorTime、 ErrorReportSeq 和 ProgressReportSeq 字段一定不请而对错误消息，以表明通话或邮件的状态。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |主键和外  <br/> |日期和时间进度错误报告包含的本进度报告。 [业务服务器 2015年的 Skype 在 ErrorReport 表](errorreport.md)的详细信息，请参阅。 <br/> |
|**ErrorId** <br/> |int  <br/> |主键和外  <br/> |与 ErrorTime，ProgressReportSeq 来唯一地标识进度报告一起使用的 ID 号。 [业务服务器 2015年的 Skype 在 ErrorReport 表](errorreport.md)的详细信息，请参阅。 <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |主键和外  <br/> |标识错误报告的 ID 号。 ErrorReporSeq 与 ErrorTime 配合使用，以唯一地标识错误报告。 [在业务服务器 2015年的 Skype 的 ErrorReport 表](errorreport.md)的详细信息，请参阅 <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |ID 号来标识进度报表。 与 ErrorTime 和 ErrorReportSeq 配合使用，用来唯一地标识进度报告。  <br/> |
|**MsDiagId** <br/> |int  <br/> ||进度报告诊断 ID。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**源 Id** <br/> |int  <br/> |外  <br/> |（如果服务器组件发送报告） 发送错误报告的服务器。 [服务器表](servers.md)的详细信息，请参阅。在 Microsoft Lync Server 2013 引入了此字段。 <br/> |
|**ApplicationId** <br/> |int  <br/> ||该报告是关于 Lync Server 进程。 应用程序表的详细信息，请参阅。  <br/> |
|**详情** <br/> |图像  <br/> ||进度报告的详细信息，存储在二进制格式，以节省空间。此数据可以转换成文本格式，使用以下语法：  <br/> 强制转换 （转换为 varchar(max)) varbinary(max)) （详细信息  <br/> |
|**TelemetryId** <br/> |唯一标识符  <br/> ||建立关联加入会议所涉及的不同组件的时间信息的唯一标识符。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定的组件加入会议时间 （以毫秒为单位）。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
   

