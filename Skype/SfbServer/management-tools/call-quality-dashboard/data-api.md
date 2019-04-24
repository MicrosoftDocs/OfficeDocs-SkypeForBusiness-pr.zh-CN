---
title: 呼叫质量仪表板 (CQD) 中的业务服务器 Skype 的数据 API
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 摘要： 了解有关 Rata API 呼叫质量仪表板。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 8dd04971533a8631b4f95be2f13bad84e41963d7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232813"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>呼叫质量仪表板 (CQD) 中的业务服务器 Skype 的数据 API
 
**摘要：** 对于呼叫质量的仪表板，请了解 Rata API。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
数据 API 提供编程访问呼叫质量仪表板的 Skype 业务服务器。
  
## <a name="data-api-for-call-quality-dashboard"></a>呼叫质量仪表板的数据 API

数据 API 提供了到 QoE 多维数据集的查询界面。 数据 API 提供了基于指定的尺寸和筛选器的聚合的 QoE 度量的多维数据库所使用的是 REST API。
  
下表中包含的其余部分操作。
  

|**操作**|**说明**|
|:-----|:-----|
|[获取多维数据集](get-cube.md) <br/> |获取可用维度和度量值的列表。  <br/> |
|[获取维度成员](get-dimension-members.md) <br/> |获取维度成员操作返回的特定维度成员的列表。 它还提供的功能来筛选成员列表和获取子集，以减少线路传输成本。  <br/> |
|[运行查询](run-query.md) <br/> |运行的查询操作提供能够运行基于指定的维度和度量，筛选器多维数据集上的查询并返回返回数据。  <br/> |
|[清除缓存](clear-cache.md) <br/> |清除缓存操作删除查询和数据的服务器上的缓存。 这将重置缓存，我们将刷新数据从 QoE 多维数据集是用于新的请求。  <br/> |
|[获取集成日志](get-integration-log.md) <br/> |获取集成日志操作返回描述 QoE 多维数据集中活动的日志条目的列表处理。  <br/> |
|[获取最后一个集成数据](get-last-integration-data.md) <br/> |获得多维数据集的最后一个集成数据。  <br/> |
   
 **跨源资源共享 (CORS) 支持的数据 API**
  
数据 API 支持跨源资源共享 (CORS)。 CORS 是 HTTP 功能，使运行下一个域的 web 应用程序以访问其他域中的资源。 Web 浏览器实现称为阻止从不同域中的调用 Api 网页的[同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)同源策略的安全限制。 CORS 提供安全的方式，以允许一个域 （原点而言的） 来调用其他域中的 Api。 请参阅 CORS [CORS 规范](https://www.w3.org/TR/cors/)的详细信息。
  
 **CORS 启用数据 API**
  
 下面是摘录数据 API web.config，显示 corsTrustedOrigin 应用程序设置中列出的两个域。 所有请求所做的这些服务器从加载脚本都信任的数据 API。
  
请记住要包含的确切协议、 主机名和端口 （如果有）。 不将任何反斜杠 （/） 字符末尾。 通过用逗号分隔，可以指定多个条目。
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


