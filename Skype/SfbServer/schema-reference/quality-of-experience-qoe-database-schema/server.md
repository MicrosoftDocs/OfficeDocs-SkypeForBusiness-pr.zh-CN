---
title: 服务器表
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Server 表是一个支持表。每个记录表示一台服务器。
---

# <a name="server-table"></a>服务器表
 
Server 表是一个支持表。每个记录表示一台服务器。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |主  <br/> |标识服务器的唯一编号。  <br/> |
|**FQDNOrIP** <br/> |nvarchar (256)   <br/> |index  <br/> |MAC 地址字符串。  <br/> |
|**ServerType** <br/> |int  <br/> |Foreign  <br/> |1：中介服务器  <br/> 2：A/V 会议服务器 16394：A/V 边缘服务 32769：网关  <br/> |
|**PoolName** <br/> |nvarchar (512)   <br/> ||服务器所属的池。仅适用于 A/V 会议服务器。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

