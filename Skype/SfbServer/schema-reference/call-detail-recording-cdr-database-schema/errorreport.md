---
title: Skype for Business Server 2015 中的 ErrorReport 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport 表存储有关发生的错误的信息。 每条记录代表发生一次错误。 错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。
ms.openlocfilehash: b2f81df1134294185124d78b90c2e4f639575ded
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821672"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ErrorReport 表
 
ErrorReport 表存储有关发生的错误的信息。 每条记录代表发生一次错误。 错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |主  <br/> |发生错误的日期和时间。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |主  <br/> |用于标识错误报告的 ID 号。 与 **ErrorTime 结合使用来** 唯一地标识错误报告。 <br/> |
|**ErrorId** <br/> |int  <br/> |Foreign  <br/> |错误类型的唯一 ID。 有关详细信息， [请参阅 Skype for Business Server 2015](errordef.md) 中的 ErrorDef 表。 <br/> |
|**FromUserId** <br/> |int  <br/> |Foreign  <br/> |导致错误的请求的用户。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**ToUserId** <br/> |int  <br/> |Foreign  <br/> |导致错误的请求的目标用户。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |与错误相关的会议 URI。 有关详细信息， [请参阅 Skype for Business Server 2015 中的 ConferenceUris](conferenceuris.md) 表。 通常，如果 ConferenceUriId 不为空，则 FromUserId 或 ToUserId 将为 null。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。 有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。 <br/> |
|**SourceId** <br/> |int  <br/> |Foreign  <br/> |如果报告从服务器组件 (，则发送错误报告的服务器) 。 有关详细信息 [，请参阅"服务器](servers.md) "表。 <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ApplicationId** <br/> |int  <br/> |Foreign  <br/> |如果报告从服务器组件 (，则发送错误报告的服务器) 。 有关详细信息， [请参阅 Skype for Business Server 2015 中的](application.md) "应用程序"表。 <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |有关错误的详细信息。  <br/> 可以使用以下语法将此数据转换为文本格式：  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |发送错误报告的客户端版本的终结点。 有关详细信息， [请参阅 Skype for Business Server 2015 中的 ClientVersions](clientversions.md) 表。 <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||错误报告是由在前端服务器上运行的 CDR 代理捕获的，还是由客户端发送的。  <br/> |
|**Flag** <br/> |smallint  <br/> ||保留以供将来使用。  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||关联会议中所涉及不同组件的加入时间信息的唯一标识符。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定组件加入会议所需的时间（以毫秒为单位）。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |表示生成错误报告的服务器的完全限定域名。  <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |表示生成错误报告的池的完全限定域名。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段在 Skype for Business Server 2015 中引入。  <br/> |
   

