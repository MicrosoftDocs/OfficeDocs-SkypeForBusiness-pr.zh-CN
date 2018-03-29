---
title: MonitoredRegionLink 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 表是支持表。 每个记录代表两个国家/地区之间的一个链接。
ms.openlocfilehash: 471291788dabee412bffef641624afad2a2c10b4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink 表
 
MonitoredRegionLink 表是支持表。 每个记录代表两个国家/地区之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |主键和外  <br/> |从[区域表](region.md)引用。  <br/> |
|**Region2Key** <br/> |int  <br/> |主键和外  <br/> |从[区域表](region.md)引用。  <br/> |
   

