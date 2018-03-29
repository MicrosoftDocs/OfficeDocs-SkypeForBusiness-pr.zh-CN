---
title: 在业务服务器 2015年的 Skype 的 ErrorCategory 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表中包含每个 Skype 业务服务器 2015年诊断分类的友好名称。 默认情况下，业务服务器 2015年的 Skype 使用下列类别：
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 ErrorCategory 表
 
ErrorCategory 表中包含每个 Skype 业务服务器 2015年诊断分类的友好名称。 默认情况下，业务服务器 2015年的 Skype 使用下列类别：
  
- 0--成功
    
- 1-预期故障
    
- 2-意外失败
    
在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**类别 id** <br/> |tinyint  <br/> |Primary  <br/> |分类的唯一标识符。  <br/> |
|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。 <br/> |nvarchar(256)  <br/> || 价值和分配给分类的友好名称。 允许的值包括： <br/>  0--成功 <br/>  1-预期故障 <br/>  2-意外失败 <br/> |
   

