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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions 视图存储参与数据库中记录的会话的各种客户端类型和版本的相关信息。 视图中的每条记录表示一个客户端版本。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815410"
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
|**ClientCategory** <br/> |nvarchar （64）  <br/> |客户端所属的类别。 例如，客户端 Conferencing_Attendant_1 .0 属于 ClientCategory CAA。  <br/> |
   

