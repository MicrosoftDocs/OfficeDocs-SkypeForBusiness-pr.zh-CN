---
title: 知识库 API 呼叫质量仪表板 (CQD) 在 Skype 业务服务器 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要： 了解关于存储库 API 呼叫质量仪表板。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 0f84e3967bd4f78f8852dbcfed8ce5d59cbe4e8c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="145b9-104">知识库 API 呼叫质量仪表板 (CQD) 在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="145b9-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="145b9-105">**摘要：**请查阅知识库 API 呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="145b9-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="145b9-106">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="145b9-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="145b9-107">知识库 API 提供编程访问调用质量仪表板为 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="145b9-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="145b9-108">知识库 API 呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="145b9-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="145b9-109">知识库 API 提供对知识库数据库的数据访问接口。</span><span class="sxs-lookup"><span data-stu-id="145b9-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="145b9-110">存储库可以树或图结构中，使用户可以将它们分组到对用户有意义的方式组织内容。</span><span class="sxs-lookup"><span data-stu-id="145b9-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="145b9-111">存储库中支持两种一般类型的用户： 系统用户，它是内置用户表示存储库中，并表示存储库中的授权的用户的一般用户。</span><span class="sxs-lookup"><span data-stu-id="145b9-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="145b9-112">知识库 API 包含三个常规服务：</span><span class="sxs-lookup"><span data-stu-id="145b9-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="145b9-113">[CQD 的用户服务](user-service.md)的访问用户。</span><span class="sxs-lookup"><span data-stu-id="145b9-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="145b9-114">[项目服务呼叫质量仪表板 (CQD)](item-service.md) -用于访问项目和项中存储的内容。</span><span class="sxs-lookup"><span data-stu-id="145b9-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="145b9-115">[用户设置服务呼叫质量仪表板 (CQD)](user-settings-service.md) -用于访问用户设置。</span><span class="sxs-lookup"><span data-stu-id="145b9-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="145b9-116">通话质量仪表板使用知识库 API 来管理以下信息：</span><span class="sxs-lookup"><span data-stu-id="145b9-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="145b9-117">**用户**-用户有权访问存储库的表示形式。</span><span class="sxs-lookup"><span data-stu-id="145b9-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="145b9-118">**报告**-列出查询、 存储为存储库项目中的内容。</span><span class="sxs-lookup"><span data-stu-id="145b9-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="145b9-119">**查询**-用于从数据 API，作为一个内容存储库项目中存储中检索数据。</span><span class="sxs-lookup"><span data-stu-id="145b9-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="145b9-120">**用户设置**的描述用户可选的应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="145b9-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
 <span data-ttu-id="145b9-121">**跨原始资源共享知识库 API (CORS) 支持**</span><span class="sxs-lookup"><span data-stu-id="145b9-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="145b9-122">知识库 API 支持跨原始资源共享 (CORS)。</span><span class="sxs-lookup"><span data-stu-id="145b9-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="145b9-123">CORS 是 HTTP 功能，可以将 web 应用程序运行在一个域访问另一个域中的资源。</span><span class="sxs-lookup"><span data-stu-id="145b9-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="145b9-124">Web 浏览器实现称为[同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)同源策略使 web 页从另一个域中调用的 Api 的安全限制。</span><span class="sxs-lookup"><span data-stu-id="145b9-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="145b9-125">CORS 提供一种安全的方法，以允许一个域 （原始域） 另一个域中调用的 Api。</span><span class="sxs-lookup"><span data-stu-id="145b9-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="145b9-126">请参阅 CORS [CORS 技术指标](https://www.w3.org/TR/cors/)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="145b9-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="145b9-127">**启用对存储库 API CORS**</span><span class="sxs-lookup"><span data-stu-id="145b9-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="145b9-128">以下是摘录的知识库 API web.config 文件中，显示在 corsTrustedOrigin 应用程序设置中列出的两个域。</span><span class="sxs-lookup"><span data-stu-id="145b9-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="145b9-129">从这些服务器加载的脚本所做的所有请求都受信任存储库 API。</span><span class="sxs-lookup"><span data-stu-id="145b9-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="145b9-130">请务必包括具体协议、 主机名称和端口 （如果有的话）。</span><span class="sxs-lookup"><span data-stu-id="145b9-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="145b9-131">不要不将任何反斜杠字符 （/） 结尾。</span><span class="sxs-lookup"><span data-stu-id="145b9-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="145b9-132">通过用逗号分隔，可以指定多个条目。</span><span class="sxs-lookup"><span data-stu-id="145b9-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>

```


