---
title: 在 Skype 的业务服务器 2015年设备表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: 设备表是一个支持的表。 每个记录都存储着一个设备 （桌面电话） 的信息。
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>在 Skype 的业务服务器 2015年设备表
 
设备表是一个支持的表。 每个记录都存储着一个设备 （桌面电话） 的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |标识此硬件版本的唯一编号。  <br/> |
|**ManufacturerId** <br/> |int  <br/> |外  <br/> |此设备的制造商。 [制造商在 Skype 的业务服务器 2015年的表](manufacturers.md)的详细信息，请参阅。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |外  <br/> |此设备的硬件版本。 [业务服务器 2015年的 Skype 在 HardwareVersions 表](hardwareversions.md)的详细信息，请参阅。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC 地址  <br/> |
   

