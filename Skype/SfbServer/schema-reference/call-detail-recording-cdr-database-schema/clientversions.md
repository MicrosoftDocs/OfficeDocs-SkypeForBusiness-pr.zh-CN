---
title: Skype for Business Server 2015 中的 ClientVersions 表
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
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 表是一个支持表，用于存储已参与数据库中记录的会话的各种客户端类型和版本的列表。表中的每条记录都代表一个客户端版本。
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813312"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ClientVersions 表
 
ClientVersions 表是一个支持表，用于存储已参与数据库中记录的会话的各种客户端类型和版本的列表。表中的每条记录都代表一个客户端版本。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |主  <br/> |标识此客户端类型和版本的唯一号码。  <br/> |
|**版本** <br/> |**nvarchar (256)** <br/> ||版本名称。  <br/> |
|**ClientType** <br/> |int  <br/> ||指定会话中使用的客户端的类型。 有关详细信息， [请参阅 UserAgentDef](useragentdef.md) 表。 <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
   

