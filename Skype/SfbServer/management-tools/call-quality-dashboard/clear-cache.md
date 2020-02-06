---
title: 清除缓存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 摘要：了解 "清除缓存" 操作，该操作是 "调用质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 821b02f204c98f5acefe69df1c848c31cd2205b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816881"
---
# <a name="clear-cache"></a>清除缓存
 
**摘要：** 了解 "清除缓存" 操作，该操作是 "调用质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"清除缓存" 操作是 "调用质量" 仪表板的数据 API 的一部分。
  
## <a name="clear-cache"></a>清除缓存

清除缓存操作在服务器上删除查询和数据的缓存。 这将重置缓存，随后将从 QoE 多维数据集中获取新请求的新数据。
  

|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|发布  <br/> |https://\<portal\>/QoEDataService/ClearCache  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码200（OK）。
  
 **响应标题**-无其他标题。
  
 **响应正文**-无。
  

