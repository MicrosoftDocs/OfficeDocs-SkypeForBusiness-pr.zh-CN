---
title: Server 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Server 表是一个支持表。 每条记录代表一个服务器。
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212107"
---
# <a name="server-table"></a>Server 表
 
Server 表是一个支持表。 每条记录代表一个服务器。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |标识服务器的唯一编号。  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |索引  <br/> |MAC 地址字符串。  <br/> |
|**ServerType** <br/> |int  <br/> |外  <br/> |1： 中介服务器  <br/> 2: A / V 会议 Server16394: A / V 边缘服务 32769： 网关  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||服务器所属的池。 仅适用于 A / V 会议服务器。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

