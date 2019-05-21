---
title: Skype for Business Server 中的呼叫质量仪表板 (CQD) 的数据 API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '摘要: 了解通话质量仪表板的有效期 API。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: f74f581a3d46ba7cf75daf92df5ade16dab510d0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274798"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Skype for Business Server 中的呼叫质量仪表板 (CQD) 的数据 API
 
**摘要:** 了解通话质量仪表板的有效期 API。 通话质量仪表板是 Skype for business 服务器的工具。
  
数据 API 提供对 Skype for business 服务器的呼叫质量仪表板的编程访问。
  
## <a name="data-api-for-call-quality-dashboard"></a>通话质量仪表板的数据 API

数据 API 提供 QoE 多维数据集的查询接口。 数据 API 是一个 REST API, 用于处理基于指定维度和筛选器提供聚合 QoE 指标的多维数据库。
  
下表中包括其余操作。
  

|**操作**|**说明**|
|:-----|:-----|
|[获取多维数据集](get-cube.md) <br/> |获取可用的维度和度量的列表。  <br/> |
|[获取维度成员](get-dimension-members.md) <br/> |获取维度成员操作返回特定维度的成员列表。 它还提供了筛选成员列表和获取子集的功能, 以降低线路传输成本。  <br/> |
|[运行查询](run-query.md) <br/> |"运行查询" 操作提供基于指定的维度、度量和筛选器对多维数据集运行查询并返回数据的功能。  <br/> |
|[清除缓存](clear-cache.md) <br/> |清除缓存操作在服务器上删除查询和数据的缓存。 这将重置缓存, 随后将从 QoE 多维数据集中获取新请求的新数据。  <br/> |
|[获取集成日志](get-integration-log.md) <br/> |获取集成日志操作返回日志条目的列表, 这些日志条目描述 QoE 多维数据集处理中的活动。  <br/> |
|[获取最后一个集成数据](get-last-integration-data.md) <br/> |获取来自多维数据集的最后一个集成数据。  <br/> |
   
 **数据 API 的跨源资源共享 (CORS) 支持**
  
数据 API 支持跨源资源共享 (CORS)。 CORS 是一种 HTTP 功能, 可使在一个域下运行的 web 应用程序访问其他域中的资源。 Web 浏览器实现了一个称为[相同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)的安全限制, 该策略可防止网页调用其他域中的 api。 CORS 提供一种安全的方法, 允许一个域 (原始域) 调用另一个域中的 Api。 有关 CORS 的详细信息, 请参阅[cors 规范](https://www.w3.org/TR/cors/)。
  
 **为数据 API 启用 CORS**
  
 下面是数据 API web.config 的节选内容, 显示了 corsTrustedOrigin 应用程序设置中列出的两个域。 从这些服务器加载的脚本发出的所有请求均受数据 API 的信任。
  
切记要包括确切的协议、主机名和端口 (如果有)。 不要在结尾处放置任何正斜杠字符 (/)。 可以通过使用逗号分隔来指定多个条目。
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


