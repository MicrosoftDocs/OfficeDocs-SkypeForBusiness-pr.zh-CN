---
title: 清除缓存
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 摘要： 了解如何清除缓存操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: c2371a7f99eb37e8e01be919bf6c31b0c9a452cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195549"
---
# <a name="clear-cache"></a>清除缓存
 
**摘要：** 了解清除缓存操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
清除缓存操作是用于呼叫的质量仪表板的数据 API 的一部分。
  
## <a name="clear-cache"></a>清除缓存

清除缓存操作删除查询和数据的服务器上的缓存。 这将重置缓存，我们将刷新数据从 QoE 多维数据集是用于新的请求。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|发布  <br/> |https://\<门户\>/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他的标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 （确定)。
  
 **响应标头**的任何其他的标头。
  
 **响应正文**-无。
  

