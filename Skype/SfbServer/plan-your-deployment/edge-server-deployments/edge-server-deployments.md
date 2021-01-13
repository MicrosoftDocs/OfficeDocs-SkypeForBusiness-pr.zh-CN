---
title: 在 Skype for Business Server 中规划边缘服务器部署
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 摘要：规划 Skype for Business Server 边缘环境。 本主题向你介绍 Edge 概念，并让你通过我们更深入的主题进行组织。
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813802"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="7000d-104">在 Skype for Business Server 中规划边缘服务器部署</span><span class="sxs-lookup"><span data-stu-id="7000d-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="7000d-105">**摘要：** 规划 Skype for Business Server 边缘环境。</span><span class="sxs-lookup"><span data-stu-id="7000d-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="7000d-106">本主题向你介绍 Edge 概念，并让你通过我们更深入的主题进行组织。</span><span class="sxs-lookup"><span data-stu-id="7000d-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="7000d-107">当你的 Skype for Business Server 环境在内部运行良好时，下一步可能是向该环境引入边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="7000d-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="7000d-108">如果希望 Skype for Business Server 提供的服务由内部网络外部的人员使用，此角色将非常重要。</span><span class="sxs-lookup"><span data-stu-id="7000d-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="7000d-109">这些可能包括：</span><span class="sxs-lookup"><span data-stu-id="7000d-109">These can potentially include:</span></span>
  
- <span data-ttu-id="7000d-110">远程用户：临时或持续离开的员工。</span><span class="sxs-lookup"><span data-stu-id="7000d-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="7000d-111">联盟用户：合作伙伴组织的员工。</span><span class="sxs-lookup"><span data-stu-id="7000d-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="7000d-112">移动用户。</span><span class="sxs-lookup"><span data-stu-id="7000d-112">Mobile Users.</span></span>
    
- <span data-ttu-id="7000d-113">要邀请参加会议和演示文稿的潜在客户、合作伙伴甚至匿名用户。</span><span class="sxs-lookup"><span data-stu-id="7000d-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="7000d-114">外部用户访问（边缘服务器提供）允许进行所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="7000d-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="7000d-115">内部用户将能够享受由 Skype for Business Server 部署托管的以下服务：</span><span class="sxs-lookup"><span data-stu-id="7000d-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="7000d-116">用于通信的 IM 和状态：授权的外部用户可以加入 IM 对话和会议。</span><span class="sxs-lookup"><span data-stu-id="7000d-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="7000d-117">他们可以获取其他用户状态信息 (获取其状态信息) 。</span><span class="sxs-lookup"><span data-stu-id="7000d-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="7000d-118">如果使用公共 IM 提供程序，则不能进行多方会议，这完全就是对等通信。</span><span class="sxs-lookup"><span data-stu-id="7000d-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="7000d-119">但支持 SIP 和 XMPP 协议。</span><span class="sxs-lookup"><span data-stu-id="7000d-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="7000d-120">A/V (音频/) 会议：授权外部用户可以参加 Skype for Business Server 音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="7000d-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="7000d-121">Web 会议：你的授权外部用户可以参加你的 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="7000d-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="7000d-122">如果需要，您还可以允许远程用户、联盟用户和匿名用户参与。</span><span class="sxs-lookup"><span data-stu-id="7000d-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="7000d-123">公共 IM 用户不能参加会议。</span><span class="sxs-lookup"><span data-stu-id="7000d-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="7000d-124">还有一些选项允许这些用户参与应用程序和桌面共享，甚至充当会议组织者或演示者。</span><span class="sxs-lookup"><span data-stu-id="7000d-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="7000d-125">支持移动设备访问，就像支持企业语音。</span><span class="sxs-lookup"><span data-stu-id="7000d-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="7000d-126">如果要向外部用户授予权限，可以邀请外部用户参加你希望他们参加的会议，甚至是匿名用户。</span><span class="sxs-lookup"><span data-stu-id="7000d-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="7000d-127">如果这看起来像是组织所需的内容，那么规划边缘环境对于部署边缘环境将大有帮助。</span><span class="sxs-lookup"><span data-stu-id="7000d-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="7000d-128">为了进一步阅读，我们在下面列出了主题。</span><span class="sxs-lookup"><span data-stu-id="7000d-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="7000d-129">XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="7000d-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7000d-130">有关详细信息 [，请参阅"迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟"。</span><span class="sxs-lookup"><span data-stu-id="7000d-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="7000d-131">规划主题：</span><span class="sxs-lookup"><span data-stu-id="7000d-131">Planning topics:</span></span>

<span data-ttu-id="7000d-132">规划文章包括：</span><span class="sxs-lookup"><span data-stu-id="7000d-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="7000d-133">Skype for Business Server 2015 中的边缘服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="7000d-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="7000d-134">Skype for Business Server 2015 中的边缘服务器环境要求</span><span class="sxs-lookup"><span data-stu-id="7000d-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="7000d-135">Skype for Business Server 2015 中的边缘服务器方案</span><span class="sxs-lookup"><span data-stu-id="7000d-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

