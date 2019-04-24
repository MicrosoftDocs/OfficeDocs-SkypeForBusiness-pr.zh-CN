---
title: tblChat
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblchat 表包含所有聊天消息。
ms.openlocfilehash: 54e19fe729d9f96afb04d22a917864118de75efe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212647"
---
# <a name="tblchat"></a>tblChat
 
tblchat 表包含所有聊天消息。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|channelId  <br/> |int，不为 null  <br/> |节点 id。  <br/> |
|chatId  <br/> |bigint，不为 null  <br/> |唯一序列号 （每个节点 ID 一个) 定义由 tblLastChatId 表生成的聊天室顺序。  <br/> |
|chatDate  <br/> |bigint，不为 null  <br/> |聊天消息的时间戳。  <br/> |
|用户 Id  <br/> |int，不为 null  <br/> |海报的主体 ID。  <br/> |
|isAlert  <br/> |bit，不为 null  <br/> |如果邮件是一条警告消息，则为 true。 如果没有，则为 false。  <br/> |
|内容  <br/> |nvarchar (max)，不为 null  <br/> | 聊天内容 （使用明文版本）。 内容通常采用纯文本有以下例外： <br/>  文件表示为 ma-filelink： 链接。 <br/>  链接表示为 HTML 元素 （但内容类型不能被视为 HTML）。 <br/>  情景被编码为"[STORY]..."的格式类似。 <br/> |
|rtf  <br/> |varchar(max)  <br/> |聊天内容 （的 RTF 版本）。 如果客户端不提供它可能为 Null。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|\<channelID chatD\>  <br/> |主键。  <br/> |
   

