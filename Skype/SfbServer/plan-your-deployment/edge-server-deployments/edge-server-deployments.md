---
title: 在 Skype for Business Server 2015 中规划边缘服务器部署
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 摘要： 针对您 Skype 业务服务器 2015年服务器边缘环境规划。 本主题介绍边缘的概念，并允许您与我们更深入的主题变得有组织。
ms.openlocfilehash: 828bdc52a6c4fe55294768d69c441b9c996fa9a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server-2015"></a><span data-ttu-id="4cd71-104">在 Skype for Business Server 2015 中规划边缘服务器部署</span><span class="sxs-lookup"><span data-stu-id="4cd71-104">Plan for Edge Server deployments in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4cd71-p102">**摘要：**规划 Skype for Business Server 2015 服务器边缘环境。本主题介绍边缘概念，并通过更深入的主题让你有条有理。</span><span class="sxs-lookup"><span data-stu-id="4cd71-p102">**Summary:** Plan for your Skype for Business Server 2015 Server Edge environment. This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="4cd71-107">当 Skype 正在很好地内部的业务服务器 2015年环境时，您的下一步可能向环境中引入边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="4cd71-107">When you have a Skype for Business Server 2015 environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="4cd71-108">此角色是非常重要的如果您想要使用通过您的内部网络之外的人的业务服务器 2015年的 Skype 所提供的服务。</span><span class="sxs-lookup"><span data-stu-id="4cd71-108">This role would be vital if you want the services provided by Skype for Business Server 2015 to be used by people who are outside your internal network.</span></span> <span data-ttu-id="4cd71-109">这些人可能包括：</span><span class="sxs-lookup"><span data-stu-id="4cd71-109">These can potentially include:</span></span>
  
- <span data-ttu-id="4cd71-110">远程用户：临时或一直不在现场的员工。</span><span class="sxs-lookup"><span data-stu-id="4cd71-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="4cd71-111">联盟用户： 您的合作伙伴公司的员工。</span><span class="sxs-lookup"><span data-stu-id="4cd71-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="4cd71-112">移动用户。</span><span class="sxs-lookup"><span data-stu-id="4cd71-112">Mobile Users.</span></span>
    
- <span data-ttu-id="4cd71-113">你想邀请其加入会议和演示会的潜在客户、合作伙伴，甚至是匿名用户。</span><span class="sxs-lookup"><span data-stu-id="4cd71-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="4cd71-114">外部用户访问，这是边缘服务器的提供，允许所有这种情况。</span><span class="sxs-lookup"><span data-stu-id="4cd71-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="4cd71-115">您的内部用户将能够享受以下承载的业务服务器 2015年部署您 Skype 的服务：</span><span class="sxs-lookup"><span data-stu-id="4cd71-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server 2015 deployment:</span></span>
  
- <span data-ttu-id="4cd71-116">IM 和通信状态：获得授权的外部用户可加入 IM 对话和会议。</span><span class="sxs-lookup"><span data-stu-id="4cd71-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="4cd71-117">他们可获得其他用户的状态信息（这些用户也获得他们的状态）。</span><span class="sxs-lookup"><span data-stu-id="4cd71-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="4cd71-118">您无法进行多方会议，如果您使用的是绝对对等通信的公用 IM 提供。</span><span class="sxs-lookup"><span data-stu-id="4cd71-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="4cd71-119">但是支持 SIP 和 XMPP 两种协议。</span><span class="sxs-lookup"><span data-stu-id="4cd71-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="4cd71-120">音频/视频 (A / V) 会议： 授权的外部用户可以参与您 Skype 业务服务器 2015年音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="4cd71-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server 2015 audio and video conferences.</span></span>
    
- <span data-ttu-id="4cd71-121">Web 会议： 您授权的外部用户可以参与您 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="4cd71-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="4cd71-122">如果您愿意，还可以启用使远程用户和联盟的用户，匿名用户的参与。</span><span class="sxs-lookup"><span data-stu-id="4cd71-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="4cd71-123">公用 IM 用户不能参加会议。</span><span class="sxs-lookup"><span data-stu-id="4cd71-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="4cd71-124">此外还有让这些用户参与应用程序和桌面共享，甚至担任会议组织者或演示者的选项。</span><span class="sxs-lookup"><span data-stu-id="4cd71-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="4cd71-125">支持移动设备的访问，是企业语音。</span><span class="sxs-lookup"><span data-stu-id="4cd71-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="4cd71-126">可以将外部用户邀请到你希望他们参加的那些会议，甚至是匿名用户（如果希望将权限授予他们）。</span><span class="sxs-lookup"><span data-stu-id="4cd71-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="4cd71-p108">如果这听上去符合你组织的需求，那么规划边缘环境对于部署该环境会有很大帮助。如需阅读更多资料，下面列出了有关主题。</span><span class="sxs-lookup"><span data-stu-id="4cd71-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>
  
## <a name="planning-topics"></a><span data-ttu-id="4cd71-129">规划主题：</span><span class="sxs-lookup"><span data-stu-id="4cd71-129">Planning topics:</span></span>

<span data-ttu-id="4cd71-130">规划文章有：</span><span class="sxs-lookup"><span data-stu-id="4cd71-130">The planning articles are:</span></span>
  
- [<span data-ttu-id="4cd71-131">边缘服务器的系统要求在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="4cd71-131">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="4cd71-132">边缘服务器环境要求在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="4cd71-132">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="4cd71-133">在业务服务器 2015年的 Skype 的边缘服务器方案</span><span class="sxs-lookup"><span data-stu-id="4cd71-133">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

