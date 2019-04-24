---
title: Tenants 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants 表是一个支持表，用于存储各种租户的列表。 表中的每条记录代表一个租户。
ms.openlocfilehash: cf7d0271c9cacfd76079a80a7e5db63d669a8dfb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212766"
---
# <a name="tenants-table"></a>Tenants 表
 
Tenants 表是一个支持表，用于存储各种租户的列表。 表中的每条记录代表一个租户。
  
> [!NOTE]
> 在本地部署中，CDR 使用内置租户 ID 指示不同的身份验证类型，如公共 IM 连接、 联盟和匿名。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |标识此租户 id。 的唯一编号  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  00000000-0000-0000-0000-000000000000-企业 <br/>  00000000-0000-0000-0000-000000000001-联盟 <br/>  00000000-0000-0000-0000-000000000002-匿名 <br/>  00000000-0000-0000-0000-000000000003-公共 IM 连接 <br/> |
   

