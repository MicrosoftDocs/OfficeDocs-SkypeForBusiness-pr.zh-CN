---
title: ErrorReport 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport 表存储有关发生的错误的信息。 每个记录是一个错误实例。 错误是可通过在前端服务器上运行的 CDR 代理捕获或从客户端发送。
ms.openlocfilehash: 99dcdc7aa78b20f555f94614ba94c80103b56211
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213128"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>ErrorReport 表中的业务服务器 2015 Skype
 
ErrorReport 表存储有关发生的错误的信息。 每个记录是一个错误实例。 错误是可通过在前端服务器上运行的 CDR 代理捕获或从客户端发送。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |日期和时间发生错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |若要确定错误报告的 ID 号。 与**ErrorTime**结合使用，来唯一地标识错误报告。 <br/> |
|**ErrorId** <br/> |int  <br/> |外  <br/> |错误类型的唯一 ID。 请参阅[ErrorDef 表中的业务服务器 2015 Skype](errordef.md)的详细信息。 <br/> |
|**FromUserId** <br/> |int  <br/> |外  <br/> |产生的请求的导致出错的用户。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**ToUserId** <br/> |int  <br/> |外  <br/> |导致出错的请求的目标用户。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外  <br/> |会议 URI 与错误相关。 请参阅[ConferenceUris 表中的业务服务器 2015 Skype](conferenceuris.md)的详细信息。 通常，如果 ConferenceUriId 不为 null，则 FromUserId 或 ToUserId 将 null。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |外  <br/> |与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SourceId** <br/> |int  <br/> |外  <br/> |（如果报告发送自服务器组件） 发送错误报告的服务器。 请参阅[服务器表](servers.md)的详细信息。 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ApplicationId** <br/> |int  <br/> |外  <br/> |（如果报告发送自服务器组件） 发送错误报告的服务器。 请参阅[应用程序表中的业务服务器 2015 Skype](application.md)的详细信息。 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**MsDiagHeader** <br/> |图像  <br/> | <br/> |有关错误的详细信息。  <br/> 使用以下语法，可以是此数据转换为文本格式：  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |外  <br/> |终结点发送错误报告的客户端版本。 请参阅[ClientVersions 表中的业务服务器 2015 Skype](clientversions.md)的详细信息。 <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||错误报告是由在前端服务器上运行的 CDR 代理捕获或客户端发送。  <br/> |
|**标志** <br/> |smallint  <br/> ||留作将来使用。  <br/> |
|**TelemetryId** <br/> |唯一标识符  <br/> ||关联会议中所涉及的不同组件的加入时间信息的唯一标识符。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||时间 （以毫秒为单位） 所需的特定组件加入会议。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ServerId** <br/> |int  <br/> |外  <br/> |代表生成错误报告的服务器的完全限定的域名。  <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |代表生成错误报告其中的池的完全限定的域名。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

