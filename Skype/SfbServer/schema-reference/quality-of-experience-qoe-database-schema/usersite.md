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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 表是支持表。 每条记录表示网络配置设置中定义的一个用户网站。
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805000"
---
# <a name="usersite-table"></a>UserSite 表
 
UserSite 表是支持表。 每条记录表示网络配置设置中定义的一个用户网站。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |标识用户网站的唯一号码。  <br/> |
|**UserSiteName** <br/> |nvarchar  <br/> |唯一  <br/> |用户网站的名称。  <br/> |
|**RegionKey** <br/> |int  <br/> |外表  <br/> |从[Region 表](region.md)中引用。  <br/> |
   

