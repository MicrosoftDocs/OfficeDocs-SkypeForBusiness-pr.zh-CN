---
title: Skype for Business Server 2015 中的对话框表
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: 对话框表是一个支持表，用于存储有关对等会话的 DialogIDs 的信息。
ms.openlocfilehash: f6cfc3e078ee8f4492d6f5baf65f66df77d7aedf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815270"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的对话框表
 
对话框表是一个支持表，用于存储有关对等会话的 DialogIDs 的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |会话请求的时间;与 SessionIDSeq 结合使用以唯一标识会话。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |标识会话的 ID 号。 与 SessionIDTime 结合使用以唯一标识会话。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID 的校验和。 此字段用于提高数据库搜索的速度。  <br/> |
|**ExternalId** <br/> |varbinary （775）  <br/> | <br/> |SIP 对话框 ID，存储为二进制。 二进制文件的格式为：  <br/> 对话框; 从-标签; 到-标记  <br/> 可以使用以下语法将此数据转换为文本格式：  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

