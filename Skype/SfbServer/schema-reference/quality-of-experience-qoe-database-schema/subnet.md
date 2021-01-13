---
title: Subnet 表
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 表是一个支持表。 每条记录均表示网络配置设置中定义的一个子网。
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831332"
---
# <a name="subnet-table"></a>Subnet 表
 
Subnet 表是一个支持表。每条记录均表示网络配置设置中定义的一个子网。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主、外  <br/> |子网 IP 的整数表示形式。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||子网掩码。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |引用自 [UserSite 表](usersite.md)。  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)   <br/> ||子网的说明。  <br/> |
   

