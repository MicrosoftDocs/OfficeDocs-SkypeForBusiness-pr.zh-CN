---
title: tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat 包含所有聊天消息。
ms.openlocfilehash: 15c7030fe14f62c5d32af54c0f5a6901da3f977b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295536"
---
# <a name="tblchat"></a>tblChat
 
tblChat 包含所有聊天消息。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|channelId  <br/> |int, not null  <br/> |节点 ID。  <br/> |
|chatId  <br/> |bigint, not null  <br/> |定义由 tblLastChatId 表生成的聊天室顺序的唯一序列号 (每个节点 ID)。  <br/> |
|chatDate  <br/> |bigint, not null  <br/> |聊天消息的时间戳。  <br/> |
|userId  <br/> |int, not null  <br/> |海报的主体 ID。  <br/> |
|isAlert  <br/> |位, not null  <br/> |如果邮件是警告消息, 则为 True。 如果不是, 则为 False。  <br/> |
|内容  <br/> |nvarchar (max), not null  <br/> | 聊天内容 (纯文本版本)。 内容通常为纯文本, 但有以下例外: <br/>  文件表示为 ma-filelink: links。 <br/>  链接表示为 HTML 元素 (尽管无法将内容类型视为 HTML)。 <br/>  情景编码为 "[情景] ..."-类似格式。 <br/> |
|rtf  <br/> |varchar (max)  <br/> |聊天内容 (RTF 版本)。 如果客户端不提供, 则可能为 Null。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |主键。  <br/> |
   

