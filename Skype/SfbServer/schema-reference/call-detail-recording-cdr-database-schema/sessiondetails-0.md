---
title: SessionDetails 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails 视图存储有关对等会话的信息，这些会话可能是 VoIP-VoIP 电话呼叫、两方 IM 会话或其他类型的会话。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: f1d0d68fe152f277c02c53fd87afdb0ea4e4ab0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814910"
---
# <a name="sessiondetails-view"></a>SessionDetails 视图
 
SessionDetails 视图存储有关对等会话的信息，这些会话可能是 VoIP-VoIP 电话呼叫、两方 IM 会话或其他类型的会话。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 表中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一次邀请请求的时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。  <br/> |
|**FromUri** <br/> |nvarchar （450）  <br/> |启动会话的用户的 URI。  <br/> |
|**ToUri** <br/> |nvarchar （450）  <br/> |加入会话的用户的 URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |启动会话的用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |加入会话的用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**FromTenant** <br/> |nvarchar （450）  <br/> |启动会话的用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |加入会话的用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**FromEndpointId** <br/> |标识符  <br/> |启动会话的用户的终结点的唯一标识符。  <br/> |
|**ToEndpointId** <br/> |标识符  <br/> |加入会话的用户的终结点的唯一标识符。  <br/> |
|**EndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|**FromMessageCount** <br/> |int  <br/> |启动会话的用户发送的消息数。  <br/> |
|**ToMessageCount** <br/> |int  <br/> |加入会话的用户发送的消息数。  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |启动会话的用户所使用的客户端版本。  <br/> |
|**FromClientType** <br/> |int  <br/> |启动会话的用户所使用的客户端。 有关详细信息，请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**FromClientCategory** <br/> |nvarchar （64）  <br/> |启动会话的用户所使用的客户端类别的名称。  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |加入会话的用户使用的客户端版本  <br/> |
|**ToClientType** <br/> |int  <br/> |加入会话的用户所使用的客户端。 有关详细信息，请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**ToClientCategory** <br/> |nvarchar （64）  <br/> |加入会话的用户所使用的客户端类别的名称。  <br/> |
|**TargetUri** <br/> |nvarchar （450）  <br/> |会话的目标用户的 URI。  <br/> |
|**TargetUriType** <br/> |nvarchar （450）  <br/> |会话的目标用户的 URI 的类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**OnBehalfOfUri** <br/> |nvarchar （450）  <br/> |已代表其启动会话的用户的 URI。  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |已代表其启动会话的用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |其代表启动会话的用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**ReferredByUri** <br/> |nvarchar （450）  <br/> |引用会话的用户的 URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |引用会话的用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |引用会话的用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**DialogId** <br/> |varchar （775）  <br/> |SIP 对话框 ID。 格式为：  <br/> 对话框; 从-标签; 到-标记  <br/> |
|**True&correlationid** <br/> |标识符  <br/> |用于关联多个会话的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |会话替换的对话的时间。 与 ReplaceDialogIdSeq 结合使用以唯一标识由会话替换的对话框。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 ReplaceDialogIdTime 结合使用以唯一标识由会话替换的对话框。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**ReplacesDialogId** <br/> |varchar （775）  <br/> |会话将替换的 SIP 对话框 ID。 格式为：  <br/> 对话框; 从-标签; 到-标记  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |对第一个邀请消息的答复时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。  <br/> |
|**ResponseCode** <br/> |int  <br/> |会议邀请的 SIP 响应代码。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从 SIP 标题捕获的诊断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |会话的内容类型。  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |捕获会话的数据的前端服务器的 FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |捕获会话的数据的池的 FQDN。  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |启动会话的用户所使用的边缘服务器的 FQDN。  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |启动会话的用户所使用的边缘服务器的 FQDN  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |指示启动会话的用户是否从内部网络登录。  <br/> |
|**IsToInternal** <br/> |bit  <br/> |指示加入会话的用户是否从内部网络登录。  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |会话的调用优先级。  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |指示启动会话的用户的属性。 允许以下属性定义：  <br/> 0x01-与桌面电话集成  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |指示启动会话的用户的属性。 允许以下属性定义：  <br/> 0x01-与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> |指示通话属性。 允许以下属性定义：  <br/> 0x01-重试会话  <br/> 0x02-代表响应组的代理发出的呼叫  <br/> |
|**位置** <br/> |varchar （max）  <br/> |紧急电话的位置。  <br/> |
|**LastModifiedTime** <br/> |从中  <br/> |供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   

