---
title: 添加前端 Web 服务 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 是https://pool01.contoso.net，则基 URL 为 pool01.contoso.net。
ms.openlocfilehash: 48d2cc4c8ce9bc1074ae42e385265b34f24c662e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685125"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="9df3a-104">添加前端 Web 服务 2010</span><span class="sxs-lookup"><span data-stu-id="9df3a-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="9df3a-105">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="9df3a-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="9df3a-106">例如，如果池的 Web 服务的完整 URL 是https://pool01.contoso.net，则基 URL 为 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="9df3a-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="9df3a-107">不能替代标准版服务器的内部 Web 服务池完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="9df3a-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="9df3a-108">如果要为企业版前端池配置域名系统（DNS）负载平衡，可以指定不同的内部基 URL （它必须与池 FQDN 不同，例如，内部-\<你的基本 URL\>）。</span><span class="sxs-lookup"><span data-stu-id="9df3a-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="9df3a-109">你可以指定与内部基础 URL 不同的外部基 URL，以区分域命名。</span><span class="sxs-lookup"><span data-stu-id="9df3a-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="9df3a-110">例如，你的内部域是 contoso.net，但你的外部域名是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="9df3a-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="9df3a-111">你可以使用 contoso.com 域名定义外部基 URL。</span><span class="sxs-lookup"><span data-stu-id="9df3a-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="9df3a-112">这对于边缘部署的反向代理服务器非常重要。</span><span class="sxs-lookup"><span data-stu-id="9df3a-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="9df3a-113">外部基 URL 域名应与反向代理的 FQDN 的域名相同。</span><span class="sxs-lookup"><span data-stu-id="9df3a-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="9df3a-114">即时消息和状态要求具有对前端池的 HTTP 访问权限。</span><span class="sxs-lookup"><span data-stu-id="9df3a-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

