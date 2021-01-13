---
title: UserStatistics 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是一个支持表。 表中的每条记录存储有关单个用户对系统使用情况的信息。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813102"
---
# <a name="userstatistics-table"></a>UserStatistics 表
 
UserStatistics 表是一个支持表。 表中的每条记录存储有关单个用户对系统使用情况的信息。 此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |主  <br/> |用于标识此用户的唯一编号。  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||用户上次登录时间。  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||用户上次组织会议的时间。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||用户上次遇到呼叫失败的时间。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||用户上次以会议组织者身份遇到呼叫失败的时间。  <br/> |
   

