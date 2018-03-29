---
title: Device 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: 设备表是一个支持的表来存储有关各种捕获的信息，或呈现设备。 每个表中的记录表示一台设备。
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a>Device 表
 
设备表是一个支持的表来存储有关各种捕获的信息，或呈现设备。 每个表中的记录表示一台设备。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |标识该设备的唯一编号。  <br/> |
|**设备名称** <br/> |nvarchar(256)  <br/> |设备名称 + 数据库是唯一  <br/> |设备名称。  <br/> |
|**数据库** <br/> |bit  <br/> |设备名称 + 数据库是唯一  <br/> |设备类型。 1 为捕获设备，0 是呈现的设备。  <br/> |
   

