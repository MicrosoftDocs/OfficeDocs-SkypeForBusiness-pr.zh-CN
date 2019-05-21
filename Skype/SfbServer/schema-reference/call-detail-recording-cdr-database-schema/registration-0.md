---
title: 注册视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: "\"注册\" 视图存储有关用户注册的信息。 此视图已引入 Lync Server 2013。"
ms.openlocfilehash: 6202e40e6385fd243f55badd25dbe196452c890a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295865"
---
# <a name="registration-view"></a>注册视图
 
"注册" 视图存储有关用户注册的信息。 此视图已引入 Lync Server 2013。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**RegisterTime** <br/> |datetime  <br/> |发生注册的时间。  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |注册用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |注册用户的 URI 的类型。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |注册用户的租户。 有关详细信息, 请参阅[租户表](tenants.md)。 <br/> |
|**EndpointId** <br/> |标识符  <br/> |注册的用户终结点的唯一标识符。  <br/> |
|**EndpointEra** <br/> |标识符  <br/> |唯一标识符, 用于区分涉及同一用户和同一终结点的注册。  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |发生取消注册的时间。  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |取消注册的原因。  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |注册用户使用的客户端版本。  <br/> |
|**ClientType** <br/> |int  <br/> |注册用户使用的客户端。 有关详细信息, 请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |注册用户使用的客户端的类别。  <br/> |
|**地址** <br/> |nvarchar(256)  <br/> |用户注册使用的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |SIP 对话框 ID。 的格式为:  <br/> 对话框; 从-标签; 到-标记  <br/> |
|**ResponseCode** <br/> |int  <br/> |会议邀请的 SIP 响应代码。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |从 SIP 标题捕获的诊断 ID。  <br/> |
|**注册器** <br/> |nvarchar(256)  <br/> |注册机构的 FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |捕获会话的数据的池的 FQDN。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |注册用户使用的边缘服务器的 FQDN。  <br/> |
|**IsInternal** <br/> |bit  <br/> |指示用户是否从内部网络登录。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |指示 UserService 在注册时是否可用。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |指示注册是否与主注册机构一起注册。  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |注册的设备的 MAC 地址。  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |注册设备的制造商。 有关详细信息, 请参阅[Skype For Business Server 2015 中的制造商表](manufacturers.md)。 <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |注册设备的硬件版本。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 HardwareVersions 表](hardwareversions.md)。 <br/> |
   

