---
title: CodecDescription 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表映射到它们相应的编解码器的编解码器的唯一标识符。 编解码器用于编码数字信号传输和广播，然后将解码播放这些信号。 此表是在 Microsoft Lync Server 2013 中引入
ms.openlocfilehash: 49dea2867ef7614fab3015efbd24e6ec47da8c55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="codecdescription-table"></a>CodecDescription 表
 
CodecDescription 表映射到它们相应的编解码器的编解码器的唯一标识符。 编解码器用于编码数字信号传输和广播，然后将解码播放这些信号。 此表是在 Microsoft Lync Server 2013 中引入
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |分配给该编解码器的唯一标识符。  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |唯一  <br/> |对应于 CodecDescriptionKey 的编解码器的唯一描述。  <br/> |
   

