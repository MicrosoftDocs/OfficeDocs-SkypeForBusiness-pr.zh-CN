---
title: 在业务服务器 2015年的 Skype 的 McuJoinsAndLeaves 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 此表中的每条记录包含有关用户加入或离开和会议服务器的一个组合的呼叫详细信息。 例如，如果用户加入会议，其中包括 web 会议和音频/视频元素时，将为该用户的 web 会议连接，创建一条记录，将为用户的音频/视频会议连接创建另一条记录。
ms.openlocfilehash: 153da84534dae4a9ad2287c355b93a4477003e6f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 McuJoinsAndLeaves 表
 
此表中的每条记录包含有关用户加入或离开和会议服务器的一个组合的呼叫详细信息。 例如，如果用户加入会议，其中包括 web 会议和音频/视频元素时，将为该用户的 web 会议连接，创建一条记录，将为用户的音频/视频会议连接创建另一条记录。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主键和外  <br/> |会议实例的时间。 与**SessionIdSeq**配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |若要标识的会议实例的 ID 号。 与**SessionIdTime**配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**用户 Id** <br/> |int  <br/> |主键和外  <br/> |识别该用户的唯一号码。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |如果用户已登录在多台计算机或设备一次，McuUserInstance 唯一地标识用户/设备组合。  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |是否该用户加入从 PSTN 或不。  <br/> |
|**McuId** <br/> |int  <br/> |主键和外  <br/> |标识此会议服务器的唯一编号。 [Mcu 中业务服务器 2015年的 Skype 的表](mcus.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |外  <br/> |会议请求的时间。 与**SessionIdSeq**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |外  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此用户将此会议服务器连接的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此用户离开本会议服务器时间。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外  <br/> |在会议中使用标识符，指定客户端软件的版本号。 [业务服务器 2015年的 Skype 在 ClientVersions 表](clientversions.md)的详细信息，请参阅。 <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> ||供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

