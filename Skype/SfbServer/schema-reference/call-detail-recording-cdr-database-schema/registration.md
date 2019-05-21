---
title: Registration 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 每条记录表示一个用户注册事件。
ms.openlocfilehash: 7dcf96c5cb5b140711590943eb7ae5d2be8704b4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295858"
---
# <a name="registration-table"></a>Registration 表
 
每条记录表示一个用户注册事件。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外部  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外部  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**UserId** <br/> |int  <br/> |外表  <br/> |用户 ID。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**EndpointId** <br/> |标识符  <br/> ||用于标识注册终结点的 GUID。 通常, 来自同一用户的同一台计算机的注册事件将具有相同的终结点 ID。 不同的计算机具有不同的终结点 ID。  <br/> |
|**EndpointEra** <br/> |标识符  <br/> ||用于区分涉及同一用户和同一终结点的注册的 ID。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |外表  <br/> |当前用户的客户端版本。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ClientVersions 表](clientversions.md)。 <br/> |
|**RegistrarId** <br/> |int  <br/> |外表  <br/> |用于注册的注册机构服务器的 ID。 有关详细信息, 请参阅[服务器表](servers.md)。 <br/> |
|**PoolId** <br/> |int  <br/> |外表  <br/> |捕获会话的池的 ID。 有关详细信息, 请参阅[pool 表](pools.md)。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外表  <br/> |注册要使用的边缘服务器。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 EdgeServers 表](edgeservers.md)。 <br/> |
|**IsInternal** <br/> |位  <br/> ||用户是否已从内部登录。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||UserService 是否可用。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||是否注册到主注册机构。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||指示用户是否已向 survivable 分支设备注册。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||注册时间。  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||取消注册时间。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||注册请求的响应代码。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||注册请求的诊断 ID。 这表示诊断信息类型。  <br/> |
|**Keyroutedeventargs.deviceid** <br/> |int  <br/> |外表  <br/> |注册请求来自的设备。 有关详细信息, 请参阅[Skype For Business Server 2015 中](devices.md)的 "设备" 表。 <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |外表  <br/> |取消注册的原因, 如 "用户启动"、"注册到期"、"客户端失败" 等。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 DeRegisterType 表](deregistertype.md)。 <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||用户注册到的终结点的 IP 地址。 这可以是 IPv4 地址或 IPv6 地址。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |从中  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   

