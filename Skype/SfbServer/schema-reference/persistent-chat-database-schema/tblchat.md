---
title: tblChat
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat 包含了所有的聊天消息。
ms.openlocfilehash: 1a1a2986d69e2f5efafe365da3394de01c911623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblchat"></a>tblChat
 
tblChat 包含了所有的聊天消息。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|channelId  <br/> |int，不为空  <br/> |节点 id。  <br/> |
|chatId  <br/> |bigint，不为空  <br/> |唯一序列号 （每个节点 ID) 定义聊天室顺序，生成的 tblLastChatId 表。  <br/> |
|chatDate  <br/> |bigint，不为空  <br/> |聊天消息的时间戳。  <br/> |
|用户 Id  <br/> |int，不为空  <br/> |海报的主体 ID。  <br/> |
|isAlert  <br/> |位，不为空  <br/> |如果消息是一条警告消息，则为 true。 如果不是，则为 false。  <br/> |
|内容  <br/> |nvarchar （最大），不为空  <br/> | 聊天的内容 （纯文字版）。 内容通常是以纯文本形式有以下例外： <br/>  文件表示为 ma filelink： 链接。 <br/>  （尽管不能将内容类型视为 HTML） 链接表示为 HTML 元素。 <br/>  故事被编码为"[叙述]..."的格式类似。 <br/> |
|rtf 格式  <br/> |varchar(max)  <br/> |聊天的内容 （RTF 版本）。 如果客户端没有提供它可能为 Null。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<channelID chatD\>  <br/> |为主键。  <br/> |
   

