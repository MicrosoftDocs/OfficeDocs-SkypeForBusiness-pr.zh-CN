---
title: 控制器常规设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 若要编辑现有控制器的设置，可参考以下各节内容：
ms.openlocfilehash: 92ddafb0029f4860f4fd36ddb9a497d21deb97d2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226878"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="660ac-103">控制器常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="660ac-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="660ac-104">若要编辑现有控制器的设置，可参考以下各节内容：</span><span class="sxs-lookup"><span data-stu-id="660ac-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="660ac-105">常规设置</span><span class="sxs-lookup"><span data-stu-id="660ac-105">General settings</span></span>
    
- <span data-ttu-id="660ac-106">Web 服务</span><span class="sxs-lookup"><span data-stu-id="660ac-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="660ac-107">常规设置</span><span class="sxs-lookup"><span data-stu-id="660ac-107">General settings</span></span>

<span data-ttu-id="660ac-108">控制器池的完全限定名称 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="660ac-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="660ac-109">编辑服务器的 FQDN 以更改该值。</span><span class="sxs-lookup"><span data-stu-id="660ac-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="660ac-110">必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="660ac-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="660ac-111">在“**关联**”中，可以编辑或指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="660ac-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="660ac-112">要使用的控制器池的文件共享。</span><span class="sxs-lookup"><span data-stu-id="660ac-112">File share for the Director pool to use.</span></span> <span data-ttu-id="660ac-113">选择现有的已在拓扑生成器中定义的文件共享或单击**新建**创建新的文件共享定义。</span><span class="sxs-lookup"><span data-stu-id="660ac-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="660ac-114">监控 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="660ac-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="660ac-115">发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。</span><span class="sxs-lookup"><span data-stu-id="660ac-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="660ac-116">如果您创建新的文件共享，则必须在您指定的服务器上创建的文件共享。</span><span class="sxs-lookup"><span data-stu-id="660ac-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="660ac-117">Web 服务</span><span class="sxs-lookup"><span data-stu-id="660ac-117">Web services</span></span>

<span data-ttu-id="660ac-118">若要编辑或指定其他设置的 Web 服务上的控制器池，您修改或指定设置中的内部 Web 服务和外部 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="660ac-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="660ac-119">**内部 web 服务**为可以指定以下各项：</span><span class="sxs-lookup"><span data-stu-id="660ac-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="660ac-120">如果您有多个前端池或前端服务器的外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="660ac-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="660ac-121">例如，如果您定义的外部 Web 服务的前端服务器的 FQDN 为**pool01.contoso.com**，不能使用**pool01.contoso.com** ，另一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="660ac-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="660ac-122">如果还要部署控制器、 外部 Web 服务 FQDN 定义任何控制器或控制器池必须不同于任何其他控制器池以及任何前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="660ac-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="660ac-123">如果您决定覆盖内部 web 服务与自定义的 FQDN，每个 FQDN 必须是唯一从任何其他前端池、 控制器或控制器池。</span><span class="sxs-lookup"><span data-stu-id="660ac-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="660ac-124">如果选择“覆盖 FQDN”，则可以为池上的“内部 Web 服务”标识指定不同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="660ac-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="660ac-125">默认情况下设置是当前的池名称，因为定义控制器池。</span><span class="sxs-lookup"><span data-stu-id="660ac-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="660ac-126">您可以指定 HTTP 和 HTTPS 部署所需侦听和已发布端口。</span><span class="sxs-lookup"><span data-stu-id="660ac-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="660ac-127">和默认设置的端口 80 HTTP 端口 443 用于 HTTPS 是最常用的设置，通常不需要被更改，除非您有您的组织和基础设施设计中的特定要求。</span><span class="sxs-lookup"><span data-stu-id="660ac-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="660ac-128">对于**外部 web 服务**，可以指定以下各项：</span><span class="sxs-lookup"><span data-stu-id="660ac-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="660ac-129">您可以定义的外部 Web 服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="660ac-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="660ac-130">此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。</span><span class="sxs-lookup"><span data-stu-id="660ac-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="660ac-131">您可以指定 HTTP 和 HTTPS 部署所需侦听和已发布端口。</span><span class="sxs-lookup"><span data-stu-id="660ac-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="660ac-132">最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。</span><span class="sxs-lookup"><span data-stu-id="660ac-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="660ac-133">根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。</span><span class="sxs-lookup"><span data-stu-id="660ac-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="660ac-134">已发布端口设置为端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认值。</span><span class="sxs-lookup"><span data-stu-id="660ac-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="660ac-135">这些值确定哪些控制器池或控制器服务器的传入请求将侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="660ac-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="660ac-136">通常，这些不需要更改，除非存在冲突的池上的端口要求。</span><span class="sxs-lookup"><span data-stu-id="660ac-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="660ac-137">应内部和外部使用相同的端口值的已发布的端口。</span><span class="sxs-lookup"><span data-stu-id="660ac-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="660ac-138">这不会出现冲突。</span><span class="sxs-lookup"><span data-stu-id="660ac-138">This is not a conflict.</span></span>
  

