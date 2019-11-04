---
title: Skype for Business Server 中的呼叫质量仪表板（CQD）的数据 API
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
description: 摘要：了解通话质量仪表板的数据 API。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "36571916"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="979ac-104">Skype for Business Server 中的呼叫质量仪表板（CQD）的数据 API</span><span class="sxs-lookup"><span data-stu-id="979ac-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="979ac-105">**摘要：** 了解通话质量仪表板的数据 API。</span><span class="sxs-lookup"><span data-stu-id="979ac-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="979ac-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="979ac-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="979ac-107">数据 API 提供对 Skype for business 服务器的呼叫质量仪表板的编程访问。</span><span class="sxs-lookup"><span data-stu-id="979ac-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="979ac-108">通话质量仪表板的数据 API</span><span class="sxs-lookup"><span data-stu-id="979ac-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="979ac-109">数据 API 提供 QoE 多维数据集的查询接口。</span><span class="sxs-lookup"><span data-stu-id="979ac-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="979ac-110">数据 API 是一个 REST API，用于处理基于指定维度和筛选器提供聚合 QoE 指标的多维数据库。</span><span class="sxs-lookup"><span data-stu-id="979ac-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="979ac-111">下表中包括其余操作。</span><span class="sxs-lookup"><span data-stu-id="979ac-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="979ac-112">**操作**</span><span class="sxs-lookup"><span data-stu-id="979ac-112">**Operation**</span></span>|<span data-ttu-id="979ac-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="979ac-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="979ac-114">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="979ac-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="979ac-115">获取可用的维度和度量的列表。</span><span class="sxs-lookup"><span data-stu-id="979ac-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="979ac-116">获取维度成员</span><span class="sxs-lookup"><span data-stu-id="979ac-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="979ac-117">获取维度成员操作返回特定维度的成员列表。</span><span class="sxs-lookup"><span data-stu-id="979ac-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="979ac-118">它还提供了筛选成员列表和获取子集的功能，以降低线路传输成本。</span><span class="sxs-lookup"><span data-stu-id="979ac-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="979ac-119">运行查询</span><span class="sxs-lookup"><span data-stu-id="979ac-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="979ac-120">"运行查询" 操作提供基于指定的维度、度量和筛选器对多维数据集运行查询并返回数据的功能。</span><span class="sxs-lookup"><span data-stu-id="979ac-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="979ac-121">清除缓存</span><span class="sxs-lookup"><span data-stu-id="979ac-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="979ac-122">清除缓存操作在服务器上删除查询和数据的缓存。</span><span class="sxs-lookup"><span data-stu-id="979ac-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="979ac-123">这将重置缓存，随后将从 QoE 多维数据集中获取新请求的新数据。</span><span class="sxs-lookup"><span data-stu-id="979ac-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="979ac-124">获取集成日志</span><span class="sxs-lookup"><span data-stu-id="979ac-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="979ac-125">获取集成日志操作返回日志条目的列表，这些日志条目描述 QoE 多维数据集处理中的活动。</span><span class="sxs-lookup"><span data-stu-id="979ac-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="979ac-126">获取最后一个集成数据</span><span class="sxs-lookup"><span data-stu-id="979ac-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="979ac-127">获取来自多维数据集的最后一个集成数据。</span><span class="sxs-lookup"><span data-stu-id="979ac-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="979ac-128">**数据 API 的跨源资源共享（CORS）支持**</span><span class="sxs-lookup"><span data-stu-id="979ac-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="979ac-129">数据 API 支持跨源资源共享（CORS）。</span><span class="sxs-lookup"><span data-stu-id="979ac-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="979ac-130">CORS 是一种 HTTP 功能，可使在一个域下运行的 web 应用程序访问其他域中的资源。</span><span class="sxs-lookup"><span data-stu-id="979ac-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="979ac-131">Web 浏览器实现了一个称为[相同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)的安全限制，该策略可防止网页调用其他域中的 api。</span><span class="sxs-lookup"><span data-stu-id="979ac-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="979ac-132">CORS 提供一种安全的方法，允许一个域（原始域）调用另一个域中的 Api。</span><span class="sxs-lookup"><span data-stu-id="979ac-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="979ac-133">有关 CORS 的详细信息，请参阅[cors 规范](https://www.w3.org/TR/cors/)。</span><span class="sxs-lookup"><span data-stu-id="979ac-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="979ac-134">**为数据 API 启用 CORS**</span><span class="sxs-lookup"><span data-stu-id="979ac-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="979ac-135">下面是数据 API web.config 的节选内容，显示了 corsTrustedOrigin 应用程序设置中列出的两个域。</span><span class="sxs-lookup"><span data-stu-id="979ac-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="979ac-136">从这些服务器加载的脚本发出的所有请求均受数据 API 的信任。</span><span class="sxs-lookup"><span data-stu-id="979ac-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="979ac-137">切记要包括确切的协议、主机名和端口（如果有）。</span><span class="sxs-lookup"><span data-stu-id="979ac-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="979ac-138">不要在结尾处放置任何正斜杠字符（/）。</span><span class="sxs-lookup"><span data-stu-id="979ac-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="979ac-139">可以通过使用逗号分隔来指定多个条目。</span><span class="sxs-lookup"><span data-stu-id="979ac-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


