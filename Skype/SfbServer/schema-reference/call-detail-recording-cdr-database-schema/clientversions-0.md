---
title: ClientVersions 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储参与数据库中记录的会话的各种客户端类型和版本的相关信息。 视图中的每条记录表示一个客户端版本。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296537"
---
# <a name="clientversions-view"></a>ClientVersions 视图
 
ClientVersions 视图存储参与数据库中记录的会话的各种客户端类型和版本的相关信息。 视图中的每条记录表示一个客户端版本。 此视图已在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> 某些列可能有多条记录。 
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |标识此客户端类型和版本的唯一编号。  <br/> |
|**版本** <br/> |nvarchar(256)  <br/> |表示用户代理。  <br/> |
|**ClientType** <br/> |int  <br/> |客户端的类型。  <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |客户端所属的类别。 例如, 客户端 Conferencing_Attendant_ 1.0 属于 ClientCategory CAA。  <br/> |
   

