---
title: UserStatistics 表
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是支持表。 表中的每条记录存储有关系统的单个用户使用情况的信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814790"
---
# <a name="userstatistics-table"></a>UserStatistics 表
 
UserStatistics 表是支持表。 表中的每条记录存储有关系统的单个用户使用情况的信息。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |标识此用户的唯一号码。  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||上次登录用户的时间。  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||上次用户组织会议的时间。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||上次用户遇到通话失败的时间。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||上次用户遇到作为会议组织者的呼叫失败的时间。  <br/> |
   

