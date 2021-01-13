---
title: MonitoredUserSiteLink 表
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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是一个支持表。 每条记录代表两个用户站点之间的一个链接。
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806352"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表
 
MonitoredUserSiteLink 表是一个支持表。每条记录代表两个用户站点之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主、外  <br/> |引用自 [UserSite 表](usersite.md)。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主、外  <br/> |[UserSite 表的引用](usersite.md)。  <br/> |
   

