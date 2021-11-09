---
title: 清除缓存
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 摘要：了解"清除缓存"操作，这是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: de956a3541416100cf7877b46340f2eccb38b3ea
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843815"
---
# <a name="clear-cache"></a>清除缓存
 
**摘要：** 了解"清除缓存"操作，这是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
"清除缓存"操作是通话质量仪表板的数据 API 的一部分。
  
## <a name="clear-cache"></a>清除缓存

清除缓存操作会删除服务器上用于查询和数据的缓存。 这将重置缓存，之后我们将从 QoE 多维数据集获取新请求的新数据。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200 (确定) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 无。
  

