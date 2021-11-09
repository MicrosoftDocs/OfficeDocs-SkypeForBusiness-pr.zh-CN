---
title: McuJoinsAndLeaves 视图
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves 视图存储有关用户加入和离开某个会议服务器的信息。 此视图中的每条记录都包含有关用户加入或离开与会议服务器的组合的呼叫详细信息。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 00871f86b258df69959fa90c4158461db6d6405b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844975"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves 视图
 
McuJoinsAndLeaves 视图存储有关用户加入和离开某个会议服务器的信息。 此视图中的每条记录都包含有关用户加入或离开与会议服务器的组合的呼叫详细信息。 此视图在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议实例的时间。 与 SessionIdSeq 结合使用来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |用于标识会议实例的 ID 号。 与 SessionIdTime 结合使用来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**McuUri** <br/> |nvarchar (256)   <br/> |用户连接到的会议服务器的 URI。  <br/> |
|**McuUriType** <br/> |nvarchar (256)   <br/> |用户连接到的会议服务器的 URI。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**UserUri** <br/> |nvarchar (450)   <br/> |已捕获其会议服务器加入/离开信息的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar (256)   <br/> |已捕获其会议服务器加入/离开信息的用户的 URI 类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**UserTenant** <br/> |nvarchar (256)   <br/> |已捕获其会议服务器加入/离开信息的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**UserClientVersion** <br/> |nvarchar (256)   <br/> |已捕获其会议服务器加入/离开信息的用户所使用的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |已捕获其会议服务器加入/离开信息的用户所使用的客户端。 有关详细信息， [请参阅 UserAgentDef](useragentdef.md) 表。 <br/> |
|**UserClientCategory** <br/> |nvarchar (64)   <br/> |已捕获其会议服务器加入/离开信息的用户所使用的客户端类别的名称。  <br/> |
|**McuUserInstance** <br/> |int  <br/> |唯一标识同时登录到多台设备的用户的用户/设备组合。  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |表示用户是否为内部用户的位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |用于标识会话的 ID 号。 与 SessionIdTime 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**DialogId** <br/> |varchar (775)   <br/> |会话的 SIP 对话 ID。格式为：dialog;from-tag;to-tag。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |用户加入会议服务器的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |用户离开会议服务器的时间。  <br/> |
   

