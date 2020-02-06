---
title: Skype for Business Server 中的呼叫质量仪表板（CQD）的知识库 API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要：了解呼叫质量仪表板的知识库 API。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: a027cc7402bad7524343391f9bf7039dd077a46c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816691"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="883a0-104">Skype for Business Server 中的呼叫质量仪表板（CQD）的知识库 API</span><span class="sxs-lookup"><span data-stu-id="883a0-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="883a0-105">**摘要：** 了解 "呼叫质量" 仪表板的知识库 API。</span><span class="sxs-lookup"><span data-stu-id="883a0-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="883a0-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="883a0-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="883a0-107">存储库 API 提供对 Skype for Business 服务器的呼叫质量仪表板的编程访问。</span><span class="sxs-lookup"><span data-stu-id="883a0-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="883a0-108">呼叫质量仪表板的知识库 API</span><span class="sxs-lookup"><span data-stu-id="883a0-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="883a0-109">知识库 API 为知识库数据库提供数据访问接口。</span><span class="sxs-lookup"><span data-stu-id="883a0-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="883a0-110">存储库允许内容按树或图形结构进行组织，以便用户可以按照对用户有意义的方式对其进行分组。</span><span class="sxs-lookup"><span data-stu-id="883a0-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="883a0-111">存储库支持两种常规类型的用户：系统用户（即表示存储库的内置用户），以及表示存储库的授权用户的常规用户。</span><span class="sxs-lookup"><span data-stu-id="883a0-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="883a0-112">存储库 API 包括三个常规服务：</span><span class="sxs-lookup"><span data-stu-id="883a0-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="883a0-113">[CQD 用户服务](user-service.md)-用于访问用户。</span><span class="sxs-lookup"><span data-stu-id="883a0-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="883a0-114">[通话质量仪表板（CQD）的项目服务](item-service.md)-用于访问项目和存储在项目中的内容。</span><span class="sxs-lookup"><span data-stu-id="883a0-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="883a0-115">[呼叫质量仪表板（CQD）的用户设置服务](user-settings-service.md)-用于访问用户设置。</span><span class="sxs-lookup"><span data-stu-id="883a0-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="883a0-116">通话质量仪表板使用知识库 API 管理以下信息：</span><span class="sxs-lookup"><span data-stu-id="883a0-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="883a0-117">**用户**可访问存储库的用户的表示形式。</span><span class="sxs-lookup"><span data-stu-id="883a0-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="883a0-118">**报表**-包含查询的列表，该列表存储为存储库项目中的内容。</span><span class="sxs-lookup"><span data-stu-id="883a0-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="883a0-119">**查询**-用于从数据 API 检索数据，这些数据存储为存储库项目中的内容。</span><span class="sxs-lookup"><span data-stu-id="883a0-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="883a0-120">**用户设置**-描述用户的可选应用程序行为。</span><span class="sxs-lookup"><span data-stu-id="883a0-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="883a0-121">**存储库 API 的跨源资源共享（CORS）支持**</span><span class="sxs-lookup"><span data-stu-id="883a0-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="883a0-122">存储库 API 支持跨源资源共享（CORS）。</span><span class="sxs-lookup"><span data-stu-id="883a0-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="883a0-123">CORS 是一种 HTTP 功能，可使在一个域下运行的 web 应用程序访问其他域中的资源。</span><span class="sxs-lookup"><span data-stu-id="883a0-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="883a0-124">Web 浏览器实现了一个称为[相同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)的安全限制，该策略可防止网页调用其他域中的 api。</span><span class="sxs-lookup"><span data-stu-id="883a0-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="883a0-125">CORS 提供一种安全的方法，允许一个域（原始域）调用另一个域中的 Api。</span><span class="sxs-lookup"><span data-stu-id="883a0-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="883a0-126">有关 CORS 的详细信息，请参阅[cors 规范](https://www.w3.org/TR/cors/)。</span><span class="sxs-lookup"><span data-stu-id="883a0-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="883a0-127">**为存储库 API 启用 CORS**</span><span class="sxs-lookup"><span data-stu-id="883a0-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="883a0-128">下面是知识库 API web.config 的节选内容，显示了 corsTrustedOrigin 应用程序设置中列出的两个域。</span><span class="sxs-lookup"><span data-stu-id="883a0-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="883a0-129">从这些服务器加载的脚本发出的所有请求均受存储库 API 的信任。</span><span class="sxs-lookup"><span data-stu-id="883a0-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="883a0-130">切记要包括确切的协议、主机名和端口（如果有）。</span><span class="sxs-lookup"><span data-stu-id="883a0-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="883a0-131">不要在结尾处放置任何正斜杠字符（/）。</span><span class="sxs-lookup"><span data-stu-id="883a0-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="883a0-132">可以通过使用逗号分隔来指定多个条目。</span><span class="sxs-lookup"><span data-stu-id="883a0-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


