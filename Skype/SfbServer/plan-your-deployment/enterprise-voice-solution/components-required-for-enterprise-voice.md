---
title: Skype for business Server 中的企业语音所需的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Skype for Business 服务器中的企业语音组件摘要。
ms.openlocfilehash: 2c87cc6dceb344e8f39717a62b27e7b50cdff643
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277004"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="b3a23-103">Skype for business Server 中的企业语音所需的组件</span><span class="sxs-lookup"><span data-stu-id="b3a23-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="b3a23-104">Skype for Business 服务器中的企业语音组件摘要。</span><span class="sxs-lookup"><span data-stu-id="b3a23-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="b3a23-105">若要部署企业语音, 拓扑中需要以下组件。</span><span class="sxs-lookup"><span data-stu-id="b3a23-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="b3a23-106">一个或多个中介服务器, 用于转换信号和在某些配置中, 在内部 Skype for business 服务器之间、企业语音基础结构和公共交换电话网络 (PSTN) 网关或会话初始协议之间的媒体(SIP) 主干。</span><span class="sxs-lookup"><span data-stu-id="b3a23-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="b3a23-107">中介服务器是企业语音部署中最重要的组件。</span><span class="sxs-lookup"><span data-stu-id="b3a23-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="b3a23-108">有关详细信息, 请参阅[Skype For Business 服务器中的中介服务器组件](mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="b3a23-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="b3a23-109">中介服务器可以与前端服务器 collocated, 也可以作为独立服务器安装。</span><span class="sxs-lookup"><span data-stu-id="b3a23-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="b3a23-110">PSTN 连接组件，可能包括 SIP 中继或 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="b3a23-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="b3a23-111">有关详细信息, 请参阅[Skype For Business 服务器中的 PSTN 连接组件](pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="b3a23-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="b3a23-112">边缘服务器, 允许用户在组织的防火墙之外使用企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="b3a23-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="b3a23-113">Access Edge 服务提供 SIP 信号, 用于从组织防火墙之外的 Skype for Business 用户进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="b3a23-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="b3a23-114">A/V 边缘服务使媒体可以遍历 NAT 和防火墙。</span><span class="sxs-lookup"><span data-stu-id="b3a23-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="b3a23-115">从公司防火墙的外部使用统一通信 (UC) 客户端的呼叫者依靠 A/V 边缘服务进行个别呼叫和电话会议。</span><span class="sxs-lookup"><span data-stu-id="b3a23-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="b3a23-p104">A/V 身份验证服务与 A/V 边缘服务并置在一起，并为后者提供身份验证服务。外部用户如果想要连接到 A/V 边缘服务，则只有在获得 A/V 身份验证服务提供的身份验证令牌之后，其呼叫才能通过。</span><span class="sxs-lookup"><span data-stu-id="b3a23-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="b3a23-118">此外, 某些企业语音组件在前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="b3a23-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="b3a23-119">有关这些组件的详细信息, 请参阅[Skype for Business 服务器的前端服务器 VoIP 组件](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="b3a23-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

