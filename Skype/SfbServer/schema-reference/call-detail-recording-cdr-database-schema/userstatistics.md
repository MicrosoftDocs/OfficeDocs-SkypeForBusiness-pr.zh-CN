---
title: UserStatistics 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是支持表。 表中的每条记录存储系统的单个用户使用的信息。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a>UserStatistics 表
 
UserStatistics 表是支持表。 表中的每条记录存储系统的单个用户使用的信息。 在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**用户 Id** <br/> |int  <br/> |Primary  <br/> |识别该用户的唯一号码。  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||上一次用户登录。  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||上一次用户组织的会议。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||上一次用户遇到呼叫失败。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||上一次用户体验作为会议组织者调用失败。  <br/> |
   

