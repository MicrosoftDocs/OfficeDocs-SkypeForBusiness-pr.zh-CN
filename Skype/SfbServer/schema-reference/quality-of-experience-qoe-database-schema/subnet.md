---
title: Subnet 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 子网表是支持表。 每个记录都表示一个网络配置设置中定义的子网。
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a>Subnet 表
 
子网表是支持表。 每个记录都表示一个网络配置设置中定义的子网。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主键和外  <br/> |子网 IP 的整数表示形式。  <br/> |
|**子网掩码** <br/> |int  <br/> ||子网掩码。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外  <br/> |从[UserSite 表](usersite.md)引用。  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||子网的描述。  <br/> |
   

