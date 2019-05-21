---
title: Skype for Business Server 2015 中的 CallType 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表是一个静态表, 用于存储可能的调用类型的列表。
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296558"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 CallType 表
 
CallType 表是一个静态表, 用于存储可能的调用类型的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 允许的值: <br/>  0--未知 <br/>  1-即时消息 <br/>  2--应用程序共享 <br/>  3--音频 <br/>  4-音频和视频 <br/>  5-文件传输 <br/> |
   

