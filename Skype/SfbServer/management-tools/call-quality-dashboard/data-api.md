---
title: 调用质量仪表板的数据 API (CQD) Skype for Business Server
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 摘要：了解调用质量仪表板的数据 API。 通话质量仪表板是用于Skype for Business Server的工具。
ms.openlocfilehash: 3204398dcf667f785f1efe71cc4d6dc5478ce54d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675734"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>调用质量仪表板的数据 API (CQD) Skype for Business Server
 
**总结：** 了解调用质量仪表板的数据 API。 通话质量仪表板是用于Skype for Business Server的工具。
  
数据 API 为Skype for Business Server的呼叫质量仪表板提供编程访问权限。
  
## <a name="data-api-for-call-quality-dashboard"></a>调用质量仪表板的数据 API

数据 API 提供 QoE 多维数据集的查询接口。 数据 API 是一种 REST API，用于处理基于指定维度和筛选器的聚合 QoE 指标的多维数据库。
  
REST 操作包含在下表中。
  

|**操作**|**说明**|
|:-----|:-----|
|[获取多维数据集](get-cube.md) <br/> |获取可用维度和度量的列表。  <br/> |
|[获取维度成员](get-dimension-members.md) <br/> |获取维度成员操作返回特定维度的成员列表。 它还提供筛选成员列表和获取子集的功能，以降低线路传输成本。  <br/> |
|[运行查询](run-query.md) <br/> |运行查询操作提供基于指定维度、度量和筛选器在多维数据集上运行查询并返回数据的功能。  <br/> |
|[清除缓存](clear-cache.md) <br/> |清除缓存操作会删除服务器上用于查询和数据的缓存。 这将重置缓存，之后我们将从 QoE 多维数据集获取新请求的新数据。  <br/> |
|[获取集成日志](get-integration-log.md) <br/> |获取集成日志操作返回描述 QoE 多维数据集处理中活动的日志条目列表。  <br/> |
|[获取最后一个集成数据](get-last-integration-data.md) <br/> |从多维数据集获取最后一个集成数据。  <br/> |
   
 **跨源资源共享 (CORS) 数据 API 支持**
  
数据 API 支持跨源资源共享 (CORS) 。 CORS 是一项 HTTP 功能，允许在一个域下运行的 Web 应用程序访问另一个域中的资源。 Web 浏览器实施称为 [同](https://www.w3.org/Security/wiki/Same_Origin_Policy) 源策略同源策略的安全限制，该限制阻止网页在其他域中调用 API。 CORS 提供了一种安全的方法，允许源域 (一个域) 在另一个域中调用 API。 有关 CORS 的详细信息，请参阅 [CORS 规范](https://www.w3.org/TR/cors/) 。
  
 **为数据 API 启用 CORS**
  
 下面是数据 API web.config的摘录，其中显示了 corsTrustedOrigin 应用程序设置中列出的两个域。 数据 API 信任从这些服务器加载的脚本发出的所有请求。
  
请记得包含确切的协议、主机名和端口 (（如果有任何) ）。 不要在结尾处 (/) 任何正斜杠字符。 可以通过逗号分隔来指定多个条目。
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
...  </appSettings>
</configuration>
```


