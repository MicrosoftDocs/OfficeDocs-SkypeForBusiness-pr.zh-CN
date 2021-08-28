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
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是一个支持表。 表中的每条记录都存储有关单个用户对系统的使用情况的信息。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: c05277c5999866ea7ba63befeef9e1198436642c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609179"
---
# <a name="userstatistics-table"></a>UserStatistics 表
 
UserStatistics 表是一个支持表。 表中的每条记录都存储有关单个用户对系统的使用情况的信息。 此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |主  <br/> |用于标识此用户的唯一编号。  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||用户上次登录时间。  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||用户上次组织会议的时间。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||用户上次遇到呼叫失败的时间。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||用户上次以会议组织者身份遇到呼叫失败的时间。  <br/> |
   

