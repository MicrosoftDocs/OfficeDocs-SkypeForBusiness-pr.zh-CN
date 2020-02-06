---
title: Tenants 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: 租户表是一个支持表，用于存储各种租户的列表。 表中的每条记录表示一个租户。
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814850"
---
# <a name="tenants-table"></a>Tenants 表
 
租户表是一个支持表，用于存储各种租户的列表。 表中的每条记录表示一个租户。
  
> [!NOTE]
> 在本地部署中，CDR 使用内部版本租户 ID 指示不同的身份验证类型，例如公共 IM 连接、联合和匿名。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |标识此租户 ID 的唯一编号。  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  00000000-0000-0000-0000-000000000000-企业版 <br/>  00000000-0000-0000-0000-000000000001-联合 <br/>  00000000-0000-0000-0000-000000000002-匿名 <br/>  00000000-0000-0000-0000-000000000003-公共 IM 连接 <br/> |
   

