---
title: 在业务服务器 2015年的 Skype 的 ErrorReport 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport 表用来存储有关已发生的错误的信息。 每个记录是一个错误事件。 错误捕获通过前端服务器上运行的 CDR 代理或者从客户端发送的。
ms.openlocfilehash: 80ae8cb9fb4bea586ac31456fc396856e5263a34
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 ErrorReport 表
 
ErrorReport 表用来存储有关已发生的错误的信息。 每个记录是一个错误事件。 错误捕获通过前端服务器上运行的 CDR 代理或者从客户端发送的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |日期和时间，出现了错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |ID 号来标识错误报告。 与**ErrorTime**配合使用，用来唯一地标识错误报告。 <br/> |
|**ErrorId** <br/> |int  <br/> |外  <br/> |错误类型的唯一 ID。 [业务服务器 2015年的 Skype 在 ErrorDef 表](errordef.md)的详细信息，请参阅。 <br/> |
|**FromUserId** <br/> |int  <br/> |外  <br/> |发起请求导致错误的用户。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**ToUserId** <br/> |int  <br/> |外  <br/> |导致此错误的请求的目标用户。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外  <br/> |会议与该错误相关的 URI。 [业务服务器 2015年的 Skype 在 ConferenceUris 表](conferenceuris.md)的详细信息，请参阅。 通常情况下，如果 ConferenceUriId 不为 null，然后 FromUserId 或 ToUserId 将为 null。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |外  <br/> |与**SessionIdSeq**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |外  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**源 Id** <br/> |int  <br/> |外  <br/> |（如果正在从一个服务器组件发送报告） 发送错误报告的服务器。 [服务器表](servers.md)的详细信息，请参阅。 <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**ApplicationId** <br/> |int  <br/> |外  <br/> |（如果正在从一个服务器组件发送报告） 发送错误报告的服务器。 [在业务服务器 2015年的 Skype 应用程序表](application.md)的详细信息，请参阅。 <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**MsDiagHeader** <br/> |图像  <br/> | <br/> |有关错误的详细信息。  <br/> 此数据可以转换为文本格式，使用以下语法：  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |外  <br/> |终结点发送错误报告的客户端版本。 [业务服务器 2015年的 Skype 在 ClientVersions 表](clientversions.md)的详细信息，请参阅。 <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||是捕获的 CDR 代理运行在前端服务器上，或由客户端发送错误报告。  <br/> |
|**标志** <br/> |smallint  <br/> ||保留供将来使用。  <br/> |
|**TelemetryId** <br/> |唯一标识符  <br/> ||将在会议中所涉及的不同部分的加入时间信息关联起来的唯一标识符。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||时间 （以毫秒为单位） 所需的特定组件加入会议。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**ServerId** <br/> |int  <br/> |外  <br/> |表示生成错误报告的服务器完全合格的域名称。  <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |表示的池生成错误报告的位置的完全限定的域名。  <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> ||供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

