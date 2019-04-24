---
title: FocusJoinsAndLeaves 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: 此表中的每条记录包含一个用户加入的 CDR 信息和保留一个会议信息。 每个会议此表中由表示一条记录的每次加入和离开会议的用户。
ms.openlocfilehash: dea6ae9e66416da41c9ca5df0d6a8c3e61550238
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213079"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>FocusJoinsAndLeaves 表中的业务服务器 2015 Skype
 
此表中的每条记录包含一个用户加入的 CDR 信息和保留一个会议信息。 每个会议此表中由表示一条记录的每次加入和离开会议的用户。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会议实例的时间。 与**SessionIdSeq**结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |若要确定会议实例的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**用户 Id** <br/> |int  <br/> |外  <br/> |标识此用户从[Users table](users.md)引用的唯一编号。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||如果用户登录在多个计算机或设备同时，使用**UserInstance**来唯一标识用户/设备组合。 <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |是否用户从内部登录或不。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |在会议中，如演示者或与会者此用户的角色。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此用户加入会议的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此用户离开会议的时间。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外  <br/> |用户的客户端软件，引用，[请参阅 ClientVersions table 中的业务服务器 2015 Skype](clientversions.md)的版本。  <br/> |
|**UserEndpointId** <br/> |唯一标识符  <br/> ||在会议中使用的终结点的全局唯一标识符 (GUID)。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

