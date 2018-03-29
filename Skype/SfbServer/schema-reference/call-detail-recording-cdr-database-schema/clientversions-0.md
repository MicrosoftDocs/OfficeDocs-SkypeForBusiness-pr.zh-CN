---
title: ClientVersions 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储不同的客户端类型和参加会话记录在数据库中的版本信息。 每个视图中的记录表示某个客户端版本。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 0906e35d0912684c9aeb169017b5df0a53202c50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-view"></a>ClientVersions 视图
 
ClientVersions 视图存储不同的客户端类型和参加会话记录在数据库中的版本信息。 每个视图中的记录表示某个客户端版本。 在 Microsoft Lync Server 2013 引入了此视图。
  
> [!NOTE]
> 可能有多个记录的某些列。 
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |标识此客户端的类型和版本的唯一编号。  <br/> |
|**版本** <br/> |nvarchar(256)  <br/> |表示用户代理。  <br/> |
|**客户端类型** <br/> |int  <br/> |客户端的类型。  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |客户端所属的类别。 例如，客户端 Conferencing_Attendant_1.0 就属于 ClientCategory CAA。  <br/> |
   

