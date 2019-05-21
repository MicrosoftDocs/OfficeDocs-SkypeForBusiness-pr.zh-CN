---
title: MonitoredUserSiteLink 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是支持表。 每条记录表示两个用户网站之间的一个链接。
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294850"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表
 
MonitoredUserSiteLink 表是支持表。 每条记录表示两个用户网站之间的一个链接。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主、外部  <br/> |从[UserSite 表](usersite.md)中引用。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主、外部  <br/> |从[UserSite 表](usersite.md)引用。  <br/> |
   

