---
title: 在业务服务器 2015年的 Skype 的位置表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每个记录表示紧急呼叫，类似 E9-1-1 调用中的一个位置引用。
ms.openlocfilehash: b15e7f0b7930871b97dc3341a47153965529810e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的位置表
 
每个记录表示紧急呼叫，类似 E9-1-1 调用中的一个位置引用。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主键和外  <br/> |会议请求的时间。 与**SessionIdSeq**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主键和外  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**位置** <br/> |nvarchar(max)  <br/> ||紧急呼叫的位置。  <br/> |
   

