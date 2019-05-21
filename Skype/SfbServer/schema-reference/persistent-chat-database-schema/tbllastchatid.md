---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 包含为每位用户生成 (并在 tblChat 表中使用) 的最后一个聊天 ID。
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295396"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId 包含为每位用户生成 (并在 tblChat 表中使用) 的最后一个聊天 ID。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|a  <br/> |int, not null  <br/> |节点 ID (聊天室-仅类型)。  <br/> |
|lastChatID  <br/> |bigint, not null  <br/> |上次使用的聊天 ID。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<lastChatID\>  <br/> |主关键字 (仅一个参数 a 足以处理)。  <br/> |
|a  <br/> |带有 tblNode 表中的 lookup 的外键。  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblChat](tblchat.md)
