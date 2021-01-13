---
title: Skype for Business Server 中用于呼叫质量仪表板 (CQD) 的数据 API
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 摘要：了解通话质量仪表板的数据 API。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832692"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="4b4e7-104">Skype for Business Server 中用于呼叫质量仪表板 (CQD) 的数据 API</span><span class="sxs-lookup"><span data-stu-id="4b4e7-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="4b4e7-105">**摘要：** 了解通话质量仪表板的数据 API。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="4b4e7-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4b4e7-107">数据 API 为 Skype for Business Server 的呼叫质量仪表板提供编程访问。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="4b4e7-108">通话质量仪表板的数据 API</span><span class="sxs-lookup"><span data-stu-id="4b4e7-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="4b4e7-109">数据 API 提供 QoE 多维数据集的查询接口。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="4b4e7-110">数据 API 是一种 REST API，用于处理基于指定维度和筛选器的聚合 QoE 指标的多维数据库。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="4b4e7-111">REST 操作包含在下表中。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="4b4e7-112">**操作**</span><span class="sxs-lookup"><span data-stu-id="4b4e7-112">**Operation**</span></span>|<span data-ttu-id="4b4e7-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="4b4e7-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4b4e7-114">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="4b4e7-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="4b4e7-115">获取可用维度和度量的列表。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="4b4e7-116">获取维度成员</span><span class="sxs-lookup"><span data-stu-id="4b4e7-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="4b4e7-117">"获取维度成员"操作返回特定维度的成员列表。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="4b4e7-118">它还提供筛选成员列表和获取子集的能力，以减少线路传输成本。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="4b4e7-119">运行查询</span><span class="sxs-lookup"><span data-stu-id="4b4e7-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="4b4e7-120">运行查询操作能够基于指定的维度、度量和筛选器对多维数据集运行查询，并返回数据。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="4b4e7-121">清除缓存</span><span class="sxs-lookup"><span data-stu-id="4b4e7-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="4b4e7-122">清除缓存操作会删除服务器上用于查询和数据的缓存。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="4b4e7-123">这将重置缓存，我们将在以后获取新请求的 QoE 多维数据集中的新数据。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="4b4e7-124">获取集成日志</span><span class="sxs-lookup"><span data-stu-id="4b4e7-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="4b4e7-125">获取集成日志操作返回描述 QoE 多维数据集处理中的活动的日志条目列表。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="4b4e7-126">获取最后一个集成数据</span><span class="sxs-lookup"><span data-stu-id="4b4e7-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="4b4e7-127">从多维数据集获取最后一个集成数据。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="4b4e7-128">**跨源资源共享 (CORS) 数据 API 支持**</span><span class="sxs-lookup"><span data-stu-id="4b4e7-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="4b4e7-129">数据 API 支持跨源资源共享 (CORS) 。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="4b4e7-130">CORS 是一项 HTTP 功能，它使运行在一个域下的 Web 应用程序能够访问另一个域中的资源。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="4b4e7-131">Web 浏览器实现一种安全限制，称为 [同](https://www.w3.org/Security/wiki/Same_Origin_Policy) 源策略同源策略，可防止网页调用不同域中的 API。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="4b4e7-132">CORS 提供了一种安全方法，允许一个 (源域) 调用另一个域中的 API。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="4b4e7-133">有关 [CORS 的详细信息，请参阅 CORS](https://www.w3.org/TR/cors/) 规范。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="4b4e7-134">**为数据 API 启用 CORS**</span><span class="sxs-lookup"><span data-stu-id="4b4e7-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="4b4e7-135">以下是数据 API 应用程序的摘录，web.config corsTrustedOrigin 应用程序设置中列出的两个域。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="4b4e7-136">从这些服务器加载的脚本的所有请求都受数据 API 信任。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="4b4e7-137">请记住包含确切的协议、主机名和端口 (（如果有) ）。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="4b4e7-138">请勿将 / (/) 放在末尾。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="4b4e7-139">可以通过用逗号分隔来指定多个条目。</span><span class="sxs-lookup"><span data-stu-id="4b4e7-139">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


