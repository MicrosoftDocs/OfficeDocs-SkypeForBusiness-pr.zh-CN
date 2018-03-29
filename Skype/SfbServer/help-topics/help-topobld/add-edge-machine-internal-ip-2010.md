---
title: 添加边缘机内部 IP 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 使用此页可以指定的内部 IP 地址和边缘服务器的内部完全合格的域名称 (FQDN)。
ms.openlocfilehash: 2fedde361e252d400f4362add4757df3f0c40057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="d36f0-103">添加边缘机内部 IP 2010</span><span class="sxs-lookup"><span data-stu-id="d36f0-103">Add Edge Machine Internal IP 2010</span></span>
 
<span data-ttu-id="d36f0-104">使用此页可以指定的内部 IP 地址和边缘服务器的内部完全合格的域名称 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="d36f0-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>
  
- <span data-ttu-id="d36f0-105">在**内部的 IPv4 地址**中，键入您想要添加到池中的边缘服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d36f0-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>
    
- <span data-ttu-id="d36f0-106">在**内部的 FQDN**，键入您想要添加到池中的边缘服务器的完全合格的域名称 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="d36f0-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>
    
<span data-ttu-id="d36f0-107">您指定的 FQDN 必须与服务器配置的计算机名称相同。</span><span class="sxs-lookup"><span data-stu-id="d36f0-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="d36f0-108">默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d36f0-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="d36f0-109">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="d36f0-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="d36f0-110">因此，您必须配置域名系统 (DNS) 后缀作为未加入到域边缘服务器进行部署的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="d36f0-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="d36f0-111">有关将 DNS 后缀添加到计算机名称的详细信息，请参阅[边缘支持配置 DNS](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="d36f0-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>
  

