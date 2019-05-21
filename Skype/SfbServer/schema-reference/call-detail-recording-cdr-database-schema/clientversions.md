---
title: Skype for Business Server 2015 中的 ClientVersions 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 表是一个支持表, 用于存储参与数据库中记录的会话的各种客户端类型和版本的列表。 表中的每条记录表示一个客户端版本。
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296509"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ClientVersions 表
 
ClientVersions 表是一个支持表, 用于存储参与数据库中记录的会话的各种客户端类型和版本的列表。 表中的每条记录表示一个客户端版本。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |标识此客户端类型和版本的唯一编号。  <br/> |
|**版本** <br/> |**nvarchar(256)** <br/> ||版本名称。  <br/> |
|**ClientType** <br/> |int  <br/> ||指定会话中使用的客户端类型。 有关详细信息, 请参阅[UserAgentDef 表](useragentdef.md)。 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

