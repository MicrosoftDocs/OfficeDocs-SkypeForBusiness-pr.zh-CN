---
title: ErrorReport 视图
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport 视图存储有关已报告的错误的信息。 每条记录代表发生一次错误。 错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 5a35cc8b3a726549be7de10259c7e59a67ca5500
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852926"
---
# <a name="errorreport-view"></a>ErrorReport 视图
 
ErrorReport 视图存储有关已报告的错误的信息。 每条记录代表发生一次错误。 错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。 此视图在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |发生错误的时间。与 ErrorReportSeq 结合使用来唯一地标识错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |用于标识错误的 ID 号。与 ErrorTime 结合使用来唯一地标识错误。  <br/> |
|**MsDiagId** <br/> |int  <br/> |错误报告的诊断 ID。  <br/> |
|**FromUri** <br/> |nvarchar (450)   <br/> |导致出错的用户的 URI。  <br/> |
|**FromUriType** <br/> |nvarchar (256)   <br/> |导致出错的用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**FromTenant** <br/> |nvarchar (256)   <br/> |导致出错的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**ToUri** <br/> |nvarchar (450)   <br/> |成为错误报告目标的用户的 URI。  <br/> |
|**ToUriType** <br/> |nvarchar (256)   <br/> |成为错误报告目标的用户的 URI 类型。有关详细信息，请参阅 UriTypes 表。  <br/> |
|**ToTenant** <br/> |nvarchar (256)   <br/> |成为错误报告目标的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**ConferenceUri** <br/> |nvarchar (450)   <br/> |成为错误报告目标的会议的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)   <br/> |成为错误报告目标的会议的 URI 类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |导致发出错误报告的会话请求的时间。 与 SessionIdSeq 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |用于标识导致发出错误报告的会话请求的 ID 编号。 与 SessionIdTime 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**DialogId** <br/> |varstring (775)   <br/> |导致出错的会话的 SIP 对话 ID。格式为：  <br/> dialog;from-tag;to-tag  <br/> 可以使用以下语法将此数据转换为文本格式：  <br/> cast(cast(ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar (256)   <br/> |导致出错的用户所使用的客户端版本。  <br/> |
|**ClientType** <br/> |int  <br/> |导致出错的用户所使用的客户端。 有关详细信息， [请参阅 UserAgentDef](useragentdef.md) 表。 <br/> |
|**ClientCategory** <br/> |nvarchar (64)   <br/> |导致出错的用户所使用的客户端的类别名称。  <br/> |
|**Source** <br/> |nvarchar (256)   <br/> |导致出错的服务器的名称（如果报告发送自服务器组件）。  <br/> |
|**应用程序** <br/> |nvarchar (256)   <br/> |导致出错的应用程序的名称（如果报告发送自服务器组件）。  <br/> |
|**ResponseCode** <br/> |int  <br/> |包含错误报告的 SIP 消息对话的 SIP 响应代码。  <br/> |
|**RequestType** <br/> |varchar (max)   <br/> |失败的请求的类型。  <br/> |
|**ContentType** <br/> |varchar (max)   <br/> |失败的请求的内容类型。  <br/> |
|**CallType** <br/> |nvarchar (256)   <br/> |会话类型。 有关详细信息，请参阅[Skype for Business Server 2015](calltype.md)中的 CallType 表。 <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |关联会议中所涉及不同组件的加入时间信息的唯一标识符。  <br/> |
|**SetupTime** <br/> |int  <br/> |特定组件加入会议所需的时间（以毫秒为单位）。  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |指示错误报告是由在前端服务器上运行的 CDR 代理捕获的，还是客户端发送的。  <br/> |
|**Flag** <br/> |smallint  <br/> |保留以供将来使用。  <br/> |
|**MsDiagHeader** <br/> |varchar (max)   <br/> |有关错误的其他信息。  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |提交报告的前端服务器的完全限定域名。  <br/> |
|**Pool** <br/> |nvarchar  <br/> |包含提交报告的前端服务器的池的完全限定域名。  <br/> |
   

