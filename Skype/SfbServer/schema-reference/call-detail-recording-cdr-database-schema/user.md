---
title: 用户视图
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 用户视图存储有关数据库中记录的呼叫或会话所涉及的用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831692"
---
# <a name="user-view"></a>用户视图
 
用户视图存储有关数据库中记录的呼叫或会话所涉及的用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**Details**|
|:-----|:-----|:-----|
|UserID  <br/> |int  <br/> |用于标识此用户的唯一编号。  <br/> |
|UserUri  <br/> |nvarchar (450)   <br/> |用户的 URI。  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |用户的租户。 有关详细信息 [，请参阅"租户](tenants.md) "表。 <br/> |
|UriType  <br/> |nvarchar (256)   <br/> |用户 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
   

