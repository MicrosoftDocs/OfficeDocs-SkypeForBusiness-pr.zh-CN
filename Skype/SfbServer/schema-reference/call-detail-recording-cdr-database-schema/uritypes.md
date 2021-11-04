---
title: UriTypes 表
ms.reviewer: ''
ms.author: v-mahoffman
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
description: UriTypes Table 包含 2015 (2015) 监视的不同 URI 和统一Skype for Business Server标识符。
ms.openlocfilehash: ee7a2d79458640eff2695ce253792e154d36dee4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767440"
---
# <a name="uritypes-table"></a>UriTypes 表
 
UriTypes Table 包含 2015 (2015) 监视的不同 URI 和统一Skype for Business Server标识符。

创建 CDR DB 时，将创建两个代表 PhoneUri 和 UserUri 的记录，然后动态分配 UriTypeId 创建记录。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |主  <br/> |分配给 URI 类型的唯一标识符。  <br/> 可能的值 - 0 到 255 |
|**UriType** <br/> |nvarchar (256)   <br/> || 不同的 URI 类型的描述。 预分配以下值： <br/>  1 - 电话 Uri <br/>  0 - 用户 Uri <br/> <br/>  其他可能的类型包括： <br/>conf：applicationsharing <br/> conf：audio-video<br/> conf：chat<br/>    conf：focus<br/>   mras<br/>
