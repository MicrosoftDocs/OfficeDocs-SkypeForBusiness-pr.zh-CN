---
title: Server 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 服务器表是支持表。 每条记录代表一台服务器。
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294710"
---
# <a name="server-table"></a>Server 表
 
服务器表是支持表。 每条记录代表一台服务器。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |标识服务器的唯一号码。  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |食指  <br/> |MAC 地址字符串。  <br/> |
|**ServerType** <br/> |int  <br/> |外表  <br/> |1: 中介服务器  <br/> 2: a/V 会议 Server16394: A/V 边缘 service32769: Gateway  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||服务器所属的池。 仅适用于 A/V 会议服务器。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

