---
title: Skype for Business Server 中用于呼叫质量仪表板 (CQD) API
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要：了解用于通话质量仪表板的存储库 API。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803122"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="a48be-104">Skype for Business Server 中用于呼叫质量仪表板 (CQD) API</span><span class="sxs-lookup"><span data-stu-id="a48be-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="a48be-105">**摘要：** 了解用于通话质量仪表板的存储库 API。</span><span class="sxs-lookup"><span data-stu-id="a48be-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a48be-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="a48be-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a48be-107">存储库 API 为 Skype for Business Server 的呼叫质量仪表板提供编程访问。</span><span class="sxs-lookup"><span data-stu-id="a48be-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="a48be-108">用于通话质量仪表板的存储库 API</span><span class="sxs-lookup"><span data-stu-id="a48be-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="a48be-109">存储库 API 提供存储库数据库的数据访问接口。</span><span class="sxs-lookup"><span data-stu-id="a48be-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="a48be-110">存储库允许将内容组织在树或图形结构中，以便用户可以按照对用户有意义的方式对内容进行分组。</span><span class="sxs-lookup"><span data-stu-id="a48be-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="a48be-111">存储库支持两种常规类型的用户：系统用户（表示存储库的内置用户）和代表存储库的授权用户的常规用户。</span><span class="sxs-lookup"><span data-stu-id="a48be-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="a48be-112">存储库 API 由三种常规服务组成：</span><span class="sxs-lookup"><span data-stu-id="a48be-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="a48be-113">[用于 CQD 的用户服务](user-service.md) - 用于访问用户。</span><span class="sxs-lookup"><span data-stu-id="a48be-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="a48be-114">[呼叫质量仪表板项目服务 (CQD) ](item-service.md) - 用于访问项目和存储在项中的内容。</span><span class="sxs-lookup"><span data-stu-id="a48be-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="a48be-115">[呼叫质量仪表板的用户设置服务 (CQD) ](user-settings-service.md) - 用于访问用户设置。</span><span class="sxs-lookup"><span data-stu-id="a48be-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="a48be-116">通话质量仪表板使用存储库 API 管理以下信息：</span><span class="sxs-lookup"><span data-stu-id="a48be-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="a48be-117">**用户** - 有权访问存储库的用户的表示形式。</span><span class="sxs-lookup"><span data-stu-id="a48be-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="a48be-118">**Report** - 包含查询列表，以内容存储在存储库项中。</span><span class="sxs-lookup"><span data-stu-id="a48be-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="a48be-119">**查询** - 用于从数据 API 检索数据，以内容存储在存储库项中。</span><span class="sxs-lookup"><span data-stu-id="a48be-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="a48be-120">**用户设置** - 描述用户的可选应用程序行为。</span><span class="sxs-lookup"><span data-stu-id="a48be-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="a48be-121">**跨源资源共享 (CORS) 存储库 API 支持**</span><span class="sxs-lookup"><span data-stu-id="a48be-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="a48be-122">存储库 API 支持跨源资源共享 (CORS) 。</span><span class="sxs-lookup"><span data-stu-id="a48be-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="a48be-123">CORS 是一项 HTTP 功能，它使运行在一个域下的 Web 应用程序能够访问另一个域中的资源。</span><span class="sxs-lookup"><span data-stu-id="a48be-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="a48be-124">Web 浏览器实现一种安全限制，称为 [同](https://www.w3.org/Security/wiki/Same_Origin_Policy) 源策略同源策略，可防止网页调用不同域中的 API。</span><span class="sxs-lookup"><span data-stu-id="a48be-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="a48be-125">CORS 提供了一种安全方法，允许一个 (源域) 调用另一个域中的 API。</span><span class="sxs-lookup"><span data-stu-id="a48be-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="a48be-126">有关 [CORS 的详细信息，请参阅 CORS](https://www.w3.org/TR/cors/) 规范。</span><span class="sxs-lookup"><span data-stu-id="a48be-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="a48be-127">**为存储库 API 启用 CORS**</span><span class="sxs-lookup"><span data-stu-id="a48be-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="a48be-128">下面摘录了存储库 API web.config，显示了 corsTrustedOrigin 应用程序设置中列出的两个域。</span><span class="sxs-lookup"><span data-stu-id="a48be-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="a48be-129">从这些服务器加载的脚本提出的所有请求都受存储库 API 信任。</span><span class="sxs-lookup"><span data-stu-id="a48be-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="a48be-130">请记住包含确切的协议、主机名和端口 (（如果有) ）。</span><span class="sxs-lookup"><span data-stu-id="a48be-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="a48be-131">请勿将 / (/) 放在末尾。</span><span class="sxs-lookup"><span data-stu-id="a48be-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="a48be-132">可以通过用逗号分隔来指定多个条目。</span><span class="sxs-lookup"><span data-stu-id="a48be-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


