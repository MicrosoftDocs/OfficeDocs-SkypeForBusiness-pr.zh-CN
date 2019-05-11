---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Lastchatid 包含为每个用户生成并且在 tblChat 表中使用） 的上一个聊天 ID。
ms.openlocfilehash: 9d19c6c873660683ff526eb144d74b6e8752bf80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929964"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
Lastchatid 包含为每个用户生成并且在 tblChat 表中使用） 的上一个聊天 ID。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|nodeID  <br/> |int，不为 null  <br/> |节点 ID （仅限聊天室类型）。  <br/> |
|lastChatID  <br/> |bigint，不为 null  <br/> |上次使用的聊天 id。  <br/> |
   
**键**

|**列**|**说明**|
|:-----|:-----|
|\<nodeID lastChatID\>  <br/> |主键 (只有 nodeid 足以进行处理)。  <br/> |
|nodeID  <br/> |在 tblNode.nodeID 表中查找的外键。  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblChat](tblchat.md)
