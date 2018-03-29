---
title: UserSite 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 表是支持表。 每个记录都表示一个网络配置设置中定义的用户站点。
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a>UserSite 表
 
UserSite 表是支持表。 每个记录都表示一个网络配置设置中定义的用户站点。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |标识用户站点的唯一编号。  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |唯一  <br/> |用户站点的名称。  <br/> |
|**RegionKey** <br/> |int  <br/> |外  <br/> |从[区域表](region.md)引用。  <br/> |
   

