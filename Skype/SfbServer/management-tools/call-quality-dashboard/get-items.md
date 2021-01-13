---
title: 获取项目
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 摘要：了解作为项目服务的一部分的 Get Items 操作。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832532"
---
# <a name="get-items"></a>获取项目
 
**摘要：** 了解"获取项目"操作，该操作是项服务的一部分。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
  
Get Items 操作是呼叫质量仪表板的存储库 API 中的项目服务的一部分。
  
## <a name="get-items"></a>获取项目

获取项目将返回存储库中的所有项目。
  
|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200 (确定) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是 JSON 中的示例响应负载。
  
> [!NOTE]
> 返回 Item 对象的数组。 有关 Item 对象的详细信息，请参阅"获取项目"。 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
