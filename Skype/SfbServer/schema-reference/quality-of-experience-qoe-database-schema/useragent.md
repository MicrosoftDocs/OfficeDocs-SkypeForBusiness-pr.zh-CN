---
title: UserAgent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 表是一个支持表, 用于存储参与数据库中记录的会话的各种用户代理的列表。 表中的每条记录表示一个用户代理
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294584"
---
# <a name="useragent-table"></a>UserAgent 表
 
UserAgent 表是一个支持表, 用于存储参与数据库中记录的会话的各种用户代理的列表。 表中的每条记录表示一个用户代理
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |标识此用户代理的唯一号码。  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |唯一  <br/> |用户代理字符串。  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1是中介服务器。  <br/> 2是 A/V 会议服务器。  <br/> 4是 Skype for business。  <br/> 8是 IP 电话。  <br/> 16是 Live Meeting 控制台。  <br/> 32是部署验证工具 (DVT)。  <br/> 64是 Macintosh 计算机上的 Skype for business 服务器。  <br/> 128是 Skype for business 服务器助理。  <br/> 256是会议公告服务。  <br/> 512是会议自动助理。  <br/> 1024是响应组应用程序。  <br/> 2048不在语音控制范围内。  <br/> |
   

