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
ms.localizationpriority: medium
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表是存储可能的呼叫类型列表的静态表。
ms.openlocfilehash: 7c84e245cac2ceb25a5012f9caf4a2a31d4cb67b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620908"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 CallType 表
 
CallType 表是存储可能的呼叫类型列表的静态表。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |主  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 允许的值： <br/>  0 -- 未知 <br/>  1 - 即时消息 <br/>  2 -- 应用程序共享 <br/>  3 -- 音频 <br/>  4 - 音频和视频 <br/>  5 - 文件传输 <br/> |
   

