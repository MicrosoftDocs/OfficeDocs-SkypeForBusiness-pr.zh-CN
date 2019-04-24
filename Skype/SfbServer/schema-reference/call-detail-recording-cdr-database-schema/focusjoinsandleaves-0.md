---
title: FocusJoinsAndLeaves 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves 视图存储信息加入和离开一个会议信息。 每个会议加入和离开会议的用户每次写入 record 所表示此视图中。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 4fa6a2ec043c5f9746a14d5214be9ad531159cd7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213674"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves 视图
 
FocusJoinsAndLeaves 视图存储信息加入和离开一个会议信息。 每个会议加入和离开会议的用户每次写入 record 所表示此视图中。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议实例的时间。 与 SessionIdSeq 结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |若要确定会议实例的 ID 号。 与 SessionIdTime 结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |已捕获其会议加入/离开信息的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |已捕获其会议加入/离开信息的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |已捕获其会议加入/离开信息的用户的租户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**UserEndpointId** <br/> |唯一标识符  <br/> |已捕获其会议加入/离开信息的用户的唯一标识符。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |已捕获其会议加入/离开信息的用户使用的客户端的版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |已捕获其会议加入/离开信息的用户使用的客户端。 有关详细信息，请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |已捕获其会议加入/离开信息的用户使用的客户端的类别的名称。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |表示不论用户是内部用户的位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |如果用户登录在多个计算机或设备同时，使用 UserInstance 来唯一标识用户/设备组合。  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP 会话的对话 ID。 格式为： 对话框; 从标记; 到标记。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |用户加入会议的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |用户离开会议的时间。  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |在会议中，如演示者或与会者的用户的角色。  <br/> |
   

