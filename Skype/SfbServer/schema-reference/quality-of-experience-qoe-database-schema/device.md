---
title: 设备表
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 表是一个支持表，用于存储有关各种捕获或呈现设备的信息。该表中的每个记录都代表一台设备。
---

# <a name="device-table"></a>设备表
 
Device 表是一个支持表，用于存储有关各种捕获或呈现设备的信息。该表中的每个记录都代表一台设备。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |主  <br/> |标识此设备的唯一数字。  <br/> |
|**DeviceName** <br/> |nvarchar (256)   <br/> |DeviceName + DeviceType 是唯一的  <br/> |设备名称。  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType 是唯一的  <br/> |设备类型。1 是捕获设备。0 是呈现设备。  <br/> |
   

