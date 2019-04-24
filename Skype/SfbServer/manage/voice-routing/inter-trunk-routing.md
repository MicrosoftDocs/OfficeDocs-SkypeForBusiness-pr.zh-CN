---
title: 内部中继路由中 Skype 业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype 业务服务器提供通过支持的中继间路由的基本会话管理。 '
ms.openlocfilehash: 9f73899d59e79d8fc93e768f0e870449baaeb7fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214794"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="7cba6-103">内部中继路由中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="7cba6-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="7cba6-104">Skype 业务服务器提供通过支持的中继间路由的基本会话管理。</span><span class="sxs-lookup"><span data-stu-id="7cba6-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="7cba6-105">此功能允许 Skype 业务服务器提供与下游电话系统的呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="7cba6-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="7cba6-106">中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="7cba6-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="7cba6-107">同样，Skype 业务服务器可以互连两个或多个 IP-PBX 系统，以便可以发出呼叫，并将其从不同的 IP PBX 系统的 PBX 电话之间收到。</span><span class="sxs-lookup"><span data-stu-id="7cba6-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="7cba6-108">下图展示了业务服务器提供 PSTN 网关和 IP-PBX 之间的互连性的 Skype。</span><span class="sxs-lookup"><span data-stu-id="7cba6-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![PSTN 网关和 IP-PBX 之间的互连性](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="7cba6-110">下图显示连接两个 IP-PBX 系统的业务服务器 Skype。</span><span class="sxs-lookup"><span data-stu-id="7cba6-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype 连接两个 IP PGX 系统的业务服务器](../../media/two-ip-pbx-systems.jpg)

