---
title: ProgressReport 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 进度报告基于呼叫或会话完毕后，对数据库客户端上载的数据。 仅对呼叫和 Skype 的业务服务器 2015年确定用于进行诊断下可能有用的会话将写入进度报告。
ms.openlocfilehash: 6d638411f39956664c977e87785a1269ee788a5f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899755"
---
# <a name="progressreport-table"></a>ProgressReport 表
 
进度报告基于呼叫或会话完毕后，对数据库客户端上载的数据。 仅对呼叫和 Skype 的业务服务器 2015年确定用于进行诊断下可能有用的会话将写入进度报告。
  
ErrorTime、 ErrorReportSeq 和 ProgressReportSeq 字段不一定引用，而对错误消息，以表明的呼叫或消息状态。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |主、 外  <br/> |日期和时间的进度错误报告包含此进度报告。 请参阅[ErrorReport 表中的业务服务器 2015 Skype](errorreport.md)的详细信息。 <br/> |
|**ErrorId** <br/> |int  <br/> |主、 外  <br/> |ErrorTime，ProgressReportSeq 来唯一地标识进度报告与配合使用的 ID 号。 请参阅[ErrorReport 表中的业务服务器 2015 Skype](errorreport.md)的详细信息。 <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |主、 外  <br/> |标识错误报告的 ID 号。 ErrorReporSeq 与 ErrorTime 配合使用，来唯一地标识错误报告。 [ErrorReport 表中的业务服务器 2015 Skype](errorreport.md)的详细信息，请参阅 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |若要确定进度报告的 ID 号。 与 ErrorTime 和 ErrorReportSeq 结合使用来唯一地标识进度报告。  <br/> |
|**MsDiagId** <br/> |int  <br/> ||进度报告的诊断 ID。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SourceId** <br/> |int  <br/> |外  <br/> |（如果报告发送自服务器组件） 发送错误报告的服务器。 请参阅[服务器表](servers.md)的详细信息。此字段是在 Microsoft Lync Server 2013 中引入的。 <br/> |
|**ApplicationId** <br/> |int  <br/> ||报告是有关 Lync Server 过程。 请参阅应用程序表的详细信息。  <br/> |
|**详情** <br/> |图像  <br/> ||进度报告详细信息，以节省空间的二进制格式存储在。可以将此数据转换为文本格式使用以下语法：  <br/> cast (cast (Detail as varbinary 作为 varchar(max))  <br/> |
|**TelemetryId** <br/> |唯一标识符  <br/> ||加入会议所涉及不同组件的时间信息关联的唯一标识符。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定组件加入会议时间 （以毫秒为单位）。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

