---
title: Skype for Business Server 2015 中的企业语音所需组件
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 在 Skype 业务服务器的企业语音组件的摘要。
ms.openlocfilehash: 2c5df4c0d580d767693717cf48585ceb0d4c7365
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="f6bc8-103">Skype for Business Server 2015 中的企业语音所需组件</span><span class="sxs-lookup"><span data-stu-id="f6bc8-103">Components required for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f6bc8-104">在 Skype 业务服务器的企业语音组件的摘要。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="f6bc8-105">若要部署企业语音，以下组件需要在您的拓扑结构。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="f6bc8-106">一个或多个中介服务器，转换信号传输和，在某些配置中，您的企业服务器，企业语音基础结构和公用交换的电话网络 (PSTN) 网关或会话初始化协议的内部 Skype 之间的介质(SIP) 干线。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="f6bc8-107">中介服务器是企业语音部署中最关键的组件。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="f6bc8-108">有关详细信息，请参阅[中业务服务器 2015年的 Skype 的中介服务器组件](mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-108">For more information, see [Mediation Server component in Skype for Business Server 2015](mediation-server.md).</span></span>
    
    <span data-ttu-id="f6bc8-109">可以搭配使用前端服务器或独立服务器作为安装中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="f6bc8-110">PSTN 连接组件，可能包括 SIP 中继或 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="f6bc8-111">有关详细信息，请参阅[中的业务服务器 2015 Skype 的 PSTN 连接组件](pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-111">For more information, see [PSTN connectivity components in Skype for Business Server 2015](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="f6bc8-112">边缘服务器，可以使用企业语音功能由您的用户在组织的防火墙之外时。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="f6bc8-113">访问边缘服务提供 SIP 信号从 Skype 电话的业务用户位于组织的防火墙之外。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="f6bc8-114">A/V 边缘服务使媒体可以遍历 NAT 和防火墙。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="f6bc8-115">从公司防火墙的外部使用统一通信 (UC) 客户端的呼叫者依靠 A/V 边缘服务进行个别呼叫和电话会议。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="f6bc8-p104">A/V 身份验证服务与 A/V 边缘服务并置在一起，并为后者提供身份验证服务。外部用户如果想要连接到 A/V 边缘服务，则只有在获得 A/V 身份验证服务提供的身份验证令牌之后，其呼叫才能通过。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="f6bc8-118">此外，某些企业语音组件在前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="f6bc8-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="f6bc8-119">有关这些组件的详细信息，请参阅[前结束服务器 VoIP 业务服务器 2015年的 Skype 的组件](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="f6bc8-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server 2015](front-end-server-voip.md)</span></span>
    

