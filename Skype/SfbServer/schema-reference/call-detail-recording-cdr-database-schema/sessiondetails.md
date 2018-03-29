---
title: SessionDetails 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 每个记录都表示一个对等会话，可能是两方的 IM 会话或其他类型的会话 VoIP VoIP 电话联络。 您可以执行与媒体表，以查找每个介质的详细信息在此会话中涉及的表联接。
ms.openlocfilehash: 9c6cbe0b69871aa4876777b235d14f8a7ced0e15
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sessiondetails-table"></a>SessionDetails 表
 
每个记录都表示一个对等会话，可能是两方的 IM 会话或其他类型的会话 VoIP VoIP 电话联络。 您可以执行与[媒体表](media.md)查找每个介质的详细信息在此会话中涉及的表联接。
  
请注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 字段已从 SessionDetails 表使用 Skype 业务服务器 2015年。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主键和外  <br/> |会议请求的时间。 与**SessionIdSeq**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识[对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息请参阅 session.*。 <br/> |
|**都会** <br/> |唯一标识符  <br/> ||一个 GUID 以建立多个会话之间的联系。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外  <br/> |ID 号来标识已替换为当前会话的对话框。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外  <br/> |以标识会话的 ID 号。 与**ReplacesDialogIdTime**配合使用，以唯一标识会话，此会话将被替换。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**User1Id** <br/> |int  <br/> |外  <br/> |一个会话中的用户 ID。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**User2Id** <br/> |int  <br/> |外  <br/> |会话中的其他用户的 ID。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**User1EndpointId** <br/> |唯一标识符  <br/> ||用户使用的第一个会话中的终结点标识的 GUID。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**User2EndpointId** <br/> |唯一标识符  <br/> ||第二个用户在会话中使用的终结点标识的 GUID。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**TargetUserId** <br/> |int  <br/> |外  <br/> |用户在 SIP URI 到原始请求。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**SessionStartedById** <br/> |int  <br/> |外  <br/> |启动该会话的用户的 ID。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外  <br/> |指示调用方是谁代表的用户的 ID。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**ReferredById** <br/> |int  <br/> |外  <br/> |由引用呼叫的用户的 ID。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**ServerId** <br/> |int  <br/> |外  <br/> |前端服务器用于该会话的 ID。 [服务器表](servers.md)的详细信息，请参阅。 <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |池在其中捕获会话的 ID。 [池表](pools.md)的详细信息，请参阅。 <br/> |
|**ContentTypeID** <br/> |int  <br/> |外  <br/> |在会话中使用的内容类型。 [内容类型表中的业务服务器 2015 Skype](contenttypes.md)的详细信息，请参阅。 <br/> |
|**User1ClientVerId** <br/> |int  <br/> |外  <br/> |使用用户 1 的客户端版本。 [业务服务器 2015年的 Skype 在 ClientVersions 表](clientversions.md)的详细信息，请参阅。 <br/> |
|**User2ClientVerId** <br/> |int  <br/> |外  <br/> |User2 所使用的客户端版本。 [业务服务器 2015年的 Skype 在 ClientVersions 表](clientversions.md)的详细信息，请参阅。 <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |外  <br/> |User1 使用边缘服务器。 [业务服务器 2015年的 Skype 在 EdgeServers 表](edgeservers.md)的详细信息，请参阅。 <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |外  <br/> |User2 所使用的边缘服务器。 [业务服务器 2015年的 Skype 在 EdgeServers 表](edgeservers.md)的详细信息，请参阅。 <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||是否 User1 登录从内部或不。  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||是否 User2 登录从内部或不。  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一次邀请请求的时间。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**响应时间** <br/> |datetime  <br/> ||对第一个 INVITE 消息的响应时间。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||SIP 会话邀请响应代码。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||从 SIP 头捕获的诊断 ID。  <br/> |
|**CallPriority** <br/> |int  <br/> |外  <br/> |调用优先级。 [业务服务器 2015年的 Skype 在 CallPriorities 表](callpriorities.md)的详细信息，请参阅。 <br/> |
|**User1MessageCount** <br/> |int  <br/> ||User1 通过会话期间发送的消息数。  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||User2 在会话期间发送的消息数。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||在会话结束时间。  <br/> |
|**MediaTypes** <br/> |int  <br/> ||有些设置指示此会话的媒体类型。 列出的类型的定义：  <br/> 1-IM  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-音频  <br/> 32-视频  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||有些设置指示 User1 特性。 下面的属性定义如下：  <br/> 0x01-与桌面电话集成  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||指示用户 2 特性位集中。 下面的属性定义如下：  <br/> 0x01-与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||有些设置指示调用特性。 下面的属性定义如下：  <br/> 0x01-重试会话  <br/> 0x02-代理代表响应组所做的调用  <br/> |
|**处理** <br/> |bit  <br/> ||供内部使用监视服务。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> ||供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   
\*对于大多数会话，SessionIdSeq 的值都为 1。 如果正好同时启动多个会话，其中一个 SessionIdSeq 将 1，为另一个将为 2，依次类推。
  

