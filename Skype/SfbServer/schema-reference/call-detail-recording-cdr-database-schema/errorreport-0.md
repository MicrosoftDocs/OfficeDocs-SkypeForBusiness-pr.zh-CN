---
title: ErrorReport 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport 视图存储错误报告的有关信息。 每个记录是一个错误事件。 错误捕获通过前端服务器上运行的 CDR 代理或者从客户端发送的。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: b1815d4420b5768b065a5695ea09174ecff91912
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-view"></a>ErrorReport 视图
 
ErrorReport 视图存储错误报告的有关信息。 每个记录是一个错误事件。 错误捕获通过前端服务器上运行的 CDR 代理或者从客户端发送的。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |发生错误的时间。 与 ErrorReportSeq 配合使用，以唯一地标识错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |若要确定错误的 ID 号。 与 ErrorTime 配合使用，以唯一地标识错误。  <br/> |
|**MsDiagId** <br/> |int  <br/> |有关错误报告的诊断 ID。  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |导致错误的用户的 URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |导致错误的用户的 URI 类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |客户端的用户导致错误。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI 的用户的是错误报告的目标。  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |URI 的用户的目标类型的错误报告。 UriTypes 表的详细信息，请参阅。  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |租户的目标用户的错误报告。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI 是错误报告的目标的会议。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI 类型是错误报告的目标的会议。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |产生错误报告的会话请求的时间。 与 SessionIdSeq 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |ID 号来标识会话请求发出错误报告。 与 SessionIdTime 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP 会话导致错误的对话框 ID。 格式为：  <br/> 对话; 从标记; 到标记  <br/> 此数据可以转换为文本格式，使用以下语法：  <br/> 强制转换 （转换为 varchar(max)) varbinary(max)) (ExternalId  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |用户使用者产生了错误的客户端版本。  <br/> |
|**客户端类型** <br/> |int  <br/> |客户端使用的用户产生错误。 [UserAgentDef 表](useragentdef.md)的更多详细信息，请参阅。 <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |客户端的用户使用者产生了错误的类别的名称。  <br/> |
|**来源** <br/> |nvarchar(256)  <br/> |（如果报表的服务器组件发送） 发出了错误的服务器的名称。  <br/> |
|**应用程序** <br/> |nvarchar(256)  <br/> |（如果报表的服务器组件发送） 发出了错误的应用程序的名称。  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 响应代码包含错误报告的 SIP 消息的会话。  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |失败的请求的类型。  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |失败的请求的内容类型。  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |会话类型。 [业务服务器 2015年的 Skype 在 CallType 表](calltype.md)的详细信息，请参阅。 <br/> |
|**TelemetryId** <br/> |唯一标识符  <br/> |将在会议中所涉及的不同部分的加入时间信息关联起来的唯一标识符。  <br/> |
|**SetupTime** <br/> |int  <br/> |时间 （以毫秒为单位） 所需的特定组件加入会议。  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |指示是否捕获的 CDR 代理运行在前端服务器上，或由客户端发送错误报告。  <br/> |
|**标志** <br/> |smallint  <br/> |保留供将来使用。  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |有关此错误的其他信息。  <br/> |
|**前端** <br/> |nvarchar  <br/> |提交报告的前端服务器的完全限定的域名。  <br/> |
|**池** <br/> |nvarchar  <br/> |完全限定的域名包含提交报告该前端服务器的池中。  <br/> |
   

