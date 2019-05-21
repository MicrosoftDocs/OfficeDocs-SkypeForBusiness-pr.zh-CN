---
title: Skype for Business Server 2015 中的 McuJoinsAndLeaves 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 此表中的每条记录包含有关用户加入或离开和会议服务器的一个组合的调用详细信息。 例如, 如果用户加入包含 web 会议和音频/视频元素的会议, 将为该用户的网络会议加入创建一条记录, 并且将为用户的音频/视频会议加入创建另一条记录。
ms.openlocfilehash: d61b3c1ef1aa6fe481a4022f7bc434b523b68213
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296068"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 McuJoinsAndLeaves 表
 
此表中的每条记录包含有关用户加入或离开和会议服务器的一个组合的调用详细信息。 例如, 如果用户加入包含 web 会议和音频/视频元素的会议, 将为该用户的网络会议加入创建一条记录, 并且将为用户的音频/视频会议加入创建另一条记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会议实例的时间。 与**SessionIdSeq**结合使用以唯一标识会议实例。 有关详细信息, 请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会议实例的 ID 号。 与**SessionIdTime**结合使用以唯一标识会议实例。 有关详细信息, 请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**UserId** <br/> |int  <br/> |主、外部  <br/> |标识此用户的唯一号码。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |如果一次用户在多台计算机或设备上登录, McuUserInstance 将唯一标识用户/设备组合。  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |用户是否从 PSTN 进行联接。  <br/> |
|**McuId** <br/> |int  <br/> |主、外部  <br/> |标识此会议服务器的唯一号码。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 Mcus 表](mcus.md)。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |外表  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |外表  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此用户加入此会议服务器的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此用户离开此会议服务器的时间。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外表  <br/> |用于指定会议中客户端软件使用的版本号的标识符。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ClientVersions 表](clientversions.md)。 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |从中  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   

