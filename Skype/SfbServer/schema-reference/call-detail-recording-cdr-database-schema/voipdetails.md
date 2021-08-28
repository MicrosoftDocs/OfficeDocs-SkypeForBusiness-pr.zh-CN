---
title: VoIPDetails 视图
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
ms.localizationpriority: medium
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 视图存储有关对等会话（其中至少有一个用户是 VoIP 用户）的信息。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 84f167fc3f4de45142d3bad80acf0fc9803b40db
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593376"
---
# <a name="voipdetails-view"></a>VoIPDetails 视图
 
VoIPDetails 视图存储有关对等会话（其中至少有一个用户是 VoIP 用户）的信息。 此视图在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> VoIPDetails 视图包含 [SessionDetails](sessiondetails-0.md) 视图中的所有列以及下面列出的列。
  
|**列**|**数据类型**|**Details**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar (450)   <br/> |启动会话的用户的电话 ID。  <br/> |
|**ToPhone** <br/> |nvarchar (450)   <br/> |加入会话的用户的电话 URI。  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)   <br/> |断开会话的用户的 URI。  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar (256)   <br/> |断开会话的用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**DisconnectedByTenant** <br/> |nvarchar (256)   <br/> |断开会话的用户的租户。  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)   <br/> |断开会话的用户的电话 URI。  <br/> |
|**FromMediationServer** <br/> |nvarchar (256)   <br/> |启动会话的用户使用的中介服务器。  <br/> |
|**ToMediationServer** <br/> |nvarchar (256)   <br/> |加入会话的用户使用的中介服务器。  <br/> |
|**FromGateway** <br/> |nvarchar (256)   <br/> |启动会话的用户使用的网关。  <br/> |
|**ToGateway** <br/> |nvarchar (256)   <br/> |加入会话的用户使用的网关。  <br/> |
   

