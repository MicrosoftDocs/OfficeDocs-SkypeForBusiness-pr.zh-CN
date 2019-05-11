---
title: CallType 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表是一个静态表，用于存储可能的呼叫类型的列表。
ms.openlocfilehash: a75ae3e22d435241e6bf2eb81b8268a7f1bb5a40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924792"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType 表中的业务服务器 2015 Skype
 
CallType 表是一个静态表，用于存储可能的呼叫类型的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 允许的值： <br/>  0-未知 <br/>  1-即时消息 <br/>  2--应用程序共享 <br/>  3-音频 <br/>  4-音频和视频 <br/>  5-文件传输 <br/> |
   

