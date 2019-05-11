---
title: 规划在 Skype 业务服务器的边缘服务器部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 摘要： 规划业务服务器边缘环境您 Skype。 本主题介绍了边缘概念，并允许您获取组织与我们更深入的主题。
ms.openlocfilehash: 4c4348d0d3aa56aa82b8ea8930176d9d135a64f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885073"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="c0860-104">规划在 Skype 业务服务器的边缘服务器部署</span><span class="sxs-lookup"><span data-stu-id="c0860-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="c0860-105">**摘要：** Plan for Business 服务器边缘环境您 Skype。</span><span class="sxs-lookup"><span data-stu-id="c0860-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="c0860-106">本主题介绍了边缘概念，并允许您获取组织与我们更深入的主题。</span><span class="sxs-lookup"><span data-stu-id="c0860-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="c0860-107">Skype 也内部使用的业务服务器环境后下, 一步您可能引入到环境的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="c0860-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="c0860-108">此角色将为重要，如果您希望 Skype 业务服务器要使用您的内部网络之外的人员提供的服务。</span><span class="sxs-lookup"><span data-stu-id="c0860-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="c0860-109">这些人可能包括：</span><span class="sxs-lookup"><span data-stu-id="c0860-109">These can potentially include:</span></span>
  
- <span data-ttu-id="c0860-110">远程用户：临时或一直不在现场的员工。</span><span class="sxs-lookup"><span data-stu-id="c0860-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="c0860-111">联盟用户： 合作伙伴组织的员工。</span><span class="sxs-lookup"><span data-stu-id="c0860-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="c0860-112">移动用户。</span><span class="sxs-lookup"><span data-stu-id="c0860-112">Mobile Users.</span></span>
    
- <span data-ttu-id="c0860-113">你想邀请其加入会议和演示会的潜在客户、合作伙伴，甚至是匿名用户。</span><span class="sxs-lookup"><span data-stu-id="c0860-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="c0860-114">外部用户访问，这是边缘服务器的提供，允许所有这种情况。</span><span class="sxs-lookup"><span data-stu-id="c0860-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="c0860-115">您的内部用户将能够享受您 Skype 业务服务器部署由以下服务：</span><span class="sxs-lookup"><span data-stu-id="c0860-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="c0860-116">IM 和通信状态：获得授权的外部用户可加入 IM 对话和会议。</span><span class="sxs-lookup"><span data-stu-id="c0860-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="c0860-117">他们可获得其他用户的状态信息（这些用户也获得他们的状态）。</span><span class="sxs-lookup"><span data-stu-id="c0860-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="c0860-118">您不能进行多方会议，如果您使用的公共 IM 提供商，即严格对等通信。</span><span class="sxs-lookup"><span data-stu-id="c0860-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="c0860-119">但是支持 SIP 和 XMPP 两种协议。</span><span class="sxs-lookup"><span data-stu-id="c0860-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="c0860-120">音频/视频 (A / V) 会议： 授权的外部用户可以参加您 Skype Business Server 音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="c0860-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="c0860-121">Web 会议： 授权的外部用户可以参加您 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="c0860-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="c0860-122">如果您愿意，您还可以启用远程用户、 联盟的用户和匿名用户参与。</span><span class="sxs-lookup"><span data-stu-id="c0860-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="c0860-123">公共 IM 用户不能参加会议。</span><span class="sxs-lookup"><span data-stu-id="c0860-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="c0860-124">此外还有让这些用户参与应用程序和桌面共享，甚至担任会议组织者或演示者的选项。</span><span class="sxs-lookup"><span data-stu-id="c0860-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="c0860-125">支持移动设备访问，如为企业语音。</span><span class="sxs-lookup"><span data-stu-id="c0860-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="c0860-126">可以将外部用户邀请到你希望他们参加的那些会议，甚至是匿名用户（如果希望将权限授予他们）。</span><span class="sxs-lookup"><span data-stu-id="c0860-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="c0860-p108">如果这听上去符合你组织的需求，那么规划边缘环境对于部署该环境会有很大帮助。如需阅读更多资料，下面列出了有关主题。</span><span class="sxs-lookup"><span data-stu-id="c0860-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="c0860-129">XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="c0860-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c0860-130">有关详细信息，请参阅[迁移 XMPP 联盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="c0860-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="c0860-131">规划主题：</span><span class="sxs-lookup"><span data-stu-id="c0860-131">Planning topics:</span></span>

<span data-ttu-id="c0860-132">规划文章有：</span><span class="sxs-lookup"><span data-stu-id="c0860-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="c0860-133">Skype for Business Server 2015 的边缘服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="c0860-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="c0860-134">Skype for Business Server 2015 的边缘服务器环境要求</span><span class="sxs-lookup"><span data-stu-id="c0860-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="c0860-135">Skype for Business Server 2015 中的边缘服务器方案</span><span class="sxs-lookup"><span data-stu-id="c0860-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

