---
title: 池表
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 表是存储有关各种前端池的信息的支持表。表中的每条记录分别表示一个池。
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815812"
---
# <a name="pool-table"></a>池表
 
Pool 表是存储有关各种前端池的信息的支持表。表中的每条记录分别表示一个池。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |主  <br/> |标识此池的唯一编号。  <br/> |
|**PoolName** <br/> |nvarchar (256)   <br/> |独特  <br/> |池 FQDN。  <br/> |
   

