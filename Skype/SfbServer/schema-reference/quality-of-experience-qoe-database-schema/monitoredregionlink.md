---
title: MonitoredRegionLink 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: f026e35dfd0c0cfd0b7a43d62089754b6824cfa8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604611"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink 表
 
MonitoredRegionLink 表是一个支持表。 每条记录代表两个国家/地区之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |主、外  <br/> |从 Region 表 [引用](region.md)。  <br/> |
|**Region2Key** <br/> |int  <br/> |主、外  <br/> |从 Region 表 [引用](region.md)。  <br/> |
   

