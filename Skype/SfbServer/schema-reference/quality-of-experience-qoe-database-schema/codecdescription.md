---
title: CodecDescription 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表将唯一的编解码器标识符映射到相应的编解码器。 编解码器用于为传输和广播编码数字信号, 然后解码这些信号以进行播放。 此表是在 Microsoft Lync Server 2013 中引入的
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295039"
---
# <a name="codecdescription-table"></a>CodecDescription 表
 
CodecDescription 表将唯一的编解码器标识符映射到相应的编解码器。 编解码器用于为传输和广播编码数字信号, 然后解码这些信号以进行播放。 此表是在 Microsoft Lync Server 2013 中引入的
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |分配给编解码器的唯一标识符。  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |唯一  <br/> |与 CodecDescriptionKey 对应的编解码器的唯一说明。  <br/> |
   

