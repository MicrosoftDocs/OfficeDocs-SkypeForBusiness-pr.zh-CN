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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat 包含所有聊天消息。
ms.openlocfilehash: 7221136c435c1d4af836174ddfde5cbd02f4c5f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814670"
---
# <a name="tblchat"></a>tblChat
 
tblChat 包含所有聊天消息。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|channelId  <br/> |int，not null  <br/> |节点 ID。  <br/> |
|chatId  <br/> |bigint，not null  <br/> |定义由 tblLastChatId 表生成的聊天室顺序的唯一序列号（每个节点 ID）。  <br/> |
|chatDate  <br/> |bigint，not null  <br/> |聊天消息的时间戳。  <br/> |
|userId  <br/> |int，not null  <br/> |海报的主体 ID。  <br/> |
|isAlert  <br/> |位，not null  <br/> |如果邮件是警告消息，则为 True。 如果不是，则为 False。  <br/> |
|内容  <br/> |nvarchar （max），not null  <br/> | 聊天内容（纯文本版本）。 内容通常为纯文本，但有以下例外： <br/>  文件表示为 ma-filelink： links。 <br/>  链接表示为 HTML 元素（尽管无法将内容类型视为 HTML）。 <br/>  情景编码为 "[情景] ..."-类似格式。 <br/> |
|rtf  <br/> |varchar （max）  <br/> |聊天内容（RTF 版本）。 如果客户端不提供，则可能为 Null。  <br/> |
   
**Key**

|**列**|**说明**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |主键。  <br/> |
   

