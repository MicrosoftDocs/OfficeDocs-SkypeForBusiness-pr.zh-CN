---
title: SessionDetails 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails view 存储有关对等会话，这可能是 Voip-voip 电话呼叫、 双方 IM 会话或其他类型的会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 9c94c106d8a290dfd81a57d1674b3fac0fa74642
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930621"
---
# <a name="sessiondetails-view"></a>SessionDetails 视图
 
SessionDetails view 存储有关对等会话，这可能是 Voip-voip 电话呼叫、 双方 IM 会话或其他类型的会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)表以了解详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一个 INVITE 请求的时间。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |启动会话的用户的 URI。  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |加入会话的用户的 URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |启动会话的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |加入会话的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |启动会话租户的用户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |加入会话的用户的租户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**FromEndpointId** <br/> |唯一标识符  <br/> |启动会话的用户的终结点的唯一标识符。  <br/> |
|**ToEndpointId** <br/> |唯一标识符  <br/> |加入会话的用户的终结点的唯一标识符。  <br/> |
|**EndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|**FromMessageCount** <br/> |int  <br/> |启动会话的用户发送的消息数。  <br/> |
|**ToMessageCount** <br/> |int  <br/> |加入会话的用户发送的消息数。  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |使用由用户启动会话的客户端版本。  <br/> |
|**FromClientType** <br/> |int  <br/> |使用客户端用户启动会话。 请参阅[UserAgentDef 表](useragentdef.md)的详细信息。 <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |使用由用户启动会话的客户端的类别的名称。  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |使用用户加入会话的客户端版本  <br/> |
|**ToClientType** <br/> |int  <br/> |使用客户端用户加入会话。 请参阅[UserAgentDef 表](useragentdef.md)的详细信息。 <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |使用用户加入会话的客户端的类别的名称。  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |会话的目标用户的 URI。  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |会话的目标用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |代表启动会话的用户的 URI。  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |代表启动会话的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |用户的租户所在代表启动会话的。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |引用会话的用户的 URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |引用会话的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |引用会话租户的用户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP 对话框 id。 格式为：  <br/> 对话框; 从标记; 到标记  <br/> |
|**CorrelationId** <br/> |唯一标识符  <br/> |用于关联多个会话的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |已由会话取代对话框的时间。 与 ReplaceDialogIdSeq 结合使用，来唯一地标识会话替换对话框。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 ReplaceDialogIdTime 结合使用，来唯一地标识会话替换对话框。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP 会话替换的对话 ID。 格式为：  <br/> 对话框; 从标记; 到标记  <br/> |
|**响应时间** <br/> |datetime  <br/> |对第一个 INVITE 消息的响应时间。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**ResponseCode** <br/> |int  <br/> |会话邀请的 SIP 响应代码。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从 SIP 标头捕获的诊断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |会话内容的类型。  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |已捕获会话数据的前端服务器的 FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |已捕获会话数据的池的 FQDN。  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |启动会话的用户使用的边缘服务器的 FQDN。  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |启动会话的用户使用的边缘服务器的 FQDN  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |指示启动会话的用户是否可以从内部网络登录。  <br/> |
|**IsToInternal** <br/> |bit  <br/> |指示加入会话的用户是否可以从内部网络登录。  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |呼叫会话的优先级。  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |指示启动会话的用户的属性。 允许以下属性定义：  <br/> 0x01-与桌面电话集成  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |指示启动会话的用户的属性。 允许以下属性定义：  <br/> 0x01-与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> |指示呼叫属性。 允许以下属性定义：  <br/> 0x01-重试会话  <br/> 0x02-代表响应组代理进行的呼叫  <br/> |
|**位置** <br/> |varchar(max)  <br/> |紧急呼叫的位置。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

