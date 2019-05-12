---
title: UserSite 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: 自 UserSite table 是一个支持表。 每条记录代表一个网络配置设置中定义用户的网站。
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906951"
---
# <a name="usersite-table"></a>UserSite 表
 
自 UserSite table 是一个支持表。 每条记录代表一个网络配置设置中定义用户的网站。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |标识用户站点的唯一编号。  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |唯一  <br/> |用户站点的名称。  <br/> |
|**RegionKey** <br/> |int  <br/> |外  <br/> |引用自[Region table](region.md)。  <br/> |
   

