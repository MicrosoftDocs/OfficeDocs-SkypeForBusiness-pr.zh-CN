---
title: 添加 Survivable Branch Appliance PSTN
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 要在分支站点为 Survivable Branch appliance 定义公用电话交换网 (pstn) 网关，请指定以下内容：
ms.openlocfilehash: e0c2bc6073035e5c752159b25dff04a9498d4015
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21069199"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="00923-103">添加 Survivable Branch Appliance PSTN</span><span class="sxs-lookup"><span data-stu-id="00923-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="00923-104">要在分支站点为 Survivable Branch appliance 定义公用电话交换网 (pstn) 网关，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="00923-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="00923-105">完全限定的域名 (FQDN) 或 IP 地址的对等网关的 Survivable Branch Appliance 或 Survivable Branch Server 相关联的路由入站和出站 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="00923-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="00923-106">如果您要定义 Survivable Branch Appliance，这是指 Survivable Branch Appliance 内的中介服务器将连接的 PSTN 连接的网关。</span><span class="sxs-lookup"><span data-stu-id="00923-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="00923-p101">将用于会话初始协议 (SIP) 消息的侦听端口。默认情况下，网关、专用交换机 (PBX) 或会话边界控制器 (SBC) 上的传输控制协议 (TCP) 端口为 5066，传输层安全性 (TLS) 的端口为 5067。在分支站点的 Survivable Branch Appliance 上，TCP 的默认端口为 5081，TLS 的默认端口为 5082。</span><span class="sxs-lookup"><span data-stu-id="00923-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="00923-110">出于安全考虑，强烈建议使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="00923-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="00923-111">如果您要定义 Survivable Branch Appliance，请参阅 Survivable Branch Appliance 供应商文档来验证您 Survivable Branch Appliance 支持 TLS 协议。</span><span class="sxs-lookup"><span data-stu-id="00923-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="00923-112">出于安全考虑，强烈建议部署可以使用 TLS 的网关。</span><span class="sxs-lookup"><span data-stu-id="00923-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="00923-113">如果要添加 PSTN 网关，可以稍后对其进行设置，但在定义和配置 PSTN 网关之前，完整功能将受到限制。</span><span class="sxs-lookup"><span data-stu-id="00923-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

