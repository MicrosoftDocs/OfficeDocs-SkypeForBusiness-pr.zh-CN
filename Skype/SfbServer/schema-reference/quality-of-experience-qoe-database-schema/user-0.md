---
title: 用户表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: User 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户的列表。该表中的每条记录表示一个用户。
ms.openlocfilehash: cdb1717d8cf842450f65a4d21efc953d2c1adffe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834830"
---
# <a name="user-table"></a>用户表
 
User 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户的列表。该表中的每条记录表示一个用户。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |主  <br/> |用于标识此用户的唯一编号。  <br/> |
|**URI** <br/> |nvarchar (450)   <br/> |独特  <br/> |URI 字符串。  <br/> |
|**URIType** <br/> |int  <br/> ||1 是未知 URI 类型。  <br/> 2 是用户 URI。  <br/> 4 是会议 URI。  <br/> 8 是电话 URI。  <br/> |
|**TenantKey** <br/> |int  <br/> |Foreign  <br/> |用户的租户，被 Tenant 表引用。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||用户具有较差音频呼叫时的最新时间戳。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

