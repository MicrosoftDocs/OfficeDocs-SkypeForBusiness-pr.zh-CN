---
title: 添加控制器 Web 服务
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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果池的 Web 服务的完整 URL 为 https://pool01.contoso.net ，则基 url 为 pool01.contoso.net。
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219463"
---
# <a name="add-director-web-service"></a><span data-ttu-id="ec924-104">添加控制器 Web 服务</span><span class="sxs-lookup"><span data-stu-id="ec924-104">Add Director Web Service</span></span>
 
<span data-ttu-id="ec924-105">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="ec924-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="ec924-106">例如，如果池的 Web 服务的完整 URL 为 https://pool01.contoso.net ，则基 url 为 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="ec924-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="ec924-107">如果仅部署单个控制器，则不能覆盖内部 Web 服务池完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ec924-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="ec924-108">如果要配置域名系统 (DNS) 控制器池的负载平衡，则可以指定不同的内部基本 URL (该 URL 必须不同于池 FQDN，例如，内部 \<your base URL\>) 。</span><span class="sxs-lookup"><span data-stu-id="ec924-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="ec924-p104">可以指定与内部基 URL 不同的外部基 URL 以区分域命名。例如，您的内部域是 contoso.net，但外部域名是 contoso.com。您可以使用 contoso.com 域名来定义外部基 URL。这对于边缘部署中的反向代理服务器非常重要。外部基 URL 域名应该与反向代理的 FQDN 域名相同。</span><span class="sxs-lookup"><span data-stu-id="ec924-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

