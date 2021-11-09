---
title: Subnet 表
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 表是一个支持表。每条记录均表示网络配置设置中定义的一个子网。
ms.openlocfilehash: abbc1317c6a0db1da0b52e5b0eef56abbfad06f5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834840"
---
# <a name="subnet-table"></a>Subnet 表
 
Subnet 表是一个支持表。每条记录均表示网络配置设置中定义的一个子网。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主、外  <br/> |子网 IP 的整数表示形式。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||子网掩码。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |引用自 [UserSite 表](usersite.md)。  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)   <br/> ||子网的说明。  <br/> |
   

