---
title: 注册表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 每条记录代表一个用户注册事件。
ms.openlocfilehash: ed8ce9f160f42384548a01d2cd6c74b3b24e60f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627774"
---
# <a name="registration-table"></a>注册表
 
每条记录代表一个用户注册事件。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主、外  <br/> |会话请求的时间。 与 **SessionIdSeq** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主、外  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime** 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |用户 ID。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||标识注册终结点的 GUID。通常，来自同一用户的同一计算机的注册事件具有相同的终结点 ID。不同计算机具有不同的终结点 ID。  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||ID 用于区分涉及同一用户和同一终结点的注册。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |当前用户的客户端版本。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ClientVersions](clientversions.md)表。 <br/> |
|**RegistrarId** <br/> |int  <br/> |Foreign  <br/> |用于注册的注册服务器的 ID。 有关详细信息 [，请参阅 Servers](servers.md) 表。 <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |在其中捕获会话的池的 ID。 有关详细信息 [，请参阅 Pools](pools.md) 表。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |Foreign  <br/> |进行注册的边缘服务器。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 EdgeServers](edgeservers.md)表。 <br/> |
|**IsInternal** <br/> |Bit  <br/> ||用户是否从内部登录。  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||UserService 是否可用。  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||是否注册到主注册器。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||指示用户是否通过 Survivable Branch Appliance 注册。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||注册时间。  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||注销时间。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||注册请求的响应代码。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||注册请求的诊断 ID。此 ID 用于指示诊断信息类型。  <br/> |
|**DeviceId** <br/> |int  <br/> |Foreign  <br/> |发出注册请求的设备。 有关详细信息[，请参阅 Skype for Business Server 2015](devices.md)中的设备表。 <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Foreign  <br/> |取消注册的原因，如"用户启动"、注册已过期、客户端失败等。 有关详细信息，请参阅[Skype for Business Server 2015 中的 DeRegisterType](deregistertype.md)表。 <br/> |
|**IPAddress** <br/> |nvarchar (256)   <br/> ||用户在其中注册的终结点的 IP 地址。 可以是 IPv4 地址或 IPv6 地址。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段是在 2015 年 Skype for Business Server引入的。  <br/> |
   

