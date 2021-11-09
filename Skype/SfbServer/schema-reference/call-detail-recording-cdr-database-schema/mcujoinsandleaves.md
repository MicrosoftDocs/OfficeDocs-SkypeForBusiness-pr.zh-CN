---
title: Skype for Business Server 2015 中的 McuJoinsAndLeaves 表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 此表中的每条记录都包含有关用户加入或离开以及会议服务器的一个组合的呼叫详细信息。 例如，如果用户加入包含 Web 会议和音频/视频元素的会议，将会为该用户的 Web 会议加入创建一条记录，为该用户的音频/视频会议加入创建另一条记录。
ms.openlocfilehash: 35b229d7a3fecbd731fc044cb4c8e30b93e736b3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844965"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 McuJoinsAndLeaves 表
 
此表中的每条记录都包含有关用户加入或离开以及会议服务器的一个组合的呼叫详细信息。 例如，如果用户加入包含 Web 会议和音频/视频元素的会议，将会为该用户的 Web 会议加入创建一条记录，为该用户的音频/视频会议加入创建另一条记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会议实例的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会议实例的 ID 号。 与 **SessionIdTime 结合使用** 来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**UserId** <br/> |int  <br/> |主、外  <br/> |用于标识此用户的唯一编号。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |主  <br/> |如果用户同时在多个计算机或设备上登录，McuUserInstance 将唯一标识用户/设备组合。  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |用户是否从 PSTN 加入。  <br/> |
|**McuId** <br/> |int  <br/> |主、外  <br/> |标识此会议服务器的唯一编号。 有关详细信息，请参阅[Skype for Business Server 2015](mcus.md)中的 Mcus 表。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |会话请求的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此用户加入此会议服务器的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此用户离开此会议服务器的时间。  <br/> |
|**ClientVerId** <br/> |int  <br/> |Foreign  <br/> |指定会议中客户端软件使用的版本号的标识符。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ClientVersions](clientversions.md)表。 <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段是在 2015 年 Skype for Business Server引入的。  <br/> |
   

