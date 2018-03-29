---
title: SessionDetails 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails 视图存储对等会话，可能是两方的 IM 会话或其他类型的会话 VoIP VoIP 电话联络有关的信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: b13b0b184d13273c339f1ca3fa09a68687d26889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sessiondetails-view"></a>SessionDetails 视图
 
SessionDetails 视图存储对等会话，可能是两方的 IM 会话或其他类型的会话 VoIP VoIP 电话联络有关的信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议请求的时间。 与 SessionIdSeq 配合使用，以唯一标识会话。 请参阅详细信息[对话框中业务服务器 2015年的 Skype 表](dialogs.md)表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |以标识会话的 ID 号。 与 SessionIdTime 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一次邀请请求的时间。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |启动该会话的用户的 URI。  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |加入会话的用户的 URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |启动该会话的用户的 URI 类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |加入会话的用户的 URI 类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |客户端的用户启动该会话。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |客户的用户的端，加入该会话。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**FromEndpointId** <br/> |唯一标识符  <br/> |终结点启动会话的用户的唯一标识符。  <br/> |
|**ToEndpointId** <br/> |唯一标识符  <br/> |终结点的连接会话的用户的唯一标识符。  <br/> |
|**结束时间** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|**FromMessageCount** <br/> |int  <br/> |启动会话的用户发送的邮件数。  <br/> |
|**ToMessageCount** <br/> |int  <br/> |由加入该会话的用户发送的邮件数。  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |由用户启动该会话的客户端版本。  <br/> |
|**FromClientType** <br/> |int  <br/> |客户端使用的用户启动该会话。 [UserAgentDef 表](useragentdef.md)的更多详细信息，请参阅。 <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |由用户启动该会话的客户端的类别的名称。  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |用户使用者加入该会话的客户端版本  <br/> |
|**ToClientType** <br/> |int  <br/> |客户端使用的用户加入该会话。 [UserAgentDef 表](useragentdef.md)的更多详细信息，请参阅。 <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |用户使用者加入该会话的客户端的类别的名称。  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |会话的目标用户的 URI。  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |URI 的目标用户的会话的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |名义启动会话的用户的 URI。  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |名义启动会话的用户的 URI 类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |租户的用户其会话启动的代表。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |引用会话的用户的 URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |URI 引用该会话的用户的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |客户端的用户引用会话。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP 对话框 id。 格式为：  <br/> 对话; 从标记; 到标记  <br/> |
|**都会** <br/> |唯一标识符  <br/> |GUID 用于关联多个会话。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |已更换由会话的对话框的时间。 结合 ReplaceDialogIdSeq 用于唯一标识替换会话的对话框。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |以标识会话的 ID 号。 结合 ReplaceDialogIdTime 用于唯一标识替换会话的对话框。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP 会话将替换对话框 ID。 格式为：  <br/> 对话; 从标记; 到标记  <br/> |
|**响应时间** <br/> |datetime  <br/> |对第一个 INVITE 消息的响应时间。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 会话邀请响应代码。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从 SIP 头捕获的诊断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |会话的内容的类型。  <br/> |
|**前端** <br/> |nvarchar(256)  <br/> |捕获为会话数据的前端服务器的 FQDN。  <br/> |
|**池** <br/> |nvarchar(256)  <br/> |捕获数据的会话池的 FQDN。  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |边缘服务器启动该会话的用户所使用的 FQDN。  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |边缘服务器启动该会话的用户所使用的 FQDN  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |指示启动会话的用户是否可以从内部网络登录。  <br/> |
|**IsToInternal** <br/> |bit  <br/> |指示连接会话的用户是否可以从内部网络登录。  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |调用会话的优先级。  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |指示启动会话的用户的属性。 允许使用下面的属性定义：  <br/> 0x01-与桌面电话集成  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |指示启动会话的用户的属性。 允许使用下面的属性定义：  <br/> 0x01-与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> |指示调用特性。 允许使用下面的属性定义：  <br/> 0x01-重试会话  <br/> 0x02-代理代表响应组所做的调用  <br/> |
|**位置** <br/> |varchar(max)  <br/> |紧急呼叫的位置。  <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> |供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

