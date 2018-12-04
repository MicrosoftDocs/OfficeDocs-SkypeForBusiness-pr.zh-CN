---
title: tblLastChatId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Lastchatid 包含为每个用户生成并且在 tblChat 表中使用） 的上一个聊天 ID。
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505086"
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