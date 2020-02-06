---
title: Skype for Business Server 2015 中的 ErrorCategory 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表包含每个 Skype for Business Server 2015 诊断分类的友好名称。 默认情况下，Skype for business Server 2015 使用以下分类：
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815250"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ErrorCategory 表
 
ErrorCategory 表包含每个 Skype for Business Server 2015 诊断分类的友好名称。 默认情况下，Skype for business Server 2015 使用以下分类：
  
- 0--成功
    
- 1--预期故障
    
- 2-意外故障
    
此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |分类的唯一标识符。  <br/> |
|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。 <br/> |nvarchar(256)  <br/> || 分配给分类的值和友好名称。 允许的值包括： <br/>  0--成功 <br/>  1--预期故障 <br/>  2-意外故障 <br/> |
   

