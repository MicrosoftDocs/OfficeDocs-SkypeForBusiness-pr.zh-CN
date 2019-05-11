---
title: SessionDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 每条记录代表一个对等会话，它可以是 Voip-voip 电话呼叫、 双方 IM 会话或其他类型的会话。 您可以执行与要查找每一种媒体的详细信息此会话中涉及的媒体表的表联接。
ms.openlocfilehash: bd4603811dd699bfe856f7151841c5f8021c2703
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888042"
---
# <a name="sessiondetails-table"></a>SessionDetails 表
 
每条记录代表一个对等会话，它可以是 Voip-voip 电话呼叫、 双方 IM 会话或其他类型的会话。 您可以执行与要查找每一种媒体的详细信息此会话中涉及的[Media 表](media.md)的表联接。
  
请注意，删除 IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 字段已删除从业务服务器 2015 Skype 中使用的 SessionDetails 表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识 session.* [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**CorrelationId** <br/> |唯一标识符  <br/> ||一个用于关联多个会话的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外  <br/> |若要确定已替换为当前会话的对话框的 ID 号。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外  <br/> |标识会话的 ID 号。 与**ReplacesDialogIdTime**结合使用，来唯一地标识已替换为此会话的会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**User1Id** <br/> |int  <br/> |外  <br/> |会话中的某个用户的 ID。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**User2Id** <br/> |int  <br/> |外  <br/> |会话中的其他用户的 ID。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**User1EndpointId** <br/> |唯一标识符  <br/> ||标识会话中使用的第一个用户的终结点的 GUID。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**User2EndpointId** <br/> |唯一标识符  <br/> ||标识会话中的第二个用户所使用的终结点的 GUID。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**TargetUserId** <br/> |int  <br/> |外  <br/> |原始收件人 SIP 请求中的用户 URI。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**SessionStartedById** <br/> |int  <br/> |外  <br/> |启动会话的用户的 ID。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外  <br/> |指示谁将呼叫者是代表用户的 ID。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**ReferredById** <br/> |int  <br/> |外  <br/> |由引用呼叫的用户 ID。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**ServerId** <br/> |int  <br/> |外  <br/> |前端服务器用于此会话的 ID。 请参阅[服务器表](servers.md)的详细信息。 <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |在其中已捕获会话的池的 ID。 请参阅[Pools 表](pools.md)的详细信息。 <br/> |
|**ContentTypeID** <br/> |int  <br/> |外  <br/> |会话中使用的内容类型。 请参阅[ContentTypes 表中的业务服务器 2015 Skype](contenttypes.md)的详细信息。 <br/> |
|**User1ClientVerId** <br/> |int  <br/> |外  <br/> |使用 User1 的客户端版本。 请参阅[ClientVersions 表中的业务服务器 2015 Skype](clientversions.md)的详细信息。 <br/> |
|**User2ClientVerId** <br/> |int  <br/> |外  <br/> |User2 使用的客户端版本。 请参阅[ClientVersions 表中的业务服务器 2015 Skype](clientversions.md)的详细信息。 <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |外  <br/> |使用 User1 的边缘服务器。 请参阅[EdgeServers 表中的业务服务器 2015 Skype](edgeservers.md)的详细信息。 <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |外  <br/> |User2 使用的边缘服务器。 请参阅[EdgeServers 表中的业务服务器 2015 Skype](edgeservers.md)的详细信息。 <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||是否 User1 是从内部登录或不。  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||是否 User2 是从内部登录或不。  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一个 INVITE 请求的时间。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**响应时间** <br/> |datetime  <br/> ||对第一个 INVITE 消息的响应时间。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||会话邀请的 SIP 响应代码。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||从 SIP 标头捕获的诊断 ID。  <br/> |
|**CallPriority** <br/> |int  <br/> |外  <br/> |调用优先级。 请参阅[CallPriorities 表中的业务服务器 2015 Skype](callpriorities.md)的详细信息。 <br/> |
|**User1MessageCount** <br/> |int  <br/> ||User1 在会话期间发送的消息数。  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||User2 在会话期间发送的消息数。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||在会话结束的时间。  <br/> |
|**MediaTypes** <br/> |int  <br/> ||位集中指示此会话的媒体类型。 列出了的类型的定义：  <br/> 1-IM  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-音频  <br/> 32-视频  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||位集中指示 User1 属性。 列出以下属性定义了：  <br/> 0x01-与桌面电话集成  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||位集中指示 User2 属性。 列出以下属性定义了：  <br/> 0x01-与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||位集中指示呼叫属性。 列出以下属性定义了：  <br/> 0x01-重试会话  <br/> 0x02-代表响应组代理进行的呼叫  <br/> |
|**处理** <br/> |bit  <br/> ||供监控服务内部使用。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   
\*对于大多数会话 SessionIdSeq 具有 1 的值。 如果完全同时启动多个会话，一个 SessionIdSeq 将 1 的另一个将为 2，依此类推。
  

