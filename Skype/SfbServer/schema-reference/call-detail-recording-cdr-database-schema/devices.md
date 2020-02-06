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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: "\"设备\" 表是支持表。 每条记录存储有关一个设备（桌面电话）的信息。"
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815280"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 "设备" 表
 
"设备" 表是支持表。 每条记录存储有关一个设备（桌面电话）的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**Keyroutedeventargs.deviceid** <br/> |int  <br/> |Primary  <br/> |标识此硬件版本的唯一号码。  <br/> |
|**ManufacturerId** <br/> |int  <br/> |外表  <br/> |此设备的制造商。 有关详细信息，请参阅[Skype For Business Server 2015 中的制造商表](manufacturers.md)。 <br/> |
|**HardwareVersionId** <br/> |int  <br/> |外表  <br/> |此设备的硬件版本。 有关详细信息，请参阅[Skype For Business Server 2015 中的 HardwareVersions 表](hardwareversions.md)。 <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC 地址  <br/> |
   

