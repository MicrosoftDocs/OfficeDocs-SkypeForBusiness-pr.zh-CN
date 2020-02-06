---
title: 添加服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 若要将新服务器添加到现有服务器池，其中池是以下项之一：
ms.openlocfilehash: d4f4afc0d4a7cb6fafe47de95c648aa1769027e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820644"
---
# <a name="add-server"></a><span data-ttu-id="735e8-103">添加服务器</span><span class="sxs-lookup"><span data-stu-id="735e8-103">Add Server</span></span>
 
<span data-ttu-id="735e8-104">若要将新服务器添加到现有服务器池，其中池是以下项之一：</span><span class="sxs-lookup"><span data-stu-id="735e8-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="735e8-105">企业版前端服务器</span><span class="sxs-lookup"><span data-stu-id="735e8-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="735e8-106">控制器服务器</span><span class="sxs-lookup"><span data-stu-id="735e8-106">Director server</span></span>
    
- <span data-ttu-id="735e8-107">中介服务器</span><span class="sxs-lookup"><span data-stu-id="735e8-107">Mediation Server</span></span>
    
- <span data-ttu-id="735e8-108">音频/视频会议服务器</span><span class="sxs-lookup"><span data-stu-id="735e8-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="735e8-109">受信任的应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="735e8-109">Trusted Application server</span></span>
    
<span data-ttu-id="735e8-110">每个新的池服务器都有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="735e8-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="735e8-111">在以下部分中，找到要添加到现有池中的服务器的类型，并提供所需的信息，这些信息是为每个服务器类型定义的。</span><span class="sxs-lookup"><span data-stu-id="735e8-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="735e8-112">你提供所需的信息来定义新的池服务器。</span><span class="sxs-lookup"><span data-stu-id="735e8-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="735e8-113">**企业版前端服务器**</span><span class="sxs-lookup"><span data-stu-id="735e8-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="735e8-114">新服务器的完全限定的域名（FQDN），该域名在域名系统（DNS）中定义。</span><span class="sxs-lookup"><span data-stu-id="735e8-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="735e8-115">选择 "**使用所有配置的 ip 地址**"，这意味着可以使用计算机上定义的任何 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="735e8-116">或者，你可以选择 "**将服务使用限制为所选 IP 地址**"，然后在新服务器上输入特定地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="735e8-117">输入的 IP 地址是唯一将响应托管服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="735e8-118">当中介服务器在前端服务器上 collocated 时，请定义**PSTN IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="735e8-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="735e8-119">选择 "**启用 ipv6** " 以为此服务器启用 ipv6。</span><span class="sxs-lookup"><span data-stu-id="735e8-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="735e8-120">**控制器服务器**</span><span class="sxs-lookup"><span data-stu-id="735e8-120">**Director server**</span></span>
  
- <span data-ttu-id="735e8-121">在 DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="735e8-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="735e8-122">选择 "**使用所有配置的 IP 地址**"，这意味着将使用计算机上定义的任何 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="735e8-123">或者，选择 "**将服务使用限制为所选 IP 地址**"，然后在新服务器上输入特定的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="735e8-124">输入的 IP 地址是唯一将响应托管服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="735e8-125">**中介服务器**</span><span class="sxs-lookup"><span data-stu-id="735e8-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="735e8-126">在 DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="735e8-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="735e8-127">选择 "**使用所有配置的 ip 地址**"，这意味着可以使用计算机上定义的任何 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="735e8-128">或者，选择 "**将服务使用限制为选定的 IP 地址**"，然后在新服务器上输入特定的 ip 地址作为主 IP 地址，并输入公共交换电话网络（PSTN） ip 地址的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="735e8-129">输入的 IP 地址是唯一将响应指定服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="735e8-130">对于中介服务器，默认情况下，为主 IP 地址和 PSTN IP 地址输入的 IP 地址是相同的。</span><span class="sxs-lookup"><span data-stu-id="735e8-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="735e8-131">如果在同一网络接口上使用专用网络接口或单独的 IP 地址，则可以单独定义 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="735e8-132">如果你有两个网络接口，一个用于本地网络连接，另一个用于 PSTN 连接，则必须分配不同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="735e8-133">**音频/视频会议服务器**</span><span class="sxs-lookup"><span data-stu-id="735e8-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="735e8-134">在 DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="735e8-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="735e8-135">选择 "**使用所有配置的 ip 地址**"，这意味着可以使用计算机上定义的任何 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="735e8-136">或者，你可以选择 "**将服务使用限制为所选 IP 地址**"，然后在新服务器上输入特定地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="735e8-137">输入的 IP 地址是唯一将响应托管服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="735e8-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="735e8-138">**受信任的应用程序服务器**</span><span class="sxs-lookup"><span data-stu-id="735e8-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="735e8-139">在 DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="735e8-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

