---
title: 在 Skype for Business 服务器中规划边缘服务器部署
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '摘要: 规划 Skype for business Server Edge 环境。 本主题向你介绍边缘概念, 让你可以使用更深入的主题进行组织。'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277158"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="36364-104">在 Skype for Business 服务器中规划边缘服务器部署</span><span class="sxs-lookup"><span data-stu-id="36364-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="36364-105">**摘要:** 规划 Skype for business Server Edge 环境。</span><span class="sxs-lookup"><span data-stu-id="36364-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="36364-106">本主题向你介绍边缘概念, 让你可以使用更深入的主题进行组织。</span><span class="sxs-lookup"><span data-stu-id="36364-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="36364-107">如果您的 Skype for Business Server 环境在内部工作良好, 则下一步可能是向环境引入边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="36364-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="36364-108">如果你希望 Skype for Business 服务器提供的服务由内部网络外部的用户使用, 此角色将非常重要。</span><span class="sxs-lookup"><span data-stu-id="36364-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="36364-109">这些人可能包括：</span><span class="sxs-lookup"><span data-stu-id="36364-109">These can potentially include:</span></span>
  
- <span data-ttu-id="36364-110">远程用户：临时或一直不在现场的员工。</span><span class="sxs-lookup"><span data-stu-id="36364-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="36364-111">联盟用户: 您的合作伙伴组织的员工。</span><span class="sxs-lookup"><span data-stu-id="36364-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="36364-112">移动用户。</span><span class="sxs-lookup"><span data-stu-id="36364-112">Mobile Users.</span></span>
    
- <span data-ttu-id="36364-113">你想邀请其加入会议和演示会的潜在客户、合作伙伴，甚至是匿名用户。</span><span class="sxs-lookup"><span data-stu-id="36364-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="36364-114">外部用户访问, 这是服务器提供的边缘, 允许所有这些操作发生。</span><span class="sxs-lookup"><span data-stu-id="36364-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="36364-115">你的内部用户将能够享受 Skype for Business Server 部署托管的以下服务:</span><span class="sxs-lookup"><span data-stu-id="36364-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="36364-116">IM 和通信状态：获得授权的外部用户可加入 IM 对话和会议。</span><span class="sxs-lookup"><span data-stu-id="36364-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="36364-117">他们可获得其他用户的状态信息（这些用户也获得他们的状态）。</span><span class="sxs-lookup"><span data-stu-id="36364-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="36364-118">如果您使用的是公共 IM 提供商, 则不能执行多方会议, 这是完全对等通信。</span><span class="sxs-lookup"><span data-stu-id="36364-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="36364-119">但是支持 SIP 和 XMPP 两种协议。</span><span class="sxs-lookup"><span data-stu-id="36364-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="36364-120">音频/视频 (A/V) 会议: 授权外部用户可以参与 Skype for Business 服务器音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="36364-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="36364-121">网络会议: 您授权的外部用户可以参与您的 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="36364-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="36364-122">如果您愿意, 也可以为远程用户、联盟用户和匿名用户启用参与。</span><span class="sxs-lookup"><span data-stu-id="36364-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="36364-123">公共 IM 用户不能参与会议。</span><span class="sxs-lookup"><span data-stu-id="36364-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="36364-124">此外还有让这些用户参与应用程序和桌面共享，甚至担任会议组织者或演示者的选项。</span><span class="sxs-lookup"><span data-stu-id="36364-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="36364-125">由于企业语音, 支持移动设备访问。</span><span class="sxs-lookup"><span data-stu-id="36364-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="36364-126">可以将外部用户邀请到你希望他们参加的那些会议，甚至是匿名用户（如果希望将权限授予他们）。</span><span class="sxs-lookup"><span data-stu-id="36364-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="36364-p108">如果这听上去符合你组织的需求，那么规划边缘环境对于部署该环境会有很大帮助。如需阅读更多资料，下面列出了有关主题。</span><span class="sxs-lookup"><span data-stu-id="36364-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="36364-129">XMPP 网关和代理在 Skype for business Server 2015 中可用, 但 Skype for business Server 2019 不再支持。</span><span class="sxs-lookup"><span data-stu-id="36364-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="36364-130">有关详细信息, 请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="36364-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="36364-131">规划主题：</span><span class="sxs-lookup"><span data-stu-id="36364-131">Planning topics:</span></span>

<span data-ttu-id="36364-132">规划文章有：</span><span class="sxs-lookup"><span data-stu-id="36364-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="36364-133">Skype for Business Server 2015 的边缘服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="36364-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="36364-134">Skype for Business Server 2015 的边缘服务器环境要求</span><span class="sxs-lookup"><span data-stu-id="36364-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="36364-135">Skype for Business Server 2015 中的边缘服务器方案</span><span class="sxs-lookup"><span data-stu-id="36364-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

