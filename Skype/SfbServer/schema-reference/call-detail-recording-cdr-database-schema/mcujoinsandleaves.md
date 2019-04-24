---
title: McuJoinsAndLeaves 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 此表中的每条记录包含呼叫详细信息的用户加入或离开和会议服务器的一个组合。 例如，如果用户加入会议包含 web 会议和音频/视频元素时，将为该用户的 web 会议加入，创建一个记录，并将为用户的音频/视频会议加入创建另一条记录。
ms.openlocfilehash: 7a31564ed770c956baa0ef7e968d0fba1dc3fd7d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212978"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>McuJoinsAndLeaves 表中的业务服务器 2015 Skype
 
此表中的每条记录包含呼叫详细信息的用户加入或离开和会议服务器的一个组合。 例如，如果用户加入会议包含 web 会议和音频/视频元素时，将为该用户的 web 会议加入，创建一个记录，并将为用户的音频/视频会议加入创建另一条记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会议实例的时间。 与**SessionIdSeq**结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |若要确定会议实例的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会议实例。 请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。 <br/> |
|**用户 Id** <br/> |int  <br/> |主、 外  <br/> |标识此用户的唯一编号。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |如果用户在登录多个计算机或设备同时，McuUserInstance 会唯一地标识用户/设备组合。  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |是否用户从 PSTN 中加入或不。  <br/> |
|**McuId** <br/> |int  <br/> |主、 外  <br/> |标识此会议服务器的唯一编号。 请参阅[Mcus 表中的业务服务器 2015 Skype](mcus.md)的详细信息。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |外  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此用户加入此会议服务器的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此用户离开此会议服务器的时间。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外  <br/> |在会议中使用指定的客户端软件的版本号的标识符。 请参阅[ClientVersions 表中的业务服务器 2015 Skype](clientversions.md)的详细信息。 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

