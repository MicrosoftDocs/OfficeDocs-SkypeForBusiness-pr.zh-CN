---
title: VoIPDetails 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 视图存储有关对等会话，其中至少一个用户是 VoIP 用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875551"
---
# <a name="voipdetails-view"></a>VoIPDetails 视图
 
VoIPDetails 视图存储有关对等会话，其中至少一个用户是 VoIP 用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
> [!NOTE]
> VoIPDetails 视图还包含[SessionDetails view](sessiondetails-0.md)中的列的所有中下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |启动会话的用户的电话 URI。  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |加入会话的用户的电话 URI。  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |断开会话的用户的 URI。  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |断开会话的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |断开会话租户的用户。  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |断开会话的用户的电话 URI。  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |启动会话的用户使用的中介服务器。  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |加入会话的用户使用的中介服务器。  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |启动会话的用户使用的网关。  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |加入会话的用户使用的网关。  <br/> |
   

