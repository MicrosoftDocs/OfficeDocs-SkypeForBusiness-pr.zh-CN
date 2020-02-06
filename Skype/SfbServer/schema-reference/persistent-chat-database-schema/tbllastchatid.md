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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 包含为每位用户生成（并在 tblChat 表中使用）的最后一个聊天 ID。
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814580"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId 包含为每位用户生成（并在 tblChat 表中使用）的最后一个聊天 ID。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|a  <br/> |int，not null  <br/> |节点 ID （聊天室-仅类型）。  <br/> |
|lastChatID  <br/> |bigint，not null  <br/> |上次使用的聊天 ID。  <br/> |
   
**标示**

|**列**|**说明**|
|:-----|:-----|
|\<lastChatID\>  <br/> |主关键字（仅一个参数 a 足以处理）。  <br/> |
|a  <br/> |带有 tblNode 表中的 lookup 的外键。  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblChat](tblchat.md)
