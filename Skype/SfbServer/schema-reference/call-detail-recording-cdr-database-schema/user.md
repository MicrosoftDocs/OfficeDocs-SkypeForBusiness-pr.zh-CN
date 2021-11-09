---
title: 用户视图
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 用户视图存储有关数据库中记录的呼叫或会话所涉及的用户的信息。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 46ce45644d66d0268a0fc57b81df50b018dccf2a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854136"
---
# <a name="user-view"></a>用户视图
 
用户视图存储有关数据库中记录的呼叫或会话所涉及的用户的信息。 此视图在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|UserID  <br/> |int  <br/> |用于标识此用户的唯一编号。  <br/> |
|UserUri  <br/> |nvarchar (450)   <br/> |用户的 URI。  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|UriType  <br/> |nvarchar (256)   <br/> |用户 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
   

