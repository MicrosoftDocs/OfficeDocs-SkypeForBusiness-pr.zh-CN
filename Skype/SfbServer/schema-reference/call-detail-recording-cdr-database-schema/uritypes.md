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
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表包含 Skype for Business Server 2015 中监视的不同 URI (统一资源标识符) 类型。
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295746"
---
# <a name="uritypes-table"></a>UriTypes 表
 
UriTypes 表包含 Skype for Business Server 2015 中监视的不同 URI (统一资源标识符) 类型。

在创建 CDR 数据库时, 将创建两个记录来表示 PhoneUri 和 UserUri, 并在此之后创建的记录会被动态分配 UriTypeId。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |分配给 URI 类型的唯一标识符。  <br/> 可能的值-0 到255 |
|**UriType** <br/> |nvarchar(256)  <br/> || 不同 URI 类型的说明。 以下值是预分配的: <br/>  1-电话 Uri <br/>  0-用户 Uri <br/> <br/>  其他可能的类型包括: <br/>conf:applicationsharing <br/> conf:audio-video<br/> 会议: 聊天<br/>    conf:focus<br/>   mras<br/>
