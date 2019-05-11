---
title: 添加 Edge 机器内部 IP 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 此页用于指定的内部 IP 地址和内部完全限定的域名 (FQDN) 边缘服务器。
ms.openlocfilehash: 1ec24b1c85b429cf5308eb7e521c7ca4d7d295dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886520"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="05192-103">添加 Edge 机器内部 IP 2010</span><span class="sxs-lookup"><span data-stu-id="05192-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="05192-104">此页用于指定的内部 IP 地址和内部完全限定的域名 (FQDN) 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="05192-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="05192-105">在**内部 IPv4 地址**框中，键入要向池中添加边缘服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="05192-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="05192-106">在**内部 FQDN**中，键入要向池中添加边缘服务器的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="05192-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="05192-107">您指定的 FQDN 必须与服务器配置的计算机名称相同。</span><span class="sxs-lookup"><span data-stu-id="05192-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="05192-108">默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="05192-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="05192-109">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="05192-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="05192-110">因此，您必须在要部署为边缘服务器的未加入域的计算机的名称配置域名系统 (DNS) 后缀。</span><span class="sxs-lookup"><span data-stu-id="05192-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="05192-111">有关向计算机名称添加 DNS 后缀的详细信息，请参阅[配置边缘支持的 DNS](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="05192-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


