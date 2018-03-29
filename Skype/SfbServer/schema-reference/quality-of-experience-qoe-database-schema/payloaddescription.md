---
title: PayloadDescription 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 表是支持表。 每个记录表示音频或视频会话中使用的一个编解码器。
ms.openlocfilehash: fb4acb8182db920e25305b2be72cbc19700792bb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="payloaddescription-table"></a>PayloadDescription 表
 
PayloadDescription 表是支持表。 每个记录表示音频或视频会话中使用的一个编解码器。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |标识编解码器的唯一编号。  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |唯一  <br/> |编解码器名称。  <br/> |
   

