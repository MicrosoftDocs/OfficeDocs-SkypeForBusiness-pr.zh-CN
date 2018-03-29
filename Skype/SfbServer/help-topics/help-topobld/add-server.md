---
title: 添加服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 将新服务器添加到现有池中的服务器，其中池是下列情况之一：
ms.openlocfilehash: 609fbb28900ac67e0a4e1e2a400f1eebb29b2ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-server"></a><span data-ttu-id="22981-103">添加服务器</span><span class="sxs-lookup"><span data-stu-id="22981-103">Add Server</span></span>
 
<span data-ttu-id="22981-104">将新服务器添加到现有池中的服务器，其中池是下列情况之一：</span><span class="sxs-lookup"><span data-stu-id="22981-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="22981-105">企业版前端服务器</span><span class="sxs-lookup"><span data-stu-id="22981-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="22981-106">Director 服务器</span><span class="sxs-lookup"><span data-stu-id="22981-106">Director server</span></span>
    
- <span data-ttu-id="22981-107">中介服务器</span><span class="sxs-lookup"><span data-stu-id="22981-107">Mediation Server</span></span>
    
- <span data-ttu-id="22981-108">音频/视频会议服务器</span><span class="sxs-lookup"><span data-stu-id="22981-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="22981-109">受信任的应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="22981-109">Trusted Application server</span></span>
    
<span data-ttu-id="22981-110">每个新的库服务器有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="22981-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="22981-111">在以下部分中，找到要添加到的现有池的服务器的类型和要求规定为每个服务器类型提供相关信息。</span><span class="sxs-lookup"><span data-stu-id="22981-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="22981-112">提供请求的信息，以定义新的库服务器。</span><span class="sxs-lookup"><span data-stu-id="22981-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="22981-113">**企业版前端服务器**</span><span class="sxs-lookup"><span data-stu-id="22981-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="22981-114">完全限定的新服务器的域名称 (FQDN)，按其定义在域名系统 (DNS)。</span><span class="sxs-lookup"><span data-stu-id="22981-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="22981-115">选择**使用已配置的所有 IP 地址**，这意味着可以使用任何 IP 地址的计算机上定义。</span><span class="sxs-lookup"><span data-stu-id="22981-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="22981-116">或者，您可以选择**限制到选定的 IP 地址的服务使用情况**并输入新的服务器上的特定地址。</span><span class="sxs-lookup"><span data-stu-id="22981-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="22981-117">输入的 IP 地址是唯一的 IP 地址，这将承载服务的响应。</span><span class="sxs-lookup"><span data-stu-id="22981-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="22981-118">中介服务器在前端服务器上搭配时，请定义**PSTN IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="22981-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="22981-119">选择要为此服务器启用 IPv6**启用 IPv6** 。</span><span class="sxs-lookup"><span data-stu-id="22981-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
 <span data-ttu-id="22981-120">**Director 服务器**</span><span class="sxs-lookup"><span data-stu-id="22981-120">**Director server**</span></span>
  
- <span data-ttu-id="22981-121">它与新服务器的 FQDN，则在 DNS 中定义。</span><span class="sxs-lookup"><span data-stu-id="22981-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="22981-122">选择**使用已配置的所有 IP 地址**，这意味着将使用在计算机上定义的任何 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22981-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="22981-123">或者，选择**限制服务使用所选的 IP 地址**，并输入新的服务器上的特定的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22981-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="22981-124">输入的 IP 地址是唯一的 IP 地址，这将承载服务的响应。</span><span class="sxs-lookup"><span data-stu-id="22981-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="22981-125">**中介服务器**</span><span class="sxs-lookup"><span data-stu-id="22981-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="22981-126">它与新服务器的 FQDN，则在 DNS 中定义。</span><span class="sxs-lookup"><span data-stu-id="22981-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="22981-127">选择**使用已配置的所有 IP 地址**，这意味着可以使用任何 IP 地址的计算机上定义。</span><span class="sxs-lookup"><span data-stu-id="22981-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="22981-128">或者，您可以选择**限制到选定的 IP 地址的服务使用情况**和新的主 IP 地址，服务器上特定的 IP 地址输入和输入公用交换的电话网络 (PSTN) IP 地址的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22981-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="22981-129">输入的 IP 地址是唯一的 IP 地址，这将指定服务的响应。</span><span class="sxs-lookup"><span data-stu-id="22981-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22981-130">中介服务器中，输入主 IP 地址和 PSTN IP 地址的 IP 地址是相同的默认情况。</span><span class="sxs-lookup"><span data-stu-id="22981-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="22981-131">如果在同一个网络接口上使用的专用的网络接口或单独的 IP 地址，可以单独定义的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22981-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="22981-132">如果您有两个网络接口，另一个用于本地网络连接的 PSTN 连接，您必须分配不同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22981-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
 <span data-ttu-id="22981-133">**音频/视频会议服务器**</span><span class="sxs-lookup"><span data-stu-id="22981-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="22981-134">它与新服务器的 FQDN，则在 DNS 中定义。</span><span class="sxs-lookup"><span data-stu-id="22981-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="22981-135">选择**使用已配置的所有 IP 地址**，这意味着可以使用任何 IP 地址的计算机上定义。</span><span class="sxs-lookup"><span data-stu-id="22981-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="22981-136">或者，您可以选择**限制到选定的 IP 地址的服务使用情况**并输入新的服务器上的特定地址。</span><span class="sxs-lookup"><span data-stu-id="22981-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="22981-137">输入的 IP 地址是唯一的 IP 地址，这将承载服务的响应。</span><span class="sxs-lookup"><span data-stu-id="22981-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="22981-138">**受信任的应用程序服务器**</span><span class="sxs-lookup"><span data-stu-id="22981-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="22981-139">它与新服务器的 FQDN，则在 DNS 中定义。</span><span class="sxs-lookup"><span data-stu-id="22981-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

