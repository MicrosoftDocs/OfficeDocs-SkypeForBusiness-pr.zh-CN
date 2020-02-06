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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 表是支持表。 每条记录表示两个国家/地区之间的一个链接。
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807810"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink 表
 
MonitoredRegionLink 表是支持表。 每条记录表示两个国家/地区之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |主、外部  <br/> |从[区域表](region.md)中引用。  <br/> |
|**Region2Key** <br/> |int  <br/> |主、外部  <br/> |从[区域表](region.md)中引用。  <br/> |
   

