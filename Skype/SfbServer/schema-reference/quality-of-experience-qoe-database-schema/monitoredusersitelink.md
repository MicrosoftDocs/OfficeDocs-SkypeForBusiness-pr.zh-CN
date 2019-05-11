---
title: MonitoredUserSiteLink 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是一个支持表。 每条记录代表一个两个用户站点之间的链接。
ms.openlocfilehash: 18f0931feb46e69db76c93225ccc11398b4d6daf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920010"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表
 
MonitoredUserSiteLink 表是一个支持表。 每条记录代表一个两个用户站点之间的链接。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主、 外  <br/> |引用[自 UserSite table](usersite.md)。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主、 外  <br/> |引用[自 UserSite table](usersite.md)。  <br/> |
   

