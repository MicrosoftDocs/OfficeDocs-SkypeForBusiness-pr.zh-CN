---
title: ErrorCategory 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表包含每个 Skype 的业务服务器 2015年诊断分类的友好名称。 默认情况下，业务服务器 2015年的 Skype 使用以下分类：
ms.openlocfilehash: 70322d30b516d003fcac015a4eda7382a13cd2be
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886957"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>ErrorCategory 表中的业务服务器 2015 Skype
 
ErrorCategory 表包含每个 Skype 的业务服务器 2015年诊断分类的友好名称。 默认情况下，业务服务器 2015年的 Skype 使用以下分类：
  
- 0-成功
    
- 1--预期失败
    
- 2-意外失败
    
此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |分类的唯一标识符。  <br/> |
|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。 <br/> |nvarchar(256)  <br/> || 值和分配给分类的友好名称。 允许的值包括： <br/>  0-成功 <br/>  1--预期失败 <br/>  2-意外失败 <br/> |
   

