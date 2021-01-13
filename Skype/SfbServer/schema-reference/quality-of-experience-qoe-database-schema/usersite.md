---
title: UserSite 表
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 表是一个支持表。 每条记录代表一个在网络配置设置中定义的用户站点。
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799912"
---
# <a name="usersite-table"></a>UserSite 表
 
UserSite 表是一个支持表。每条记录代表一个在网络配置设置中定义的用户站点。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |主  <br/> |标识用户站点的唯一编号。  <br/> |
|**UserSiteName** <br/> |nvarchar (128)   <br/> |独特  <br/> |用户网站的名称。  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |引用自 [Region 表](region.md)。  <br/> |
   

