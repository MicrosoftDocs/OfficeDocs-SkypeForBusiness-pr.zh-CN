---
title: McuJoinsAndLeaves 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves 视图存储有关用户加入和离开一个会议服务器的信息。 在此视图中的每个记录包含调用的详细信息的用户加入或离开和会议服务器的一个组合。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 77045d852708cd7d8ceb0da473032485e130ea50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves 视图
 
McuJoinsAndLeaves 视图存储有关用户加入和离开一个会议服务器的信息。 在此视图中的每个记录包含调用的详细信息的用户加入或离开和会议服务器的一个组合。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议实例的时间。 与 SessionIdSeq 配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |若要标识的会议实例的 ID 号。 与 SessionIdTime 配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |在用户连接到会议服务器的 URI。  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |在用户连接到会议服务器的 URI。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |其会议服务器加入/退出信息被捕获的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |被捕获的 URI 的用户的会议服务器加入/退出信息的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |捕获的用户的会议服务器加入/退出信息的租户。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |捕获的用户的会议服务器加入/退出信息所使用的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |客户端使用的用户的会议服务器加入/退出信息被捕获。 [UserAgentDef 表](useragentdef.md)的更多详细信息，请参阅。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |捕获客户端使用的用户的会议服务器加入/退出信息的类别的名称。  <br/> |
|**McuUserInstance** <br/> |int  <br/> |唯一地标识用户同时登录到多个设备上的用户/设备组合。  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |表示该用户是内部用户或未位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |会议请求的时间。 与 SessionIdSeq 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |以标识会话的 ID 号。 与 SessionIdTime 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP 会话的对话框 ID。 格式是： 对话; 从标记; 到标记。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |用户加入会议的服务器的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |离开会议服务器的用户的时间。  <br/> |
   

