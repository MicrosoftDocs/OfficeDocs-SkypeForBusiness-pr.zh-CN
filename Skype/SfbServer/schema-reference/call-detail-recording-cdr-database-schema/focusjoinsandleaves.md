---
title: Skype for Business Server 2015 中的 FocusJoinsAndLeaves 表
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
ms.localizationpriority: medium
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: 此表中的每条记录都包含有关一个用户加入和离开一个会议的 CDR 信息。 每次用户加入和离开会议时，此表中每个会议都由一条记录表示。
ms.openlocfilehash: 80f4d9f93b840b4c76e28c295356ebd85cc88979
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632666"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 FocusJoinsAndLeaves 表
 
此表中的每条记录都包含有关一个用户加入和离开一个会议的 CDR 信息。 每次用户加入和离开会议时，此表中每个会议都由一条记录表示。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会议实例的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会议实例的 ID 号。 与 **SessionIdTime 结合使用** 来唯一地标识会议实例。 有关详细信息[，请参阅 Skype for Business Server 2015](conferences.md)中的 Conferences 表。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会话请求的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |标识此用户的唯一编号，从 Users 表 [引用](users.md)。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||如果用户同时登录多台计算机或设备， **则 UserInstance** 用于唯一标识用户/设备组合。 <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |用户是否从内部登录。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |此用户在会议中的角色，例如演示者或与会者。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此用户加入会议的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此用户离开会议的时间。  <br/> |
|**ClientVerId** <br/> |int  <br/> |Foreign  <br/> |[2015](clientversions.md)年 10 月中引用了 ClientVersions 表的用户Skype for Business Server的版本。  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||会议中使用的 (GUID) 全局唯一标识符。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段是在 2015 年 Skype for Business Server引入的。  <br/> |
   

