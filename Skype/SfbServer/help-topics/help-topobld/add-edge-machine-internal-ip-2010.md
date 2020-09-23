---
title: 添加边缘计算机内部 IP 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 使用此页指定边缘服务器的内部 IP 地址和内部完全限定域名 (FQDN)。
ms.openlocfilehash: 857e2041779efd02007939b7046860cc295cb7b8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219373"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="9c76a-103">添加边缘计算机内部 IP 2010</span><span class="sxs-lookup"><span data-stu-id="9c76a-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="9c76a-104">使用此页指定边缘服务器的内部 IP 地址和内部完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="9c76a-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="9c76a-105">在 " **内部 IPv4 地址**" 中，键入要添加到池中的边缘服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9c76a-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="9c76a-106">在 " **内部 FQDN**" 中，键入要添加到池的边缘服务器 (FQDN) 的完全限定的域名称。</span><span class="sxs-lookup"><span data-stu-id="9c76a-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="9c76a-107">指定的 FQDN 必须与在服务器上配置的计算机名称相同。</span><span class="sxs-lookup"><span data-stu-id="9c76a-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="9c76a-108">默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9c76a-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="9c76a-109">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="9c76a-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="9c76a-110">因此，必须在要部署为未加入域的边缘服务器的计算机名称上配置域名系统 (DNS) 后缀。</span><span class="sxs-lookup"><span data-stu-id="9c76a-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="9c76a-111">有关向计算机名称添加 DNS 后缀的详细信息，请参阅[Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9c76a-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


