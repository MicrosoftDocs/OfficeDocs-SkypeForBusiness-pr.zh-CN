---
title: MonitoredUserSiteLink 表
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是一个支持表。每条记录代表两个用户站点之间的一个链接。
ms.openlocfilehash: 83278162f5e2a499bd68b874ca9eb961c09cf3d3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829756"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表
 
MonitoredUserSiteLink 表是一个支持表。每条记录代表两个用户站点之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主、外  <br/> |引用自 [UserSite 表](usersite.md)。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主、外  <br/> |引用 [UserSite 表](usersite.md)。  <br/> |
   

