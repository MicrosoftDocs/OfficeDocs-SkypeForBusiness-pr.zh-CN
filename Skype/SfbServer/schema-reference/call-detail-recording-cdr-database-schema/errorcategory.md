---
title: Skype for Business Server 2015 中的 ErrorCategory 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表包含每个 2015 Skype for Business Server分类的友好名称。 默认情况下，Skype for Business Server 2015 使用下列分类：
ms.openlocfilehash: 68114e96e04ca8e2cb45fbb2b9ba0b3934df4e363700f8a872f05cb1aa0e8a37
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347767"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ErrorCategory 表
 
ErrorCategory 表包含每个 2015 Skype for Business Server分类的友好名称。 默认情况下，Skype for Business Server 2015 使用下列分类：
  
- 0 -- 成功
    
- 1 -- 预期失败
    
- 2 - 意外失败
    
此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |主  <br/> |分类的唯一标识符。  <br/> |
|**名称** <br/> |nvarchar (256)   <br/> || 分配给分类的值和友好名称。允许的值有： <br/>  0 -- 成功 <br/>  1 -- 预期失败 <br/>  2 - 意外失败 <br/> |
   

