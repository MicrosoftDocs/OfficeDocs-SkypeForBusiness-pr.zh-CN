---
title: Skype for Business Server 2015 中的中继间路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: 了解业务服务器企业语音的 Skype 如何支持间中继路由。
ms.openlocfilehash: 58872fccca335792ccbdf03c2c8475c328197426
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="inter-trunk-routing-in-skype-for-business-server-2015"></a><span data-ttu-id="2380b-103">Skype for Business Server 2015 中的中继间路由</span><span class="sxs-lookup"><span data-stu-id="2380b-103">Inter-trunk routing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2380b-104">了解业务服务器企业语音的 Skype 如何支持间中继路由。</span><span class="sxs-lookup"><span data-stu-id="2380b-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="2380b-105">Skype 业务服务器提供支持的 intertrunk 路由的基本会话管理。</span><span class="sxs-lookup"><span data-stu-id="2380b-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="2380b-106">这使 Skype 业务服务器提供到下游的电话服务系统的呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="2380b-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="2380b-107">中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="2380b-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="2380b-108">同样，Skype 业务服务器可以互连两个或多个 IP PBX 系统，以便能放和接收之间从不同的 IP PBX 系统的 PBX 电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="2380b-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="2380b-109">下图展示了 Skype 业务服务器提供 IP PBX 的 PSTN 网关之间的互连性。</span><span class="sxs-lookup"><span data-stu-id="2380b-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server - 连接 PSTN 网关/IP-PBX 图示](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="2380b-111">下图展示了业务服务器连接两个 IP PBX 系统 Skype。</span><span class="sxs-lookup"><span data-stu-id="2380b-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server - 将 IP-PAX 系统相互连接的图示](../../media/inter_trunk02.jpg)
  

