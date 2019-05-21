---
title: SessionDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 每条记录表示一个对等会话, 可以是 VoIP-VoIP 电话呼叫、两方 IM 会话或其他类型的会话。 你可以使用 Media 表执行表联接, 以查找此会话中涉及的每个媒体的详细信息。
ms.openlocfilehash: d6c0d68cf5b8efd83cc764e74a56621cdd591ac1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295802"
---
# <a name="sessiondetails-table"></a>SessionDetails 表
 
每条记录表示一个对等会话, 可以是 VoIP-VoIP 电话呼叫、两方 IM 会话或其他类型的会话。 你可以使用[Media 表](media.md)执行表联接, 以查找此会话中涉及的每个媒体的详细信息。
  
请注意, IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 字段已从 Skype for business Server 2015 中使用的 SessionDetails 表中删除。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会话。 * 有关详细信息, 请参阅[Skype for business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**True&correlationid** <br/> |标识符  <br/> ||用于关联多个会话的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外表  <br/> |标识由当前会话替换的对话框的 ID 号。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外表  <br/> |标识会话的 ID 号。 与**ReplacesDialogIdTime**结合使用以唯一标识此会话替换的会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**User1Id** <br/> |int  <br/> |外表  <br/> |会话中一个用户的 ID。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**User2Id** <br/> |int  <br/> |外表  <br/> |会话中其他用户的 ID。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**User1EndpointId** <br/> |标识符  <br/> ||标识会话中第一个用户使用的终结点的 GUID。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**User2EndpointId** <br/> |标识符  <br/> ||标识会话中第二用户使用的终结点的 GUID。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**TargetUserId** <br/> |int  <br/> |外表  <br/> |SIP 请求中的原始用户 URI。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**SessionStartedById** <br/> |int  <br/> |外表  <br/> |启动会话的用户的 ID。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外表  <br/> |指明呼叫者代表的用户的 ID。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**ReferredById** <br/> |int  <br/> |外表  <br/> |按呼叫者引用的用户的 ID。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**ServerId** <br/> |int  <br/> |外表  <br/> |用于此会话的前端服务器的 ID。 有关详细信息, 请参阅[服务器表](servers.md)。 <br/> |
|**PoolId** <br/> |int  <br/> |外表  <br/> |捕获会话的池的 ID。 有关详细信息, 请参阅[pool 表](pools.md)。 <br/> |
|**ContentTypeID** <br/> |int  <br/> |外表  <br/> |会话中使用的内容类型。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ContentTypes 表](contenttypes.md)。 <br/> |
|**User1ClientVerId** <br/> |int  <br/> |外表  <br/> |User1 使用的客户端版本。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ClientVersions 表](clientversions.md)。 <br/> |
|**User2ClientVerId** <br/> |int  <br/> |外表  <br/> |用户2使用的客户端版本。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ClientVersions 表](clientversions.md)。 <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |外表  <br/> |由 User1 使用的边缘服务器。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 EdgeServers 表](edgeservers.md)。 <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |外表  <br/> |由服务者使用的边缘服务器。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 EdgeServers 表](edgeservers.md)。 <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||User1 是否从内部登录。  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||2/2 是否已从内部登录。  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一次邀请请求的时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||对第一个邀请消息的答复时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||会议邀请的 SIP 响应代码。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||从 SIP 标题捕获的诊断 ID。  <br/> |
|**CallPriority** <br/> |int  <br/> |外表  <br/> |通话优先级。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 CallPriorities 表](callpriorities.md)。 <br/> |
|**User1MessageCount** <br/> |int  <br/> ||在会话期间由 User1 发送的消息数。  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||会话期间由操作者发送的邮件数。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||会话结束时的时间。  <br/> |
|**MediaTypes** <br/> |int  <br/> ||指示此会话的媒体类型的位集。 列出的是以下类型的定义:  <br/> 1-IM  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-音频  <br/> 32-视频  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||指示 User1 属性的位集。 列出了以下属性定义:  <br/> 0x01-与桌面电话集成  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||指示 "工作 2" 属性的位集。 列出了以下属性定义:  <br/> 0x01-与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||指示通话属性的位集。 列出了以下属性定义:  <br/> 0x01-重试会话  <br/> 0x02-代表响应组的代理发出的呼叫  <br/> |
|**过** <br/> |bit  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |从中  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   
\*对于大多数会话, SessionIdSeq 将具有值1。 如果多个会话的开始时间完全相同, 则一个会话的 SessionIdSeq 将为 1, 而另一个会话将为 2, 依此类推。
  

