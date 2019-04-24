---
title: ConferenceSessionDetails 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 每条记录代表一个会议会话，它可以是具有焦点会话或与特定会议服务器的会话。
ms.openlocfilehash: ab51ff0c75ba5ea9c6164fdee00be65ff5538c73
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213254"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>ConferenceSessionDetails 表中的业务服务器 2015 Skype
 
每条记录代表一个会议会话，它可以是具有焦点会话或与特定会议服务器的会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |主、 外  <br/> |会话请求; 的时间与**SessionIdSeq**结合使用，来唯一地标识会议会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会议会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外  <br/> |与此会话相关焦点会议 URI。 请参阅[ConferenceUris 表中的业务服务器 2015 Skype](conferenceuris.md)的详细信息。 此 URI 是基于会议状态中心的会议 URI。 <br/> |
|**ConfInstance** <br/> |唯一标识符  <br/> ||区分定期会议的实例的标识符。 每个定期会议实例具有相同的 ConferenceURI，但 ConfInstance 不同值。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |外  <br/> |会议服务器会议 URI 相关到此会话中。 请参阅[ConferenceUris 表中的业务服务器 2015 Skype](conferenceuris.md)的详细信息。 此 URI 是会议基于服务器的会议 URI。 对于焦点会议会话，此列将为空。 <br/> |
|**用户 Id** <br/> |int  <br/> |外  <br/> |会议会话中的某个用户的 ID。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**UserEndpointId** <br/> |唯一标识符  <br/> ||一个 GUID，以确定终结点的实例。 例如，如果一个用户登录到不同的计算机使用相同的帐户，然后每台计算机将具有不同的终结点 id。  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外  <br/> |指示谁将呼叫者是代表用户的 ID。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**ReferredById** <br/> |int  <br/> |外  <br/> |由引用呼叫的用户 ID。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**UserClientVersionId** <br/> |int  <br/> |外  <br/> |会议用户使用的客户端版本。 请参阅[ClientVersions 表中的业务服务器 2015 Skype](clientversions.md)的详细信息。 <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |外  <br/> |会议服务器使用的客户端版本。 请参阅[ClientVersions 表中的业务服务器 2015 Skype](clientversions.md)的详细信息。 <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外  <br/> |若要确定已替换为当前会话的对话框的 ID 号。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外  <br/> |标识会话的 ID 号。 与**ReplacesDialogIdTime**结合使用，来唯一地标识已替换为此会话的会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||指示是否会话启动会议服务器。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||指示会议服务器是否结束会话。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||是否用户登录从内部或不。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||会话邀请的会话初始协议 (SIP) 响应代码。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||从 SIP 标头捕获的诊断 ID。  <br/> |
|**ServerId** <br/> |int  <br/> |外  <br/> |前端服务器用于此会话的 ID。 请参阅[服务器表](servers.md)的详细信息。 <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |在其中已捕获会话的池的 ID。 请参阅[Pools 表](pools.md)的详细信息。 <br/> |
|**MediationServerId** <br/> |int  <br/> |外  <br/> |使用呼叫中介服务器。 请参阅[MediationServers 表](mediationservers.md)的详细信息。 <br/> |
|**GatewayId** <br/> |int  <br/> |外  <br/> |使用呼叫的网关。 请参阅[网关表中的业务服务器 2015 Skype](gateways.md)的详细信息。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外  <br/> |使用呼叫边缘服务器。 请参阅[EdgeServers 表中的业务服务器 2015 Skype](edgeservers.md)的详细信息。 <br/> |
|**ContentTypeId** <br/> |int  <br/> |外  <br/> |会话中使用的内容类型。 请参阅[ContentTypes 表中的业务服务器 2015 Skype](contenttypes.md)的详细信息。 <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一个 INVITE 请求的时间。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**响应时间** <br/> |datetime  <br/> ||第一个 SIP 响应的时间。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||当在会话结束的时间。  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |外  <br/> |包含[UriTypes 表](uritypes.md)中的 MCU URI 类型值。 此字段用于提高查询性能。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**UserFlag** <br/> |smallint  <br/> || 位集中，指示用户属性。 列出以下属性定义了： <br/>  与桌面电话集成-1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || 位集中指示呼叫属性。 列出以下属性定义了： <br/>  重试的会话-1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   
\*对于大多数会话 SessionIdSeq 具有 1 的值。 如果完全同时启动多个会话，一个 SessionIdSeq 将 1 的另一个将为 2，依此类推。
  

