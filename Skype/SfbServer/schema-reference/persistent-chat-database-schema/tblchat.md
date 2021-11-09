---
title: tblChat
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat 表包含所有聊天消息。
ms.openlocfilehash: e8a07c0c8ff8b3b473855ee86f6fc0c276e959f6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839814"
---
# <a name="tblchat"></a>tblChat
 
tblChat 表包含所有聊天消息。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|channelId  <br/> |int，不为 null  <br/> |节点 ID。  <br/> |
|chatId  <br/> |bigint，不为 null  <br/> |由 tblLastChatId 表生成的用于确定聊天室顺序的唯一序列号（每个节点 ID 一个）。  <br/> |
|chatDate  <br/> |bigint，不为 null  <br/> |聊天消息的时间戳。  <br/> |
|userId  <br/> |int，不为 null  <br/> |发布者的主要 ID。  <br/> |
|isAlert  <br/> |bit，不为 null  <br/> |如果消息是警报消息，则为 True。否则为 False。  <br/> |
|content  <br/> |nvarchar (max)，不为 null  <br/> | 聊天内容（纯文本版本）。该内容通常为纯文本，但以下情况除外： <br/>  文件表示为 ma-filelink: 链接。 <br/>  链接表示为 HTML 元素（但内容类型不能被视为 HTML）。 <br/>  情景编码为"[STORY]...."-like 格式。 <br/> |
|rtf  <br/> |varchar (max)   <br/> |聊天内容（RTF 版本）。 如果客户端未提供，可能为 Null。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |主键。  <br/> |
   

