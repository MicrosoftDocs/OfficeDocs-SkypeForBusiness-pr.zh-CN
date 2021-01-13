---
title: UserAgent 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户代理的列表。 表中的每条记录表示一个用户代理
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799928"
---
# <a name="useragent-table"></a>UserAgent 表
 
UserAgent 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户代理的列表。 表中的每条记录表示一个用户代理
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |主  <br/> |标识此用户代理的唯一编号。  <br/> |
|**UserAgent** <br/> |nvarchar (256)   <br/> |独特  <br/> |用户代理字符串。  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 是中介服务器。  <br/> 2 是 A/V 会议服务器。  <br/> 4 是 Skype for Business。  <br/> 8 是 IP 电话。  <br/> 16 是 Live Meeting 控制台。  <br/> 32 是部署验证工具 (DVDT) 。  <br/> 64 是 Macintosh 计算机上的 Skype for Business Server。  <br/> 128 是 Skype for Business Server Attendant。  <br/> 256 是会议通知服务。  <br/> 512 是会议自动助理。  <br/> 1024 是响应组应用程序。  <br/> 2048 是外部语音控制。  <br/> |
   

