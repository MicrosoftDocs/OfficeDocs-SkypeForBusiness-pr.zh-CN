---
title: Skype for Business Server 2015 中的 "设备" 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: "\"设备\" 表是支持表。 每条记录存储有关一个设备 (桌面电话) 的信息。"
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296376"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 "设备" 表
 
"设备" 表是支持表。 每条记录存储有关一个设备 (桌面电话) 的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**Keyroutedeventargs.deviceid** <br/> |int  <br/> |Primary  <br/> |标识此硬件版本的唯一号码。  <br/> |
|**ManufacturerId** <br/> |int  <br/> |外表  <br/> |此设备的制造商。 有关详细信息, 请参阅[Skype For Business Server 2015 中的制造商表](manufacturers.md)。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |外表  <br/> |此设备的硬件版本。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 HardwareVersions 表](hardwareversions.md)。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC 地址  <br/> |
   

