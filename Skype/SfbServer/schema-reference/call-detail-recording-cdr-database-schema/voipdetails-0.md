---
title: VoipDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 每条记录表示至少有一位用户是 VoIP 用户的 1 2 方呼叫。
ms.openlocfilehash: 7f0be2fb2f14e34cbe989d5912db1f66d3d65d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295676"
---
# <a name="voipdetails-table"></a>VoipDetails 表
 
每条记录表示至少有一位用户是 VoIP 用户的 1 2 方呼叫。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**FromNumberId** <br/> |int  <br/> |外表  <br/> |呼叫方的**PhoneId** 。 有关详细信息, 请参阅 "[电话" 表](phones.md)。 如果 not NULL 且**FromGatewayId**不为 null, 则呼叫方是 PSTN 用户。 <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |外表  <br/> |呼叫接收器的**PhoneId** 。 有关详细信息, 请参阅 "[电话" 表](phones.md)。 如果 not NULL 且**ToGatewayId**不为 null, 则呼叫接收器是 PSTN 用户。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |外表  <br/> |呼叫来自的中介服务器。 有关详细信息, 请参阅[MediationServers 表](mediationservers.md)。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |外表  <br/> |将调用的中介服务器将转到。 有关详细信息, 请参阅[MediationServers 表](mediationservers.md)。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |外表  <br/> |呼叫的网关来自。 有关详细信息, 请参阅[Skype For Business Server 2015 中的网关表](gateways.md)。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |外表  <br/> |呼叫将转网网关。 有关详细信息, 请参阅[Skype For Business Server 2015 中的网关表](gateways.md)。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |外表  <br/> |断开呼叫的用户的 URI (如果用户具有 URI)。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |外表  <br/> |断开通话的电话的 ID 已断开与电话的连接。 有关详细信息, 请参阅 "[电话" 表](phones.md)。 <br/> |
|**LastModifiedTime** <br/> |从中  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   

