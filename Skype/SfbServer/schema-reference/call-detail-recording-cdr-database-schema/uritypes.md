---
title: UriTypes 表
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
ms.openlocfilehash: e21fe7d88c64acf57ad8d318a755b7fa6c73c1c2
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570056"
---
# <a name="uritypes-table"></a>UriTypes 表
 
UriTypes 表包含的业务服务器 2015 Skype 中监控的不同 URI （统一资源标识符） 类型。

当创建 CDR 数据库后时，将创建两个记录表示 PhoneUri 和 UserUri 和其他内容 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |分配给 URI 类型的唯一标识符。  <br/> 可能值-0 到 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || 不同的 URI 类型的说明。 预先分配是以下值： <br/>  1-电话 Uri <br/>  0-用户 Uri <br/> <br/>  其他可能的类型包括： <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>