---
title: 在业务服务器 2015年的 Skype 的 ClientVersions 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 是一个支持的表来存储各种客户端类型的列表和参加会话记录在数据库中的版本。 每个表中的记录表示某个客户端版本。
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 ClientVersions 表
 
ClientVersions 是一个支持的表来存储各种客户端类型的列表和参加会话记录在数据库中的版本。 每个表中的记录表示某个客户端版本。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |标识此客户端的类型和版本的唯一编号。  <br/> |
|**版本** <br/> |**nvarchar(256)** <br/> ||版本名称。  <br/> |
|**客户端类型** <br/> |int  <br/> ||指定客户端会话中使用的类型。 [UserAgentDef 表](useragentdef.md)的详细信息，请参阅。 <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
   

