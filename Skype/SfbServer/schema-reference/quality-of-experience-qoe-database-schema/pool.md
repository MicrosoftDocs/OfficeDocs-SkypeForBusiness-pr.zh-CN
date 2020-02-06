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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 表是一个支持表，用于存储各种前端池的相关信息。 表中的每条记录表示一个池。
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807400"
---
# <a name="pool-table"></a>Pool 表
 
Pool 表是一个支持表，用于存储各种前端池的相关信息。 表中的每条记录表示一个池。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |标识此池的唯一号码。  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |唯一  <br/> |池 FQDN。  <br/> |
   

