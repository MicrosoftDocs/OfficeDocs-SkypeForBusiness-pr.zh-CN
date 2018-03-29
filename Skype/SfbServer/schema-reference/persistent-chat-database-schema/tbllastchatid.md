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
description: tblLastChatId 包含已生成 （和 tblChat 表中） 的最后一个聊天 ID 为每个用户。
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId 包含已生成 （和 tblChat 表中） 的最后一个聊天 ID 为每个用户。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|nodeID  <br/> |int，不为空  <br/> |节点 ID （仅聊天室类型）。  <br/> |
|lastChatID  <br/> |bigint，不为空  <br/> |最后用的聊天 id。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<nodeID lastChatID\>  <br/> |主关键字 （仅 nodeID 是足够进行处理）。  <br/> |
|nodeID  <br/> |TblNode.nodeID 表中查找与外键。  <br/> |
   
## <a name="see-also"></a>另请参阅

#### 

[tblChat](tblchat.md)

