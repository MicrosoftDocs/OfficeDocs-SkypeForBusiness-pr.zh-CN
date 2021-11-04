---
title: FocusJoinsAndLeaves 视图
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves 视图存储有关加入和离开某会议的信息。 每个会议在此视图中由一条在每次用户加入和离开该会议时编写的记录表示。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 6195558ec7a59e9e7605db4b56f761aec374f831
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740298"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves 视图
 
FocusJoinsAndLeaves 视图存储有关加入和离开某会议的信息。 每个会议在此视图中由一条在每次用户加入和离开该会议时编写的记录表示。 此视图在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议实例的时间。 与 SessionIdSeq 结合使用来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |用于标识会议实例的 ID 号。 与 SessionIdTime 结合使用来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**UserUri** <br/> |nvarchar (450)   <br/> |已捕获其会议加入/离开信息的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar (256)   <br/> |已捕获其会议加入/离开信息的用户的 URI 类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**UserTenant** <br/> |nvarchar (256)   <br/> |已捕获其会议加入/离开信息的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |已捕获其会议加入/离开信息的用户的唯一标识符。  <br/> |
|**UserClientVersion** <br/> |nvarchar (256)   <br/> |由已捕获其会议加入/离开信息的用户使用的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |由已捕获其会议加入/离开信息的用户使用的客户端。 有关详细信息 [，请参阅 UserAgentDef](useragentdef.md) 表。 <br/> |
|**UserClientCategory** <br/> |nvarchar (64)   <br/> |由已捕获其会议加入/离开信息的用户使用的客户端的类别名称。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |表示用户是否为内部用户的位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |如果用户同时在多台计算机或设备登录，则使用 UserInstance 来唯一地标识该用户/设备组合。  <br/> |
|**DialogId** <br/> |varchar (775)   <br/> |会话的 SIP 对话 ID。格式为：dialog;from-tag;to-tag。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |用户加入会议的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |用户离开会议的时间。  <br/> |
|**UserRole** <br/> |nvarchar (256)   <br/> |用户在会议中的角色，例如演示者或与会者。  <br/> |
   

