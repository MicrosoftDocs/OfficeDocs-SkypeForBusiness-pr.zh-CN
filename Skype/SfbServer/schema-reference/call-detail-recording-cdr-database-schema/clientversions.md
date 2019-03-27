---
title: 请参阅 ClientVersions table 中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 表是一个支持表，用于存储各种客户端类型的列表和已参与记录数据库中的会话的版本。 表中的每条记录代表一个客户端版本。
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898527"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>请参阅 ClientVersions table 中的业务服务器 2015 Skype
 
ClientVersions 表是一个支持表，用于存储各种客户端类型的列表和已参与记录数据库中的会话的版本。 表中的每条记录代表一个客户端版本。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |标识此客户端类型和版本的唯一编号。  <br/> |
|**版本** <br/> |**nvarchar(256)** <br/> ||版本名称。  <br/> |
|**客户端类型** <br/> |int  <br/> ||指定客户端会话中使用的类型。 请参阅[UserAgentDef 表](useragentdef.md)的详细信息。 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

