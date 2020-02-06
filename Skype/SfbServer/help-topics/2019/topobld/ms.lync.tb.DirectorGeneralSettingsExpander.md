---
title: 控制器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑现有控制器的设置，您将看到以下部分：
ms.openlocfilehash: ffdfd169095175346a89eb6d6d001161bec0f465
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793850"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="2c00f-103">控制器常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="2c00f-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="2c00f-104">若要编辑现有控制器的设置，您将看到以下部分：</span><span class="sxs-lookup"><span data-stu-id="2c00f-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="2c00f-105">常规设置</span><span class="sxs-lookup"><span data-stu-id="2c00f-105">General settings</span></span>
    
- <span data-ttu-id="2c00f-106">Web 服务</span><span class="sxs-lookup"><span data-stu-id="2c00f-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="2c00f-107">常规设置</span><span class="sxs-lookup"><span data-stu-id="2c00f-107">General settings</span></span>

<span data-ttu-id="2c00f-108">控制器池的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="2c00f-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="2c00f-109">编辑服务器的 FQDN 以更改该值。</span><span class="sxs-lookup"><span data-stu-id="2c00f-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="2c00f-110">必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="2c00f-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="2c00f-111">在“**关联**”中，可以编辑或指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="2c00f-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="2c00f-112">要使用的 Director pool 的文件共享。</span><span class="sxs-lookup"><span data-stu-id="2c00f-112">File share for the Director pool to use.</span></span> <span data-ttu-id="2c00f-113">选择拓扑生成器中已定义的现有文件共享，或单击 "**新建**" 以创建新的文件共享定义。</span><span class="sxs-lookup"><span data-stu-id="2c00f-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="2c00f-114">监视 SQL Server 应用商店。</span><span class="sxs-lookup"><span data-stu-id="2c00f-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2c00f-115">发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。</span><span class="sxs-lookup"><span data-stu-id="2c00f-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="2c00f-116">如果你创建了新的文件共享，则必须在你指定的服务器上创建文件共享。</span><span class="sxs-lookup"><span data-stu-id="2c00f-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="2c00f-117">Web 服务</span><span class="sxs-lookup"><span data-stu-id="2c00f-117">Web services</span></span>

<span data-ttu-id="2c00f-118">若要在 Director 池中编辑或指定 Web 服务的其他设置，请修改或指定内部 Web 服务和外部 Web 服务中的设置。</span><span class="sxs-lookup"><span data-stu-id="2c00f-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="2c00f-119">对于**内部 web 服务**，你可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="2c00f-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="2c00f-120">如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2c00f-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="2c00f-121">例如，如果你将前端服务器的外部 Web 服务 FQDN 定义为**pool01.contoso.com**，则不能将**Pool01.contoso.com**用于其他前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2c00f-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="2c00f-122">如果你还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。</span><span class="sxs-lookup"><span data-stu-id="2c00f-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="2c00f-123">如果你决定使用自定义的 FQDN 替代内部 web 服务，则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。</span><span class="sxs-lookup"><span data-stu-id="2c00f-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="2c00f-124">如果选择“覆盖 FQDN”，则可以为池上的“内部 Web 服务”标识指定不同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2c00f-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="2c00f-125">默认情况下，该设置是为 Director 池定义的当前池名称。</span><span class="sxs-lookup"><span data-stu-id="2c00f-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="2c00f-126">你可以为你的部署所需的 HTTP 和 HTTPS 指定侦听和已发布端口。</span><span class="sxs-lookup"><span data-stu-id="2c00f-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="2c00f-127">HTTPS 的端口80和端口443的默认设置是最常见的设置，通常不需要更改，除非你在组织和基础结构设计中具有特定要求。</span><span class="sxs-lookup"><span data-stu-id="2c00f-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="2c00f-128">对于**外部 web 服务**，你可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="2c00f-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="2c00f-129">你可以定义外部 Web 服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2c00f-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="2c00f-130">此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。</span><span class="sxs-lookup"><span data-stu-id="2c00f-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="2c00f-131">你可以为你的部署所需的 HTTP 和 HTTPS 指定侦听和已发布端口。</span><span class="sxs-lookup"><span data-stu-id="2c00f-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="2c00f-132">最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。</span><span class="sxs-lookup"><span data-stu-id="2c00f-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="2c00f-133">根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。</span><span class="sxs-lookup"><span data-stu-id="2c00f-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="2c00f-134">已发布端口设置为端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认值。</span><span class="sxs-lookup"><span data-stu-id="2c00f-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="2c00f-135">这些值确定了控制器池或控制器服务器将在哪些端口上侦听传入的请求。</span><span class="sxs-lookup"><span data-stu-id="2c00f-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="2c00f-136">通常情况下，不需要更改这些项，除非该池上的端口要求冲突。</span><span class="sxs-lookup"><span data-stu-id="2c00f-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="2c00f-137">需要使用相同端口值的内部和外部发布端口。</span><span class="sxs-lookup"><span data-stu-id="2c00f-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="2c00f-138">这不会出现冲突。</span><span class="sxs-lookup"><span data-stu-id="2c00f-138">This is not a conflict.</span></span>
  

