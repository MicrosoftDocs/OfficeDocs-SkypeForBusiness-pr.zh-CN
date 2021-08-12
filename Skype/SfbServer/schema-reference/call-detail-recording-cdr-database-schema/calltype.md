---
title: Skype for Business Server 2015 中的 CallType 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表是存储可能的呼叫类型列表的静态表。
ms.openlocfilehash: d5dce646dfff73d9935aba568827e21671daf4073721f8b892f369d62348e945
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296959"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 CallType 表
 
CallType 表是存储可能的呼叫类型列表的静态表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |主  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 允许的值： <br/>  0 -- 未知 <br/>  1 - 即时消息 <br/>  2 -- 应用程序共享 <br/>  3 -- 音频 <br/>  4 - 音频和视频 <br/>  5 - 文件传输 <br/> |
   

