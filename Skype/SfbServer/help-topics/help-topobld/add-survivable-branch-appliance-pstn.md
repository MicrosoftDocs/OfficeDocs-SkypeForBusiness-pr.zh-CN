---
title: 添加 Survivable Branch Appliance PSTN
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 若要定义的分支站点高存活力分支装置公用交换的电话网络 (PSTN) 网关，指定以下项：
ms.openlocfilehash: cefdc46eb2f5b7573e5e5bd9acb93cb5ab384622
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="16bcd-103">添加 Survivable Branch Appliance PSTN</span><span class="sxs-lookup"><span data-stu-id="16bcd-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="16bcd-104">若要定义的分支站点高存活力分支装置公用交换的电话网络 (PSTN) 网关，指定以下项：</span><span class="sxs-lookup"><span data-stu-id="16bcd-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="16bcd-105">完全限定的域名称 (FQDN) 或 IP 地址，对高存活力的分支装置或自动恢复分支服务器程序与入站和出站路由的网关等 PSTN 调用。</span><span class="sxs-lookup"><span data-stu-id="16bcd-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="16bcd-106">如果您正在定义一个高存活力的分支装置，这是高存活力的分支装置内的中介服务器将连接的 PSTN 连接的网关。</span><span class="sxs-lookup"><span data-stu-id="16bcd-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="16bcd-p101">将用于会话初始协议 (SIP) 消息的侦听端口。默认情况下，网关、专用交换机 (PBX) 或会话边界控制器 (SBC) 上的传输控制协议 (TCP) 端口为 5066，传输层安全性 (TLS) 的端口为 5067。在分支站点的 Survivable Branch Appliance 上，TCP 的默认端口为 5081，TLS 的默认端口为 5082。</span><span class="sxs-lookup"><span data-stu-id="16bcd-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="16bcd-110">出于安全考虑，强烈建议使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="16bcd-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="16bcd-111">如果您正在定义一个高存活力的分支装置，参考高存活力的分支装置供应商文档，验证您高存活力的分支装置支持 TLS 协议。</span><span class="sxs-lookup"><span data-stu-id="16bcd-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="16bcd-112">出于安全考虑，强烈建议部署可以使用 TLS 的网关。</span><span class="sxs-lookup"><span data-stu-id="16bcd-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="16bcd-113">如果要添加 PSTN 网关，可以稍后对其进行设置，但在定义和配置 PSTN 网关之前，完整功能将受到限制。</span><span class="sxs-lookup"><span data-stu-id="16bcd-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

