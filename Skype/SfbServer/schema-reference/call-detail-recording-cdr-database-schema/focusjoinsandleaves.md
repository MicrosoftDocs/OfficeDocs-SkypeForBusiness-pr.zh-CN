---
title: 在业务服务器 2015年的 Skype 的 FocusJoinsAndLeaves 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: 此表中的每个记录包含一个用户联接的 CDR 信息和保留信息的一个会议。 每个会议在此表中由表示一条记录每次用户加入和离开会议。
ms.openlocfilehash: f07790af63de562672cefc8d8fbd09d75dff1eec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 FocusJoinsAndLeaves 表
 
此表中的每个记录包含一个用户联接的 CDR 信息和保留信息的一个会议。 每个会议在此表中由表示一条记录每次用户加入和离开会议。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主键和外  <br/> |会议实例的时间。 与**SessionIdSeq**配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |若要标识的会议实例的 ID 号。 与**SessionIdTime**配合使用，以唯一标识的会议实例。 [业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |主键和外  <br/> |会议请求的时间。 与**SessionIdSeq**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**用户 Id** <br/> |int  <br/> |外  <br/> |标识该用户，从[用户表](users.md)中引用的唯一编号。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||如果用户登录多台计算机或设备在同一时间，则使用**UserInstance**来唯一地标识用户/设备组合。 <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |无论用户登录从内部或不。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |在会议中，例如，演示者或与会者的该用户的角色。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此用户加入会议的时间。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此用户离开会议时间。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外  <br/> |引用到[ClientVersions 表中的业务服务器 2015 Skype](clientversions.md)的用户的客户端软件的版本。  <br/> |
|**UserEndpointId** <br/> |唯一标识符  <br/> ||在会议中使用方终结点的全局唯一标识符 (GUID)。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> ||供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

