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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881801"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="34c83-104">呼叫质量仪表板 (CQD) 中的业务服务器 Skype 的数据 API</span><span class="sxs-lookup"><span data-stu-id="34c83-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="34c83-105">**摘要：** 对于呼叫质量的仪表板，请了解 Rata API。</span><span class="sxs-lookup"><span data-stu-id="34c83-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="34c83-106">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="34c83-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="34c83-107">数据 API 提供编程访问呼叫质量仪表板的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="34c83-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="34c83-108">呼叫质量仪表板的数据 API</span><span class="sxs-lookup"><span data-stu-id="34c83-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="34c83-109">数据 API 提供了到 QoE 多维数据集的查询界面。</span><span class="sxs-lookup"><span data-stu-id="34c83-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="34c83-110">数据 API 提供了基于指定的尺寸和筛选器的聚合的 QoE 度量的多维数据库所使用的是 REST API。</span><span class="sxs-lookup"><span data-stu-id="34c83-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="34c83-111">下表中包含的其余部分操作。</span><span class="sxs-lookup"><span data-stu-id="34c83-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="34c83-112">**操作**</span><span class="sxs-lookup"><span data-stu-id="34c83-112">**Operation**</span></span>|<span data-ttu-id="34c83-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="34c83-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="34c83-114">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="34c83-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="34c83-115">获取可用维度和度量值的列表。</span><span class="sxs-lookup"><span data-stu-id="34c83-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="34c83-116">获取维度成员</span><span class="sxs-lookup"><span data-stu-id="34c83-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="34c83-117">获取维度成员操作返回的特定维度成员的列表。</span><span class="sxs-lookup"><span data-stu-id="34c83-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="34c83-118">它还提供的功能来筛选成员列表和获取子集，以减少线路传输成本。</span><span class="sxs-lookup"><span data-stu-id="34c83-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="34c83-119">运行查询</span><span class="sxs-lookup"><span data-stu-id="34c83-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="34c83-120">运行的查询操作提供能够运行基于指定的维度和度量，筛选器多维数据集上的查询并返回返回数据。</span><span class="sxs-lookup"><span data-stu-id="34c83-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="34c83-121">清除缓存</span><span class="sxs-lookup"><span data-stu-id="34c83-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="34c83-122">清除缓存操作删除查询和数据的服务器上的缓存。</span><span class="sxs-lookup"><span data-stu-id="34c83-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="34c83-123">这将重置缓存，我们将刷新数据从 QoE 多维数据集是用于新的请求。</span><span class="sxs-lookup"><span data-stu-id="34c83-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="34c83-124">获取集成日志</span><span class="sxs-lookup"><span data-stu-id="34c83-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="34c83-125">获取集成日志操作返回描述 QoE 多维数据集中活动的日志条目的列表处理。</span><span class="sxs-lookup"><span data-stu-id="34c83-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="34c83-126">获取最后一个集成数据</span><span class="sxs-lookup"><span data-stu-id="34c83-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="34c83-127">获得多维数据集的最后一个集成数据。</span><span class="sxs-lookup"><span data-stu-id="34c83-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="34c83-128">**跨源资源共享 (CORS) 支持的数据 API**</span><span class="sxs-lookup"><span data-stu-id="34c83-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="34c83-129">数据 API 支持跨源资源共享 (CORS)。</span><span class="sxs-lookup"><span data-stu-id="34c83-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="34c83-130">CORS 是 HTTP 功能，使运行下一个域的 web 应用程序以访问其他域中的资源。</span><span class="sxs-lookup"><span data-stu-id="34c83-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="34c83-131">Web 浏览器实现称为阻止从不同域中的调用 Api 网页的[同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)同源策略的安全限制。</span><span class="sxs-lookup"><span data-stu-id="34c83-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="34c83-132">CORS 提供安全的方式，以允许一个域 （原点而言的） 来调用其他域中的 Api。</span><span class="sxs-lookup"><span data-stu-id="34c83-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="34c83-133">请参阅 CORS [CORS 规范](https://www.w3.org/TR/cors/)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34c83-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="34c83-134">**CORS 启用数据 API**</span><span class="sxs-lookup"><span data-stu-id="34c83-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="34c83-135">下面是摘录数据 API web.config，显示 corsTrustedOrigin 应用程序设置中列出的两个域。</span><span class="sxs-lookup"><span data-stu-id="34c83-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="34c83-136">所有请求所做的这些服务器从加载脚本都信任的数据 API。</span><span class="sxs-lookup"><span data-stu-id="34c83-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="34c83-137">请记住要包含的确切协议、 主机名和端口 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="34c83-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="34c83-138">不将任何反斜杠 （/） 字符末尾。</span><span class="sxs-lookup"><span data-stu-id="34c83-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="34c83-139">通过用逗号分隔，可以指定多个条目。</span><span class="sxs-lookup"><span data-stu-id="34c83-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


