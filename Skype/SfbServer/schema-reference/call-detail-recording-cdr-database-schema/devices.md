---
title: Skype for Business Server 2015 中的 Devices 表
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 表是一个支持表。每条记录存储有关一个设备（桌面电话）的信息。
---

# <a name="devices-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 Devices 表
 
Devices 表是一个支持表。每条记录存储有关一个设备（桌面电话）的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |主  <br/> |用于标识此硬件版本的唯一编号。  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Foreign  <br/> |此设备的制造商。 有关详细信息[，请参阅 Skype for Business Server 2015](manufacturers.md) 中的制造商表。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Foreign  <br/> |此设备的硬件版本。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 HardwareVersions](hardwareversions.md) 表。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC 地址  <br/> |
   

