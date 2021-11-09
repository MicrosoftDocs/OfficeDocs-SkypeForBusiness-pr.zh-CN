---
title: MonitoredRegionLink 表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 表是一个支持表。 每条记录代表两个国家/地区之间的一个链接。
ms.openlocfilehash: 0efac1d496889645ffb52db5c419397337ebf9f2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858099"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink 表
 
MonitoredRegionLink 表是一个支持表。 每条记录代表两个国家/地区之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |主、外  <br/> |从 Region 表 [引用](region.md)。  <br/> |
|**Region2Key** <br/> |int  <br/> |主、外  <br/> |从 Region 表 [引用](region.md)。  <br/> |
   

