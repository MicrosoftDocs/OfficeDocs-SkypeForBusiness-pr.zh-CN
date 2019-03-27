---
title: UriTypes 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表包含的业务服务器 2015 Skype 中监控的不同 URI （统一资源标识符） 类型。
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899643"
---
# <a name="uritypes-table"></a>UriTypes 表
 
UriTypes 表包含的业务服务器 2015 Skype 中监控的不同 URI （统一资源标识符） 类型。

创建 CDR 数据库后，创建两个记录表示 PhoneUri 和 UserUri，并在的动态分配 UriTypeId 后创建的记录。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |分配给 URI 类型的唯一标识符。  <br/> 可能值-0 到 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || 不同的 URI 类型的说明。 预先分配是以下值： <br/>  1-电话 Uri <br/>  0-用户 Uri <br/> <br/>  其他可能的类型包括： <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
