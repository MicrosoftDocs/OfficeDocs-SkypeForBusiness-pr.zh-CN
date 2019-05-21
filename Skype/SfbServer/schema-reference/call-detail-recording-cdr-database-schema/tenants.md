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
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: 租户表是一个支持表, 用于存储各种租户的列表。 表中的每条记录表示一个租户。
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295767"
---
# <a name="tenants-table"></a>Tenants 表
 
租户表是一个支持表, 用于存储各种租户的列表。 表中的每条记录表示一个租户。
  
> [!NOTE]
> 在本地部署中, CDR 使用内部版本租户 ID 指示不同的身份验证类型, 例如公共 IM 连接、联合和匿名。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |标识此租户 ID 的唯一编号。  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 允许的值: <br/>  00000000-0000-0000-0000-000000000000-企业版 <br/>  00000000-0000-0000-0000-000000000001-联合 <br/>  00000000-0000-0000-0000-000000000002-匿名 <br/>  00000000-0000-0000-0000-000000000003-公共 IM 连接 <br/> |
   

