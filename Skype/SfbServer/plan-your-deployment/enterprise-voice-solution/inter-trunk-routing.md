---
title: 内部中继路由中 Skype 业务服务器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: 了解如何为业务 Server 企业语音的 Skype 支持内部中继路由。
ms.openlocfilehash: 281e722898655e463c3db281014421ae224c2cec
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207298"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="10ad7-103">内部中继路由中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="10ad7-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="10ad7-104">了解如何为业务 Server 企业语音的 Skype 支持内部中继路由。</span><span class="sxs-lookup"><span data-stu-id="10ad7-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="10ad7-105">Skype 业务服务器提供通过支持的中继间路由的基本会话管理。</span><span class="sxs-lookup"><span data-stu-id="10ad7-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="10ad7-106">这样 Skype 业务服务器提供与下游电话系统的呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="10ad7-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="10ad7-107">中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="10ad7-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="10ad7-108">同样，Skype 业务服务器可以互连两个或多个 IP-PBX 系统，以便可以发出呼叫，并将其从不同的 IP PBX 系统的 PBX 电话之间收到。</span><span class="sxs-lookup"><span data-stu-id="10ad7-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="10ad7-109">下图展示了业务服务器提供 PSTN 网关和 IP-PBX 之间的互连性的 Skype。</span><span class="sxs-lookup"><span data-stu-id="10ad7-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server - 连接 PSTN 网关/IP-PBX 图示](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="10ad7-111">下图显示连接两个 IP-PBX 系统的业务服务器 Skype。</span><span class="sxs-lookup"><span data-stu-id="10ad7-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server - 将 IP-PAX 系统相互连接的图示](../../media/inter_trunk02.jpg)
  

