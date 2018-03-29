---
title: VoipDetails 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 一次两方调用中的至少一个用户是 VoIP 用户每个记录表示。
ms.openlocfilehash: 8f28ec3ac1d4049f24c5af5b768026bdd8a98486
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-table"></a>VoipDetails 表
 
一次两方调用中的至少一个用户是 VoIP 用户每个记录表示。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |会议请求的时间。 与**SessionIdSeq**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**FromNumberId** <br/> |int  <br/> |外  <br/> |**PhoneId**的调用方。 [电话表](phones.md)的详细信息，请参阅。 如果不为 NULL 和**FromGatewayId**不是 NULL，则调用方是 PSTN 用户。 <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |外  <br/> |**PhoneId**的调用接收器。 [电话表](phones.md)的详细信息，请参阅。 如果不为 NULL 和**ToGatewayId**不是 NULL，则调用接收器是 PSTN 用户。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |外  <br/> |来自中介服务器调用。 [MediationServers 表](mediationservers.md)的详细信息，请参阅。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |外  <br/> |进入调用中介服务器。 [MediationServers 表](mediationservers.md)的详细信息，请参阅。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |外  <br/> |来自网关呼叫。 [业务服务器 2015年的 Skype 在网关表](gateways.md)的详细信息，请参阅。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |外  <br/> |网关呼叫转到。 [业务服务器 2015年的 Skype 在网关表](gateways.md)的详细信息，请参阅。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |外  <br/> |断开呼叫，如果用户具有一个 URI 的用户的 URI。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |外  <br/> |断开呼叫连接的电话 ID 被从电话中断。 [电话表](phones.md)的详细信息，请参阅。 <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> ||供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

