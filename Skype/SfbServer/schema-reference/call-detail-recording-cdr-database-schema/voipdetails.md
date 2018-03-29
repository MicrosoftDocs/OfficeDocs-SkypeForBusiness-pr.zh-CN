---
title: VoIPDetails 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 视图存储对等会话，其中至少一个用户是 VoIP 用户有关的信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 93c2afb6383817a4d3941d5b427565fb1d0db098
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-view"></a>VoIPDetails 视图
 
VoIPDetails 视图存储对等会话，其中至少一个用户是 VoIP 用户有关的信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
> [!NOTE]
> VoIPDetails 视图它包含[SessionDetails 视图](sessiondetails-0.md)中的列的所有除了下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |电话的启动会话的用户的 URI。  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |电话连接会话的用户的 URI。  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |断开连接会话的用户的 URI。  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |URI 的用户已断开连接的会话的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |客户端的用户的用户已断开连接的会话。  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |电话断开连接会话的用户的 URI。  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |中介服务器启动该会话的用户的使用。  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |加入会话的用户所使用的中介服务器。  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |启动该会话的用户使用的网关。  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |加入会话的用户使用的网关。  <br/> |
   

