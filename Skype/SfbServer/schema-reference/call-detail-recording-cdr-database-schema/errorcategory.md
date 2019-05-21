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
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'ErrorCategory 表包含每个 Skype for Business Server 2015 诊断分类的友好名称。 默认情况下, Skype for business Server 2015 使用以下分类:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296285"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ErrorCategory 表
 
ErrorCategory 表包含每个 Skype for Business Server 2015 诊断分类的友好名称。 默认情况下, Skype for business Server 2015 使用以下分类:
  
- 0--成功
    
- 1--预期故障
    
- 2-意外故障
    
此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |分类的唯一标识符。  <br/> |
|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。 <br/> |nvarchar(256)  <br/> || 分配给分类的值和友好名称。 允许的值包括： <br/>  0--成功 <br/>  1--预期故障 <br/>  2-意外故障 <br/> |
   

