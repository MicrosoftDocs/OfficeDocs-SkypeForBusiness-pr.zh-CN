---
title: McuJoinsAndLeaves 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves 视图存储信息用户加入和离开一个会议服务器的信息。 在此视图中的每条记录包含呼叫详细信息的用户加入或离开和会议服务器的一个组合。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: db759e324689cfbad92389f30c8fd632c24ebd5e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892806"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves 视图
 
McuJoinsAndLeaves 视图存储信息用户加入和离开一个会议服务器的信息。 在此视图中的每条记录包含呼叫详细信息的用户加入或离开和会议服务器的一个组合。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议实例的时间。 与 SessionIdSeq 结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |若要确定会议实例的 ID 号。 与 SessionIdTime 结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |用户连接到会议服务器的 URI。  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |用户连接到会议服务器的 URI。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |已捕获其会议服务器加入/离开信息的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |已捕获其会议服务器加入/离开信息的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |已捕获其会议服务器加入/离开信息的用户的租户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |已捕获其会议服务器加入/离开信息的用户使用的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |已捕获其会议服务器加入/离开信息的用户使用的客户端。 请参阅[UserAgentDef 表](useragentdef.md)的详细信息。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |已捕获其会议服务器加入/离开信息的用户使用的客户端的类别的名称。  <br/> |
|**McuUserInstance** <br/> |int  <br/> |唯一标识同时登录到多个设备的用户的用户/设备组合。  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |表示不论用户是内部用户的位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP 会话的对话 ID。 格式为： 对话框; 从标记; 到标记。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |用户加入的会议服务器的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |用户离开会议服务器的时间。  <br/> |
   

