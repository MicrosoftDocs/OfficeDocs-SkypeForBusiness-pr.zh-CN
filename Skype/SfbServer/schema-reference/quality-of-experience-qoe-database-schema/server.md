---
title: Server 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 服务器表是支持表。 每个记录表示一台服务器。
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a>Server 表
 
服务器表是支持表。 每个记录表示一台服务器。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |用于标识服务器的唯一编号。  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |索引  <br/> |MAC 地址字符串。  <br/> |
|**ServerType** <br/> |int  <br/> |外  <br/> |1： 中介服务器  <br/> 2: A / V 会议 Server16394: A / V 边缘 service32769： 网关  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||服务器所属的池。 仅适用于 A / V 会议服务器。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

