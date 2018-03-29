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
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="03b52-104">企业服务器 2015年的 Skype 通话质量的仪表板 (CQD) 数据为 API</span><span class="sxs-lookup"><span data-stu-id="03b52-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="03b52-105">**摘要：**请查阅 Rata API 呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="03b52-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="03b52-106">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="03b52-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="03b52-107">数据 API 提供编程访问调用质量仪表板为 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="03b52-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="03b52-108">数据 API 呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="03b52-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="03b52-109">数据 API 提供 QoE 多维数据集的查询接口。</span><span class="sxs-lookup"><span data-stu-id="03b52-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="03b52-110">数据 API 是 REST API 的使用提供了基于指定的尺寸和筛选器的聚合的 QoE 指标的多维数据库。</span><span class="sxs-lookup"><span data-stu-id="03b52-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="03b52-111">下表中包括的其余操作。</span><span class="sxs-lookup"><span data-stu-id="03b52-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="03b52-112">**操作**</span><span class="sxs-lookup"><span data-stu-id="03b52-112">**Operation**</span></span>|<span data-ttu-id="03b52-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="03b52-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="03b52-114">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="03b52-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="03b52-115">获取可用的维度和度量值的列表。</span><span class="sxs-lookup"><span data-stu-id="03b52-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="03b52-116">维度成员</span><span class="sxs-lookup"><span data-stu-id="03b52-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="03b52-117">获取维度成员操作返回的特定维度中的成员的列表。</span><span class="sxs-lookup"><span data-stu-id="03b52-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="03b52-118">它还提供筛选成员名单和获取子集，以减少网络传输成本的能力。</span><span class="sxs-lookup"><span data-stu-id="03b52-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="03b52-119">运行查询</span><span class="sxs-lookup"><span data-stu-id="03b52-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="03b52-120">运行的查询操作提供了基于指定的尺寸、 尺寸和筛选多维数据集上运行查询的能力，并重新返回的数据。</span><span class="sxs-lookup"><span data-stu-id="03b52-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="03b52-121">清除缓存</span><span class="sxs-lookup"><span data-stu-id="03b52-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="03b52-122">清除缓存操作删除服务器上的查询和数据缓存。</span><span class="sxs-lookup"><span data-stu-id="03b52-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="03b52-123">这将重置缓存，我们将最新数据从 QoE 多维数据集之后用于新的请求。</span><span class="sxs-lookup"><span data-stu-id="03b52-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="03b52-124">获得整合日志</span><span class="sxs-lookup"><span data-stu-id="03b52-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="03b52-125">获取操作返回描述 QoE 多维数据集中活动的日志条目的列表处理整合日志。</span><span class="sxs-lookup"><span data-stu-id="03b52-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="03b52-126">获取最后一个集成数据</span><span class="sxs-lookup"><span data-stu-id="03b52-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="03b52-127">从多维数据集获取最后的集成数据。</span><span class="sxs-lookup"><span data-stu-id="03b52-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="03b52-128">**跨来源的资源共享 (CORS) 数据 API 支持**</span><span class="sxs-lookup"><span data-stu-id="03b52-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="03b52-129">数据 API 支持跨原始资源共享 (CORS)。</span><span class="sxs-lookup"><span data-stu-id="03b52-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="03b52-130">CORS 是 HTTP 功能，可以将 web 应用程序运行在一个域访问另一个域中的资源。</span><span class="sxs-lookup"><span data-stu-id="03b52-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="03b52-131">Web 浏览器实现称为[同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)同源策略使 web 页从另一个域中调用的 Api 的安全限制。</span><span class="sxs-lookup"><span data-stu-id="03b52-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="03b52-132">CORS 提供一种安全的方法，以允许一个域 （原始域） 另一个域中调用的 Api。</span><span class="sxs-lookup"><span data-stu-id="03b52-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="03b52-133">请参阅 CORS [CORS 技术指标](https://www.w3.org/TR/cors/)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="03b52-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="03b52-134">**启用数据 API CORS**</span><span class="sxs-lookup"><span data-stu-id="03b52-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="03b52-135">以下是摘录数据 API web.config 文件中，显示在 corsTrustedOrigin 应用程序设置中列出的两个域。</span><span class="sxs-lookup"><span data-stu-id="03b52-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="03b52-136">从这些服务器加载的脚本所做的所有请求都受信任数据 API。</span><span class="sxs-lookup"><span data-stu-id="03b52-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="03b52-137">请务必包括具体协议、 主机名称和端口 （如果有的话）。</span><span class="sxs-lookup"><span data-stu-id="03b52-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="03b52-138">不要不将任何反斜杠字符 （/） 结尾。</span><span class="sxs-lookup"><span data-stu-id="03b52-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="03b52-139">通过用逗号分隔，可以指定多个条目。</span><span class="sxs-lookup"><span data-stu-id="03b52-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>

```


