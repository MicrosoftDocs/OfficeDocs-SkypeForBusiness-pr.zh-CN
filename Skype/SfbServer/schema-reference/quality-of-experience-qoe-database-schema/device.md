---
title: Device 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 表是一个支持表, 用于存储有关各种捕获或呈现设备的信息。 表中的每条记录表示一个设备。
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295004"
---
# <a name="device-table"></a>Device 表
 
Device 表是一个支持表, 用于存储有关各种捕获或呈现设备的信息。 表中的每条记录表示一个设备。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |标识此设备的唯一号码。  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType 是唯一的  <br/> |设备名称。  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType 是唯一的  <br/> |设备类型。 1是捕获设备, 0 是呈现设备。  <br/> |
   

