---
title: ConferenceSessionDetails 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails 视图存储有关多方会话的信息。 每条记录代表一个会议会话，它可以是具有焦点会话或与特定会议服务器的会话。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 448b73326f7caf7657d146939eb01729e97628f9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213226"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails 视图
 
ConferenceSessionDetails 视图存储有关多方会话的信息。 每条记录代表一个会议会话，它可以是具有焦点会话或与特定会议服务器的会话。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一个 INVITE 请求的时间。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |会议的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |会议 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**ConfInstance** <br/> |唯一标识符  <br/> |区分定期会议的实例的标识符。 每个定期会议实例具有相同的 ConferenceURI，但 ConfInstance 不同值。  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |会议服务器的 URI。  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |会议服务器 URI 类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |会话所涉及的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |已作为会话一部分的类型的用户的 URI。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |已作为会话一部分的用户的租户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**UserEndpointId** <br/> |唯一标识符  <br/> |已作为会话一部分的用户的唯一标识符。  <br/> |
|**EndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |会议服务器的版本。  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |会议服务器的类型。 请参阅[UserAgentDef 表](useragentdef.md)的详细信息。 <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |会议服务器类别。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |使用用户参与会话的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |使用客户端用户参与会话。 请参阅[UserAgentDef 表](useragentdef.md)的详细信息。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |使用用户所属于会话的客户端的类别的名称。  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |代表启动会话的用户的 URI。  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |代表启动会话的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |用户的租户所在代表启动会话的。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |引用会话的用户的 URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |引用会话的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |引用会话租户的用户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP 对话框 id。 格式  <br/> ： 对话框; 从标记; 到标记  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |若要确定已替换为当前会话的对话框的 ID 号。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 ReplaceDialogIdTime 结合使用，来唯一地标识已替换为此会话的会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP 会话替换的对话 ID。 格式为：  <br/> 对话框; 从标记; 到标记  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |指示是否由会议服务器启动以来在会话。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |指示会议服务器是否已结束会话。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |指示用户是否可以从内部网络登录。  <br/> |
|**响应时间** <br/> |datetime  <br/> |对第一个 INVITE 消息的响应时间。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**ResponseCode** <br/> |int  <br/> |会话邀请的 SIP 响应代码。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从会话 SIP 标头捕获的诊断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |会话的内容类型。  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |已捕获会话数据的前端服务器的 FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |已捕获会话数据的池的 FQDN。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |参与会话的用户使用的中介服务器。  <br/> |
|**网关** <br/> |nvarchar(256)  <br/> |使用用户参与的网关会话。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |参与会话的用户使用的边缘服务器的 FQDN。  <br/> |
|**UserFlag** <br/> |smallint  <br/> |指示参与会话的用户的属性。 允许的以下属性定义：  <br/> 0x01-与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> |指示呼叫属性。 允许以下属性定义：  <br/> 0x01-重试 Session0  <br/> x02-代表响应组代理进行的呼叫  <br/> |
   

