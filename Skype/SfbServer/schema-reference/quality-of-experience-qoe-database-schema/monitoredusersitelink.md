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
ms.localizationpriority: medium
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是一个支持表。每条记录代表两个用户站点之间的一个链接。
ms.openlocfilehash: a5a8802f3821fff3d08c2365d4f76655b5824606
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610569"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表
 
MonitoredUserSiteLink 表是一个支持表。每条记录代表两个用户站点之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主、外  <br/> |引用自 [UserSite 表](usersite.md)。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主、外  <br/> |引用 [UserSite 表](usersite.md)。  <br/> |
   

