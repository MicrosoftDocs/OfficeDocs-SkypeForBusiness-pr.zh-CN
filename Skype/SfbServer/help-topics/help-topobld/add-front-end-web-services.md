---
title: 添加前端 Web 服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果 Web 服务的池的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
ms.openlocfilehash: 6626bb14221aaa909219451d26b76b0cd15bc576
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="be885-104">添加前端 Web 服务</span><span class="sxs-lookup"><span data-stu-id="be885-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="be885-105">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="be885-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="be885-106">例如，如果 Web 服务的池的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="be885-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="be885-107">不能重写内部 Web 服务池完全合格的域名称 (FQDN) 标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="be885-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="be885-108">如果您在配置域名系统 (DNS) 负载平衡的前端企业版池，您可以指定不同内部基本 URL，它必须与池的 FQDN 不同 (例如，内部的\<基 URL\>)。</span><span class="sxs-lookup"><span data-stu-id="be885-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="be885-109">您可以指定不同的外部的基 URL 从您内部的基 URL 来区分域命名它。</span><span class="sxs-lookup"><span data-stu-id="be885-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="be885-110">例如，您的内部域是 contoso.net，但外部域名 contoso.com。您需要定义外部的基 URL 使用 contoso.com 域的名称。</span><span class="sxs-lookup"><span data-stu-id="be885-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="be885-111">这是非常重要的反向代理服务器的边缘部署。</span><span class="sxs-lookup"><span data-stu-id="be885-111">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="be885-112">外部的基 URL 域名称应与反向代理服务器的 FQDN 的域的名称相同。</span><span class="sxs-lookup"><span data-stu-id="be885-112">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="be885-113">即时消息和状态要求对前端池的 HTTP 访问。</span><span class="sxs-lookup"><span data-stu-id="be885-113">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

