---
title: 在业务服务器 2015年的 Skype 的 ConferenceSessionDetails 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 每个记录都表示一个会议会话，可能是具有焦点的会话或与特定会议服务器的会话。
ms.openlocfilehash: 72f2eb11c79348ad72815be7acfd337a40d288af
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 ConferenceSessionDetails 表
 
每个记录都表示一个会议会话，可能是具有焦点的会话或与特定会议服务器的会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日期时间  <br/> |主键和外  <br/> |会话的请求; 时间与**SessionIdSeq**配合使用，以唯一标识会议会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识会议会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外  <br/> |专注与此会话相关 URI 的会议。 [业务服务器 2015年的 Skype 在 ConferenceUris 表](conferenceuris.md)的详细信息，请参阅。 此 URI 是基于焦点的会议 URI。 <br/> |
|**ConfInstance** <br/> |唯一标识符  <br/> ||区分的定期会议的实例的标识符。 每个定期会议实例具有相同但值不同的 ConfInstance ConferenceURI。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |外  <br/> |URI 与本次会议服务器会议。 [业务服务器 2015年的 Skype 在 ConferenceUris 表](conferenceuris.md)的详细信息，请参阅。 此 URI 是会议基于服务器的会议 URI。 对于焦点会议会话，此列将为空。 <br/> |
|**用户 Id** <br/> |int  <br/> |外  <br/> |在会议进程中的一个用户 ID。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**UserEndpointId** <br/> |唯一标识符  <br/> ||终结点的实例标识的 GUID。 例如，如果一个用户登录到不同计算机上使用相同的帐户，然后每个机将具有不同的终结点标识。  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外  <br/> |指示调用方是谁代表的用户的 ID。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**ReferredById** <br/> |int  <br/> |外  <br/> |由引用呼叫的用户的 ID。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**UserClientVersionId** <br/> |int  <br/> |外  <br/> |会议用户使用的客户端版本。 [业务服务器 2015年的 Skype 在 ClientVersions 表](clientversions.md)的详细信息，请参阅。 <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |外  <br/> |会议服务器所使用的客户端版本。 [业务服务器 2015年的 Skype 在 ClientVersions 表](clientversions.md)的详细信息，请参阅。 <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外  <br/> |ID 号来标识已替换为当前会话的对话框。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外  <br/> |以标识会话的 ID 号。 与**ReplacesDialogIdTime**配合使用，以唯一标识会话，此会话将被替换。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||指示是否通过会议服务器启动该会话。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||指示是否会话结束的会议服务器。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||无论用户登录从内部或不。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||会话启动协议 (SIP) 响应代码添加到会话邀请。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||从 SIP 头捕获的诊断 ID。  <br/> |
|**ServerId** <br/> |int  <br/> |外  <br/> |前端服务器用于该会话的 ID。 [服务器表](servers.md)的详细信息，请参阅。 <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |池在其中捕获会话的 ID。 [池表](pools.md)的详细信息，请参阅。 <br/> |
|**MediationServerId** <br/> |int  <br/> |外  <br/> |中介服务器使用的调用。 [MediationServers 表](mediationservers.md)的详细信息，请参阅。 <br/> |
|**GatewayId** <br/> |int  <br/> |外  <br/> |使用网关呼叫。 [业务服务器 2015年的 Skype 在网关表](gateways.md)的详细信息，请参阅。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外  <br/> |边缘服务器调用使用。 [业务服务器 2015年的 Skype 在 EdgeServers 表](edgeservers.md)的详细信息，请参阅。 <br/> |
|**ContentTypeId** <br/> |int  <br/> |外  <br/> |在会话中使用的内容类型。 [内容类型表中的业务服务器 2015 Skype](contenttypes.md)的详细信息，请参阅。 <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一次邀请请求的时间。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**响应时间** <br/> |datetime  <br/> ||第一个 SIP 响应的时间。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||在会话结束时的时间。  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |外  <br/> |包含从[UriTypes 表](uritypes.md)的 MCU URI 类型值。 此字段用于提高查询性能。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**UserFlag** <br/> |smallint  <br/> || 有些设置指示用户的属性。 下面的属性定义如下： <br/>  桌面电话-1 与集成在一起 <br/> |
|**CallFlag** <br/> |smallint  <br/> || 有些设置指示调用特性。 下面的属性定义如下： <br/>  已重试的会话-1 <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> ||供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   
\*对于大多数会话，SessionIdSeq 的值都为 1。 如果正好同时启动多个会话，其中一个 SessionIdSeq 将 1，为另一个将为 2，依次类推。
  

