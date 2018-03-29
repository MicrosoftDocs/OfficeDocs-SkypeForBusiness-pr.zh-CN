---
title: ConferenceSessionDetails 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails 视图存储有关多方会话信息。 每个记录都表示一个会议会话，可能是具有焦点的会话或与特定会议服务器的会话。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 8e81f33a68fc90a589f4d3574f9ca3070076c479
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails 视图
 
ConferenceSessionDetails 视图存储有关多方会话信息。 每个记录都表示一个会议会话，可能是具有焦点的会话或与特定会议服务器的会话。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议请求的时间。 与 SessionIdSeq 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |以标识会话的 ID 号。 与 SessionIdTime 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一次邀请请求的时间。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |该会议的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |会议 URI 的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**ConfInstance** <br/> |唯一标识符  <br/> |区分的定期会议的实例的标识符。 每个定期会议实例具有相同但值不同的 ConfInstance ConferenceURI。  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |会议服务器的 URI。  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |会议服务器 URI 类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |参与该会话的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |URI 的用户的类型，其是会话的一部分。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |租户的用户，它的是会话的一部分。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**UserEndpointId** <br/> |唯一标识符  <br/> |用户的唯一标识符，它的是会话的一部分。  <br/> |
|**结束时间** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |会议服务器的版本。  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |会议服务器的类型。 [UserAgentDef 表](useragentdef.md)的详细信息，请参阅。 <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |会议服务器类别。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |用户使用者参与该会话的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |客户端用户使用的会话参加。 [UserAgentDef 表](useragentdef.md)的更多详细信息，请参阅。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |客户端使用的用户会话的一部分的类别的名称。  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |名义启动会话的用户的 URI。  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |名义启动会话的用户的 URI 类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |租户的用户其会话启动的代表。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |引用会话的用户的 URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |URI 引用该会话的用户的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |客户端的用户引用会话。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP 对话框 id。 格式是  <br/> ： 对话; 从标记; 到标记  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |ID 号来标识已替换为当前会话的对话框。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |以标识会话的 ID 号。 与 ReplaceDialogIdTime 配合使用，以唯一标识会话，此会话将被替换。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP 会话将替换对话框 ID。 格式是：  <br/> 对话; 从标记; 到标记  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |指示是否已通过会议服务器启动会话。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |指示会议服务器是否已终止会话。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |指示用户是否可以从内部网络登录。  <br/> |
|**响应时间** <br/> |datetime  <br/> |对第一个 INVITE 消息的响应时间。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 会话邀请响应代码。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从会话 SIP 头捕获的诊断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |会话的内容类型。  <br/> |
|**前端** <br/> |nvarchar(256)  <br/> |捕获为会话数据的前端服务器的 FQDN。  <br/> |
|**池** <br/> |nvarchar(256)  <br/> |捕获数据的会话池的 FQDN。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |中介服务器参与会话的用户使用。  <br/> |
|**网关** <br/> |nvarchar(256)  <br/> |参加的用户使用网关会话。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |边缘服务器参与会话的用户所使用的 FQDN。  <br/> |
|**UserFlag** <br/> |smallint  <br/> |表示参与该会话的用户的属性。 下面的属性定义允许：  <br/> 0x01-与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> |指示调用特性。 允许使用下面的属性定义：  <br/> 0x01-重试 Session0  <br/> x02-代理代表响应组所做的调用  <br/> |
   

