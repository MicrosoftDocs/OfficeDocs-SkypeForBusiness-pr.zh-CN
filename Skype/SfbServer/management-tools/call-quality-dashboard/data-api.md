---
title: 企业服务器 2015年的 Skype 通话质量的仪表板 (CQD) 数据为 API
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 摘要： 了解有关 Rata API 呼叫质量仪表板。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 038324064177c110c0736092985e9da1b330ea8b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a>企业服务器 2015年的 Skype 通话质量的仪表板 (CQD) 数据为 API
 
**摘要：**请查阅 Rata API 呼叫质量仪表板。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
数据 API 提供编程访问调用质量仪表板为 Skype 业务服务器 2015年个。
  
## <a name="data-api-for-call-quality-dashboard"></a>数据 API 呼叫质量仪表板

数据 API 提供 QoE 多维数据集的查询接口。 数据 API 是 REST API 的使用提供了基于指定的尺寸和筛选器的聚合的 QoE 指标的多维数据库。
  
下表中包括的其余操作。
  

|**操作**|**说明**|
|:-----|:-----|
|[获取多维数据集](get-cube.md) <br/> |获取可用的维度和度量值的列表。  <br/> |
|[维度成员](get-dimension-members.md) <br/> |获取维度成员操作返回的特定维度中的成员的列表。 它还提供筛选成员名单和获取子集，以减少网络传输成本的能力。  <br/> |
|[运行查询](run-query.md) <br/> |运行的查询操作提供了基于指定的尺寸、 尺寸和筛选多维数据集上运行查询的能力，并重新返回的数据。  <br/> |
|[清除缓存](clear-cache.md) <br/> |清除缓存操作删除服务器上的查询和数据缓存。 这将重置缓存，我们将最新数据从 QoE 多维数据集之后用于新的请求。  <br/> |
|[获得整合日志](get-integration-log.md) <br/> |获取操作返回描述 QoE 多维数据集中活动的日志条目的列表处理整合日志。  <br/> |
|[获取最后一个集成数据](get-last-integration-data.md) <br/> |从多维数据集获取最后的集成数据。  <br/> |
   
 **跨来源的资源共享 (CORS) 数据 API 支持**
  
数据 API 支持跨原始资源共享 (CORS)。 CORS 是 HTTP 功能，可以将 web 应用程序运行在一个域访问另一个域中的资源。 Web 浏览器实现称为[同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)同源策略使 web 页从另一个域中调用的 Api 的安全限制。 CORS 提供一种安全的方法，以允许一个域 （原始域） 另一个域中调用的 Api。 请参阅 CORS [CORS 技术指标](https://www.w3.org/TR/cors/)的详细信息。
  
 **启用数据 API CORS**
  
 以下是摘录数据 API web.config 文件中，显示在 corsTrustedOrigin 应用程序设置中列出的两个域。 从这些服务器加载的脚本所做的所有请求都受信任数据 API。
  
请务必包括具体协议、 主机名称和端口 （如果有的话）。 不要不将任何反斜杠字符 （/） 结尾。 通过用逗号分隔，可以指定多个条目。
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>

```


