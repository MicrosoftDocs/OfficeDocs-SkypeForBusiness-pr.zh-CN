---
title: UserAgent 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: 用户代理表是一个支持的表来存储会话记录在数据库中都可以参加的各种用户代理的列表。 每个表中的记录表示一个用户代理
ms.openlocfilehash: 5b9bcc35fbad3d20a006410aeb3538b6f5daa77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-table"></a>UserAgent 表
 
用户代理表是一个支持的表来存储会话记录在数据库中都可以参加的各种用户代理的列表。 每个表中的记录表示一个用户代理
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |标识此用户代理的唯一编号。  <br/> |
|**用户代理** <br/> |nvarchar(256)  <br/> |唯一  <br/> |用户代理字符串。  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 是中介服务器。  <br/> 2 是 A / V 会议服务器。  <br/> 4 是 Skype 的业务。  <br/> IP 电话是 8。  <br/> 16 是 Live Meeting 控制台。  <br/> 32 是部署验证工具 (DVT)。  <br/> 64 是在 Macintosh 计算机上的 Skype 业务服务器。  <br/> 128 是 Skype 业务服务器助理。  <br/> 256 是会议发布服务。  <br/> 512 是会议自动助理。  <br/> 1024 是响应组应用程序。  <br/> 2048 是外部声音控制。  <br/> |
   

