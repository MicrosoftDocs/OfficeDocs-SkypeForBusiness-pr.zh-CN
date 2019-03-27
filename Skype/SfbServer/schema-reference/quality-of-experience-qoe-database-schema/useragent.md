---
title: UserAgent 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 表是一个支持表，用于存储已参与记录数据库中的会话的各种用户代理的列表。 表中的每条记录代表一个用户代理
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893102"
---
# <a name="useragent-table"></a>UserAgent 表
 
UserAgent 表是一个支持表，用于存储已参与记录数据库中的会话的各种用户代理的列表。 表中的每条记录代表一个用户代理
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |标识此用户代理的唯一编号。  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |唯一  <br/> |用户代理字符串。  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 是中介服务器。  <br/> 2 是 A / V 会议服务器。  <br/> 4 是 for Business 的 Skype。  <br/> 8 是 IP 电话。  <br/> 16 是 Live Meeting 控制台。  <br/> 32 是部署验证工具 (DVT)。  <br/> 64 是 Macintosh 计算机上的 Skype 业务服务器。  <br/> 128 是业务 Server attendant 的 Skype。  <br/> 256 是会议公告服务。  <br/> 512 是会议自动助理。  <br/> 1024 是响应组应用程序。  <br/> 2048 是外部语音控制。  <br/> |
   

