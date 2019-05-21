---
title: MonitoredRegionLink 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 表是支持表。 每条记录表示两个国家/地区之间的一个链接。
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294871"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink 表
 
MonitoredRegionLink 表是支持表。 每条记录表示两个国家/地区之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |主、外部  <br/> |从[区域表](region.md)中引用。  <br/> |
|**Region2Key** <br/> |int  <br/> |主、外部  <br/> |从[区域表](region.md)中引用。  <br/> |
   

