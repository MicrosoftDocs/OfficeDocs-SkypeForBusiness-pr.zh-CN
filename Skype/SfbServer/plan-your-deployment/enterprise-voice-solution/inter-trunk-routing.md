---
title: Skype for Business 服务器中的中继间路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: 了解 Skype for business Server 企业版语音支持中继间路由。
ms.openlocfilehash: 85a77fea8fb414a90b556e5862c42e2c59046dec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802852"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="fbfad-103">Skype for Business 服务器中的中继间路由</span><span class="sxs-lookup"><span data-stu-id="fbfad-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="fbfad-104">了解 Skype for business Server 企业版语音支持中继间路由。</span><span class="sxs-lookup"><span data-stu-id="fbfad-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="fbfad-105">Skype for business 服务器通过 intertrunk 路由支持提供基本的会话管理。</span><span class="sxs-lookup"><span data-stu-id="fbfad-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="fbfad-106">这使 Skype for business 服务器能够向下游电话系统提供呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="fbfad-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="fbfad-107">中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="fbfad-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="fbfad-108">同样，Skype for Business 服务器可以互连两个或更多的 IP PBX 系统，以便可以在不同的 IP PBX 系统中的 PBX 电话之间放置和接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="fbfad-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="fbfad-109">下图介绍了在 PSTN 网关和 IP PBX 之间提供 interconnectivity 的 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="fbfad-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server - 连接 PSTN 网关/IP-PBX 图示](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="fbfad-111">下图显示了连接两个 IP PBX 系统的 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="fbfad-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server - 将 IP-PAX 系统相互连接的图示](../../media/inter_trunk02.jpg)
  

