---
title: MediaList 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 表是一个静态表，用于存储各种媒体类型的列表。
ms.openlocfilehash: 00667806e5099db35cce29b07248569faf09ee24
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767490"
---
# <a name="medialist-table"></a>MediaList 表
 
MediaList 表是一个静态表，用于存储各种媒体类型的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |主  <br/> |值：1-7  <br/> |
|**Media** <br/> |nvarchar (256)   <br/> || MediaID 和 Media 值的静态映射： <br/>  1 -- IM <br/>  2 - 文件传输 <br/>  3 - 远程协助 <br/>  4 - 应用程序共享 <br/>  5 -- 音频 <br/>  6 -- 视频 <br/>  7 - 应用邀请 <br/> |
   
如果你尝试确定 LcsCDR.SessionDetailsView.MediaTypes 中值模态类型，则需要使用以下 Join 代码段： 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
