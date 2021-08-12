---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: LastChatId 包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。
ms.openlocfilehash: ecd707a8e6c9dbec220f137c69042c22ac6e1d8a4e46a46e4c2d8a6f035c8a0d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322934"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
LastChatId 包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|nodeID  <br/> |int，不为 null  <br/> |节点 ID（仅限聊天室类型）。  <br/> |
|lastChatID  <br/> |bigint，不为 null  <br/> |上次使用的聊天 ID。  <br/> |
   
**Keys**

|**列**|**说明**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |主键（只有 nodeID 足以进行处理）。  <br/> |
|nodeID  <br/> |其查找包含在 tblNode.nodeID 表中的外键。  <br/> |
   
## <a name="see-also"></a>另请参阅

[tblChat](tblchat.md)
