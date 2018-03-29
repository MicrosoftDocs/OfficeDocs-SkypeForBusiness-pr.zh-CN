---
title: 注册视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: 注册视图存储有关用户注册信息。 在 Lync Server 2013 引入了此视图。
ms.openlocfilehash: e116c2609f1f26268eaaa3413c3a4491da096585
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="registration-view"></a>注册视图
 
注册视图存储有关用户注册信息。 在 Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议请求的时间。 与 SessionIdSeq 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |以标识会话的 ID 号。 与 SessionIdTime 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**RegisterTime** <br/> |datetime  <br/> |注册的发生时间。  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |注册的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |URI 的用户的注册类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |客户端的用户注册。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**EndpointId** <br/> |唯一标识符  <br/> |使用注册的终结点的用户的唯一标识符。  <br/> |
|**EndpointEra** <br/> |唯一标识符  <br/> |用于区分登记涉及相同的用户和同一个终结点的唯一标识符。  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |在时间的注销发生。  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |取消注册的理由。  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |用户使用人注册的客户端版本。  <br/> |
|**客户端类型** <br/> |int  <br/> |客户端使用的用户注册。 [UserAgentDef 表](useragentdef.md)的更多详细信息，请参阅。 <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |客户端使用的用户注册的类别。  <br/> |
|**Ip 地址** <br/> |nvarchar(256)  <br/> |用户注册的 IP 地址。 这可能是一个 IPv4 或 IPv6 地址。  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP 对话框 id。 格式是：  <br/> 对话; 从标记; 到标记  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 会话邀请响应代码。 通常是通过生成从初始的邀请邮件会话中的数据填充此字段。 如果没有邀请消息字段已经用的日期和时间的第一个相关 SIP 消息 （再见、 取消、 邮件或信息）。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从 SIP 头捕获的诊断 ID。  <br/> |
|**注册** <br/> |nvarchar(256)  <br/> |注册器 FQDN。  <br/> |
|**池** <br/> |nvarchar(256)  <br/> |捕获数据的会话池的 FQDN。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |边缘服务器注册的用户所使用的 FQDN。  <br/> |
|**IsInternal** <br/> |bit  <br/> |指示用户是否可以从内部网络登录。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |指示是否在注册时间，可用的 UserService。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |指示是否的主注册登记。  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |注册设备的 MAC 地址。  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |注册设备的制造商。 [制造商在 Skype 的业务服务器 2015年的表](manufacturers.md)的详细信息，请参阅。 <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |注册设备的硬件版本。 [业务服务器 2015年的 Skype 在 HardwareVersions 表](hardwareversions.md)的详细信息，请参阅。 <br/> |
   

