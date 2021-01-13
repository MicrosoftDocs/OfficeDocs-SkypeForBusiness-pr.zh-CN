---
title: Skype for Business Server 2015 中的 McuJoinsAndLeaves 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 此表中的每条记录都包含有关用户加入或离开和会议服务器的一个组合的呼叫详细信息。 例如，如果用户加入包含 Web 会议和音频/视频元素的会议，将会为该用户的 Web 会议加入创建一条记录，为该用户的音频/视频会议加入创建另一条记录。
ms.openlocfilehash: 8c9e6cba970e113d119ab3ce894dee8d5b4f6b28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821492"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 McuJoinsAndLeaves 表
 
此表中的每条记录都包含有关用户加入或离开和会议服务器的一个组合的呼叫详细信息。 例如，如果用户加入包含 Web 会议和音频/视频元素的会议，将会为该用户的 Web 会议加入创建一条记录，为该用户的音频/视频会议加入创建另一条记录。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会议实例的时间。 与 **SessionIdSeq 结合使用** 来唯一地标识会议实例。 有关详细信息 [，请参阅 Skype for Business Server 2015](conferences.md) 中的 Conferences 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会议实例的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会议实例。 有关详细信息 [，请参阅 Skype for Business Server 2015](conferences.md) 中的 Conferences 表。 <br/> |
|**UserId** <br/> |int  <br/> |主、外  <br/> |用于标识此用户的唯一编号。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |主  <br/> |如果用户同时在多个计算机或设备上登录，McuUserInstance 将唯一标识用户/设备组合。  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |用户是否从 PSTN 加入。  <br/> |
|**McuId** <br/> |int  <br/> |主、外  <br/> |标识此会议服务器的唯一编号。 有关详细信息，请参阅 [Skype for Business Server 2015](mcus.md) 中的 Mcus 表。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |会话请求的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。 有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。 <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此用户加入此会议服务器的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此用户离开此会议服务器的时间。  <br/> |
|**ClientVerId** <br/> |int  <br/> |Foreign  <br/> |用于指定会议中客户端软件使用的版本号的标识符。 有关详细信息， [请参阅 Skype for Business Server 2015 中的 ClientVersions](clientversions.md) 表。 <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段在 Skype for Business Server 2015 中引入。  <br/> |
   

