---
title: Pool 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 表是一个支持表，用于存储有关各种前端池的信息。 表中的每条记录代表一个池。
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874016"
---
# <a name="pool-table"></a>Pool 表
 
Pool 表是一个支持表，用于存储有关各种前端池的信息。 表中的每条记录代表一个池。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |标识此池的唯一编号。  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |唯一  <br/> |池 FQDN。  <br/> |
   

