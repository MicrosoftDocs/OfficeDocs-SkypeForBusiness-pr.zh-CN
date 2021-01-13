---
title: 添加前端 Web 服务 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为，则基 https://pool01.contoso.net URL pool01.contoso.net。
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824022"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="6caf0-104">添加前端 Web 服务 2010</span><span class="sxs-lookup"><span data-stu-id="6caf0-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="6caf0-105">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="6caf0-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="6caf0-106">例如，如果池的 Web 服务的完整 URL 为，则基 https://pool01.contoso.net URL pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="6caf0-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="6caf0-107">不能覆盖 Standard Edition Server 的内部 Web 服务池 (FQDN) FQDN。</span><span class="sxs-lookup"><span data-stu-id="6caf0-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="6caf0-108">如果要为 Enterprise Edition 前端池配置域名系统 (DNS) 负载平衡，可以指定一个不同的内部基 URL (该 URL 必须不同于池 FQDN，例如，可以是内部 url) 。 \<your base URL\></span><span class="sxs-lookup"><span data-stu-id="6caf0-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="6caf0-109">可以指定与内部基 URL 不同的外部基 URL 以区分域命名。</span><span class="sxs-lookup"><span data-stu-id="6caf0-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="6caf0-110">例如，您的内部域是 contoso.net，但外部域名是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="6caf0-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="6caf0-111">您可以使用 contoso.com 域名来定义外部基 URL。</span><span class="sxs-lookup"><span data-stu-id="6caf0-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="6caf0-112">这对于边缘部署中的反向代理服务器非常重要。</span><span class="sxs-lookup"><span data-stu-id="6caf0-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="6caf0-113">外部基 URL 域名应该与反向代理的 FQDN 域名相同。</span><span class="sxs-lookup"><span data-stu-id="6caf0-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="6caf0-114">即时消息和状态要求对前端池具有 HTTP 访问权限。</span><span class="sxs-lookup"><span data-stu-id="6caf0-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

