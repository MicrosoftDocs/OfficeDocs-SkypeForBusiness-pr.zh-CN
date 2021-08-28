---
title: 注册视图
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
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: 注册视图存储有关用户注册的信息。 Lync Server 2013 中引入了此视图。
ms.openlocfilehash: d754c4027c6440aa8f53a9dac78f1ce1b00c9488
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611881"
---
# <a name="registration-view"></a>注册视图
 
注册视图存储有关用户注册的信息。 Lync Server 2013 中引入了此视图。
  
|**列**|**数据类型**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |用于标识会话的 ID 号。 与 SessionIdTime 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**RegisterTime** <br/> |datetime  <br/> |注册发生的时间。  <br/> |
|**UserUri** <br/> |nvarchar (450)   <br/> |注册用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar (256)   <br/> |注册用户的 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**UserTenant** <br/> |nvarchar (256)   <br/> |注册用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |用户注册使用的终结点的唯一标识符。  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |用于区分涉及相同用户和相同终结点的注册的唯一标识符。  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |取消注册发生的时间。  <br/> |
|**DeRegisterReason** <br/> |nvarchar (256)   <br/> |取消注册的原因。  <br/> |
|**ClientVersion** <br/> |nvarchar (256)   <br/> |注册用户使用的客户端版本。  <br/> |
|**ClientType** <br/> |int  <br/> |注册用户使用的客户端。 有关详细信息， [请参阅 UserAgentDef](useragentdef.md) 表。 <br/> |
|**ClientCategory** <br/> |nvarchar (64)   <br/> |注册用户使用的客户端的类别。  <br/> |
|**IpAddress** <br/> |nvarchar (256)   <br/> |用户注册使用的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|**DialogId** <br/> |varstring (775)   <br/> |SIP 对话 ID。格式如下：  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从 SIP 标头捕获的诊断 ID。  <br/> |
|**注册器** <br/> |nvarchar (256)   <br/> |注册器的 FQDN。  <br/> |
|**Pool** <br/> |nvarchar (256)   <br/> |已捕获会话的数据的池的 FQDN。  <br/> |
|**EdgeServer** <br/> |nvarchar (256)   <br/> |注册用户使用的边缘服务器的 FQDN。  <br/> |
|**IsInternal** <br/> |bit  <br/> |指示用户是否是从内部网络登录的。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |指示 UserService 在注册时是否可用。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |指示注册是否是使用主注册器的注册。  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |已注册设备的 MAC 地址。  <br/> |
|**DeviceManufacturer** <br/> |nvarchar (256)   <br/> |已注册设备的制造商。 有关详细信息[，请参阅 Skype for Business Server 2015](manufacturers.md)中的制造商表。 <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar (256)   <br/> |已注册设备的硬件版本。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 HardwareVersions](hardwareversions.md)表。 <br/> |
   

