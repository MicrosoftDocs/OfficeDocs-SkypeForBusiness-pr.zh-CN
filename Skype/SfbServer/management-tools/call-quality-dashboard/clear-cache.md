---
title: 清除缓存
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: f81e22b11851f4b2121f2444d7ded824f3d8530a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396364"
---
# <a name="clear-cache"></a>清除缓存
 
**摘要：** 了解"清除缓存"操作，这是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
"清除缓存"操作是通话质量仪表板的数据 API 的一部分。
  
## <a name="clear-cache"></a>清除缓存

清除缓存操作会删除服务器上用于查询和数据的缓存。 这将重置缓存，之后我们将从 QoE 多维数据集获取新请求的新数据。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|POST  <br/> |\<portal\>https:///QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200， (确定) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 无。
  

