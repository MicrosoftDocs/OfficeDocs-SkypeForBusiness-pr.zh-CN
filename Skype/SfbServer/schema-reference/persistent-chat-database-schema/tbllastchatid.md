---
title: tblLastChatId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: LastChatId 包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。
ms.openlocfilehash: 219aa136ed24d6ffd0f5793fe12511c41c037da4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390854"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
LastChatId 包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。
  
**列**

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
