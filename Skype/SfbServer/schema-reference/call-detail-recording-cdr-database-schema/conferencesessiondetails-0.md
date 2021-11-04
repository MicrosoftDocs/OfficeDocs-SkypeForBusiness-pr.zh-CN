---
title: ConferenceSessionDetails table in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 每个记录表示一个会议会话，它可以是具有会议状态中心的会话，也可以是具有特定会议服务器的会话。
ms.openlocfilehash: 087dd056dae0041ab63934b25038672a74410343
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759444"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>ConferenceSessionDetails table in Skype for Business Server 2015
 
每个记录表示一个会议会话，它可以是具有会议状态中心的会话，也可以是具有特定会议服务器的会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |主、外  <br/> |会话请求的时间；与 **SessionIdSeq** 结合使用来唯一地标识会议会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会议会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |与此会话相关的会议状态中心会议 URI。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ConferenceUris](conferenceuris.md)表。 此 URI 是基于会议状态中心的会议 URI。 <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||区分各个定期会议实例的标识符。每个定期会议实例的 ConferenceURI 都相同，但具有不同的 ConfInstance 值。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |与此会话相关的会议服务器会议 URI。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ConferenceUris](conferenceuris.md)表。 此 URI 是基于会议服务器的会议 URI。 对于会议状态中心会议会话，此列将为 null。 <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |会议会话中的一个用户的 ID。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||用于标识终结点的实例的 GUID。例如，如果一个用户使用相同帐户登录到不同的计算机上，则每台计算机将具有不同的终结点 ID。  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Foreign  <br/> |指示呼叫者所代表的用户的 ID。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**ReferredById** <br/> |int  <br/> |Foreign  <br/> |引用呼叫的用户的 ID。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Foreign  <br/> |会议用户使用的客户端版本。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ClientVersions](clientversions.md)表。 <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Foreign  <br/> |会议服务器使用的客户端版本。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ClientVersions](clientversions.md)表。 <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Foreign  <br/> |用于标识由当前会话取代的对话的 ID 号。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Foreign  <br/> |用于标识会话的 ID 号。 与 **ReplacesDialogIdTime** 结合使用来唯一地标识由此会话取代的会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||指示会话是否是由会议服务器启动的。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||指示会话是否是由会议服务器终止的。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||用户是否从内部登录。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||会话邀请的会话初始协议 (SIP) 响应代码。 此字段通常用从会话中的初始 INVITE 消息生成的数据填充。 如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||从 SIP 标头捕获的诊断 ID。  <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |用于此会话的前端服务器的 ID。 有关详细信息 [，请参阅 Servers](servers.md) 表。 <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |在其中捕获会话的池的 ID。 有关详细信息 [，请参阅 Pools](pools.md) 表。 <br/> |
|**MediationServerId** <br/> |int  <br/> |Foreign  <br/> |呼叫使用的中介服务器。 有关详细信息， [请参阅 MediationServers](mediationservers.md) 表。 <br/> |
|**GatewayId** <br/> |int  <br/> |Foreign  <br/> |呼叫使用的网关。 有关详细信息，请参阅[Skype for Business Server 2015](gateways.md)中的 Gateways 表。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |Foreign  <br/> |呼叫使用的边缘服务器。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 EdgeServers](edgeservers.md)表。 <br/> |
|**ContentTypeId** <br/> |int  <br/> |Foreign  <br/> |会话中使用的内容类型。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ContentTypes](contenttypes.md)表。 <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一个 INVITE 请求的时间。此字段通常用从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||第一个 SIP 响应的时间。 此字段通常用从会话中的初始 INVITE 消息生成的数据填充。 如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||会话结束的时间。  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Foreign  <br/> |包含 [UriTypes](uritypes.md)表中的 MCU URI 类型值。 此字段用于改进查询性能。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**UserFlag** <br/> |smallint  <br/> || 指示用户属性的位集。列出了以下属性定义： <br/>  与桌面电话集成 - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || 指示呼叫属性的位集。列出了以下属性定义： <br/>  重试会话 - 1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段是在 2015 年 Skype for Business Server引入的。  <br/> |
   
\* 对于大多数会话，SessionIdSeq 的值为 1。 如果多个会话完全同时启动，则一个会话的 SessionIdSeq 将为 1，另一个会话的 SessionIdSeq 将为 2，依此类推。
  

