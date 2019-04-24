---
title: Dialogs 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs 表是一个支持表，用于存储对等会话的 Dialogid 的信息。
ms.openlocfilehash: af7816c202f995e826567391bf32c5c32a2d0d94
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213653"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Dialogs 表中的业务服务器 2015 Skype
 
Dialogs 表是一个支持表，用于存储对等会话的 Dialogid 的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |会话请求; 的时间与 SessionIDSeq 结合使用，来唯一地标识会话。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |标识会话的 ID 号。 与 SessionIDTime 结合使用，来唯一地标识会话。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID 的校验和。 使用此字段来提高的搜索数据库的速度。  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |SIP 对话 ID，存储为二进制文件。 二进制文件格式为：  <br/> 对话框; 从标记; 到标记  <br/> 使用以下语法，可以是此数据转换为文本格式：  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

