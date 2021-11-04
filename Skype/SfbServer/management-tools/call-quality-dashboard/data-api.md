---
title: 通话质量仪表板数据 API (CQD) 中Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 摘要：了解通话质量仪表板的数据 API。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 3a305ce3c6b4a1bbfcc0fbdedbb575477f76d62c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742038"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>通话质量仪表板数据 API (CQD) 中Skype for Business Server
 
**摘要：** 了解通话质量仪表板的数据 API。 通话质量仪表板是一种用于Skype for Business Server。
  
数据 API 为通话质量仪表板提供编程访问，Skype for Business Server。
  
## <a name="data-api-for-call-quality-dashboard"></a>通话质量仪表板的数据 API

数据 API 提供 QoE 多维数据集的查询接口。 数据 API 是一种 REST API，用于处理基于指定维度和筛选器提供聚合 QoE 指标的多维数据库。
  
REST 操作包含在下表中。
  

|**操作**|**说明**|
|:-----|:-----|
|[获取多维数据集](get-cube.md) <br/> |获取可用维度和度量的列表。  <br/> |
|[获取维度成员](get-dimension-members.md) <br/> |"获取维度成员"操作返回特定维度的成员列表。 它还提供筛选成员列表和获取子集的能力，以降低线路传输成本。  <br/> |
|[运行查询](run-query.md) <br/> |运行查询操作能够基于指定的维度、度量和筛选器对多维数据集运行查询，并返回数据。  <br/> |
|[清除缓存](clear-cache.md) <br/> |清除缓存操作会删除服务器上用于查询和数据的缓存。 这将重置缓存，之后我们将从 QoE 多维数据集获取新请求的新数据。  <br/> |
|[获取集成日志](get-integration-log.md) <br/> |获取集成日志操作返回描述 QoE 多维数据集处理中的活动的日志条目列表。  <br/> |
|[获取最后一个集成数据](get-last-integration-data.md) <br/> |从多维数据集获取最后一个集成数据。  <br/> |
   
 **跨源资源共享 (CORS) 数据 API 支持**
  
数据 API 支持跨源资源共享 (CORS) 。 CORS 是一项 HTTP 功能，它使在一个域下运行的 Web 应用程序可以访问另一个域中的资源。 Web 浏览器实现一个称为同源 [策略](https://www.w3.org/Security/wiki/Same_Origin_Policy) 同源策略的安全限制，阻止网页调用其他域中的 API。 CORS 提供了一种安全方法，允许源域 (一个) 域中调用 API。 有关 [CORS 的详细信息，请参阅 CORS](https://www.w3.org/TR/cors/) 规范。
  
 **启用 CORS for Data API**
  
 下面摘录了数据 API 应用程序，web.config corsTrustedOrigin 应用程序设置中列出的两个域。 从这些服务器加载的脚本提出的所有请求都受数据 API 信任。
  
请记住包含确切的协议、主机名和端口 (（如果有) ）。 不要将任何正斜杠字符 (/) 末尾。 可以通过用逗号分隔来指定多个条目。
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


