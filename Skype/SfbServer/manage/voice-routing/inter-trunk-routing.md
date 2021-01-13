---
title: Skype for Business Server 中的中继间路由
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server 通过支持跨平台路由提供基本的会话管理。 '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814122"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="63f34-103">Skype for Business Server 中的中继间路由</span><span class="sxs-lookup"><span data-stu-id="63f34-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="63f34-104">Skype for Business Server 通过支持跨平台路由提供基本的会话管理。</span><span class="sxs-lookup"><span data-stu-id="63f34-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="63f34-105">此功能使 Skype for Business Server 能够向下游电话系统提供呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="63f34-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="63f34-106">中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="63f34-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="63f34-107">同样，Skype for Business Server 可以将两个或多个 IP-PBX 系统相互连接，以便可以在不同 IP-PBX 系统的 PBX 电话之间拨打和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="63f34-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="63f34-108">下图说明了在 PSTN 网关和 IP-PBX 之间提供互连性的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="63f34-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![PSTN 网关和 IP-PBX 之间的互连性](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="63f34-110">下图说明了连接两个 IP-PBX 系统的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="63f34-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![连接两个 IP-PGX 系统的 Skype for Business Server](../../media/two-ip-pbx-systems.jpg)

