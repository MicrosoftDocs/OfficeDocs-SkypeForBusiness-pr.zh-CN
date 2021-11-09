---
title: SessionDetails 表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 每条记录表示一个点对点会话，它可以是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。 你可以对 Media 表执行表联接，以查找此会话中涉及的每个媒体的详细信息。
ms.openlocfilehash: e7b89dc242fb3e4adec215948915218b579631ef
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863429"
---
# <a name="sessiondetails-table"></a>SessionDetails 表
 
每条记录表示一个点对点会话，它可以是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。 你可以对 Media 表执行表[](media.md)联接，以查找此会话中涉及的每个媒体的详细信息。
  
请注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 字段已从 Skype for Business Server 2015 中使用的 SessionDetails 表中删除。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会话请求的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。* 有关详细信息，请参阅 [Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||用于关联多个会话的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Foreign  <br/> |用于标识由当前会话取代的对话的 ID 号。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Foreign  <br/> |用于标识会话的 ID 号。 与 **ReplacesDialogIdTime** 结合使用来唯一地标识由此会话取代的会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**User1Id** <br/> |int  <br/> |Foreign  <br/> |会话中的一个用户的 ID。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**User2Id** <br/> |int  <br/> |Foreign  <br/> |会话中另一个用户的 ID。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||标识会话中的第一个用户所使用的终结点的 GUID。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||标识会话中的第二个用户所使用的终结点的 GUID。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**TargetUserId** <br/> |int  <br/> |Foreign  <br/> |SIP 请求中的原始目标用户 URI。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**SessionStartedById** <br/> |int  <br/> |Foreign  <br/> |启动会话的用户的 ID。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Foreign  <br/> |指示呼叫者所代表的用户的 ID。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**ReferredById** <br/> |int  <br/> |Foreign  <br/> |引用呼叫的用户的 ID。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |用于此会话的前端服务器的 ID。 有关详细信息 [，请参阅 Servers](servers.md) 表。 <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |在其中捕获会话的池的 ID。 有关详细信息 [，请参阅 Pools](pools.md) 表。 <br/> |
|**ContentTypeID** <br/> |int  <br/> |Foreign  <br/> |会话中使用的内容类型。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ContentTypes](contenttypes.md)表。 <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Foreign  <br/> |User1 使用的客户端版本。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ClientVersions](clientversions.md)表。 <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Foreign  <br/> |User2 使用的客户端版本。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ClientVersions](clientversions.md)表。 <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Foreign  <br/> |User1 使用的边缘服务器。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 EdgeServers](edgeservers.md)表。 <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Foreign  <br/> |User2 使用的边缘服务器。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 EdgeServers](edgeservers.md)表。 <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||User1 是否从内部登录。  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||User2 是否从内部登录。  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一个 INVITE 请求的时间。 此字段通常用从会话中的初始 INVITE 消息生成的数据填充。 如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。 此字段通常用从会话中的初始 INVITE 消息生成的数据填充。 如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||第一个 INVITE 消息的响应时间。 此字段通常用从会话中的初始 INVITE 消息生成的数据填充。 如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||从 SIP 标头捕获的诊断 ID。  <br/> |
|**CallPriority** <br/> |int  <br/> |Foreign  <br/> |呼叫优先级。 有关详细信息，请参阅[Skype for Business Server 2015 中的 CallPriorities](callpriorities.md)表。 <br/> |
|**User1MessageCount** <br/> |int  <br/> ||User1 在会话期间发送的消息数。  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||User2 在会话期间发送的消息数。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||会话的结束时间。  <br/> |
|**MediaTypes** <br/> |int  <br/> ||指示此会话的媒体类型的位集。下面列出了类型的定义：  <br/> 1 - IM  <br/> 2- FILE_TRANSFER  <br/> 4- REMOTE_ASSISTANCE  <br/> 8- APP_SHARING  <br/> 16- 音频  <br/> 32- 视频  <br/> 64- APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||指示 User1 属性的位集。列出了以下属性定义：  <br/> 0x01 - 与桌面电话集成  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||指示 User2 属性的位集。列出了以下属性定义：  <br/> 0x01 - 与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||指示呼叫属性的位集。列出了以下属性定义：  <br/> 0x01 - 重试会话  <br/> 0x02 - 代表响应组的代理进行的呼叫  <br/> |
|**已处理** <br/> |bit  <br/> ||供监控服务内部使用。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段是在 2015 年 Skype for Business Server引入的。  <br/> |
   
\* 对于大多数会话，SessionIdSeq 的值为 1。 如果多个会话完全同时启动，则一个会话的 SessionIdSeq 将为 1，另一个会话的 SessionIdSeq 将为 2，依此类推。
  

