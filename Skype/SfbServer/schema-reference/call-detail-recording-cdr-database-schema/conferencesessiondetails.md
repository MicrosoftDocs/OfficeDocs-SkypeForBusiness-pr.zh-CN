---
title: ConferenceSessionDetails 视图
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails 视图可存储有关多方会话的信息。 每个记录表示一个会议会话，它可以是具有会议状态中心的会话，也可以是具有特定会议服务器的会话。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 49d351030019d6d42862352913b90af68191c19a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590086"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails 视图
 
ConferenceSessionDetails 视图可存储有关多方会话的信息。 每个记录表示一个会议会话，它可以是具有会议状态中心的会话，也可以是具有特定会议服务器的会话。 此视图在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |用于标识会话的 ID 号。 与 SessionIdTime 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一个 INVITE 请求的时间。此字段通常用从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)   <br/> |会议的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)   <br/> |会议 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |区分各个定期会议实例的标识符。每个定期会议实例的 ConferenceURI 都相同，但具有不同的 ConfInstance 值。  <br/> |
|**McuConferenceUri** <br/> |nvarchar (450)   <br/> |会议服务器的 URI。  <br/> |
|**McuConferenceUriType** <br/> |nvarchar (256)   <br/> |会议服务器 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**UserUri** <br/> |nvarchar (450)   <br/> |会话所涉及的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar (256)   <br/> |已作为会话的一部分的用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**UserTenant** <br/> |nvarchar (256)   <br/> |已作为会话的一部分的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |已作为会话的一部分的用户的唯一标识符。  <br/> |
|**EndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar (256)   <br/> |会议服务器的版本。  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |会议服务器的类型。 有关详细信息， [请参阅 UserAgentDef](useragentdef.md) 表。 <br/> |
|**ConferenceCategory** <br/> |nvarchar (64)   <br/> |会议服务器类别。  <br/> |
|**UserClientVersion** <br/> |nvarchar (256)   <br/> |参与会话的用户所使用的客户端的版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |参与会话的用户所使用的客户端。 有关详细信息， [请参阅 UserAgentDef](useragentdef.md) 表。 <br/> |
|**UserClientCategory** <br/> |nvarchar (64)   <br/> |已作为会话的一部分的用户所使用的客户端的类别名称。  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)   <br/> |作为启动会话的主体的用户的 URI。  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar (256)   <br/> |代表启动会话的用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar (256)   <br/> |代表启动会话的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**ReferredByUri** <br/> |nvarchar (450)   <br/> |提交会话的用户的 URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar (256)   <br/> |提交会话的用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**ReferredByUriTenant** <br/> |nvarchar (256)   <br/> |提交会话的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**DialogId** <br/> |varstring (775)   <br/> |SIP 对话 ID。格式如下：  <br/> :d ialog;from-tag;to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |用于标识由当前会话取代的对话的 ID 号。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |用于标识会话的 ID 号。 与 ReplaceDialogIdTime 结合使用来唯一地标识此会话替换的会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**ReplacesDialogId** <br/> |varchar (775)   <br/> |会话取代的 SIP 对话 ID。格式如下：  <br/> dialog;from-tag;to-tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |指示会议服务器是否已启动会话。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |指示会议服务器是否已结束会话。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |指示用户是否是从内部网络登录的。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |对第一个 INVITE 消息的响应时间。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**ResponseCode** <br/> |int  <br/> |会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从会话 SIP 标头捕获的诊断 ID。  <br/> |
|**ContentType** <br/> |nvarchar (256)   <br/> |会话的内容类型。  <br/> |
|**FrontEnd** <br/> |nvarchar (256)   <br/> |捕获会话数据的前端服务器的 FQDN。  <br/> |
|**Pool** <br/> |nvarchar (256)   <br/> |已捕获会话的数据的池的 FQDN。  <br/> |
|**MediationServer** <br/> |nvarchar (256)   <br/> |参与会话的用户所使用的中介服务器。  <br/> |
|**网关** <br/> |nvarchar (256)   <br/> |参与会话的用户所使用的网关。  <br/> |
|**EdgeServer** <br/> |nvarchar (256)   <br/> |参与会话的用户所使用的边缘服务器的 FQDN。  <br/> |
|**UserFlag** <br/> |smallint  <br/> |指示参与会话的用户的属性。以下是允许的属性定义：  <br/> 0x01 - 与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> |指示呼叫属性。以下是允许的属性定义：  <br/> 0x01 - 重试会话  <br/> 0x02 - 代表响应组的代理进行的呼叫  <br/> |
   

