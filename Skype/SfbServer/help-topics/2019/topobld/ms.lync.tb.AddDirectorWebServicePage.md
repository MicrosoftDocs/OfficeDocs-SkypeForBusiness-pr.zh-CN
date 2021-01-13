---
title: 添加控制器 Web 服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为，则基 https://pool01.contoso.net URL pool01.contoso.net。
ms.openlocfilehash: 481fe9d0a63af723346f7fac5f04e8a9b9bb7edd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807742"
---
# <a name="add-director-web-service"></a><span data-ttu-id="e005e-104">添加控制器 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e005e-104">Add Director Web Service</span></span>
 
<span data-ttu-id="e005e-105">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="e005e-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="e005e-106">例如，如果池的 Web 服务的完整 URL 为，则基 https://pool01.contoso.net URL pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="e005e-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="e005e-107">如果仅部署单个控制器，则不能覆盖内部 Web 服务池完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e005e-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="e005e-108">如果要为控制器池配置域名系统 (DNS) 负载平衡，可以指定一个不同的内部基 URL (该 URL 必须与池 FQDN 不同，例如，可以是 \<your base URL\> internal-) 。</span><span class="sxs-lookup"><span data-stu-id="e005e-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="e005e-p104">可以指定与内部基 URL 不同的外部基 URL 以区分域命名。例如，您的内部域是 contoso.net，但外部域名是 contoso.com。您可以使用 contoso.com 域名来定义外部基 URL。这对于边缘部署中的反向代理服务器非常重要。外部基 URL 域名应该与反向代理的 FQDN 域名相同。</span><span class="sxs-lookup"><span data-stu-id="e005e-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

