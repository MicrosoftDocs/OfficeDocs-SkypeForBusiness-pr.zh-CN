---
title: Tenants 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants 表是一个支持表，用于存储各个租户的列表。 表中的每条记录分别表示一个租户。
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831712"
---
# <a name="tenants-table"></a>Tenants 表
 
Tenants 表是一个支持表，用于存储各个租户的列表。表中的每条记录分别表示一个租户。
  
> [!NOTE]
> 在本地部署中，CDR 使用内置租户 ID 指示不同的身份验证类型，例如公共 IM 连接、联盟和匿名。 
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |主  <br/> |标识此租户 ID 的唯一编号。  <br/> |
|**TenantKey** <br/> |nvarchar (256)   <br/> || 允许的值： <br/>  00000000-0000-0000-0000-000000000000 - Enterprise <br/>  00000000-0000-0000-0000-00000000001 - 联合 <br/>  00000000-0000-0000-0000-000000000002 - 匿名 <br/>  00000000-0000-0000-0000-000000000003 - 公共 IM 连接 <br/> |
   

