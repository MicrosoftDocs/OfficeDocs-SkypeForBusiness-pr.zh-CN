---
title: Skype for Business Server 2015 中的 FocusJoinsAndLeaves 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: 此表中的每条记录包含有关一个用户的加入的 CDR 信息，并为一个会议留下信息。 每次用户加入和离开会议时，每个会议都将在此表中由一条记录表示。
ms.openlocfilehash: ac5e2b7316dd7d3477d76675d3a3960154b90f35
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815180"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 FocusJoinsAndLeaves 表
 
此表中的每条记录包含有关一个用户的加入的 CDR 信息，并为一个会议留下信息。 每次用户加入和离开会议时，每个会议都将在此表中由一条记录表示。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会议实例的时间。 与**SessionIdSeq**结合使用以唯一标识会议实例。 有关详细信息，请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会议实例的 ID 号。 与**SessionIdTime**结合使用以唯一标识会议实例。 有关详细信息，请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**UserId** <br/> |int  <br/> |外表  <br/> |标识此用户的唯一号码，从 "[用户" 表](users.md)中引用。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||如果用户同时在多台计算机或设备上登录，则**UserInstance**用于唯一标识用户/设备组合。 <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |用户是否已从内部登录。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |此用户在会议中的角色，如 "演示者" 或 "与会者"。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此用户加入会议的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此用户离开会议的时间。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外表  <br/> |用户的客户端软件版本，[在 Skype For Business Server 2015 中引用 ClientVersions 表](clientversions.md)。  <br/> |
|**UserEndpointId** <br/> |标识符  <br/> ||会议中使用的终结点的全局唯一标识符（GUID）。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |从中  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   

