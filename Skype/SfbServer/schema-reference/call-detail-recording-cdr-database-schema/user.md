---
title: 用户视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 用户视图存储已参与呼叫或在数据库中包含记录的会话的用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877641"
---
# <a name="user-view"></a>用户视图
 
用户视图存储已参与呼叫或在数据库中包含记录的会话的用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|用户 Id  <br/> |int  <br/> |标识此用户的唯一编号。  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |用户的 Uri。  <br/> |
|TenantKey  <br/> |唯一标识符  <br/> |用户的租户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |用户 URI 类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
   

