---
title: FocusJoinsAndLeaves 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves 视图存储有关加入和离开一次会议的信息的信息。 每个会议在用户加入和离开会议时编写的记录在此视图中表示。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: f739ae390b636913d96b49dd516d2618c72515e6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296215"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves 视图
 
FocusJoinsAndLeaves 视图存储有关加入和离开一次会议的信息的信息。 每个会议在用户加入和离开会议时编写的记录在此视图中表示。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议实例的时间。 与 SessionIdSeq 结合使用以唯一标识会议实例。 有关详细信息, 请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会议实例的 ID 号。 与 SessionIdTime 结合使用以唯一标识会议实例。 有关详细信息, 请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |已捕获其会议加入/离开信息的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |已捕获其会议加入/离开信息的用户的 URI 类型。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |已捕获其会议加入/离开信息的用户的租户。 有关详细信息, 请参阅[租户表](tenants.md)。 <br/> |
|**UserEndpointId** <br/> |标识符  <br/> |已捕获其会议加入/离开信息的用户的唯一标识符。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |已捕获其会议加入/离开信息的用户使用的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |已捕获会议加入/离开信息的用户使用的客户端。 有关详细信息, 请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |已捕获会议加入/离开信息的用户所使用的客户端类别的名称。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |表示用户是否为内部用户的位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |如果用户同时在多台计算机或设备上登录, 则 UserInstance 用于唯一标识用户/设备组合。  <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |会话的 SIP 对话框 ID。 格式为: 对话框; 从-标签; 到-标记。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |用户加入会议的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |用户离开会议的时间。  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |用户在会议中的角色, 如 "演示者" 或 "与会者"。  <br/> |
   

