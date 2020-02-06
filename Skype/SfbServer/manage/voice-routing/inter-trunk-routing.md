---
title: Skype for Business 服务器中的中继间路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for business 服务器通过 intertrunk 路由支持提供基本的会话管理。 '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816962"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="9e7a0-103">Skype for Business 服务器中的中继间路由</span><span class="sxs-lookup"><span data-stu-id="9e7a0-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="9e7a0-104">Skype for business 服务器通过 intertrunk 路由支持提供基本的会话管理。</span><span class="sxs-lookup"><span data-stu-id="9e7a0-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="9e7a0-105">此功能使 Skype for business 服务器能够向下游电话系统提供呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="9e7a0-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="9e7a0-106">中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="9e7a0-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="9e7a0-107">同样，Skype for Business 服务器可以互连两个或更多的 IP PBX 系统，以便可以在不同的 IP PBX 系统中的 PBX 电话之间放置和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e7a0-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="9e7a0-108">下图介绍了在 PSTN 网关和 IP PBX 之间提供 interconnectivity 的 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="9e7a0-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![PSTN 网关和 IP PBX 之间的 Interconnectivity](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="9e7a0-110">下图显示了连接两个 IP PBX 系统的 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="9e7a0-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![连接两个 IP-PGX 系统的 Skype for Business 服务器](../../media/two-ip-pbx-systems.jpg)

