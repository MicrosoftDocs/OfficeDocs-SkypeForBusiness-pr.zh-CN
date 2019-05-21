---
title: 添加 Survivable Branch Appliance PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: '若要为分支站点上的 Survivable 分支装置定义公共交换电话网络 (PSTN) 网关, 请指定以下内容:'
ms.openlocfilehash: bd069a5bc9c8dcb4f1f787cbd436e31872bceddd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288141"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="8730b-103">添加 Survivable Branch Appliance PSTN</span><span class="sxs-lookup"><span data-stu-id="8730b-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="8730b-104">若要为分支站点上的 Survivable 分支装置定义公共交换电话网络 (PSTN) 网关, 请指定以下内容:</span><span class="sxs-lookup"><span data-stu-id="8730b-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="8730b-105">网关对等的完全限定的域名 (FQDN) 或 IP 地址 Survivable 分支装置或 Survivable 分支服务器与路由入站和出站 PSTN 呼叫相关联。</span><span class="sxs-lookup"><span data-stu-id="8730b-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8730b-106">如果你要定义 Survivable 分支设备, 这是 Survivable 分支设备中的中介服务器将连接到 PSTN 连接的网关。</span><span class="sxs-lookup"><span data-stu-id="8730b-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="8730b-p101">将用于会话初始协议 (SIP) 消息的侦听端口。默认情况下，网关、专用交换机 (PBX) 或会话边界控制器 (SBC) 上的传输控制协议 (TCP) 端口为 5066，传输层安全性 (TLS) 的端口为 5067。在分支站点的 Survivable Branch Appliance 上，TCP 的默认端口为 5081，TLS 的默认端口为 5082。</span><span class="sxs-lookup"><span data-stu-id="8730b-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="8730b-110">出于安全考虑，强烈建议使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="8730b-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="8730b-111">如果你要定义 Survivable 分支设备, 请参阅 Survivable 分支设备供应商文档, 以验证你的 Survivable 分支设备是否支持 TLS 协议。</span><span class="sxs-lookup"><span data-stu-id="8730b-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8730b-112">出于安全考虑，强烈建议部署可以使用 TLS 的网关。</span><span class="sxs-lookup"><span data-stu-id="8730b-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8730b-113">如果要添加 PSTN 网关，可以稍后对其进行设置，但在定义和配置 PSTN 网关之前，完整功能将受到限制。</span><span class="sxs-lookup"><span data-stu-id="8730b-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

