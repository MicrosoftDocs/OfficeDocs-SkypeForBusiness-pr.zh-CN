---
title: 添加服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 若要将新服务器添加到现有池的服务器，其中池是以下项之一：
ms.openlocfilehash: b138dc46f8259620e1e3a34bb86a83d243e9c825
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373981"
---
# <a name="add-server"></a><span data-ttu-id="1c97f-103">添加服务器</span><span class="sxs-lookup"><span data-stu-id="1c97f-103">Add Server</span></span>
 
<span data-ttu-id="1c97f-104">若要将新服务器添加到现有池的服务器，其中池是以下项之一：</span><span class="sxs-lookup"><span data-stu-id="1c97f-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="1c97f-105">Enterprise Edition 前端服务器</span><span class="sxs-lookup"><span data-stu-id="1c97f-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="1c97f-106">控制器服务器</span><span class="sxs-lookup"><span data-stu-id="1c97f-106">Director server</span></span>
    
- <span data-ttu-id="1c97f-107">中介服务器</span><span class="sxs-lookup"><span data-stu-id="1c97f-107">Mediation Server</span></span>
    
- <span data-ttu-id="1c97f-108">音频/视频会议服务器</span><span class="sxs-lookup"><span data-stu-id="1c97f-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="1c97f-109">受信任应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="1c97f-109">Trusted Application server</span></span>
    
<span data-ttu-id="1c97f-110">每个新池服务器具有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="1c97f-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="1c97f-111">以下各节，查找要添加到的现有池的服务器的类型和要求，它定义每种服务器类型提供相关信息。</span><span class="sxs-lookup"><span data-stu-id="1c97f-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="1c97f-112">提供定义的新池服务器请求的信息。</span><span class="sxs-lookup"><span data-stu-id="1c97f-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="1c97f-113">**Enterprise Edition 前端服务器**</span><span class="sxs-lookup"><span data-stu-id="1c97f-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="1c97f-114">定义在域名系统 (DNS) 的完全限定域名 (FQDN) 的新服务器。</span><span class="sxs-lookup"><span data-stu-id="1c97f-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="1c97f-115">选择**使用所有已配置的 IP 地址**，这意味着可使用的计算机上定义任意 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1c97f-116">此外，您可以选择**将服务使用率限制为所选的 IP 地址**，并输入新的服务器上的特定地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1c97f-117">输入的 IP 地址是唯一的 IP 地址，其中将响应的托管服务。</span><span class="sxs-lookup"><span data-stu-id="1c97f-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="1c97f-118">前端服务器上并置中介服务器，请定义**PSTN IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="1c97f-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="1c97f-119">选择**启用 IPv6**为此服务器启用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="1c97f-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="1c97f-120">**控制器服务器**</span><span class="sxs-lookup"><span data-stu-id="1c97f-120">**Director server**</span></span>
  
- <span data-ttu-id="1c97f-121">在 DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1c97f-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1c97f-122">选择**使用所有已配置的 IP 地址**，这意味着将使用的计算机上定义任意 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="1c97f-123">此外，您选择**将服务使用率限制为所选的 IP 地址**，并输入新服务器上的特定的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="1c97f-124">输入的 IP 地址是唯一的 IP 地址，其中将响应的托管服务。</span><span class="sxs-lookup"><span data-stu-id="1c97f-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="1c97f-125">**中介服务器**</span><span class="sxs-lookup"><span data-stu-id="1c97f-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="1c97f-126">在 DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1c97f-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1c97f-127">选择**使用所有已配置的 IP 地址**，这意味着可使用的计算机上定义任意 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1c97f-128">或者，您选择**服务使用率限制为所选的 IP 地址**和主 IP 地址，在新服务器上输入特定的 IP 地址和 enter 公用电话交换网 (pstn) 的 IP 地址的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="1c97f-129">输入的 IP 地址是唯一的 IP 地址，这将指定服务的响应。</span><span class="sxs-lookup"><span data-stu-id="1c97f-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c97f-130">为中介服务器中，输入的主要 IP 地址和 PSTN IP 地址的 IP 地址是默认情况下相同。</span><span class="sxs-lookup"><span data-stu-id="1c97f-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="1c97f-131">如果您使用专用的网络接口或单独的 IP 地址相同的网络接口上，可以单独定义的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="1c97f-132">如果您有两个网络接口，一个用于本地网络连接，一个用于 PSTN 连接，则必须分配不同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="1c97f-133">**音频/视频会议服务器**</span><span class="sxs-lookup"><span data-stu-id="1c97f-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="1c97f-134">在 DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1c97f-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1c97f-135">选择**使用所有已配置的 IP 地址**，这意味着可使用的计算机上定义任意 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1c97f-136">此外，您可以选择**将服务使用率限制为所选的 IP 地址**，并输入新的服务器上的特定地址。</span><span class="sxs-lookup"><span data-stu-id="1c97f-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1c97f-137">输入的 IP 地址是唯一的 IP 地址，其中将响应的托管服务。</span><span class="sxs-lookup"><span data-stu-id="1c97f-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="1c97f-138">**受信任应用程序服务器**</span><span class="sxs-lookup"><span data-stu-id="1c97f-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="1c97f-139">在 DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1c97f-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

