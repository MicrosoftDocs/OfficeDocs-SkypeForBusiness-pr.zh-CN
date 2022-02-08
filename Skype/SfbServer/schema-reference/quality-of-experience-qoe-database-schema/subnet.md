---
title: Subnet 表
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 表是一个支持表。每条记录均表示网络配置设置中定义的一个子网。
ms.openlocfilehash: 92e582332e0e7c20c443a57c4ba0cc6abbb66cad
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394594"
---
# <a name="subnet-table"></a>Subnet 表
 
Subnet 表是一个支持表。每条记录均表示网络配置设置中定义的一个子网。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主、外  <br/> |子网 IP 的整数表示形式。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||子网掩码。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |从 [UserSite 表中引用](usersite.md)。  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)   <br/> ||子网的说明。  <br/> |
   

