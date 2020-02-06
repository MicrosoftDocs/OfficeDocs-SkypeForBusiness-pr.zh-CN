---
title: User 表
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
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: 用户表是一个支持表，用于存储参与数据库中记录的会话的各种用户的列表。 表中的每条记录表示一个用户。
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805090"
---
# <a name="user-table"></a>User 表
 
用户表是一个支持表，用于存储参与数据库中记录的会话的各种用户的列表。 表中的每条记录表示一个用户。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |标识此用户的唯一号码。  <br/> |
|**URI** <br/> |nvarchar （450）  <br/> |唯一  <br/> |URI 字符串。  <br/> |
|**URIType** <br/> |int  <br/> ||1是未知的 URI 类型。  <br/> 2是用户 URI。  <br/> 4是会议 URI。  <br/> 8是电话 URI。  <br/> |
|**TenantKey** <br/> |int  <br/> |外表  <br/> |用户的租户，从租户表引用。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||当用户的音频通话较差时的最晚时间戳。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

