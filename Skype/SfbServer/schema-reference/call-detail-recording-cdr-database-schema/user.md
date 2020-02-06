---
title: 用户视图
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: "\"用户\" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。"
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814830"
---
# <a name="user-view"></a>用户视图
 
"用户" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |标识此用户的唯一号码。  <br/> |
|UserUri  <br/> |nvarchar （450）  <br/> |用户的 Uri。  <br/> |
|TenantKey  <br/> |标识符  <br/> |用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |用户 URI 的类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
   

