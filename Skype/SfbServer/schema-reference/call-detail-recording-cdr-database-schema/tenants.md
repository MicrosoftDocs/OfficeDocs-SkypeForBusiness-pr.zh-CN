---
title: Tenants 表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants 表是一个支持表，用于存储各个租户的列表。表中的每条记录分别表示一个租户。
ms.openlocfilehash: 37387fe3bbb4bae7b09a0898ee65373f5342c488
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863329"
---
# <a name="tenants-table"></a>Tenants 表
 
Tenants 表是一个支持表，用于存储各个租户的列表。表中的每条记录分别表示一个租户。
  
> [!NOTE]
> 在本地部署中，CDR 使用内置租户 ID 指示不同的身份验证类型，例如公共 IM 连接、联盟和匿名。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |主  <br/> |标识此租户 ID 的唯一编号。  <br/> |
|**TenantKey** <br/> |nvarchar (256)   <br/> || 允许的值： <br/>  00000000-0000-0000-0000-0000000000000 - Enterprise <br/>  00000000-0000-0000-0000-000000000001 - Federated <br/>  00000000-0000-0000-0000-000000000002 - 匿名 <br/>  00000000-0000-0000-0000-000000000003 - 公共 IM 连接 <br/> |
   

