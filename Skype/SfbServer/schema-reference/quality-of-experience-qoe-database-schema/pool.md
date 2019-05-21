---
title: Pool 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 表是一个支持表, 用于存储各种前端池的相关信息。 表中的每条记录表示一个池。
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294801"
---
# <a name="pool-table"></a>Pool 表
 
Pool 表是一个支持表, 用于存储各种前端池的相关信息。 表中的每条记录表示一个池。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |标识此池的唯一号码。  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |唯一  <br/> |池 FQDN。  <br/> |
   

