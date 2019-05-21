---
title: Subnet 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 子网表是支持表。 每条记录表示网络配置设置中定义的一个子网。
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294633"
---
# <a name="subnet-table"></a>Subnet 表
 
子网表是支持表。 每条记录表示网络配置设置中定义的一个子网。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主、外部  <br/> |子网 IP 的整数表示形式。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||子网掩码。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外表  <br/> |从[UserSite 表](usersite.md)中引用。  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||子网的说明。  <br/> |
   

