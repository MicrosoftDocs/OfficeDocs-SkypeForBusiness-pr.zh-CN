---
title: UriTypes 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表包含 Skype for Business Server 2015 中监视的不同 URI （统一资源标识符）类型。
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814840"
---
# <a name="uritypes-table"></a>UriTypes 表
 
UriTypes 表包含 Skype for Business Server 2015 中监视的不同 URI （统一资源标识符）类型。

在创建 CDR 数据库时，将创建两个记录来表示 PhoneUri 和 UserUri，并在此之后创建的记录会被动态分配 UriTypeId。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |分配给 URI 类型的唯一标识符。  <br/> 可能的值-0 到255 |
|**UriType** <br/> |nvarchar(256)  <br/> || 不同 URI 类型的说明。 以下值是预分配的： <br/>  1-电话 Uri <br/>  0-用户 Uri <br/> <br/>  其他可能的类型包括： <br/>conf:applicationsharing <br/> conf:audio-video<br/> 会议：聊天<br/>    conf:focus<br/>   mras<br/>
