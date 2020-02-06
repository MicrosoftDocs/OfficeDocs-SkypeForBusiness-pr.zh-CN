---
title: MediaList 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 表是一个静态表，用于存储各种媒体类型的列表。
ms.openlocfilehash: 7742baf17240ca810268721c0e47e37f17e555cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815030"
---
# <a name="medialist-table"></a>MediaList 表
 
MediaList 表是一个静态表，用于存储各种媒体类型的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |值：1-7  <br/> |
|**媒体** <br/> |nvarchar(256)  <br/> || MediaID 与媒体值的静态映射： <br/>  1 – IM <br/>  2-文件传输 <br/>  3-远程协助 <br/>  4-应用程序共享 <br/>  5 – 音频 <br/>  6 – 视频 <br/>  7-应用邀请 <br/> |
   
如果你尝试确定 LcsCDR.SessionDetailsView.MediaTypes 中的值的形式类型，则需要使用以下加入代码段： 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
