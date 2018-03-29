---
title: Tenants 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: 承租人表是一个支持的表来存储各种承租人的列表。 每个表中的记录表示一个租户。
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a>Tenants 表
 
承租人表是一个支持的表来存储各种承租人的列表。 每个表中的记录表示一个租户。
  
> [!NOTE]
> 在内部部署中，CDR 使用生成在租户 ID 来表示不同的身份验证类型，例如公用 IM 连接，联盟和匿名。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |唯一的编号，用于标识此租户 id。  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  00000000-0000-0000-0000-000000000000-企业 <br/>  00000000-0000-0000-0000-000000000001-联合 <br/>  00000000-0000-0000-0000-000000000002-匿名 <br/>  00000000-0000-0000-0000-000000000003-公用 IM 连接 <br/> |
   

