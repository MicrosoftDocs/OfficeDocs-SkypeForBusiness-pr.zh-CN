---
title: Device 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: 设备表是一个支持表，用于存储有关各种捕获的信息或呈现设备。 表中的每条记录代表一个设备。
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920024"
---
# <a name="device-table"></a>Device 表
 
设备表是一个支持表，用于存储有关各种捕获的信息或呈现设备。 表中的每条记录代表一个设备。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |标识此设备的唯一编号。  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType 是唯一  <br/> |设备名称。  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType 是唯一  <br/> |设备类型。 1 是捕获设备，0 为呈现设备。  <br/> |
   

