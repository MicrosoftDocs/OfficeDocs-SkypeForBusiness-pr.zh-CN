---
title: 注册视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: 注册视图存储有关用户注册信息。 此视图是在 Lync Server 2013 中引入的。
ms.openlocfilehash: 820e99296b93743d13709e5296ed1c317079be3b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930656"
---
# <a name="registration-view"></a>注册视图
 
注册视图存储有关用户注册信息。 此视图是在 Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**RegisterTime** <br/> |datetime  <br/> |注册发生的时间。  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |注册的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |注册用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |注册租户的用户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**EndpointId** <br/> |唯一标识符  <br/> |用户注册的终结点的唯一标识符。  <br/> |
|**EndpointEra** <br/> |唯一标识符  <br/> |用于区分涉及同一用户和同一终结点的注册的唯一标识符。  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |时间取消注册发生的。  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |取消注册的原因。  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |使用用户注册的客户端版本。  <br/> |
|**客户端类型** <br/> |int  <br/> |使用客户端用户注册。 请参阅[UserAgentDef 表](useragentdef.md)的详细信息。 <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |使用用户注册的客户端的类别。  <br/> |
|**Ip 地址** <br/> |nvarchar(256)  <br/> |用户注册的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP 对话框 id。 格式为：  <br/> 对话框; 从标记; 到标记  <br/> |
|**ResponseCode** <br/> |int  <br/> |会话邀请的 SIP 响应代码。 通常由会话中生成从初始的 INVITE 消息的数据填充此字段。 如果没有邀请消息然后字段中填充的日期和时间的第一个相关 SIP 消息 （BYE、 取消、 消息或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从 SIP 标头捕获的诊断 ID。  <br/> |
|**注册器** <br/> |nvarchar(256)  <br/> |注册器的 FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |已捕获会话数据的池的 FQDN。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |注册用户使用的边缘服务器的 FQDN。  <br/> |
|**IsInternal** <br/> |bit  <br/> |指示用户是否可以从内部网络登录。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |指示 UserService 在注册时是否可用。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |指示注册是否是使用主注册器。  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |注册设备的 MAC 地址。  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |设备的制造商注册。 请参阅[Manufacturers 表中的业务服务器 2015 Skype](manufacturers.md)的详细信息。 <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |硬件版本注册的设备。 请参阅[HardwareVersions 表中的业务服务器 2015 Skype](hardwareversions.md)的详细信息。 <br/> |
   

