---
title: Devices 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 表是一个支持表。 每个记录存储设备 （桌面电话） 的信息。
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213163"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Devices 表中的业务服务器 2015 Skype
 
Devices 表是一个支持表。 每个记录存储设备 （桌面电话） 的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |标识此硬件版本的唯一编号。  <br/> |
|**ManufacturerId** <br/> |int  <br/> |外  <br/> |此设备的制造商。 请参阅[Manufacturers 表中的业务服务器 2015 Skype](manufacturers.md)的详细信息。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |外  <br/> |此设备硬件版本。 请参阅[HardwareVersions 表中的业务服务器 2015 Skype](hardwareversions.md)的详细信息。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC 地址  <br/> |
   

