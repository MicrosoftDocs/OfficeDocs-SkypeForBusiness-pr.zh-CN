---
title: ConferenceSessionDetails 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails 视图存储有关多方会话的信息。 每个记录表示一个会议会话，该会话可以是与焦点的会话，也可以是与特定的会议服务器的会话。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 3dc345c10836a34f99baa4d6a088ab152b23427d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815330"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails 视图
 
ConferenceSessionDetails 视图存储有关多方会话的信息。 每个记录表示一个会议会话，该会话可以是与焦点的会话，也可以是与特定的会议服务器的会话。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一次邀请请求的时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。  <br/> |
|**ConferenceUri** <br/> |nvarchar （450）  <br/> |会议的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |会议 URI 的类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**ConfInstance** <br/> |标识符  <br/> |区分定期会议的实例的标识符。 每个定期会议实例具有相同的 ConferenceURI，但具有不同的 ConfInstance 值。  <br/> |
|**McuConferenceUri** <br/> |nvarchar （450）  <br/> |会议服务器的 URI。  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |会议服务器 URI 的类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**UserUri** <br/> |nvarchar （450）  <br/> |会话中涉及的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |属于会话的用户的 URI 的类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |属于会话一部分的用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**UserEndpointId** <br/> |标识符  <br/> |属于会话的用户的唯一标识符。  <br/> |
|**EndTime** <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |会议服务器的版本。  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |会议服务器的类型。 有关详细信息，请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**ConferenceCategory** <br/> |nvarchar （64）  <br/> |"会议服务器" 类别。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |参与会话的用户使用的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |参与会话的用户所使用的客户端。 有关详细信息，请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**UserClientCategory** <br/> |nvarchar （64）  <br/> |参与会话的用户所使用的客户端类别的名称。  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar （450）  <br/> |已代表其启动会话的用户的 URI。  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |已代表其启动会话的用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |其代表启动会话的用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**ReferredByUri** <br/> |nvarchar （450）  <br/> |引用会话的用户的 URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |引用会话的用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |引用会话的用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**DialogId** <br/> |varstring （775）  <br/> |SIP 对话框 ID。 格式为  <br/> :d ialog; from-标记; to-标记  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |标识由当前会话替换的对话框的 ID 号。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 ReplaceDialogIdTime 结合使用以唯一标识此会话替换的会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**ReplacesDialogId** <br/> |varchar （775）  <br/> |会话将替换的 SIP 对话框 ID。 的格式为：  <br/> 对话框; 从-标签; 到-标记  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |指示会话是否由会议服务器启动。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |指示会话是否已由会议服务器结束。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |指示用户是否从内部网络登录。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |对第一个邀请消息的答复时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。  <br/> |
|**ResponseCode** <br/> |int  <br/> |会议邀请的 SIP 响应代码。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从会话 SIP 标题捕获的诊断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |会话的内容类型。  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |捕获会话的数据的前端服务器的 FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |捕获会话的数据的池的 FQDN。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |参与会话的用户使用的中介服务器。  <br/> |
|**网关** <br/> |nvarchar(256)  <br/> |参与会话的用户使用的网关。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |参与会话的用户所使用的边缘服务器的 FQDN。  <br/> |
|**UserFlag** <br/> |smallint  <br/> |指示参与会话的用户的属性。 允许以下属性定义：  <br/> 0x01-与桌面电话集成  <br/> |
|**CallFlag** <br/> |smallint  <br/> |指示通话属性。 允许以下属性定义：  <br/> 0x01-重试 Session0  <br/> x02-代表响应组的代理发出的呼叫  <br/> |
   

