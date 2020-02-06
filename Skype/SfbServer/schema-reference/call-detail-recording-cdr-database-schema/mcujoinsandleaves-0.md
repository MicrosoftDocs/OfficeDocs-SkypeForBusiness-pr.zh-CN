---
title: McuJoinsAndLeaves 视图
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
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves 视图存储有关用户为一个会议服务器加入和离开信息的信息。 此视图中的每条记录包含有关用户加入或离开和会议服务器的一个组合的调用详细信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 7a7569795d55620051e617d9312d87f3c96c628a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815090"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves 视图
 
McuJoinsAndLeaves 视图存储有关用户为一个会议服务器加入和离开信息的信息。 此视图中的每条记录包含有关用户加入或离开和会议服务器的一个组合的调用详细信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议实例的时间。 与 SessionIdSeq 结合使用以唯一标识会议实例。 有关详细信息，请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会议实例的 ID 号。 与 SessionIdTime 结合使用以唯一标识会议实例。 有关详细信息，请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |用户连接到的会议服务器的 URI。  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |用户连接到的会议服务器的 URI。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**UserUri** <br/> |nvarchar （450）  <br/> |已捕获其会议服务器加入/离开信息的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |已捕获其会议服务器加入/离开信息的用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |已捕获其会议服务器加入/离开信息的用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |已捕获会议服务器加入/离开信息的用户所使用的客户端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |已捕获会议服务器加入/离开信息的用户所使用的客户端。 有关详细信息，请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**UserClientCategory** <br/> |nvarchar （64）  <br/> |已捕获其会议服务器加入/离开信息的用户所使用的客户端类别的名称。  <br/> |
|**McuUserInstance** <br/> |int  <br/> |为同时登录到多台设备的用户唯一标识用户/设备组合。  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |表示用户是否为内部用户的位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**DialogId** <br/> |varchar （775）  <br/> |会话的 SIP 对话框 ID。 格式为：对话框; 从-标签; 到-标记。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |用户加入会议服务器的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |用户离开会议服务器的时间。  <br/> |
   

