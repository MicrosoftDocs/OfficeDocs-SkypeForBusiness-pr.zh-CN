---
title: UriTypes 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes Table 包含 2015 (2015) 监视的不同 URI Skype for Business Server统一资源标识符。
ms.openlocfilehash: 196207a60bd738b4ef987248d53356b3f20336e8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394874"
---
# <a name="uritypes-table"></a>UriTypes 表
 
UriTypes Table 包含 2015 (2015) 监视的不同 URI Skype for Business Server统一资源标识符。

创建 CDR DB 时，将创建两个代表 PhoneUri 和 UserUri 的记录，然后动态分配 UriTypeId 创建记录。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |主  <br/> |分配给 URI 类型的唯一标识符。  <br/> 可能的值 - 0 到 255 |
|**UriType** <br/> |nvarchar (256)   <br/> || 不同的 URI 类型的描述。 预分配以下值： <br/>  1 - 电话 Uri <br/>  0 - 用户 Uri <br/> <br/>  其他可能的类型包括： <br/>conf：applicationsharing <br/> conf：audio-video<br/> conf：chat<br/>    conf：focus<br/>   mras<br/>
