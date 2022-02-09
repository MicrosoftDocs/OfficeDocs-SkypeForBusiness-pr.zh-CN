---
title: MediaList 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: da5d1c90f768e059ccb61b471d8f8e538c8c53aa
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418365"
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
