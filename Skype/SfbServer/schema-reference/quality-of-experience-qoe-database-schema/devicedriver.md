---
title: DeviceDriver 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver 表是一个支持表。每条记录都代表捕获设备或呈现设备所使用的一个驱动程序。
ms.openlocfilehash: 31b847ce089ca042282ad04aa4af77fc0e6681c6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740268"
---
# <a name="devicedriver-table"></a>DeviceDriver 表
 
DeviceDriver 表是一个支持表。每条记录都代表捕获设备或呈现设备所使用的一个驱动程序。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |主  <br/> |用于标识此设备驱动程序记录的唯一编号。  <br/> |
|**DeviceDriver** <br/> |varchar (256)   <br/> |unique  <br/> |设备驱动程序的名称。  <br/> |
   

