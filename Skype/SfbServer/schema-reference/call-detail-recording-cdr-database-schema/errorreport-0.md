---
title: ErrorReport 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport 视图存储有关错误报告的信息。 每个记录是一个错误实例。 错误是可通过在前端服务器上运行的 CDR 代理捕获或从客户端发送。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 8d72ad73b5894e73b7d95b1b11bc10dffcabc5f7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874177"
---
# <a name="errorreport-view"></a>ErrorReport 视图
 
ErrorReport 视图存储有关错误报告的信息。 每个记录是一个错误实例。 错误是可通过在前端服务器上运行的 CDR 代理捕获或从客户端发送。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |发生的错误的时间。 与 ErrorReportSeq 结合使用，来唯一地标识错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |若要确定错误的 ID 号。 与 ErrorTime 结合使用，来唯一地标识错误。  <br/> |
|**MsDiagId** <br/> |int  <br/> |错误报告的诊断 ID。  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |导致出错的用户的 URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |导致出错的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |用户的租户，导致出错。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |错误报告目标的用户的 URI。  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |目标用户的 URI 类型的错误报告。 UriTypes 表的详细信息，请参阅。  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |目标的用户的租户的错误报告。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |会议的错误报告的目标 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |会议的错误报告的目标 URI 类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |产生错误报告的会话请求的时间。 与 SessionIdSeq 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |若要确定产生错误报告的会话请求的 ID 号。 与 SessionIdTime 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |导致出错的会话的 SIP 对话 ID。 格式为：  <br/> 对话框; 从标记; 到标记  <br/> 使用以下语法，可以是此数据转换为文本格式：  <br/> cast (cast (ExternalId as varbinary 作为 varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |客户端版本的用户使用产生错误。  <br/> |
|**客户端类型** <br/> |int  <br/> |使用客户端用户产生错误。 请参阅[UserAgentDef 表](useragentdef.md)的详细信息。 <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |使用用户导致出错的客户端的类别的名称。  <br/> |
|**来源** <br/> |nvarchar(256)  <br/> |产生错误 （如果报告发送自服务器组件） 的服务器的名称。  <br/> |
|**应用程序** <br/> |nvarchar(256)  <br/> |产生错误 （如果报告发送自服务器组件） 的应用程序的名称。  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 响应代码包含错误报告的 SIP 消息的会话。  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |失败的请求的类型。  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |失败的请求的内容类型。  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |会话类型。 请参阅[CallType 表中的业务服务器 2015 Skype](calltype.md)的详细信息。 <br/> |
|**TelemetryId** <br/> |唯一标识符  <br/> |关联会议中所涉及的不同组件的加入时间信息的唯一标识符。  <br/> |
|**SetupTime** <br/> |int  <br/> |时间 （以毫秒为单位） 所需的特定组件加入会议。  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |指示错误报告是由在前端服务器上，运行的 CDR 代理捕获还是客户端发送。  <br/> |
|**标志** <br/> |smallint  <br/> |留作将来使用。  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |有关错误的其他信息。  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |提交报表的前端服务器的完全限定的域名。  <br/> |
|**Pool** <br/> |nvarchar  <br/> |完全限定的域名称包含提交报表的前端服务器的池。  <br/> |
   

