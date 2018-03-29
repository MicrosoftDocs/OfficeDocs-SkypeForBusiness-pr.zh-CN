---
title: 在业务服务器 2015年的 Skype 的 CallType 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表是一个静态的表来存储可能调用类型的列表。
ms.openlocfilehash: e2353176a69db9eada137525561541d26caa7a8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 CallType 表
 
CallType 表是一个静态的表来存储可能调用类型的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 允许的值： <br/>  0--未知 <br/>  1-即时消息 <br/>  2--应用程序共享 <br/>  3-音频 <br/>  4-音频和视频 <br/>  5-文件传输 <br/> |
   

