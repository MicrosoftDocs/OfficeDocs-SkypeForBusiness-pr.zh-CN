---
title: Skype for Business Server 2015 中的 ConferenceSessionDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 每个记录表示一个会议会话, 该会话可以是与焦点的会话, 也可以是与特定的会议服务器的会话。
ms.openlocfilehash: 40216d159c9d52dcf8c22f7fe7b915255ed0f741
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296439"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ConferenceSessionDetails 表
 
每个记录表示一个会议会话, 该会话可以是与焦点的会话, 也可以是与特定的会议服务器的会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |从中  <br/> |主、外部  <br/> |会话请求的时间;与**SessionIdSeq**结合使用以唯一标识会议会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会议会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外表  <br/> |与此会话相关的焦点会议 URI。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ConferenceUris 表](conferenceuris.md)。 此 URI 是基于焦点的会议 URI。 <br/> |
|**ConfInstance** <br/> |标识符  <br/> ||区分定期会议的实例的标识符。 每个定期会议实例具有相同的 ConferenceURI, 但具有不同的 ConfInstance 值。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |外表  <br/> |与此会话相关的会议服务器会议 URI。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ConferenceUris 表](conferenceuris.md)。 此 URI 是基于会议服务器的会议 URI。 对于聚焦会议会话, 此列将为 null。 <br/> |
|**UserId** <br/> |int  <br/> |外表  <br/> |会议会话中一个用户的 ID。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**UserEndpointId** <br/> |标识符  <br/> ||标识终结点实例的 GUID。 例如, 如果一个用户使用同一帐户登录到不同的计算机, 则每台计算机都将具有不同的终结点 ID。  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外表  <br/> |指明呼叫者代表的用户的 ID。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**ReferredById** <br/> |int  <br/> |外表  <br/> |按呼叫者引用的用户的 ID。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**UserClientVersionId** <br/> |int  <br/> |外表  <br/> |会议用户使用的客户端版本。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ClientVersions 表](clientversions.md)。 <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |外表  <br/> |会议服务器使用的客户端版本。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ClientVersions 表](clientversions.md)。 <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外表  <br/> |标识由当前会话替换的对话框的 ID 号。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外表  <br/> |标识会话的 ID 号。 与**ReplacesDialogIdTime**结合使用以唯一标识此会话替换的会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||指示会议服务器是否已启动会话。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||指示会议服务器是否已结束会话。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||用户是否从内部登录。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||会话初始协议 (SIP) 响应代码到会话邀请。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||从 SIP 标题捕获的诊断 ID。  <br/> |
|**ServerId** <br/> |int  <br/> |外表  <br/> |用于此会话的前端服务器的 ID。 有关详细信息, 请参阅[服务器表](servers.md)。 <br/> |
|**PoolId** <br/> |int  <br/> |外表  <br/> |捕获会话的池的 ID。 有关详细信息, 请参阅[pool 表](pools.md)。 <br/> |
|**MediationServerId** <br/> |int  <br/> |外表  <br/> |通话所使用的中介服务器。 有关详细信息, 请参阅[MediationServers 表](mediationservers.md)。 <br/> |
|**GatewayId** <br/> |int  <br/> |外表  <br/> |呼叫使用的网关。 有关详细信息, 请参阅[Skype For Business Server 2015 中的网关表](gateways.md)。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外表  <br/> |通话所使用的边缘服务器。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 EdgeServers 表](edgeservers.md)。 <br/> |
|**ContentTypeId** <br/> |int  <br/> |外表  <br/> |会话中使用的内容类型。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ContentTypes 表](contenttypes.md)。 <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一次邀请请求的时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||第一次 SIP 响应的时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||会话结束的时间。  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |外表  <br/> |包含[UriTypes 表](uritypes.md)中的 MCU URI 类型值。 此字段用于提高查询性能。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**UserFlag** <br/> |smallint  <br/> || 指示用户属性的位集。 列出了以下属性定义: <br/>  与桌面电话集成-1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || 指示通话属性的位集。 列出了以下属性定义: <br/>  重试会话-1 <br/> |
|**LastModifiedTime** <br/> |从中  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   
\*对于大多数会话, SessionIdSeq 将具有值1。 如果多个会话的开始时间完全相同, 则一个会话的 SessionIdSeq 将为 1, 而另一个会话将为 2, 依此类推。
  

