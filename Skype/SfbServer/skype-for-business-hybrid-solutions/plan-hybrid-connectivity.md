---
title: 规划 Skype for Business Server 与 Skype for Business Online 之间的混合连接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
description: 摘要： 请阅读本主题，以了解如何规划业务服务器的 Skype 和 Skype 的在线业务之间的混合连接。 设置混合连接是部署多种 Skype for Business 混合解决方案的第一步。
ms.openlocfilehash: 86478b373ccc9c39d1a79668ca13487305319cb8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a><span data-ttu-id="2f6d5-104">规划 Skype for Business Server 与 Skype for Business Online 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="2f6d5-104">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>
 
<span data-ttu-id="2f6d5-105">**摘要：**阅读本主题可了解如何规划 Skype for Business Server 与 Skype for Business Online 之间的混合连接。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-105">**Summary:** Read this topic to learn how to plan hybrid connectivity between Skype for Business Server and Skype for Business Online.</span></span> <span data-ttu-id="2f6d5-106">设置混合连接是部署多种 Skype for Business 混合解决方案的第一步。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-106">Setting up hybrid connectivity is the first step in deploying many Skype for Business hybrid solutions.</span></span>
  
<span data-ttu-id="2f6d5-107">本主题简要介绍，并介绍了基础结构和系统要求您将需要配置之间现有的混合连接内部 Skype 业务服务器部署--与您在部署中创建的用户Active Directory — — 和 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-107">This topic provides an overview, and describes the infrastructure and system requirements you'll need to configure hybrid connectivity between your existing on-premises Skype for Business Server deployment—with users who were created in your on-premises Active Directory—and Skype for Business Online.</span></span> 
  
<span data-ttu-id="2f6d5-108">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-108">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="2f6d5-109">概述</span><span class="sxs-lookup"><span data-stu-id="2f6d5-109">Overview</span></span>](plan-hybrid-connectivity.md#BKMK_Overview)
    
- [<span data-ttu-id="2f6d5-110">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="2f6d5-110">Infrastructure requirements</span></span>](plan-hybrid-connectivity.md#BKMK_Infrastructure)
    
- [<span data-ttu-id="2f6d5-111">多林支持</span><span class="sxs-lookup"><span data-stu-id="2f6d5-111">Multi-forest support</span></span>](plan-hybrid-connectivity.md#BKMK_MultiForest)
    
- [<span data-ttu-id="2f6d5-112">交换共存</span><span class="sxs-lookup"><span data-stu-id="2f6d5-112">Exchange co-existence</span></span>](plan-hybrid-connectivity.md#BKMK_Exchange)
    
- [<span data-ttu-id="2f6d5-113">管理员凭据</span><span class="sxs-lookup"><span data-stu-id="2f6d5-113">Administrator credentials</span></span>](plan-hybrid-connectivity.md#BKMK_Credentials)
    
- [<span data-ttu-id="2f6d5-114">Skype 业务在线 PowerShell 的</span><span class="sxs-lookup"><span data-stu-id="2f6d5-114">Skype for Business Online PowerShell</span></span>](plan-hybrid-connectivity.md#BKMK_PowerShell)
    
- [<span data-ttu-id="2f6d5-115">Skype 业务客户端支持</span><span class="sxs-lookup"><span data-stu-id="2f6d5-115">Skype for Business client support</span></span>](plan-hybrid-connectivity.md#BKMK_ClientSupport)
    
- [<span data-ttu-id="2f6d5-116">拓扑结构要求</span><span class="sxs-lookup"><span data-stu-id="2f6d5-116">Topology requirements</span></span>](plan-hybrid-connectivity.md#BKMK_Topology)
    
- [<span data-ttu-id="2f6d5-117">联盟允许/阻止列表的要求</span><span class="sxs-lookup"><span data-stu-id="2f6d5-117">Federation Allowed/Blocked Lists requirements</span></span>](plan-hybrid-connectivity.md#BKMK_Federation)
    
- [<span data-ttu-id="2f6d5-118">DNS 设置</span><span class="sxs-lookup"><span data-stu-id="2f6d5-118">DNS settings</span></span>](plan-hybrid-connectivity.md#BKMK_DNS)
    
- [<span data-ttu-id="2f6d5-119">防火墙注意事项</span><span class="sxs-lookup"><span data-stu-id="2f6d5-119">Firewall considerations</span></span>](plan-hybrid-connectivity.md#BKMK_Firewall)
    
- [<span data-ttu-id="2f6d5-120">协议和端口要求</span><span class="sxs-lookup"><span data-stu-id="2f6d5-120">Port and protocol requirements</span></span>](plan-hybrid-connectivity.md#BKMK_Ports)
    
- [<span data-ttu-id="2f6d5-121">用户帐户和数据</span><span class="sxs-lookup"><span data-stu-id="2f6d5-121">User accounts and data</span></span>](plan-hybrid-connectivity.md#BKMK_UserAccounts)
    
- [<span data-ttu-id="2f6d5-122">用户策略和功能</span><span class="sxs-lookup"><span data-stu-id="2f6d5-122">User policies and features</span></span>](plan-hybrid-connectivity.md#BKMK_UserPolicies)
    
<span data-ttu-id="2f6d5-123">在阅读此主题并准备部署信息，请参阅[部署混合业务服务器和 Skype 的在线业务 Skype 之间的连接](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-123">After you have read this topic and are ready to deploy, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span> <span data-ttu-id="2f6d5-124">部署主题提供了设置本地部署与 Skype for Business Online 之间的混合连接的分步指导。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-124">The deployment topics provide step-by-step guidance for setting up hybrid connectivity between your on-premises deployment and Skype for Business Online.</span></span>
  
<span data-ttu-id="2f6d5-125">（有关配置 Lync Server 2013 或混合的 Lync Server 2010 部署信息，请参见[Lync Server 2013 混合](https://go.microsoft.com/fwlink/p/?LinkId=617360)）。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-125">(For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)</span></span>
  
## <a name="overview"></a><span data-ttu-id="2f6d5-126">概述</span><span class="sxs-lookup"><span data-stu-id="2f6d5-126">Overview</span></span>
<span data-ttu-id="2f6d5-127"><a name="BKMK_Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-127"></span></span>

<span data-ttu-id="2f6d5-128">混合解决方案使你可以根据自己的计划和业务需求将用户迁移到云。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-128">Hybrid solutions enable you to move your users to the cloud based on your schedule and business need.</span></span> <span data-ttu-id="2f6d5-129">本主题重点介绍 Skype for Business Server 本地部署与 Skype for Business Online 之间的混合连接。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-129">This topic focuses on hybrid connectivity between an on-premises deployment of Skype for Business Server and Skype for Business Online.</span></span> <span data-ttu-id="2f6d5-130">通过此连接，你可以将一些用户在本地托管，一些用户在线托管。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-130">This connectivity allows you to have some users homed on-premises and some users homed online.</span></span>
  
<span data-ttu-id="2f6d5-131">这种类型的部署有时也称为"拆分域"— — 意味着用户的域，如 contoso.com，都分为使用 Skype 业务服务器上部署和 Skype 的在线业务，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-131">This type of deployment is sometimes referred to as "split domain"—meaning users of a domain, such as contoso.com, are split between using Skype for Business Server on premises and Skype for Business Online as follows:</span></span>
  
- <span data-ttu-id="2f6d5-132">在本地托管的用户与本地 Skype for Business 服务器交互</span><span class="sxs-lookup"><span data-stu-id="2f6d5-132">Users who are homed on premises interact with on premises Skype for Business servers</span></span>
    
- <span data-ttu-id="2f6d5-133">在线托管的用户与 Skype for Business 在线服务交互</span><span class="sxs-lookup"><span data-stu-id="2f6d5-133">Users who are homed online interact with Skype for Business online services</span></span>
    
- <span data-ttu-id="2f6d5-134">两个环境的用户可以使用即时消息或通过参与电话会议和 VoIP 通话等方式相互协作</span><span class="sxs-lookup"><span data-stu-id="2f6d5-134">Users from both environments can collaborate with each other by using Instant Messaging, participating in conference calls, VoIP calls, and so on</span></span>
    
- <span data-ttu-id="2f6d5-135">Azure Active Directory Connect 用于将你的本地目录与 Office 365 同步</span><span class="sxs-lookup"><span data-stu-id="2f6d5-135">Azure Active Directory Connect is used to synchronize your on-premises directory with Office 365</span></span>
    
<span data-ttu-id="2f6d5-136">本地 Active Directory 是权威性的，即你必须执行下列操作以确保本地和在线用户可以相互发现：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-136">The on-premises Active Directory is authoritative, which means that you must do the following to ensure that on-premises and online users are discoverable to one another:</span></span>
  
- <span data-ttu-id="2f6d5-137">应首先创建在内部部署 Active Directory 中，然后到 Azure AD 同步所有用户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-137">All users should be created in the on-premises Active Directory first, and then synchronized to Azure AD.</span></span> 
    
- <span data-ttu-id="2f6d5-138">如果你的用户托管在本地 Skype for Business 中，你需要为本地 Skype for Business 启用这些用户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-138">If your users are homed on premises for Skype for Business, then you need to enable them for Skype for Business on premises.</span></span>
    
- <span data-ttu-id="2f6d5-139">如果你的用户在本地托管，但想要利用某些在线功能（例如 Skype 会议广播），你需要向其分配 Skype for Business Online 套餐 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-139">If your users are homed on premises, but want to take advantage of some online features, such as Skype Meeting Broadcast, you need to assign them a Skype for Business Online plan 2 license.</span></span>
    
- <span data-ttu-id="2f6d5-140">如果你的用户在 Skype for Business Online 中托管，则其帐户同步到 Azure AD 之后，你将需要为其分配 Skype for Business Online 套餐 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-140">If your users are homed in Skype for Business Online, once their account is synchronized to Azure AD, you need to assign them a Skype for Business Online plan 2 license.</span></span> 
    
- <span data-ttu-id="2f6d5-141">为 Skype for Business Online 用户分配许可证后，你需要为 Skype for Business 或本地 Enterprise Voice 启用这些用户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-141">After Skype for Business Online users are assigned a license, you need to enable them for Skype for Business or for Enterprise Voice on premises.</span></span> <span data-ttu-id="2f6d5-142">有关详细信息，请参阅[启用用于内部部署的企业语音用户](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-142">For more information, see [Enable the users for Enterprise Voice on premises](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md).</span></span> <span data-ttu-id="2f6d5-143">混合语音要求的详细信息，请参阅[计划内部 Skype 业务服务器中的 PSTN 连接与 Office 365 中的电话系统](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-143">For more information about hybrid voice requirements, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
<span data-ttu-id="2f6d5-144">在下面的部分，你将了解有关 Active Directory 配置的更多信息。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-144">You'll learn more about Active Directory configuration in the sections that follow.</span></span> <span data-ttu-id="2f6d5-145">但首先是下图以及众多混合连接主题中使用的术语和缩略词概述：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-145">But first, an overview of the terminology and acronyms used in the diagrams below, and in many of the hybrid connectivity topics:</span></span>
  
- <span data-ttu-id="2f6d5-146">PSTN - 公用电话交换网</span><span class="sxs-lookup"><span data-stu-id="2f6d5-146">PSTN - Public Switched Telephone Network</span></span>
    
- <span data-ttu-id="2f6d5-147">PBX - 专用交换机电话系统</span><span class="sxs-lookup"><span data-stu-id="2f6d5-147">PBX - Private Branch Exchange phone system</span></span>
    
- <span data-ttu-id="2f6d5-148">电话系统 - Microsoft 的云 PBX 电话系统产品</span><span class="sxs-lookup"><span data-stu-id="2f6d5-148">Phone System - Microsoft's Cloud PBX phone system offering</span></span>
    
- <span data-ttu-id="2f6d5-149">干线的电话线路连接到 PSTN 的 Pbx — 干线可能使用会话初始协议 (SIP) — — 语音通信 (Voip) — — 或较早的时间时分多路复用技术 (TDM) 技术</span><span class="sxs-lookup"><span data-stu-id="2f6d5-149">Trunk - Telephony line that connects PBXs to the PSTN—A trunk might use Session Initiation Protocol (SIP)—A Voice over Internet Protocol (VoIP)—or the older Time-Division Multiplexing (TDM) technology</span></span> 
    
- <span data-ttu-id="2f6d5-150">SBC - 会话边界控制器 - 在电话网络中充当防火墙和路由器的设备。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-150">SBC - Session Border Controller - Device that serves as a firewall and router in telephony networks.</span></span> <span data-ttu-id="2f6d5-151">例如，提供安全性、连接性、互操作性和服务质量。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-151">For example, provides security, connectivity, interoperability, and Quality of Services.</span></span> 
    
- <span data-ttu-id="2f6d5-152">PSTN 网关 - 在电话网络中充当路由器的设备，能够执行 SBC 可以执行的大部分操作，安全和 NAT 遍历除外。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-152">PSTN gateway - A device that serves as a router in telephony networks, capable of doing most of what an SBC can do except security and NAT traversal.</span></span>
    
<span data-ttu-id="2f6d5-153">下图显示了 Skype 业务"拆分域"混合配置。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-153">The following diagram shows a Skype for Business "split domain" hybrid configuration.</span></span> <span data-ttu-id="2f6d5-154">用户 A 和 B 在线托管，但可以被本地用户发现；用户 C 和 D 在本地托管，但可以被在线用户发现。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-154">Users A and B are homed online but are discoverable by on-premises users; users C and D are homed on premises, but are discoverable by online users.</span></span>
  
![SfB 混合连接 - 拆分域](../media/c4fc9311-1930-4a58-877f-3c1524dfab5c.png)
  
<span data-ttu-id="2f6d5-156">你可能也已对“混合语音”一词很熟悉—它是指向在云中托管的用户提供功能的本地语音主干。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-156">You might also be familiar with the term "hybrid voice"—which refers to on-premises voice trunks that provide functionality to users homed in the cloud.</span></span> <span data-ttu-id="2f6d5-157">通过混合语音，可以在保留本地语音配置的同时迁移到云。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-157">Hybrid voice enables migration to the cloud while preserving on-premises voice configuration.</span></span> <span data-ttu-id="2f6d5-158">如果你已具有 Skype for Business Server 部署，启用混合语音的第一步是配置拆分域环境。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-158">If you already have a Skype for Business Server deployment, the first step to enable hybrid voice is to configure a split domain environment.</span></span> 
  
<span data-ttu-id="2f6d5-159">例如，假定您的公司有大型移动字段需要最少的 PBX 的组织提供支持的声音，但广泛使用的智能手机。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-159">For example, assume your company has a large mobile field support organization that requires minimal PBX voice, but extensive smart phone use.</span></span> <span data-ttu-id="2f6d5-160">你可以选择将这些用户迁移到云，以利用 Microsoft 的 Office 365 电话系统（云 PBX）。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-160">You might choose to move these users to the cloud to take advantage of Microsoft's Phone System in Office 365 (Cloud PBX).</span></span> <span data-ttu-id="2f6d5-161">如果您的公司也有内部部署大型呼叫中心作为内部 PBX 的一部分需要高级、 复杂的联系中心软件，您可以选择在部署上保留这些用户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-161">If your company also has a large on-premises call center that requires advanced, complex contact center software as part of your on-premises PBX, you might choose to leave these users on premises.</span></span> <span data-ttu-id="2f6d5-162">在线托管和在本地托管的用户均具有通过本地部署的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-162">Users homed online and on premises both have PSTN connectivity through your on-premises deployment.</span></span>
  
<span data-ttu-id="2f6d5-163">下图显示了 Skype for Business 混合语音部署：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-163">The following diagram shows a Skype for Business hybrid voice deployment:</span></span>
  
![SfB 拆分域和云 PBX](../media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)
  
<span data-ttu-id="2f6d5-165">有关设置混合语音解决方案与您 Skype 业务服务器部署的详细信息，请参阅[计划内部 Skype 业务服务器中的 PSTN 连接与 Office 365 中的电话系统](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-165">For more information about setting up a hybrid voice solution with your Skype for Business Server deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span> 
  
<span data-ttu-id="2f6d5-166">您还可以配置与的集成的混合部署内部交换和 SharePoint，或与 Microsoft Office 365 的应用程序，包括 Exchange 联机和 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-166">You can also configure hybrid deployments for integration with on-premises Exchange and SharePoint, or with Microsoft Office 365 applications, including Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="2f6d5-167">你还可以使用云连接器版本配置不需要完整 Skype for Business Server 部署的混合语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-167">You can also configure a hybrid voice solution that does not require a full Skype for Business Server deployment by using Cloud Connector Edition.</span></span> <span data-ttu-id="2f6d5-168">有关所有 Skype 业务混合解决方案和规划迁移到云环境的详细信息，请参阅[Skype 业务混合解决方案](skype-for-business-hybrid-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-168">For more information about all Skype for Business hybrid solutions and planning your move to the cloud, see [Skype for Business hybrid solutions](skype-for-business-hybrid-solutions.md).</span></span>
  
## <a name="infrastructure-requirements"></a><span data-ttu-id="2f6d5-169">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="2f6d5-169">Infrastructure requirements</span></span>
<span data-ttu-id="2f6d5-170"><a name="BKMK_Infrastructure"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-170"></span></span>

<span data-ttu-id="2f6d5-171">要实施和部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接，必须在环境中进行以下配置：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-171">To implement and deploy hybrid connectivity between Skype for Business Server and Skype for Business Online, you must configure the following in your environment:</span></span>
  
- <span data-ttu-id="2f6d5-172">一个内部的 Skype 业务服务器或部署在受支持的拓扑的 Lync 服务器的部署。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-172">A single on-premises deployment of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="2f6d5-173">请参阅本主题中的[拓扑要求](plan-hybrid-connectivity.md#BKMK_Topology)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-173">See [Topology requirements](plan-hybrid-connectivity.md#BKMK_Topology) in this topic.</span></span>
    
- <span data-ttu-id="2f6d5-174">与 Skype 业务在线启用 Microsoft Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-174">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2f6d5-175">只能将混合配置的单个租户与你的本地部署结合使用。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-175">You can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span> 
  
- <span data-ttu-id="2f6d5-176">Skype 业务服务器 2015年管理工具。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-176">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="2f6d5-177">（如果您正在使用 Lync Server 2013 或 Lync Server 2010 中，可以使用 Lync Server 2013 管理工具。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-177">(If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="2f6d5-178">有关详细信息，请参阅[Lync Server 2013 混合](https://go.microsoft.com/fwlink/p/?LinkId=617360)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-178">For more information, see [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)</span></span>
    
- <span data-ttu-id="2f6d5-179">Azure Active Directory Connect 用于将你的本地目录与 Office 365 同步。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-179">Azure Active Directory Connect to synchronize your on-premises directory with Office 365.</span></span> <span data-ttu-id="2f6d5-180">有关详细信息，请参阅[使用 Azure 活动目录连接 Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-180">For more information, see [Connect Active Directory with Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).</span></span>
    
    <span data-ttu-id="2f6d5-181">若要支持 Office 365 的单一登录，使用户能使用在本地所用的同一登录凭据，可以使用 Azure Active Directory (AAD) Connect 的密码同步功能。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-181">To support Single Sign-on with Office 365 so that users can use the same login credentials as they do for on premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="2f6d5-182">还可以使用 Active Directory 联合身份验证服务 (AD FS) 来进行 Office 365 单一登录。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-182">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span> 
    
- <span data-ttu-id="2f6d5-183">已在你的本地 Skype for Business 部署与 Office 365 租户之间启用联盟。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-183">Enabled federation between your on-premises Skype for Business deployment and your Office 365 tenant.</span></span> <span data-ttu-id="2f6d5-184">联合身份验证允许用户在内部部署的 Office 365 提供组织中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-184">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="2f6d5-185">有关详细信息，请参阅[配置联合身份验证与 Skype 的在线业务](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-185">For more information, see [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="2f6d5-186">已启用共享会话初始协议 (SIP) 地址空间。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-186">Enabled shared Session Initiation Protocol (SIP) address space.</span></span> <span data-ttu-id="2f6d5-187">SIP 地址是网络上每个用户的唯一标识符，类似于电话号码或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-187">A SIP address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="2f6d5-188">尝试将用户移动从内部到 Skype 的在线业务之前，您需要配置您的 Office 365 租户在内部部署共享共享会话启动协议 (SIP) 地址空间。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-188">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="2f6d5-189">有关详细信息，请参阅[配置联合身份验证与 Skype 的在线业务](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-189">For more information, see [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).</span></span>
    
## <a name="multi-forest-support"></a><span data-ttu-id="2f6d5-190">多林支持</span><span class="sxs-lookup"><span data-stu-id="2f6d5-190">Multi-forest support</span></span>
<span data-ttu-id="2f6d5-191"><a name="BKMK_MultiForest"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-191"></span></span>

<span data-ttu-id="2f6d5-192">如果满足下列要求，用户可以访问其他林中的 Skype for Business 功能：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-192">Users can access Skype for Business functionality in another forest if the following requirements are met:</span></span>
  
- <span data-ttu-id="2f6d5-193">用户已正确同步到托管 Skype for Business 的林中：在混合配置中，这意味着用户必须作为已禁用的用户对象同步。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-193">Users are properly synchronized into the forest that hosts Skype for Business: In hybrid configurations, this means that users must be synchronized as disabled user objects.</span></span>
    
- <span data-ttu-id="2f6d5-194">托管 Skype for Business 的林必须信任包含用户的林。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-194">The forest hosting Skype for Business must trust the forest containing the users.</span></span>
    
<span data-ttu-id="2f6d5-195">混合多目录林方案的详细信息，请参阅[配置多目录林环境中的混合业务的 Skype](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-195">For details on multi-forest hybrid scenarios, see [Configure a multi-forest environment for hybrid Skype for Business](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).</span></span>
  
## <a name="exchange-co-existence"></a><span data-ttu-id="2f6d5-196">Exchange 共存</span><span class="sxs-lookup"><span data-stu-id="2f6d5-196">Exchange co-existence</span></span>
<span data-ttu-id="2f6d5-197"><a name="BKMK_Exchange"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-197"></span></span>

<span data-ttu-id="2f6d5-198">要支持与 Exchange 共存，请记住下列事项：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-198">To support co-existence with Exchange, keep the following in mind:</span></span>
  
- <span data-ttu-id="2f6d5-199">最佳做法是在移动业务的用户的 Skype 家庭之前将用户的邮箱移动到 Exchange 联机。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-199">The best practice is to move the user's mailbox to Exchange Online before moving the user's Skype for Business home.</span></span>
    
- <span data-ttu-id="2f6d5-200">支持具有本地 Exchange 邮箱的用户，但存在下列已知限制：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-200">Users with Exchange mailboxes on premises are supported with following known limitations:</span></span>
    
  - <span data-ttu-id="2f6d5-201">客户端登录：在 SfB 客户端登录过程中，用户可能需要登录两次</span><span class="sxs-lookup"><span data-stu-id="2f6d5-201">Client sign on: Users may need to sign on twice during SfB client sign on</span></span>
    
  - <span data-ttu-id="2f6d5-202">服务器端对话历史记录，存档、 统一联系人存储库、 HighRes 照片需要交换 2013年或更高版本，并且您必须启用 OAuth 服务器到服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-202">Server side conversation history, Archiving, Unified Contact Store, HighRes Photo requires Exchange 2013 or later, and you must enable OAuth Server to Server communication.</span></span> <span data-ttu-id="2f6d5-203">有关详细信息，请参阅[管理服务器的身份验证 (OAuth) 和业务服务器 2015年的 Skype 的合作伙伴应用程序](https://technet.microsoft.com/en-us/library/jj204817.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-203">For more information, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).</span></span>
    
<span data-ttu-id="2f6d5-204">有关 Exchange Server 与共存的详细信息，包括支持条件和限制的各种组合的内部部署和联机，请参阅[计划集成 Skype 业务和交换](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)中的[支持的功能](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-204">For details on co-existence with Exchange Server, including support criteria and limitations in various combinations of on-premises and online, see [Feature support](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).</span></span>
  
## <a name="administrator-credentials"></a><span data-ttu-id="2f6d5-205">管理员凭据</span><span class="sxs-lookup"><span data-stu-id="2f6d5-205">Administrator credentials</span></span>
<span data-ttu-id="2f6d5-206"><a name="BKMK_Credentials"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-206"></span></span>

<span data-ttu-id="2f6d5-207">当询问您要提供管理员凭据时，使用的用户名和密码管理员帐户为 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-207">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="2f6d5-208">您还将使用这些凭据配置时 Azure Active Directory 联合身份验证、 目录同步、 单一登录，和移动用户 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-208">You will also use these credentials when you configure Azure Active Directory for federation, directory synchronization, single sign-on, and moving users to Skype for Business Online.</span></span>
  
## <a name="skype-for-business-online-powershell"></a><span data-ttu-id="2f6d5-209">Skype for Business Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f6d5-209">Skype for Business Online PowerShell</span></span>
<span data-ttu-id="2f6d5-210"><a name="BKMK_PowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-210"></span></span>

<span data-ttu-id="2f6d5-211">管理员现在可以使用 Windows PowerShell 管理 Skype 的在线业务和其 Skype 的在线业务的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-211">Administrators now have the ability to use Windows PowerShell to manage Skype for Business Online and their Skype for Business Online user accounts.</span></span> <span data-ttu-id="2f6d5-212">若要执行此操作，您必须首先下载并安装 Skype 业务在线连接器模块，从 Microsoft 下载中心获取。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-212">To do this, you must first download and install the Skype for Business Online Connector Module from the Microsoft Download Center.</span></span> <span data-ttu-id="2f6d5-213">有关下载的详细信息，安装和使用 Skype 业务在线连接器模块，并使用 Windows PowerShell 管理 Skype 的在线业务的详细信息，请参阅[使用 Windows PowerShell 管理业务的 Skype联机](https://technet.microsoft.com/library/dn362831.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-213">For more information on downloading, installing, and using the Skype for Business Online Connector Module, and for detailed information on using Windows PowerShell to manage Skype for Business Online, see [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/library/dn362831.aspx).</span></span> 
  
## <a name="skype-for-business-client-support"></a><span data-ttu-id="2f6d5-214">Skype for Business 客户端支持</span><span class="sxs-lookup"><span data-stu-id="2f6d5-214">Skype for Business client support</span></span>
<span data-ttu-id="2f6d5-215"><a name="BKMK_ClientSupport"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-215"></span></span>

<span data-ttu-id="2f6d5-216">客户端中支持的功能与本地和联机环境中提供的功能一样，存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-216">There are some differences in the features supported in clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="2f6d5-217">下列客户端支持 Skype 的在线业务中混合部署：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-217">The following clients are supported with Skype for Business Online in a hybrid deployment:</span></span>
  
- <span data-ttu-id="2f6d5-218">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2f6d5-218">Skype for Business</span></span>
    
- <span data-ttu-id="2f6d5-219">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2f6d5-219">Lync 2013</span></span>
    
- <span data-ttu-id="2f6d5-220">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2f6d5-220">Lync 2010</span></span>
    
- <span data-ttu-id="2f6d5-221">Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="2f6d5-221">Lync Windows Store app</span></span>
    
- <span data-ttu-id="2f6d5-222">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="2f6d5-222">Lync Web App</span></span>
    
- <span data-ttu-id="2f6d5-223">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="2f6d5-223">Lync Mobile</span></span>
    
- <span data-ttu-id="2f6d5-224">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="2f6d5-224">Lync for Mac 2011</span></span>
    
- <span data-ttu-id="2f6d5-225">Lync 空间系统和 Skype 业务空间系统</span><span class="sxs-lookup"><span data-stu-id="2f6d5-225">Lync Room System and Skype for Business Room System</span></span>
    
- <span data-ttu-id="2f6d5-226">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="2f6d5-226">Lync Basic 2013</span></span>
    
- <span data-ttu-id="2f6d5-227">Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="2f6d5-227">Microsoft Surface Hub</span></span>
    
<span data-ttu-id="2f6d5-228">在决定要给家庭用户组织中之前，应检查[业务 Skype 的桌面客户端功能比较](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)确定的 Skype 业务服务器的各种配置的客户端支持。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-228">Before you decide where you want to home users in your organization, you should review the [Desktop client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) to determine the client support for the various configurations of Skype for Business Server.</span></span> <span data-ttu-id="2f6d5-229">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-229">See also:</span></span>
  
- [<span data-ttu-id="2f6d5-230">规划客户端和设备</span><span class="sxs-lookup"><span data-stu-id="2f6d5-230">Plan for clients and devices</span></span>](../plan-your-deployment/clients-and-devices/clients-and-devices.md)
    
- [<span data-ttu-id="2f6d5-231">Skype 业务的移动客户端功能比较</span><span class="sxs-lookup"><span data-stu-id="2f6d5-231">Mobile client feature comparison for Skype for Business</span></span>](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)
    
## <a name="topology-requirements"></a><span data-ttu-id="2f6d5-232">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="2f6d5-232">Topology requirements</span></span>
<span data-ttu-id="2f6d5-233"><a name="BKMK_Topology"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-233"></span></span>

<span data-ttu-id="2f6d5-234">若要配置为混合部署与 Skype 的在线业务时，需要有一个受支持的拓扑：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-234">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>
  
- <span data-ttu-id="2f6d5-235">与所有服务器运行业务服务器 2015 Skype 业务服务器 2015年部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-235">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="2f6d5-236">与所有服务器运行 Lync Server 2013 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-236">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>
    
    <span data-ttu-id="2f6d5-237">对于混合语音连接，指定为联盟边缘的边缘服务器必须为 Skype for Business 2015，边缘也需要 Skype for Business Server 后端。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-237">For hybrid voice connectivity, the Edge Server that is designated as Federation Edge must be Skype for Business 2015, the Edge also requires a Skype for Business Server backend.</span></span> <span data-ttu-id="2f6d5-238">你可能有一个池中没有任何用户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-238">You might have a pool with no users on it.</span></span> 
    
- <span data-ttu-id="2f6d5-239">通过最新的累积更新运行 Lync Server 2010 中的所有服务器使用 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-239">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
  - <span data-ttu-id="2f6d5-240">联合身份验证边缘服务器和从联盟边缘服务器的下一个跃点服务器必须运行 Lync Server 2010 通过最新的累积更新。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-240">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
  - <span data-ttu-id="2f6d5-241">Skype 业务服务器 2015年或 Lync Server 2013 管理工具必须安装至少一台服务器或管理工作站上。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-241">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>
    
- <span data-ttu-id="2f6d5-242">一个混合的 Lync Server 2013 和 Skype 运行业务服务器 2015 Skype 的至少一个站点中的下列服务器角色具有的业务服务器 2015年部署：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-242">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
  - <span data-ttu-id="2f6d5-243">至少一个企业版池或 Standard Edition 服务器 </span><span class="sxs-lookup"><span data-stu-id="2f6d5-243">At least one Enterprise Pool or Standard Edition server</span></span> 
    
  - <span data-ttu-id="2f6d5-244">与 SIP 联盟关联的控制器池（如果存在）</span><span class="sxs-lookup"><span data-stu-id="2f6d5-244">The Director Pool associated with SIP federation, if it exists</span></span>
    
  - <span data-ttu-id="2f6d5-245">与 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="2f6d5-245">The Edge Pool associated with SIP federation</span></span>
    
- <span data-ttu-id="2f6d5-246">一个混合的 Lync Server 2010 和运行业务服务器 2015 Skype 的至少一个站点中的下列服务器角色具有的业务服务器 2015年部署 Skype:</span><span class="sxs-lookup"><span data-stu-id="2f6d5-246">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
  - <span data-ttu-id="2f6d5-247">至少一个企业版池或 Standard Edition 服务器 </span><span class="sxs-lookup"><span data-stu-id="2f6d5-247">At least one Enterprise Pool or Standard Edition server</span></span> 
    
  - <span data-ttu-id="2f6d5-248">与 SIP 联盟关联的控制器池（如果存在）</span><span class="sxs-lookup"><span data-stu-id="2f6d5-248">The Director Pool associated with SIP federation, if it exists</span></span>
    
  - <span data-ttu-id="2f6d5-249">与站点的 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="2f6d5-249">The Edge Pool associated with SIP federation for the Site</span></span>
    
- <span data-ttu-id="2f6d5-250">混合的 Lync Server 2010 和 Lync Server 2013 部署与运行 Lync Server 2013 的至少一个站点中的下列服务器角色：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-250">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
  - <span data-ttu-id="2f6d5-251">站点中至少一个企业版池或 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="2f6d5-251">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
  - <span data-ttu-id="2f6d5-252">与 SIP 联盟关联的控制器池（如果站点中存在）</span><span class="sxs-lookup"><span data-stu-id="2f6d5-252">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
  - <span data-ttu-id="2f6d5-253">与站点的 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="2f6d5-253">The Edge Pool associated with SIP federation for the site</span></span>
    
## <a name="federation-allowedblocked-lists-requirements"></a><span data-ttu-id="2f6d5-254">联盟允许/阻止列表的要求</span><span class="sxs-lookup"><span data-stu-id="2f6d5-254">Federation Allowed/Blocked Lists requirements</span></span>
<span data-ttu-id="2f6d5-255"><a name="BKMK_Federation"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-255"></span></span>

<span data-ttu-id="2f6d5-256">允许域列表包括已配置合作伙伴“边缘”完全限定域名 (FQDN) 的域。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-256">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="2f6d5-257">这些有时被称为允许的合作伙伴服务器 ordirect 联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-257">These are sometimes referred to as allowed partner servers ordirect federation partners.</span></span> <span data-ttu-id="2f6d5-258">您应该熟悉开放联盟和关闭的联盟，称为伙伴发现 andallowed 合作伙伴域列表，分别在内部部署之间的差异。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-258">You should be familiar with the difference between Open Federation and Closed Federation, referred to as partner discovery andallowed partner domain list, respectively, in on-premises deployments.</span></span>
  
<span data-ttu-id="2f6d5-259">必须满足以下要求才能成功配置混合部署：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-259">The following requirements must be met to successfully configure a hybrid deployment:</span></span>
  
- <span data-ttu-id="2f6d5-p125">为您的本地部署和您的 Office 365 租户配置的域匹配必须相同。如果在本地部署中启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。如果未启用合作伙伴发现，则必须为您的联机租户配置封闭联盟。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-p125">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>
    
- <span data-ttu-id="2f6d5-263">本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-263">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>
    
- <span data-ttu-id="2f6d5-264">本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-264">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>
    
- <span data-ttu-id="2f6d5-265">必须为在线组织，通过 Skype 业务在线控制面板配置外部通信启用联盟。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-265">Federation must be enabled for the external communications for the online tenant, which is configured by using the Skype for Business Online Control Panel.</span></span>
    
## <a name="dns-settings"></a><span data-ttu-id="2f6d5-266">DNS 设置</span><span class="sxs-lookup"><span data-stu-id="2f6d5-266">DNS settings</span></span>
<span data-ttu-id="2f6d5-267"><a name="BKMK_DNS"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-267"></span></span>

<span data-ttu-id="2f6d5-268">创建混合部署 DNS 记录时，所有 Skype 业务外部 DNS 记录应都指向内部部署基础结构。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-268">When creating DNS records for hybrid deployments, all Skype for Business external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="2f6d5-269">有关所需的 DNS 记录的详细信息，请参阅[DNS 业务服务器 2015年的 Skype 的要求](../plan-your-deployment/network-requirements/dns.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-269">For details on required DNS records, please refer to [DNS requirements for Skype for Business Server 2015](../plan-your-deployment/network-requirements/dns.md).</span></span>
  
<span data-ttu-id="2f6d5-270">此外，您还需要确保下表中所述的 DNS 解析在您的本地部署中正常运行：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-270">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="2f6d5-271">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2f6d5-271">DNS record</span></span>  <br/> |<span data-ttu-id="2f6d5-272">解析者</span><span class="sxs-lookup"><span data-stu-id="2f6d5-272">Resolvable by</span></span>  <br/> |<span data-ttu-id="2f6d5-273">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="2f6d5-273">DNS requirement</span></span>  <br/> |
|<span data-ttu-id="2f6d5-274">_Sipfederationtls._tcp 的 DNS SRV 记录。\<sipdomain.com\>为所有支持的 SIP 域解析为访问边缘外部 IP(s)</span><span class="sxs-lookup"><span data-stu-id="2f6d5-274">DNS SRV record for _sipfederationtls._tcp.\<sipdomain.com\> for all supported SIP domains resolving to Access Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="2f6d5-275">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="2f6d5-275">Edge server(s)</span></span>  <br/> |<span data-ttu-id="2f6d5-p127">在混合配置中启用联盟通信。边缘服务器需要知道在什么位置为 SIP 域路由分布在本地设备和在线设备上的联盟流量。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-p127">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span>  <br/> <span data-ttu-id="2f6d5-278">必须使用用户名与 SRV 记录中的域之间的严格 DNS 名称匹配。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-278">Must use strict DNS name matching between the domain in the user name and the SRV record.</span></span>  <br/> |
|<span data-ttu-id="2f6d5-279">边缘 Web 会议服务 FQDN 的 DNS A 记录，例如解析为 Web 会议边缘外部 IP 的 webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f6d5-279">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="2f6d5-280">公司内部网络连接的用户的计算机</span><span class="sxs-lookup"><span data-stu-id="2f6d5-280">Internal corporate network connected users' computers</span></span>  <br/> |<span data-ttu-id="2f6d5-p128">让在线用户能够在本地托管会议中演示或查看内容。内容包括 PowerPoint 文件、白板、轮询和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-p128">Enable online users to present or view content in on-premises hosted meetings. Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span>  <br/> |
   
<span data-ttu-id="2f6d5-283">根据 DNS 在您的组织中如何配置，您可能需要将这些记录添加到内部托管 DNS 区域，以便相应的 SIP 域能够提供对这些记录的内部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-283">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>
  
## <a name="firewall-considerations"></a><span data-ttu-id="2f6d5-284">防火墙注意事项</span><span class="sxs-lookup"><span data-stu-id="2f6d5-284">Firewall considerations</span></span>
<span data-ttu-id="2f6d5-285"><a name="BKMK_Firewall"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-285"></span></span>

<span data-ttu-id="2f6d5-p129">您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-p129">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>
  
<span data-ttu-id="2f6d5-288">根据 Microsoft Online Services 数据中心的位置，您还必须配置您的网络防火墙设备以接受连接基于通配符域名 (例如，所有流量从\*。 outlook.com)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-288">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="2f6d5-289">如果您的组织的防火墙不支持通配符名称配置，您需要手动确定您想要允许的 IP 地址范围和指定的端口。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-289">If your organization's firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>
  
<span data-ttu-id="2f6d5-290">有关详细信息，请参阅[Office 365 的 Url 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?LinkId=252942)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-290">For more information, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?LinkId=252942).</span></span>
  
## <a name="port-and-protocol-requirements"></a><span data-ttu-id="2f6d5-291">端口和协议要求</span><span class="sxs-lookup"><span data-stu-id="2f6d5-291">Port and protocol requirements</span></span>
<span data-ttu-id="2f6d5-292"><a name="BKMK_Ports"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-292"></span></span>

<span data-ttu-id="2f6d5-293">除了内部通信的端口要求，还必须配置以下端口以启用混合连接：</span><span class="sxs-lookup"><span data-stu-id="2f6d5-293">In addition to the port requirements for internal communication, you must also configure the following ports to enable hybrid connectivity:</span></span>
  

|<span data-ttu-id="2f6d5-294">**协议**</span><span class="sxs-lookup"><span data-stu-id="2f6d5-294">**Protocol**</span></span>|<span data-ttu-id="2f6d5-295">**TCP 或 UDP**</span><span class="sxs-lookup"><span data-stu-id="2f6d5-295">**TCP or UDP**</span></span>|<span data-ttu-id="2f6d5-296">**源 IP**</span><span class="sxs-lookup"><span data-stu-id="2f6d5-296">**Source IP**</span></span>|<span data-ttu-id="2f6d5-297">**目标 IP**</span><span class="sxs-lookup"><span data-stu-id="2f6d5-297">**Destination IP**</span></span>|<span data-ttu-id="2f6d5-298">**源端口**</span><span class="sxs-lookup"><span data-stu-id="2f6d5-298">**Source Port**</span></span>|<span data-ttu-id="2f6d5-299">**目标端口**</span><span class="sxs-lookup"><span data-stu-id="2f6d5-299">**Destination Port**</span></span>|<span data-ttu-id="2f6d5-300">**说明**</span><span class="sxs-lookup"><span data-stu-id="2f6d5-300">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f6d5-301">SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2f6d5-301">SIP (MTLS)</span></span>  <br/> |<span data-ttu-id="2f6d5-302">TCP</span><span class="sxs-lookup"><span data-stu-id="2f6d5-302">TCP</span></span>  <br/> |<span data-ttu-id="2f6d5-303">访问边缘</span><span class="sxs-lookup"><span data-stu-id="2f6d5-303">Access Edge</span></span>  <br/> |<span data-ttu-id="2f6d5-304">Office 365</span><span class="sxs-lookup"><span data-stu-id="2f6d5-304">Office 365</span></span>  <br/> |<span data-ttu-id="2f6d5-305">任何</span><span class="sxs-lookup"><span data-stu-id="2f6d5-305">Any</span></span>  <br/> |<span data-ttu-id="2f6d5-306">5061</span><span class="sxs-lookup"><span data-stu-id="2f6d5-306">5061</span></span>  <br/> |<span data-ttu-id="2f6d5-307">信号</span><span class="sxs-lookup"><span data-stu-id="2f6d5-307">Signaling</span></span>  <br/> |
|<span data-ttu-id="2f6d5-308">SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="2f6d5-308">SIP (MTLS)</span></span>  <br/> |<span data-ttu-id="2f6d5-309">TCP</span><span class="sxs-lookup"><span data-stu-id="2f6d5-309">TCP</span></span>  <br/> |<span data-ttu-id="2f6d5-310">Office 365</span><span class="sxs-lookup"><span data-stu-id="2f6d5-310">Office 365</span></span>  <br/> |<span data-ttu-id="2f6d5-311">访问边缘</span><span class="sxs-lookup"><span data-stu-id="2f6d5-311">Access Edge</span></span>  <br/> |<span data-ttu-id="2f6d5-312">任何</span><span class="sxs-lookup"><span data-stu-id="2f6d5-312">Any</span></span>  <br/> |<span data-ttu-id="2f6d5-313">5061</span><span class="sxs-lookup"><span data-stu-id="2f6d5-313">5061</span></span>  <br/> |<span data-ttu-id="2f6d5-314">信号</span><span class="sxs-lookup"><span data-stu-id="2f6d5-314">Signaling</span></span>  <br/> |
|<span data-ttu-id="2f6d5-315">STUN</span><span class="sxs-lookup"><span data-stu-id="2f6d5-315">STUN</span></span>  <br/> |<span data-ttu-id="2f6d5-316">TCP</span><span class="sxs-lookup"><span data-stu-id="2f6d5-316">TCP</span></span>  <br/> |<span data-ttu-id="2f6d5-317">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="2f6d5-317">A/V Edge</span></span>  <br/> |<span data-ttu-id="2f6d5-318">Office 365</span><span class="sxs-lookup"><span data-stu-id="2f6d5-318">Office 365</span></span>  <br/> |<span data-ttu-id="2f6d5-319">50000-59999</span><span class="sxs-lookup"><span data-stu-id="2f6d5-319">50000-59999</span></span>  <br/> |<span data-ttu-id="2f6d5-320">443，50000-59999</span><span class="sxs-lookup"><span data-stu-id="2f6d5-320">443, 50000-59999</span></span>  <br/> |<span data-ttu-id="2f6d5-321">为音频、视频、应用程序共享会话打开</span><span class="sxs-lookup"><span data-stu-id="2f6d5-321">Open for audio, video, application sharing sessions</span></span>  <br/> |
|<span data-ttu-id="2f6d5-322">STUN</span><span class="sxs-lookup"><span data-stu-id="2f6d5-322">STUN</span></span>  <br/> |<span data-ttu-id="2f6d5-323">TCP</span><span class="sxs-lookup"><span data-stu-id="2f6d5-323">TCP</span></span>  <br/> |<span data-ttu-id="2f6d5-324">Office 365</span><span class="sxs-lookup"><span data-stu-id="2f6d5-324">Office 365</span></span>  <br/> |<span data-ttu-id="2f6d5-325">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="2f6d5-325">A/V Edge</span></span>  <br/> |<span data-ttu-id="2f6d5-326">443</span><span class="sxs-lookup"><span data-stu-id="2f6d5-326">443</span></span>  <br/> |<span data-ttu-id="2f6d5-327">50000-59999</span><span class="sxs-lookup"><span data-stu-id="2f6d5-327">50000-59999</span></span>  <br/> |<span data-ttu-id="2f6d5-328">为音频、视频、应用程序共享会话打开</span><span class="sxs-lookup"><span data-stu-id="2f6d5-328">Open for audio, video, application sharing sessions</span></span>  <br/> |
|<span data-ttu-id="2f6d5-329">STUN</span><span class="sxs-lookup"><span data-stu-id="2f6d5-329">STUN</span></span>  <br/> |<span data-ttu-id="2f6d5-330">UDP</span><span class="sxs-lookup"><span data-stu-id="2f6d5-330">UDP</span></span>  <br/> |<span data-ttu-id="2f6d5-331">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="2f6d5-331">A/V Edge</span></span>  <br/> |<span data-ttu-id="2f6d5-332">Office 365</span><span class="sxs-lookup"><span data-stu-id="2f6d5-332">Office 365</span></span>  <br/> |<span data-ttu-id="2f6d5-333">3478</span><span class="sxs-lookup"><span data-stu-id="2f6d5-333">3478</span></span>  <br/> |<span data-ttu-id="2f6d5-334">3478</span><span class="sxs-lookup"><span data-stu-id="2f6d5-334">3478</span></span>  <br/> |<span data-ttu-id="2f6d5-335">为音频、视频会话打开</span><span class="sxs-lookup"><span data-stu-id="2f6d5-335">Open for audio, video sessions</span></span>  <br/> |
|<span data-ttu-id="2f6d5-336">STUN</span><span class="sxs-lookup"><span data-stu-id="2f6d5-336">STUN</span></span>  <br/> |<span data-ttu-id="2f6d5-337">UDP</span><span class="sxs-lookup"><span data-stu-id="2f6d5-337">UDP</span></span>  <br/> |<span data-ttu-id="2f6d5-338">Office 365</span><span class="sxs-lookup"><span data-stu-id="2f6d5-338">Office 365</span></span>  <br/> |<span data-ttu-id="2f6d5-339">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="2f6d5-339">A/V Edge</span></span>  <br/> |<span data-ttu-id="2f6d5-340">3478</span><span class="sxs-lookup"><span data-stu-id="2f6d5-340">3478</span></span>  <br/> |<span data-ttu-id="2f6d5-341">3478</span><span class="sxs-lookup"><span data-stu-id="2f6d5-341">3478</span></span>  <br/> |<span data-ttu-id="2f6d5-342">为音频、视频会话打开</span><span class="sxs-lookup"><span data-stu-id="2f6d5-342">Open for audio, video sessions</span></span>  <br/> |
   
<span data-ttu-id="2f6d5-343">有关端口和防火墙的边缘服务器规划的详细信息，请参阅[在 Skype 业务服务器 2015年的边缘服务器环境的要求](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-343">For more information about port and firewall planning for Edge Server, see [Edge Server environmental requirements in Skype for Business Server 2015](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md).</span></span> <span data-ttu-id="2f6d5-344">请参阅[服务器的端口和协议要求](../plan-your-deployment/network-requirements/ports-and-protocols.md)和[协议工作负荷图](http://go.microsoft.com/fwlink/p/?LinkId=550989)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-344">See also [Port and protocol requirements for servers](../plan-your-deployment/network-requirements/ports-and-protocols.md) and the [Protocol workloads diagram](http://go.microsoft.com/fwlink/p/?LinkId=550989).</span></span>
  
## <a name="user-accounts-and-data"></a><span data-ttu-id="2f6d5-345">用户帐户和数据</span><span class="sxs-lookup"><span data-stu-id="2f6d5-345">User accounts and data</span></span>
<span data-ttu-id="2f6d5-346"><a name="BKMK_UserAccounts"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-346"></span></span>

<span data-ttu-id="2f6d5-347">在混合部署中，想要在线家庭任何用户必须首先创建在内部部署中，以便在 Active Directory 域服务中创建的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-347">In a hybrid deployment, any user that you want to home online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="2f6d5-348">然后可以移动到 Skype 业务在线，它将用户的联系人列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-348">You can then move the user to Skype for Business Online, which will move the user's contact list.</span></span>
  
<span data-ttu-id="2f6d5-349">在同步到内部部署和联机使用连接 AAD 的租户之间的用户帐户时，您需要同步 AD 帐户为所有对您的组织中的业务或 Lync 用户 Skype 即使用户不在线移动到。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-349">When you synchronize user accounts between your on-premises deployment and online tenant using AAD Connect, you need to synchronize the AD accounts for all Skype for Business or Lync users in your organization, even if users are not moved to online.</span></span> <span data-ttu-id="2f6d5-350">如果未同步所有用户，则组织中本地和联机用户之间的通信可能无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-350">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2f6d5-351">所有的用户管理，包括用户内部和 Skype 之间移动的业务联机，必须使用最新安装的管理工具版本。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-351">All user management, including user moves between on-premises and Skype for Business Online, must be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="2f6d5-352">必须对现有的内部部署和互联网已连接访问的独立服务器上安装管理工具。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-352">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="2f6d5-353">从管理工具连接到内部部署必须运行该 cmdlet 将用户从移到内部部署到 Skype 的业务联机，[移动 CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-353">The cmdlet to move users from your on-premises deployment to Skype for Business Online, [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps), must be run from the administrative tools connected to your on-premises deployment.</span></span> <span data-ttu-id="2f6d5-354">有关移动用户的详细信息，请参阅[移动用户 Skype 的在线业务的场所上](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-354">For more information about moving users, see [Move users from on premises to Skype for Business Online](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2f6d5-355">如果用户是使用 Office 365 的联机门户创建的，则该用户帐户将不会与本地 Active Directory 同步，并且该用户将不会存在于本地 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-355">If the user was created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="2f6d5-356">如果你已在联机租户中创建用户，并且希望配置与本地部署的混合，请参阅“将用户从联机移动到本地”。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-356">If you have already created users in your online tenant, and want to configure hybrid with an on-premises deployment, see Move users from online to on premises.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2f6d5-357">如果您目前正在为具有未在内部部署中启用的用户 Skype 的在线业务启用联机业务客户 Skype，请参阅[移动用户从 Skype 业务联机到内部部署](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-357">If you are currently a Skype for Business Online customer who has users enabled for Skype for Business Online who have not been enabled in an on-premises deployment, see [Move users from Skype for Business Online to on premises](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md).</span></span> 
  
<span data-ttu-id="2f6d5-358">规划混合部署时还应考虑以下用户相关的问题。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-358">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>
  
- <span data-ttu-id="2f6d5-359">**用户的联系人**Lync Online 用户联系人的限制为 250 个字符。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-359">**User contacts** The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="2f6d5-360">当帐户移至 Lync Online 超过该数字的所有联系人将都从用户的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-360">Any contacts beyond that number will be removed from the user's contact list when the account is moved to Lync Online.</span></span>
    
- <span data-ttu-id="2f6d5-361">**即时消息和状态**使用用户帐户迁移联系人列表的用户、 组和访问控制列表 (Acl)。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-361">**Instant Messaging and Presence** User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>
    
- <span data-ttu-id="2f6d5-362">**会议数据、 会议内容和计划的会议**此内容不会迁移的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-362">**Conferencing data, meeting content, and scheduled meetings** This content is not migrated with the user account.</span></span> <span data-ttu-id="2f6d5-363">用户必须在其帐户迁移到 Lync Online 之后重新安排会议。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-363">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>
    
## <a name="user-policies-and-features"></a><span data-ttu-id="2f6d5-364">用户策略和功能</span><span class="sxs-lookup"><span data-stu-id="2f6d5-364">User policies and features</span></span>
<span data-ttu-id="2f6d5-365"><a name="BKMK_UserPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="2f6d5-365"></span></span>

- <span data-ttu-id="2f6d5-366">在混合环境中，可以为本地或联机用户（但不是同时）启用即时消息和会议。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-366">In a hybrid environment, users can be enabled for Instant Messaging and conferencing (meetings) either on premises or online, but not both simultaneously.</span></span>
    
- <span data-ttu-id="2f6d5-367">**客户端支持**有些用户可能需要新的客户端版本，当他们移动到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-367">**Client support** Some users may require a new client version when they are moved to Skype for Business Online.</span></span> <span data-ttu-id="2f6d5-368">对于办公室通信服务器 2007 R2 中，用户必须将移动到 Skype 业务服务器或 Lync Server 2013 池之前迁移到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-368">For Office Communications Server 2007 R2, users must be moved to a Skype for Business Server or Lync Server 2013 pool prior to migration to Skype for Business Online.</span></span>
    
- <span data-ttu-id="2f6d5-369">**内部部署策略和配置 （非用户）**联机和本地策略需要单独的配置。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-369">**On-premises policies and configuration (non-user)** Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="2f6d5-370">无法设置适用于二者的全局策略。</span><span class="sxs-lookup"><span data-stu-id="2f6d5-370">You cannot set global policies that apply to both.</span></span>
    

