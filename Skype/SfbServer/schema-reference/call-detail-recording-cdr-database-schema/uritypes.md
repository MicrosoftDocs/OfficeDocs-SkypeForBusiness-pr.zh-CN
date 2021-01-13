---
title: UriTypes 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表包含 Skype for Business Server 2015 中 (受监视) 统一资源标识符的不同 URI。
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831682"
---
# <a name="uritypes-table"></a>UriTypes 表
 
UriTypes 表包含 Skype for Business Server 2015 中 (受监视) 统一资源标识符的不同 URI。

创建 CDR DB 后，将创建两条代表 PhoneUri 和 UserUri 的记录，然后动态分配 UriTypeId。 
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |主  <br/> |分配给 URI 类型的唯一标识符。  <br/> 可能的值 - 0 到 255 |
|**UriType** <br/> |nvarchar (256)   <br/> || 不同的 URI 类型的描述。 预分配以下值： <br/>  1 - 电话 Uri <br/>  0 - 用户 Uri <br/> <br/>  其他可能的类型包括： <br/>conf：applicationsharing <br/> conf：audio-video<br/> conf：chat<br/>    conf：focus<br/>   mras<br/>
