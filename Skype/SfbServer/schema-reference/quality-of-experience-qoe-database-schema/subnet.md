---
title: Subnet 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 表是一个支持表。 每条记录代表一个网络配置设置中定义的子网。
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907064"
---
# <a name="subnet-table"></a>Subnet 表
 
Subnet 表是一个支持表。 每条记录代表一个网络配置设置中定义的子网。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主、 外  <br/> |子网 IP 的整数表示形式。  <br/> |
|**子网掩码** <br/> |int  <br/> ||子网掩码。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外  <br/> |引用[自 UserSite table](usersite.md)。  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||子网的描述。  <br/> |
   

