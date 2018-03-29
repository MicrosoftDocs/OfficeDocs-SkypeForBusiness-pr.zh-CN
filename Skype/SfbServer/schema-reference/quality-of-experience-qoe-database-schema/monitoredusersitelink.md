---
title: MonitoredUserSiteLink 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是支持表。 每个记录表示两个用户站点之间的一个链接。
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表
 
MonitoredUserSiteLink 表是支持表。 每个记录表示两个用户站点之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主键和外  <br/> |从[UserSite 表](usersite.md)引用。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主键和外  <br/> |从[UserSite 表](usersite.md)的引用。  <br/> |
   

