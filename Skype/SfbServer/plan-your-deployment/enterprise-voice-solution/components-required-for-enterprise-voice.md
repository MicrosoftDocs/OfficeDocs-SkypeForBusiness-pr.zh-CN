---
title: 所需的 Skype 中的企业语音的企业服务器组件
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 企业语音组件中的业务服务器 Skype 摘要。
ms.openlocfilehash: 513f116f1c92bbe931e9015bc8507b0c1f16fc1a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881802"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="950e8-103">所需的 Skype 中的企业语音的企业服务器组件</span><span class="sxs-lookup"><span data-stu-id="950e8-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="950e8-104">企业语音组件中的业务服务器 Skype 摘要。</span><span class="sxs-lookup"><span data-stu-id="950e8-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="950e8-105">若要部署企业语音，需要以下组件在拓扑中。</span><span class="sxs-lookup"><span data-stu-id="950e8-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="950e8-106">一个或多个中介服务器，翻译信号的以及在某些配置中，对于业务 Server，企业语音基础结构和公用电话交换网 (pstn) 网关或会话初始协议您内部 Skype 之间的媒体(SIP) 中继。</span><span class="sxs-lookup"><span data-stu-id="950e8-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="950e8-107">中介服务器是企业语音部署中最重要的组件。</span><span class="sxs-lookup"><span data-stu-id="950e8-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="950e8-108">有关详细信息，请参阅[Skype 业务服务器中的中介服务器组件](mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="950e8-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="950e8-109">可以与前端服务器并置或独立服务器安装中介服务器。</span><span class="sxs-lookup"><span data-stu-id="950e8-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="950e8-110">PSTN 连接组件，可能包括 SIP 中继或 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="950e8-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="950e8-111">有关详细信息，请参阅[Skype 业务服务器中的 PSTN 连接组件](pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="950e8-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="950e8-112">边缘服务器，贵组织的防火墙之外时允许的用户的企业语音功能使用。</span><span class="sxs-lookup"><span data-stu-id="950e8-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="950e8-113">访问边缘服务提供的 Skype 从组织防火墙之外的业务用户的呼叫的 SIP 信号。</span><span class="sxs-lookup"><span data-stu-id="950e8-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="950e8-114">A/V 边缘服务使媒体可以遍历 NAT 和防火墙。</span><span class="sxs-lookup"><span data-stu-id="950e8-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="950e8-115">从公司防火墙的外部使用统一通信 (UC) 客户端的呼叫者依靠 A/V 边缘服务进行个别呼叫和电话会议。</span><span class="sxs-lookup"><span data-stu-id="950e8-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="950e8-p104">A/V 身份验证服务与 A/V 边缘服务并置在一起，并为后者提供身份验证服务。外部用户如果想要连接到 A/V 边缘服务，则只有在获得 A/V 身份验证服务提供的身份验证令牌之后，其呼叫才能通过。</span><span class="sxs-lookup"><span data-stu-id="950e8-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="950e8-118">此外，在前端服务器上运行某些企业语音组件。</span><span class="sxs-lookup"><span data-stu-id="950e8-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="950e8-119">有关这些组件的详细信息，请参阅[Skype 业务服务器的前端服务器 VoIP 组件](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="950e8-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

