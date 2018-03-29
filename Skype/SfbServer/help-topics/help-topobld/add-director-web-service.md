---
title: 添加 Web 服务主管
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如，如果 Web 服务的池的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。
ms.openlocfilehash: c65d7d9276aaa394d1810136a97dcc8c075d3607
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-web-service"></a><span data-ttu-id="3519b-104">添加 Web 服务主管</span><span class="sxs-lookup"><span data-stu-id="3519b-104">Add Director Web Service</span></span>
 
<span data-ttu-id="3519b-105">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="3519b-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="3519b-106">例如，如果 Web 服务的池的完整 URL 为https://pool01.contoso.net的基 URL 是 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="3519b-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="3519b-107">如果您正在部署一个导演，不能重写的内部 Web 服务池完全合格的域名称 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="3519b-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="3519b-108">如果您在配置域名系统 (DNS) 负载平衡控制器的池，您可以指定不同的内部基本 URL (它必须不同于池的 FQDN，并可能是，例如，内部的\<基 URL\>)。</span><span class="sxs-lookup"><span data-stu-id="3519b-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="3519b-109">您可以指定不同的外部的基 URL 从您内部的基 URL 来区分域命名它。</span><span class="sxs-lookup"><span data-stu-id="3519b-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="3519b-110">例如，您的内部域是 contoso.net，但外部域名 contoso.com。将通过使用 contoso.com 域的名称来定义外部的基 URL。</span><span class="sxs-lookup"><span data-stu-id="3519b-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="3519b-111">这是非常重要的反向代理服务器的边缘部署。</span><span class="sxs-lookup"><span data-stu-id="3519b-111">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="3519b-112">外部的基 URL 域名称应与反向代理服务器的 FQDN 的域的名称相同。</span><span class="sxs-lookup"><span data-stu-id="3519b-112">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

