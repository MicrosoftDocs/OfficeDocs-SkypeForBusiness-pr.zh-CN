---
title: 添加前端 Web 服务 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
ms.openlocfilehash: 1e18c4956e9b9d369bae766ed557debe44586298
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21015702"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="15bba-104">添加前端 Web 服务 2010</span><span class="sxs-lookup"><span data-stu-id="15bba-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="15bba-105">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="15bba-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="15bba-106">例如，如果池的 Web 服务的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="15bba-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="15bba-107">无法覆盖内部 Web 服务池完全限定的域名 (FQDN) 的 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="15bba-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="15bba-108">如果要配置域名系统 (DNS) 负载平衡对于 Enterprise Edition 前端池，则可以指定不同的内部基本 URL (哪些必须与池 FQDN 不同，可能是，例如，内部-\<基 URL\>)。</span><span class="sxs-lookup"><span data-stu-id="15bba-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="15bba-109">您可以指定不同的外部基 URL 从您的内部基本 URL 区分域命名。</span><span class="sxs-lookup"><span data-stu-id="15bba-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="15bba-110">例如，内部域 contoso.net，但在您的外部域的名称是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="15bba-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="15bba-111">将使用的 contoso.com 域的名称来定义外部基 URL。</span><span class="sxs-lookup"><span data-stu-id="15bba-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="15bba-112">这是重要边缘部署的反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="15bba-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="15bba-113">外部基 URL 域名称应为反向代理服务器的 FQDN 的域名相同。</span><span class="sxs-lookup"><span data-stu-id="15bba-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="15bba-114">即时消息和状态需要对前端池的 HTTP 访问。</span><span class="sxs-lookup"><span data-stu-id="15bba-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

