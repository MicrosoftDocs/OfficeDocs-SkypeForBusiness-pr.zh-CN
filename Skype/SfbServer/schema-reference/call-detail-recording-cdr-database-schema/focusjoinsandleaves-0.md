---
title: FocusJoinsAndLeaves 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves 视图存储有关连接的信息，并留下一个会议的信息。 每个会议编写用户每次加入和离开会议的记录表示在此视图中。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 3ae234977ef541ca523178f41b40f12135b16bfd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves 视图
 
FocusJoinsAndLeaves 视图存储有关连接的信息，并留下一个会议的信息。 每个会议编写用户每次加入和离开会议的记录表示在此视图中。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议实例的时间。 与 SessionIdSeq 配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |若要标识的会议实例的 ID 号。 与 SessionIdTime 配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |其会议加入/退出信息被捕获的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |被捕获的 URI 的用户的会议加入/退出信息的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |租户的用户其会议加入/退出信息被捕获。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**UserEndpointId** <br/> |唯一标识符  <br/> |其会议加入/退出信息被捕获的用户的唯一标识符。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |使用其会议加入/退出信息被捕获用户的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |客户端使用其会议加入/退出信息被捕获的用户。 有关详细信息，请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |客户端使用其会议加入/退出信息被捕获的用户类别的名称。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |表示该用户是内部用户或未位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |会议请求的时间。 与 SessionIdSeq 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |如果用户登录多台计算机或设备在同一时间，则使用 UserInstance 来唯一地标识用户/设备组合。  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP 会话的对话框 ID。 格式是： 对话; 从标记; 到标记。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |用户加入会议的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |用户离开会议的时间。  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |在会议中，与会者和演示者的用户的角色。  <br/> |
   

