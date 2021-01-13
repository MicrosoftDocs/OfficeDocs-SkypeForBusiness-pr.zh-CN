---
title: 控制器常规设置扩展器
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
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 要编辑现有控制器的设置，可参考以下各节内容：
ms.openlocfilehash: b7478779e54a7860726ae967eb1e203625c8b17b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835332"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="64670-103">控制器常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="64670-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="64670-104">要编辑现有控制器的设置，可参考以下各节内容：</span><span class="sxs-lookup"><span data-stu-id="64670-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="64670-105">常规设置</span><span class="sxs-lookup"><span data-stu-id="64670-105">General settings</span></span>
    
- <span data-ttu-id="64670-106">Web 服务</span><span class="sxs-lookup"><span data-stu-id="64670-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="64670-107">常规设置</span><span class="sxs-lookup"><span data-stu-id="64670-107">General settings</span></span>

<span data-ttu-id="64670-p101">控制器池的完全限定域名 (FQDN)。编辑服务器的 FQDN 以更改该值。必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="64670-p101">Fully qualified domain name (FQDN) of the Director pool. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="64670-111">在“关联”中，可以编辑或指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="64670-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="64670-112">控制器池使用的文件共享。</span><span class="sxs-lookup"><span data-stu-id="64670-112">File share for the Director pool to use.</span></span> <span data-ttu-id="64670-113">选择已在拓扑生成器中定义的现有文件共享，或单击"新建"以创建新的文件共享定义。</span><span class="sxs-lookup"><span data-stu-id="64670-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="64670-114">监控 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="64670-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="64670-p103">发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。如果创建了新的文件共享，则必须在指定的服务器上创建文件共享。</span><span class="sxs-lookup"><span data-stu-id="64670-p103">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain. If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="64670-117">Web 服务</span><span class="sxs-lookup"><span data-stu-id="64670-117">Web services</span></span>

<span data-ttu-id="64670-118">要为控制器池中的 Web 服务编辑或指定其他设置，请在内部 Web 服务和外部 Web 服务中修改或指定设置。</span><span class="sxs-lookup"><span data-stu-id="64670-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="64670-119">对于“内部 Web 服务”，可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="64670-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="64670-120">如果您具有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="64670-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="64670-121">例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 **pool01.contoso.com，** 则不能将 pool01.contoso.com **用于另** 一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="64670-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="64670-122">如果还要部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器是唯一的。</span><span class="sxs-lookup"><span data-stu-id="64670-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="64670-123">如果您决定使用自定义的 FQDN 覆盖内部 Web 服务，则每个 FQDN 都必须与任何其他前端池、控制器或控制器池是唯一的。</span><span class="sxs-lookup"><span data-stu-id="64670-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="64670-p105">如果选择“覆盖 FQDN”，则可以为池上的内部 Web 服务标识指定不同的 FQDN。默认情况下，该设置是为控制器池定义的当前池名称。</span><span class="sxs-lookup"><span data-stu-id="64670-p105">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool. By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="64670-p106">可以为部署所需的 HTTP 和 HTTPS 指定侦听端口和已发布端口。端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认设置是最常见的设置，通常不需要更改，除非在您的组织和基础结构设计中有具体的要求。</span><span class="sxs-lookup"><span data-stu-id="64670-p106">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="64670-128">对于“外部 Web 服务”，可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="64670-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="64670-p107">可以定义外部 Web 服务的 FQDN。此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。</span><span class="sxs-lookup"><span data-stu-id="64670-p107">You can define the FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="64670-p108">可以为部署所需的 HTTP 和 HTTPS 指定侦听端口和已发布端口。最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。已发布端口设置为端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认值。这些值确定了控制器池或控制器服务器将侦听哪些端口的传入请求。通常，这些值不需要更改，除非池上的端口要求有冲突。建议使用相同端口值的内部和外部已发布端口，这样不会出现冲突。</span><span class="sxs-lookup"><span data-stu-id="64670-p108">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. The published ports are set to default of port 80 for HTTP and port 443 for HTTPS. These values determine what ports the Director pool or Director server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the pool. Internal and external published ports that use the same port values are expected. This is not a conflict.</span></span>
  

