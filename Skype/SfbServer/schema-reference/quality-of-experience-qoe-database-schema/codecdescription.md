---
title: CodecDescription 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表可将唯一编解码器标识符映射到其相应的编解码器。 编解码器用于对传输和广播的数字信号进行编码，然后解码这些信号以进行播放。 此表在 Microsoft Lync Server 2013 中引入
ms.openlocfilehash: cfd0953322f9cc34d90947c0d9be7ecb13cd3c33
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609169"
---
# <a name="codecdescription-table"></a>CodecDescription 表
 
CodecDescription 表可将唯一编解码器标识符映射到其相应的编解码器。 编解码器用于对传输和广播的数字信号进行编码，然后解码这些信号以进行播放。 此表在 Microsoft Lync Server 2013 中引入
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |主  <br/> |分配给编解码器的唯一标识符。  <br/> |
|**CodecDescription** <br/> |varchar (256)   <br/> |独特  <br/> |与 CodecDescriptionKey 对应的编解码器的唯一说明。  <br/> |
   

