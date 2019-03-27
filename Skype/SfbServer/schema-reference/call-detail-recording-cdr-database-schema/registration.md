---
title: Registration 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 每条记录代表一个用户注册事件。
ms.openlocfilehash: 1dd8f623799753e078d112d08de960076618dfac
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885681"
---
# <a name="registration-table"></a>Registration 表
 
每条记录代表一个用户注册事件。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、 外  <br/> |会话请求的时间。 与**SessionIdSeq**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、 外  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**用户 Id** <br/> |int  <br/> |外  <br/> |用户 id。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**EndpointId** <br/> |唯一标识符  <br/> ||要确定注册终结点的 GUID。 来自同一台计算机的同一用户的注册事件通常将具有相同的终结点 id。 不同的计算机具有不同的终结点 id。  <br/> |
|**EndpointEra** <br/> |唯一标识符  <br/> ||ID 用于区分涉及同一用户和同一终结点的注册。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |外  <br/> |当前用户的客户端版本。 请参阅[ClientVersions 表中的业务服务器 2015 Skype](clientversions.md)的详细信息。 <br/> |
|**RegistrarId** <br/> |int  <br/> |外  <br/> |用于注册的注册器服务器的 ID。 请参阅[服务器表](servers.md)的详细信息。 <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |在其中已捕获会话的池的 ID。 请参阅[Pools 表](pools.md)的详细信息。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外  <br/> |将边缘服务器注册。 请参阅[EdgeServers 表中的业务服务器 2015 Skype](edgeservers.md)的详细信息。 <br/> |
|**IsInternal** <br/> |位  <br/> ||是否用户登录从内部或不。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||UserService 是否可用。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||是否注册到主注册器或不。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||指示用户与 survivable branch appliance 注册。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||注册时间。  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||注销时间。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||注册请求的响应代码。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||注册请求的诊断 ID。 这表明该诊断信息类型。  <br/> |
|**DeviceId** <br/> |int  <br/> |外  <br/> |注册请求来自设备。 请参阅[设备表中的业务服务器 2015 Skype](devices.md)的详细信息。 <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |外  <br/> |De-register，例如启动的用户、 注册过期、 客户端故障，等原因。 请参阅[DeRegisterType 表中的业务服务器 2015 Skype](deregistertype.md)的详细信息。 <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||用户注册的终结点的 IP 地址。 这可以是 IPv4 地址或 IPv6 地址。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

