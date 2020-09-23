---
title: 添加前端 Web 服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为 https://pool01.contoso.net ，则基 url 为 pool01.contoso.net。
ms.openlocfilehash: 45705ea940fa0f43f600546a680d76b41b645e59
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217933"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="b1eb3-104">添加前端 Web 服务</span><span class="sxs-lookup"><span data-stu-id="b1eb3-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="b1eb3-105">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="b1eb3-106">例如，如果池的 Web 服务的完整 URL 为 https://pool01.contoso.net ，则基 url 为 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="b1eb3-107">无法覆盖 Standard Edition Server 的内部 Web 服务池完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="b1eb3-108">如果要配置域名系统 (DNS) 对企业版前端池的负载平衡，则可以指定不同的内部基本 URL，该 URL 必须不同于池 FQDN (例如，internal- \<your base URL\>) 。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="b1eb3-p104">可以指定与内部基 URL 不同的外部基 URL 以区分域命名。例如，您的内部域是 contoso.net，但外部域名是 contoso.com。您可以使用 contoso.com 域名来定义外部基 URL。这对于边缘部署中的反向代理服务器非常重要。外部基 URL 域名应该与反向代理的 FQDN 域名相同。即时消息和状态要求对前端池具有 HTTP 访问权限。</span><span class="sxs-lookup"><span data-stu-id="b1eb3-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy. Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

