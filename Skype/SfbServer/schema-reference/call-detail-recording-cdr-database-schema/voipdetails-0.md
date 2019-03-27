---
title: VoipDetails 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 每条记录均表示一个其中至少一个用户的双方呼叫是 VoIP 用户。
ms.openlocfilehash: 304efbd8148c363afaa792abe97d0b15ab5a34fd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879670"
---
# <a name="voipdetails-table"></a>VoipDetails 表
 
每条记录均表示一个其中至少一个用户的双方呼叫是 VoIP 用户。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**FromNumberId** <br/> |int  <br/> |外  <br/> |呼叫者的**PhoneId** 。 请参阅[Phones 表](phones.md)的详细信息。 如果不为 NULL 并**FromGatewayId**不为 NULL，则呼叫者是 PSTN 用户。 <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |外  <br/> |呼叫接收者的**PhoneId** 。 请参阅[Phones 表](phones.md)的详细信息。 如果不为 NULL 并**ToGatewayId**不为 NULL，然后呼叫接收者的 PSTN 用户。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |外  <br/> |呼叫来自中介服务器。 请参阅[MediationServers 表](mediationservers.md)的详细信息。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |外  <br/> |中介服务器称为转到。 请参阅[MediationServers 表](mediationservers.md)的详细信息。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |外  <br/> |来自网关呼叫。 请参阅[网关表中的业务服务器 2015 Skype](gateways.md)的详细信息。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |外  <br/> |网关呼叫转到。 请参阅[网关表中的业务服务器 2015 Skype](gateways.md)的详细信息。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |外  <br/> |断开呼叫，如果用户具有 URI 的用户的 URI。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |外  <br/> |从电话情况下，断开呼叫的电话 ID 已断开连接。 请参阅[Phones 表](phones.md)的详细信息。 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

