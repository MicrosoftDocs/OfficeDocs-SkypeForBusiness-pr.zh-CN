---
title: 在业务服务器 2015年的 Skype 的对话表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: 对话表是一个支持的表来存储有关 DialogIDs 的对等会话的信息。
ms.openlocfilehash: b2953ff2bec35575221bc0d43785eb6c0d90e2d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的对话表
 
对话表是一个支持的表来存储有关 DialogIDs 的对等会话的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |会话的请求; 时间与 SessionIDSeq 配合使用，以唯一标识会话。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |以标识会话的 ID 号。 与 SessionIDTime 配合使用，以唯一标识会话。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID 的校验和。 此字段用于提高数据库搜索的速度。  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |SIP 对话框 ID 存储为二进制文件。 该二进制文件的格式为：  <br/> 对话; 从标记; 到标记  <br/> 此数据可以转换为文本格式，使用以下语法：  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

