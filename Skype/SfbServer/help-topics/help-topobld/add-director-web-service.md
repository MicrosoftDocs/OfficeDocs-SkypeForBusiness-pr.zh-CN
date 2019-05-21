---
title: 添加控制器 Web 服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 基 URL 指的是 URL 的 Web 服务标识减去 https://。 例如, 如果池的 Web 服务的完整 URL 是https://pool01.contoso.net, 则基 URL 为 pool01.contoso.net。
ms.openlocfilehash: 6d4b99446e4c64f6185c58bd82ef9ca59cadb28c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304742"
---
# <a name="add-director-web-service"></a><span data-ttu-id="711bf-104">添加控制器 Web 服务</span><span class="sxs-lookup"><span data-stu-id="711bf-104">Add Director Web Service</span></span>
 
<span data-ttu-id="711bf-105">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="711bf-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="711bf-106">例如, 如果池的 Web 服务的完整 URL 是https://pool01.contoso.net, 则基 URL 为 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="711bf-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="711bf-107">如果仅部署单个控制器, 则不能替代内部 Web 服务池完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="711bf-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="711bf-108">如果你要为控制器池配置域名系统 (DNS) 负载平衡, 你可以指定不同的内部基 URL (该 URL 必须不同于池 FQDN, 例如, 内部-\<你的基本 url\>)。</span><span class="sxs-lookup"><span data-stu-id="711bf-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="711bf-109">你可以指定与内部基础 URL 不同的外部基 URL, 以区分域命名。</span><span class="sxs-lookup"><span data-stu-id="711bf-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="711bf-110">例如, 你的内部域是 contoso.net, 但你的外部域名是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="711bf-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="711bf-111">你可以使用 contoso.com 域名定义外部基 URL。</span><span class="sxs-lookup"><span data-stu-id="711bf-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="711bf-112">这对于边缘部署的反向代理服务器非常重要。</span><span class="sxs-lookup"><span data-stu-id="711bf-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="711bf-113">外部基 URL 域名应与反向代理的 FQDN 的域名相同。</span><span class="sxs-lookup"><span data-stu-id="711bf-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

