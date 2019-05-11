---
title: 添加 Edge Server 内部 IP 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: 使用此页指定的内部 IP 地址和内部完全限定的域名 (FQDN) 边缘服务器。
ms.openlocfilehash: db70b63840012d0828b45398bc51cbe54debd719
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886337"
---
# <a name="add-edge-server-internal-ip-2010"></a><span data-ttu-id="e4d64-103">添加 Edge Server 内部 IP 2010</span><span class="sxs-lookup"><span data-stu-id="e4d64-103">Add Edge Server Internal IP 2010</span></span>

<span data-ttu-id="e4d64-104">使用此页指定的内部 IP 地址和内部完全限定的域名 (FQDN) 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="e4d64-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="e4d64-105">您指定的 FQDN 必须与服务器配置的计算机名称相同。</span><span class="sxs-lookup"><span data-stu-id="e4d64-105">That FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="e4d64-106">默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e4d64-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="e4d64-107">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="e4d64-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="e4d64-108">因此，您必须在要部署为边缘服务器的未加入域的计算机的名称配置域名系统 (DNS) 后缀。</span><span class="sxs-lookup"><span data-stu-id="e4d64-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="e4d64-109">有关向计算机名称添加 DNS 后缀的详细信息，请参阅[配置边缘支持的 DNS](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e4d64-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).</span></span>


