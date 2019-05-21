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
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: "\"用户\" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。"
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295739"
---
# <a name="user-view"></a>用户视图
 
"用户" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |标识此用户的唯一号码。  <br/> |
|UserUri  <br/> |nvarchar (450)  <br/> |用户的 Uri。  <br/> |
|TenantKey  <br/> |标识符  <br/> |用户的租户。 有关详细信息, 请参阅[租户表](tenants.md)。 <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |用户 URI 的类型。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
   

