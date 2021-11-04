---
title: Skype for Business Server 2015 中的 ErrorCategory 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表包含每个 2015 Skype for Business Server分类的友好名称。 默认情况下，Skype for Business Server 2015 使用下列分类：
ms.openlocfilehash: 19fa265b337f293656473aa24c85bb5fc22008de
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743908"
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
   

