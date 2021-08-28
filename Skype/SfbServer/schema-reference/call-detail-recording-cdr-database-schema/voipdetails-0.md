---
title: VoipDetails 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 每条记录均表示一个其中至少有一个用户是 VoIP 用户的双方呼叫。
ms.openlocfilehash: 75fd9b26baebef1fcfb06eb91eddc2d9be1e70d5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584806"
---
# <a name="voipdetails-table"></a>VoipDetails 表
 
每条记录均表示一个其中至少有一个用户是 VoIP 用户的双方呼叫。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主  <br/> |会话请求的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**FromNumberId** <br/> |int  <br/> |Foreign  <br/> |呼叫者的 **PhoneId**。 有关详细信息 [，请参阅 Phones](phones.md) 表。 如果不为 null，并且 **FromGatewayId** 也为不为 null，则呼叫者是 PSTN 用户。 <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Foreign  <br/> |呼叫接收者的 **PhoneId**。 有关详细信息 [，请参阅 Phones](phones.md) 表。 如果不为 null，并且 **ToGatewayId** 也为不为 null，则呼叫接收者是 PSTN 用户。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Foreign  <br/> |呼叫的源中介服务器。 有关详细信息， [请参阅 MediationServers](mediationservers.md) 表。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Foreign  <br/> |呼叫的目标中介服务器。 有关详细信息， [请参阅 MediationServers](mediationservers.md) 表。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |Foreign  <br/> |呼叫的源网关。 有关详细信息，请参阅[Skype for Business Server 2015](gateways.md)中的 Gateways 表。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |Foreign  <br/> |呼叫的目标网关。 有关详细信息，请参阅[Skype for Business Server 2015](gateways.md)中的 Gateways 表。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Foreign  <br/> |断开呼叫的用户的 URI（如果用户具有 URI）。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Foreign  <br/> |断开呼叫的电话的 ID。 有关详细信息 [，请参阅 Phones](phones.md) 表。 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段是在 2015 年 Skype for Business Server引入的。  <br/> |
   

