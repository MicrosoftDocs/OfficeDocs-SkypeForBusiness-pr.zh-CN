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
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes Table 包含 2015 (2015 中) 监视的不同 URI Skype for Business Server统一资源标识符。
ms.openlocfilehash: e6be4abb02fc29fb5becd9da8a1b45c4d8c6271f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583766"
---
# <a name="uritypes-table"></a>UriTypes 表
 
UriTypes Table 包含 2015 (2015 中) 监视的不同 URI Skype for Business Server统一资源标识符。

创建 CDR DB 时，将创建两个代表 PhoneUri 和 UserUri 的记录，然后动态分配 UriTypeId 创建记录。 
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |主  <br/> |分配给 URI 类型的唯一标识符。  <br/> 可能的值 - 0 到 255 |
|**UriType** <br/> |nvarchar (256)   <br/> || 不同的 URI 类型的描述。 预分配以下值： <br/>  1 - 电话 Uri <br/>  0 - 用户 Uri <br/> <br/>  其他可能的类型包括： <br/>conf：applicationsharing <br/> conf：audio-video<br/> conf：chat<br/>    conf：focus<br/>   mras<br/>
