---
title: 在 Skype for Business Server 2015 中规划边缘服务器部署
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 摘要： 规划业务服务器 2015年服务器边缘环境您 Skype。 本主题介绍了边缘概念，并允许您获取组织与我们更深入的主题。
ms.openlocfilehash: 973cda4f049f4d9d606ba1fe047c99f671ed2e86
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server-2015"></a><span data-ttu-id="bc0da-104">在 Skype for Business Server 2015 中规划边缘服务器部署</span><span class="sxs-lookup"><span data-stu-id="bc0da-104">Plan for Edge Server deployments in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bc0da-p102">**摘要：**规划 Skype for Business Server 2015 服务器边缘环境。本主题介绍边缘概念，并通过更深入的主题让你有条有理。</span><span class="sxs-lookup"><span data-stu-id="bc0da-p102">**Summary:** Plan for your Skype for Business Server 2015 Server Edge environment. This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="bc0da-107">Skype 也内部使用的业务服务器 2015年环境后下, 一步您可能引入到环境的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="bc0da-107">When you have a Skype for Business Server 2015 environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="bc0da-108">此角色将为重要，如果您希望 Skype 的业务服务器 2015 以供内部网络之外的人员提供的服务。</span><span class="sxs-lookup"><span data-stu-id="bc0da-108">This role would be vital if you want the services provided by Skype for Business Server 2015 to be used by people who are outside your internal network.</span></span> <span data-ttu-id="bc0da-109">这些人可能包括：</span><span class="sxs-lookup"><span data-stu-id="bc0da-109">These can potentially include:</span></span>
  
- <span data-ttu-id="bc0da-110">远程用户：临时或一直不在现场的员工。</span><span class="sxs-lookup"><span data-stu-id="bc0da-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="bc0da-111">联盟用户： 合作伙伴组织的员工。</span><span class="sxs-lookup"><span data-stu-id="bc0da-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="bc0da-112">移动用户。</span><span class="sxs-lookup"><span data-stu-id="bc0da-112">Mobile Users.</span></span>
    
- <span data-ttu-id="bc0da-113">你想邀请其加入会议和演示会的潜在客户、合作伙伴，甚至是匿名用户。</span><span class="sxs-lookup"><span data-stu-id="bc0da-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="bc0da-114">外部用户访问，这是边缘服务器的提供，允许所有这种情况。</span><span class="sxs-lookup"><span data-stu-id="bc0da-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="bc0da-115">您的内部用户将能够享受业务服务器 2015年部署您 Skype 由以下服务：</span><span class="sxs-lookup"><span data-stu-id="bc0da-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server 2015 deployment:</span></span>
  
- <span data-ttu-id="bc0da-116">IM 和通信状态：获得授权的外部用户可加入 IM 对话和会议。</span><span class="sxs-lookup"><span data-stu-id="bc0da-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="bc0da-117">他们可获得其他用户的状态信息（这些用户也获得他们的状态）。</span><span class="sxs-lookup"><span data-stu-id="bc0da-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="bc0da-118">您不能进行多方会议，如果您使用的公共 IM 提供商，即严格对等通信。</span><span class="sxs-lookup"><span data-stu-id="bc0da-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="bc0da-119">但是支持 SIP 和 XMPP 两种协议。</span><span class="sxs-lookup"><span data-stu-id="bc0da-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="bc0da-120">音频/视频 (A / V) 会议： 授权的外部用户可以参加您 Skype 业务服务器 2015年音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="bc0da-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server 2015 audio and video conferences.</span></span>
    
- <span data-ttu-id="bc0da-121">Web 会议： 授权的外部用户可以参加您 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="bc0da-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="bc0da-122">如果您愿意，您还可以启用远程用户、 联盟的用户和匿名用户参与。</span><span class="sxs-lookup"><span data-stu-id="bc0da-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="bc0da-123">公共 IM 用户不能参加会议。</span><span class="sxs-lookup"><span data-stu-id="bc0da-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="bc0da-124">此外还有让这些用户参与应用程序和桌面共享，甚至担任会议组织者或演示者的选项。</span><span class="sxs-lookup"><span data-stu-id="bc0da-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="bc0da-125">支持移动设备访问，如为企业语音。</span><span class="sxs-lookup"><span data-stu-id="bc0da-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="bc0da-126">可以将外部用户邀请到你希望他们参加的那些会议，甚至是匿名用户（如果希望将权限授予他们）。</span><span class="sxs-lookup"><span data-stu-id="bc0da-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="bc0da-p108">如果这听上去符合你组织的需求，那么规划边缘环境对于部署该环境会有很大帮助。如需阅读更多资料，下面列出了有关主题。</span><span class="sxs-lookup"><span data-stu-id="bc0da-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>
  
## <a name="planning-topics"></a><span data-ttu-id="bc0da-129">规划主题：</span><span class="sxs-lookup"><span data-stu-id="bc0da-129">Planning topics:</span></span>

<span data-ttu-id="bc0da-130">规划文章有：</span><span class="sxs-lookup"><span data-stu-id="bc0da-130">The planning articles are:</span></span>
  
- [<span data-ttu-id="bc0da-131">边缘服务器的系统要求中 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="bc0da-131">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="bc0da-132">边缘服务器环境要求中 Skype 的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="bc0da-132">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="bc0da-133">边缘服务器中的业务服务器 2015 Skype 的方案</span><span class="sxs-lookup"><span data-stu-id="bc0da-133">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

