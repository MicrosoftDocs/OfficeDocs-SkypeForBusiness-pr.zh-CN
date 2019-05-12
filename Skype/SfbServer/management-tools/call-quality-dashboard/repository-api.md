---
title: 呼叫质量仪表板 (CQD) 中的业务服务器 Skype 的库 API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要： 了解呼叫质量仪表板的存储库 API。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: cc3e7709255ae8fce2821b6555b9bc230658565a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915267"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="13e60-104">呼叫质量仪表板 (CQD) 中的业务服务器 Skype 的库 API</span><span class="sxs-lookup"><span data-stu-id="13e60-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="13e60-105">**摘要：** 对于呼叫质量的仪表板，请了解库 API。</span><span class="sxs-lookup"><span data-stu-id="13e60-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="13e60-106">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="13e60-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="13e60-107">存储库 API 提供编程访问呼叫质量仪表板的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="13e60-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="13e60-108">呼叫质量仪表板的库 API</span><span class="sxs-lookup"><span data-stu-id="13e60-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="13e60-109">存储库 API 提供了一个数据访问接口到存储库数据库。</span><span class="sxs-lookup"><span data-stu-id="13e60-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="13e60-110">存储库中允许的内容，以便用户可以将它们组合中对用户有意义的方式来组织树或图结构中。</span><span class="sxs-lookup"><span data-stu-id="13e60-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="13e60-111">存储库支持两种常规用户： 系统的用户，即表示存储库，内置用户与表示存储库的授权的用户的常规用户。</span><span class="sxs-lookup"><span data-stu-id="13e60-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="13e60-112">存储库 API 包含三个常规服务：</span><span class="sxs-lookup"><span data-stu-id="13e60-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="13e60-113">[用户服务 CQD](user-service.md) -用于访问用户。</span><span class="sxs-lookup"><span data-stu-id="13e60-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="13e60-114">[项服务的呼叫质量仪表板 (CQD)](item-service.md) -用于访问项目和存储在项目中的内容。</span><span class="sxs-lookup"><span data-stu-id="13e60-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="13e60-115">[用户设置服务的呼叫质量仪表板 (CQD)](user-settings-service.md) -用于访问用户设置。</span><span class="sxs-lookup"><span data-stu-id="13e60-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="13e60-116">呼叫质量仪表板使用存储库 API 来管理的以下信息：</span><span class="sxs-lookup"><span data-stu-id="13e60-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="13e60-117">**用户**-表示形式到存储库具有访问权的用户。</span><span class="sxs-lookup"><span data-stu-id="13e60-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="13e60-118">**报表**-包含查询，作为存储库项目中的内容存储的列表。</span><span class="sxs-lookup"><span data-stu-id="13e60-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="13e60-119">**查询**-用于检索数据 API，作为存储库项目中的内容存储中的数据。</span><span class="sxs-lookup"><span data-stu-id="13e60-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="13e60-120">**用户设置**-介绍用户可选的应用程序行为。</span><span class="sxs-lookup"><span data-stu-id="13e60-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="13e60-121">**跨源资源共享 (CORS) 库 API 支持**</span><span class="sxs-lookup"><span data-stu-id="13e60-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="13e60-122">存储库 API 支持跨源资源共享 (CORS)。</span><span class="sxs-lookup"><span data-stu-id="13e60-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="13e60-123">CORS 是 HTTP 功能，使运行下一个域的 web 应用程序以访问其他域中的资源。</span><span class="sxs-lookup"><span data-stu-id="13e60-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="13e60-124">Web 浏览器实现称为阻止从不同域中的调用 Api 网页的[同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)同源策略的安全限制。</span><span class="sxs-lookup"><span data-stu-id="13e60-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="13e60-125">CORS 提供安全的方式，以允许一个域 （原点而言的） 来调用其他域中的 Api。</span><span class="sxs-lookup"><span data-stu-id="13e60-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="13e60-126">请参阅 CORS [CORS 规范](https://www.w3.org/TR/cors/)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="13e60-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="13e60-127">**启用库 API 的 CORS**</span><span class="sxs-lookup"><span data-stu-id="13e60-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="13e60-128">下面是摘录存储库 API web.config，显示 corsTrustedOrigin 应用程序设置中列出的两个域。</span><span class="sxs-lookup"><span data-stu-id="13e60-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="13e60-129">通过从这些服务器中加载脚本所做的所有请求都受信任库 API。</span><span class="sxs-lookup"><span data-stu-id="13e60-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="13e60-130">请记住要包含的确切协议、 主机名和端口 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="13e60-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="13e60-131">不将任何反斜杠 （/） 字符末尾。</span><span class="sxs-lookup"><span data-stu-id="13e60-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="13e60-132">通过用逗号分隔，可以指定多个条目。</span><span class="sxs-lookup"><span data-stu-id="13e60-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


