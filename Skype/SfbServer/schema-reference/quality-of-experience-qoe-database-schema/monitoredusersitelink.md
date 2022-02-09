---
title: MonitoredUserSiteLink 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 7c9e924092b687abe6fefe579109e943fd7c71ca
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399526"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表
 
MonitoredUserSiteLink 表是一个支持表。每条记录代表两个用户站点之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主、外  <br/> |从 [UserSite 表中引用](usersite.md)。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主、外  <br/> |[UserSite 表中的引用](usersite.md)。  <br/> |
   

