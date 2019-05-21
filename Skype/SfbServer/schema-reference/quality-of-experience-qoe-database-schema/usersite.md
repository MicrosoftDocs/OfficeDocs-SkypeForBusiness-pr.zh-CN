---
title: UserSite 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 表是支持表。 每条记录表示网络配置设置中定义的一个用户网站。
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294570"
---
# <a name="usersite-table"></a>UserSite 表
 
UserSite 表是支持表。 每条记录表示网络配置设置中定义的一个用户网站。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |标识用户网站的唯一号码。  <br/> |
|**UserSiteName** <br/> |nvarchar  <br/> |唯一  <br/> |用户网站的名称。  <br/> |
|**RegionKey** <br/> |int  <br/> |外表  <br/> |从[Region 表](region.md)中引用。  <br/> |
   

