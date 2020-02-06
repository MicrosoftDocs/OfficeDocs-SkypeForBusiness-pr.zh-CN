---
title: VoIPDetails 视图
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 视图存储有关对等会话的信息，其中至少有一个用户是 VoIP 用户。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814770"
---
# <a name="voipdetails-view"></a>VoIPDetails 视图
 
VoIPDetails 视图存储有关对等会话的信息，其中至少有一个用户是 VoIP 用户。 此视图已在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> VoIPDetails 视图包含[SessionDetails 视图](sessiondetails-0.md)中的所有列以及下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar （450）  <br/> |启动会话的用户的电话 URI。  <br/> |
|**ToPhone** <br/> |nvarchar （450）  <br/> |加入会话的用户的电话 URI。  <br/> |
|**DisconnectedByUri** <br/> |nvarchar （450）  <br/> |断开会话的用户的 URI。  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |断开会话的用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |断开会话的用户的租户。  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar （450）  <br/> |断开会话的用户的电话 URI。  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |启动会话的用户所使用的中介服务器。  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |加入会话的用户所使用的中介服务器。  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |启动会话的用户所使用的网关。  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |加入会话的用户所使用的网关。  <br/> |
   

