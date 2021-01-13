---
title: 添加服务器
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
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 向现有服务器池添加新的服务器，其中池为以下几项之一：
ms.openlocfilehash: e40cf71b0ab52e66a3a28e0362de4f9106ddd831
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818622"
---
# <a name="add-server"></a><span data-ttu-id="63162-103">添加服务器</span><span class="sxs-lookup"><span data-stu-id="63162-103">Add Server</span></span>
 
<span data-ttu-id="63162-104">向现有服务器池添加新的服务器，其中池为以下几项之一：</span><span class="sxs-lookup"><span data-stu-id="63162-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="63162-105">Enterprise Edition 前端服务器</span><span class="sxs-lookup"><span data-stu-id="63162-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="63162-106">控制器服务器</span><span class="sxs-lookup"><span data-stu-id="63162-106">Director server</span></span>
    
- <span data-ttu-id="63162-107">中介服务器</span><span class="sxs-lookup"><span data-stu-id="63162-107">Mediation Server</span></span>
    
- <span data-ttu-id="63162-108">音频/视频会议服务器</span><span class="sxs-lookup"><span data-stu-id="63162-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="63162-109">受信任应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="63162-109">Trusted Application server</span></span>
    
<span data-ttu-id="63162-p101">每个新池服务器都有不同的要求。在以下各节中，查找要添加到现有池的服务器类型，并根据为每种服务器类型定义的要求提供所请求的信息。提供请求的信息以定义新的池服务器。</span><span class="sxs-lookup"><span data-stu-id="63162-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="63162-113">**Enterprise Edition 前端服务器**</span><span class="sxs-lookup"><span data-stu-id="63162-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="63162-114">域名系统 (DNS) 中定义的新服务器的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="63162-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="63162-p102">选择 **“使用所有配置 IP 地址”**，这意味着可以使用计算机上定义的任何 IP 地址。此外，还可以选择 **“服务仅供选定 IP 地址使用”**，然后在新服务器上输入特定的地址。输入的 IP 地址是唯一响应托管服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="63162-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="63162-118">如果在前端服务器上并置中介服务器，则定义“PSTN IP 地址”。</span><span class="sxs-lookup"><span data-stu-id="63162-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="63162-119">选择“启用 IPv6”为此服务器启用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="63162-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="63162-120">**控制器服务器**</span><span class="sxs-lookup"><span data-stu-id="63162-120">**Director server**</span></span>
  
- <span data-ttu-id="63162-121">DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="63162-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="63162-p103">选择“使用所有已配置的 IP 地址”，这意味着将使用计算机上定义的任何 IP 地址。此外，还可以选择“将服务用途限制为所选 IP 地址”，然后在新服务器上输入特定的 IP 地址。输入的 IP 地址是唯一响应托管服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="63162-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="63162-125">**中介服务器**</span><span class="sxs-lookup"><span data-stu-id="63162-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="63162-126">DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="63162-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="63162-p104">选择 **“使用所有配置 IP 地址”**，这意味着可以使用计算机上定义的任何 IP 地址。此外，还可以选择 **“服务仅供选定 IP 地址使用”**，然后在新服务器上输入特定的 IP 地址作为主 IP 地址，并输入公用电话交换网 (PSTN) IP 地址的 IP 地址。输入的 IP 地址是唯一响应指定服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="63162-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="63162-p105">对于中介服务器，默认情况下，为主 IP 地址和 PSTN IP 地址输入的 IP 地址是相同的。如果使用专用的网络接口或同一网络接口上单独的 IP 地址，则可以单独定义这些 IP 地址。如果具有两个网络接口，其中一个用于本地网络连接，另一个用于 PSTN 连接，则必须分配不同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="63162-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="63162-133">**音频/视频会议服务器**</span><span class="sxs-lookup"><span data-stu-id="63162-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="63162-134">DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="63162-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="63162-p106">选择“使用所有已配置的 IP 地址”，这意味着可以使用计算机上定义的任何 IP 地址。此外，还可以选择“将服务用途限制为所选 IP 地址”，然后在新服务器上输入特定的地址。输入的 IP 地址是唯一响应托管服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="63162-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="63162-138">**受信任应用程序服务器**</span><span class="sxs-lookup"><span data-stu-id="63162-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="63162-139">DNS 中定义的新服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="63162-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

