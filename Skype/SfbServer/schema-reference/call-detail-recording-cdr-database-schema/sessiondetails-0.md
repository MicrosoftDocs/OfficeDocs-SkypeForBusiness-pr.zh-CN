---
title: SessionDetails 视图
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails 视图存储有关点对点会话的信息，这应该是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 6a100fcd2143244bda5ad7273b5a681468ad5713
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852916"
---
# <a name="sessiondetails-view"></a>SessionDetails 视图
 
SessionDetails 视图存储有关点对点会话的信息，这应该是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。 此视图在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md) Table 中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |用于标识会话的 ID 号。 与 SessionIdTime 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一个 INVITE 请求的时间。此字段通常由从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**FromUri** <br/> |nvarchar (450)   <br/> |启动会话的用户的 URI。  <br/> |
|**ToUri** <br/> |nvarchar (450)   <br/> |加入会话的用户的 URI。  <br/> |
|**FromUriType** <br/> |nvarchar (256)   <br/> |启动会话的用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**ToUriType** <br/> |nvarchar (256)   <br/> |加入会话的用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**FromTenant** <br/> |nvarchar (450)   <br/> |启动会话的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**ToTenant** <br/> |nvarchar (256)   <br/> |加入会话的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |启动会话的用户的终结点的唯一标识符。  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |加入会话的用户的终结点的唯一标识符。  <br/> |
|**EndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|**FromMessageCount** <br/> |int  <br/> |启动会话的用户发送的消息数。  <br/> |
|**ToMessageCount** <br/> |int  <br/> |加入会话的用户发送的消息数。  <br/> |
|**FromClientVersion** <br/> |nvarchar (256)   <br/> |启动会话的用户使用的客户端的版本。  <br/> |
|**FromClientType** <br/> |int  <br/> |启动会话的用户使用的客户端。 有关详细信息， [请参阅 UserAgentDef](useragentdef.md) 表。 <br/> |
|**FromClientCategory** <br/> |nvarchar (64)   <br/> |启动会话的用户使用的客户端的类别名称。  <br/> |
|**ToClientVersion** <br/> |nvarchar (256)   <br/> |加入会话的用户使用的客户端的版本。  <br/> |
|**ToClientType** <br/> |int  <br/> |加入会话的用户使用的客户端。 有关详细信息， [请参阅 UserAgentDef](useragentdef.md) 表。 <br/> |
|**ToClientCategory** <br/> |nvarchar (64)   <br/> |加入会话的用户使用的客户端的类别名称。  <br/> |
|**TargetUri** <br/> |nvarchar (450)   <br/> |会话的目标用户的 URI。  <br/> |
|**TargetUriType** <br/> |nvarchar (450)   <br/> |会话的目标用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)   <br/> |代表启动会话的用户的 URI。  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar (256)   <br/> |代表启动会话的用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar (256)   <br/> |代表启动会话的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**ReferredByUri** <br/> |nvarchar (450)   <br/> |提交会话的用户的 URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar (256)   <br/> |提交会话的用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**ReferredByTenant** <br/> |nvarchar (256)   <br/> |提交会话的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**DialogId** <br/> |varchar (775)   <br/> |SIP 对话 ID。格式为：  <br/> dialog;from-tag;to-tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |用于关联多个会话的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |由会话取代的对话的时间。 与 ReplaceDialogIdSeq 结合起来使用，以唯一地标识由此会话取代的对话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |用于标识会话的 ID 号。 与 ReplacesDialogIdTime 结合使用来唯一地标识由该会话取代的会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**ReplacesDialogId** <br/> |varchar (775)   <br/> |会话取代的 SIP 对话 ID。格式为：  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |对第一个 INVITE 消息的响应时间。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**ResponseCode** <br/> |int  <br/> |会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从 SIP 标头捕获的诊断 ID。  <br/> |
|**ContentType** <br/> |nvarchar (256)   <br/> |会话内容的类型。  <br/> |
|**FrontEnd** <br/> |nvarchar (256)   <br/> |捕获会话数据的前端服务器的 FQDN。  <br/> |
|**Pool** <br/> |nvarchar (256)   <br/> |捕获会话数据的池的 FQDN。  <br/> |
|**FromEdgeServer** <br/> |nvarchar (256)   <br/> |启动会话的用户使用的边缘服务器的 FQDN。  <br/> |
|**ToEdgeServer** <br/> |nvarchar (256)   <br/> |启动会话的用户使用的边缘服务器的 FQDN  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |指示启动会话的用户是否从内部网络登录。  <br/> |
|**IsToInternal** <br/> |bit  <br/> |指示加入会话的用户是否从内部网络登录。  <br/> |
|**CallPriority** <br/> |nvarchar (256)   <br/> |会话的呼叫属性。  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |指示启动会话的用户的属性。允许以下属性定义：  <br/> 0x01 - 与桌面电话集成  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |指示启动会话的用户的属性。允许以下属性定义：  <br/> 0x01 - 与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> |指示呼叫属性。允许以下属性定义：  <br/> 0x01 - 重试会话  <br/> 0x02 - 代表响应组的代理进行的呼叫  <br/> |
|**位置** <br/> |varchar (max)   <br/> |紧急呼叫的位置。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |供监控服务内部使用。  <br/> 此字段是在 2015 年 Skype for Business Server引入的。  <br/> |
   

