---
title: CodecDescription 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表将唯一的编解码器标识符映射到其对应的编解码器。 编解码器用于编码数字信号传输和广播，然后进行解码播放这些信号。 此表是在 Microsoft Lync Server 2013 中引入
ms.openlocfilehash: 9881c802e332801d4990bf01894d5f8b68150fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920101"
---
# <a name="codecdescription-table"></a>CodecDescription 表
 
CodecDescription 表将唯一的编解码器标识符映射到其对应的编解码器。 编解码器用于编码数字信号传输和广播，然后进行解码播放这些信号。 此表是在 Microsoft Lync Server 2013 中引入
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |分配给编解码器的唯一标识符。  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |唯一  <br/> |与 CodecDescriptionKey 对应的编解码器的唯一说明。  <br/> |
   

