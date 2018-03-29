---
title: 用户视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 用户视图存储有关已调用或数据库中具有记录的会话中涉及的用户信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 014b773a60cc053c0ec258c7dd853e31a590319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-view"></a>用户视图
 
用户视图存储有关已调用或数据库中具有记录的会话中涉及的用户信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|用户 Id  <br/> |int  <br/> |识别该用户的唯一号码。  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |用户的 Uri。  <br/> |
|TenantKey  <br/> |唯一标识符  <br/> |用户的客户端。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |用户 URI 类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
   

