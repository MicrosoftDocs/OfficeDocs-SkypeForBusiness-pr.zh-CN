---
title: Registration 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 每个记录表示一个用户注册事件。
ms.openlocfilehash: 87a05d49c9dbf723203bf8efe02dee7cd16550a3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="registration-table"></a>Registration 表
 
每个记录表示一个用户注册事件。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主键和外  <br/> |会议请求的时间。 与**SessionIdSeq**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**用户 Id** <br/> |int  <br/> |外  <br/> |用户 id。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**EndpointId** <br/> |唯一标识符  <br/> ||GUID 来标识注册终结点。 通常从同一台计算机的同一个用户注册事件将具有相同的终结点 id。 不同的计算机具有不同的端点的 id。  <br/> |
|**EndpointEra** <br/> |唯一标识符  <br/> ||用于区分登记涉及相同的用户和同一个终结点的 ID。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |外  <br/> |当前用户的客户端版本。 [业务服务器 2015年的 Skype 在 ClientVersions 表](clientversions.md)的详细信息，请参阅。 <br/> |
|**RegistrarId** <br/> |int  <br/> |外  <br/> |用于注册的注册服务器的 ID。 [服务器表](servers.md)的详细信息，请参阅。 <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |池在其中捕获会话的 ID。 [池表](pools.md)的详细信息，请参阅。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外  <br/> |将边缘服务器注册。 [业务服务器 2015年的 Skype 在 EdgeServers 表](edgeservers.md)的详细信息，请参阅。 <br/> |
|**IsInternal** <br/> |位  <br/> ||无论用户登录从内部或不。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||UserService 是否可用。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||是否注册到主注册与否。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||指示使用高存活力的分支装置注册用户。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||登记时间。  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||撤消注册码注册时间。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||注册请求的响应代码。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||诊断的注册请求的 ID。 这表明该诊断信息类型。  <br/> |
|**DeviceId** <br/> |int  <br/> |外  <br/> |注册请求来自该设备。 请参阅[设备表中业务服务器 2015年的 Skype](devices.md)的详细信息。 <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |外  <br/> |De-register，如启动用户、 注册过期、 客户端故障，和更多的原因。 [业务服务器 2015年的 Skype 在 DeRegisterType 表](deregistertype.md)的详细信息，请参阅。 <br/> |
|**Ip 地址** <br/> |nvarchar(256)  <br/> ||终结点用户的 IP 地址注册。 这可以是一个 IPv4 地址或 IPv6 地址。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> ||供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   

