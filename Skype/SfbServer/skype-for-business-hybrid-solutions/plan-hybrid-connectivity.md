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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
description: 摘要：阅读本主题可了解如何规划 Skype for Business Server 与 Skype for Business Online 之间的混合连接。 设置混合连接是部署多种 Skype for Business 混合解决方案的第一步。
ms.openlocfilehash: d3fe994535197209a8d35c10144e45badb4391a8
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890473"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a><span data-ttu-id="e98ed-104">规划 Skype for Business Server 与 Skype for Business Online 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="e98ed-104">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>

<span data-ttu-id="e98ed-105">**摘要：** 阅读本主题可了解如何规划 Skype for Business Server 与 Skype for Business Online 之间的混合连接。</span><span class="sxs-lookup"><span data-stu-id="e98ed-105">**Summary:** Read this topic to learn how to plan hybrid connectivity between Skype for Business Server and Skype for Business Online.</span></span> <span data-ttu-id="e98ed-106">设置混合连接是部署多种 Skype for Business 混合解决方案的第一步。</span><span class="sxs-lookup"><span data-stu-id="e98ed-106">Setting up hybrid connectivity is the first step in deploying many Skype for Business hybrid solutions.</span></span>

<span data-ttu-id="e98ed-107">本主题提供了概述，并描述基础结构和系统要求您需要配置混合连接之间您现有的内部部署 Skype Business Server 部署的 — 与在您的内部部署中创建的用户Active Directory — 和 Skype for Business 联机。</span><span class="sxs-lookup"><span data-stu-id="e98ed-107">This topic provides an overview, and describes the infrastructure and system requirements you'll need to configure hybrid connectivity between your existing on-premises Skype for Business Server deployment—with users who were created in your on-premises Active Directory—and Skype for Business Online.</span></span>

<span data-ttu-id="e98ed-108">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="e98ed-108">This topic contains the following sections:</span></span>

- [<span data-ttu-id="e98ed-109">概述</span><span class="sxs-lookup"><span data-stu-id="e98ed-109">Overview</span></span>](plan-hybrid-connectivity.md#BKMK_Overview)

- [<span data-ttu-id="e98ed-110">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="e98ed-110">Infrastructure requirements</span></span>](plan-hybrid-connectivity.md#BKMK_Infrastructure)

- [<span data-ttu-id="e98ed-111">多林支持</span><span class="sxs-lookup"><span data-stu-id="e98ed-111">Multi-forest support</span></span>](plan-hybrid-connectivity.md#BKMK_MultiForest)

- [<span data-ttu-id="e98ed-112">Exchange 共存</span><span class="sxs-lookup"><span data-stu-id="e98ed-112">Exchange co-existence</span></span>](plan-hybrid-connectivity.md#BKMK_Exchange)

- [<span data-ttu-id="e98ed-113">管理员凭据</span><span class="sxs-lookup"><span data-stu-id="e98ed-113">Administrator credentials</span></span>](plan-hybrid-connectivity.md#BKMK_Credentials)

- [<span data-ttu-id="e98ed-114">Skype for Business Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e98ed-114">Skype for Business Online PowerShell</span></span>](plan-hybrid-connectivity.md#BKMK_PowerShell)

- [<span data-ttu-id="e98ed-115">Skype for Business 客户端支持</span><span class="sxs-lookup"><span data-stu-id="e98ed-115">Skype for Business client support</span></span>](plan-hybrid-connectivity.md#BKMK_ClientSupport)

- [<span data-ttu-id="e98ed-116">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="e98ed-116">Topology requirements</span></span>](plan-hybrid-connectivity.md#BKMK_Topology)

- [<span data-ttu-id="e98ed-117">联盟允许/阻止列表的要求</span><span class="sxs-lookup"><span data-stu-id="e98ed-117">Federation Allowed/Blocked Lists requirements</span></span>](plan-hybrid-connectivity.md#BKMK_Federation)

- [<span data-ttu-id="e98ed-118">DNS 设置</span><span class="sxs-lookup"><span data-stu-id="e98ed-118">DNS settings</span></span>](plan-hybrid-connectivity.md#BKMK_DNS)

- [<span data-ttu-id="e98ed-119">防火墙注意事项</span><span class="sxs-lookup"><span data-stu-id="e98ed-119">Firewall considerations</span></span>](plan-hybrid-connectivity.md#BKMK_Firewall)

- [<span data-ttu-id="e98ed-120">端口和协议要求</span><span class="sxs-lookup"><span data-stu-id="e98ed-120">Port and protocol requirements</span></span>](plan-hybrid-connectivity.md#BKMK_Ports)

- [<span data-ttu-id="e98ed-121">用户帐户和数据</span><span class="sxs-lookup"><span data-stu-id="e98ed-121">User accounts and data</span></span>](plan-hybrid-connectivity.md#BKMK_UserAccounts)

- [<span data-ttu-id="e98ed-122">用户策略和功能</span><span class="sxs-lookup"><span data-stu-id="e98ed-122">User policies and features</span></span>](plan-hybrid-connectivity.md#BKMK_UserPolicies)

<span data-ttu-id="e98ed-123">之后，您已阅读本主题和准备部署，请参阅[Deploy Skype 业务服务器和 Skype 业务 online 之间的混合连接性](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-123">After you have read this topic and are ready to deploy, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span> <span data-ttu-id="e98ed-124">部署主题提供了设置本地部署与 Skype for Business Online 之间的混合连接的分步指导。</span><span class="sxs-lookup"><span data-stu-id="e98ed-124">The deployment topics provide step-by-step guidance for setting up hybrid connectivity between your on-premises deployment and Skype for Business Online.</span></span>

<span data-ttu-id="e98ed-125">（有关配置 Lync Server 2013 或 Lync Server 2010 混合部署的信息，请参阅[Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360)。）</span><span class="sxs-lookup"><span data-stu-id="e98ed-125">(For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)</span></span>

## <a name="overview"></a><span data-ttu-id="e98ed-126">概述</span><span class="sxs-lookup"><span data-stu-id="e98ed-126">Overview</span></span>
<span data-ttu-id="e98ed-127"><a name="BKMK_Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-127"></span></span>

<span data-ttu-id="e98ed-128">混合解决方案使你可以根据自己的计划和业务需求将用户迁移到云。</span><span class="sxs-lookup"><span data-stu-id="e98ed-128">Hybrid solutions enable you to move your users to the cloud based on your schedule and business need.</span></span> <span data-ttu-id="e98ed-129">本主题重点介绍 Skype for Business Server 本地部署与 Skype for Business Online 之间的混合连接。</span><span class="sxs-lookup"><span data-stu-id="e98ed-129">This topic focuses on hybrid connectivity between an on-premises deployment of Skype for Business Server and Skype for Business Online.</span></span> <span data-ttu-id="e98ed-130">通过此连接，你可以将一些用户在本地托管，一些用户在线托管。</span><span class="sxs-lookup"><span data-stu-id="e98ed-130">This connectivity allows you to have some users homed on-premises and some users homed online.</span></span>

<span data-ttu-id="e98ed-131">这种部署有时称为"拆分域"— 含义用户的域名，例如，contoso.com，分别驻留在使用 Skype 本地 Business Server 和 Skype 业务 online，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e98ed-131">This type of deployment is sometimes referred to as "split domain"—meaning users of a domain, such as contoso.com, are split between using Skype for Business Server on premises and Skype for Business Online as follows:</span></span>

- <span data-ttu-id="e98ed-132">在本地托管的用户与本地 Skype for Business 服务器交互</span><span class="sxs-lookup"><span data-stu-id="e98ed-132">Users who are homed on premises interact with on premises Skype for Business servers</span></span>

- <span data-ttu-id="e98ed-133">在线托管的用户与 Skype for Business 在线服务交互</span><span class="sxs-lookup"><span data-stu-id="e98ed-133">Users who are homed online interact with Skype for Business online services</span></span>

- <span data-ttu-id="e98ed-134">两个环境的用户可以使用即时消息或通过参与电话会议和 VoIP 通话等方式相互协作</span><span class="sxs-lookup"><span data-stu-id="e98ed-134">Users from both environments can collaborate with each other by using Instant Messaging, participating in conference calls, VoIP calls, and so on</span></span>

- <span data-ttu-id="e98ed-135">Azure Active Directory Connect 用于将你的本地目录与 Office 365 同步</span><span class="sxs-lookup"><span data-stu-id="e98ed-135">Azure Active Directory Connect is used to synchronize your on-premises directory with Office 365</span></span>

<span data-ttu-id="e98ed-136">本地 Active Directory 是权威性的，即你必须执行下列操作以确保本地和在线用户可以相互发现：</span><span class="sxs-lookup"><span data-stu-id="e98ed-136">The on-premises Active Directory is authoritative, which means that you must do the following to ensure that on-premises and online users are discoverable to one another:</span></span>

- <span data-ttu-id="e98ed-137">所有用户应首先，在内部部署 Active Directory 中创建，然后同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="e98ed-137">All users should be created in the on-premises Active Directory first, and then synchronized to Azure AD.</span></span>

- <span data-ttu-id="e98ed-138">如果你的用户托管在本地 Skype for Business 中，你需要为本地 Skype for Business 启用这些用户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-138">If your users are homed on premises for Skype for Business, then you need to enable them for Skype for Business on premises.</span></span>

- <span data-ttu-id="e98ed-139">如果你的用户在本地托管，但想要利用某些在线功能（例如 Skype 会议广播），你需要向其分配 Skype for Business Online 套餐 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="e98ed-139">If your users are homed on premises, but want to take advantage of some online features, such as Skype Meeting Broadcast, you need to assign them a Skype for Business Online plan 2 license.</span></span>

- <span data-ttu-id="e98ed-140">如果你的用户在 Skype for Business Online 中托管，则其帐户同步到 Azure AD 之后，你将需要为其分配 Skype for Business Online 套餐 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="e98ed-140">If your users are homed in Skype for Business Online, once their account is synchronized to Azure AD, you need to assign them a Skype for Business Online plan 2 license.</span></span>

- <span data-ttu-id="e98ed-141">为 Skype for Business Online 用户分配许可证后，你需要为 Skype for Business 或本地 Enterprise Voice 启用这些用户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-141">After Skype for Business Online users are assigned a license, you need to enable them for Skype for Business or for Enterprise Voice on premises.</span></span> <span data-ttu-id="e98ed-142">有关详细信息，请参阅[启用本地的企业语音的用户](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-142">For more information, see [Enable the users for Enterprise Voice on premises](plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md).</span></span> <span data-ttu-id="e98ed-143">有关混合语音要求的详细信息，请参阅[规划与业务服务器 Skype 中的内部部署 PSTN 连接的 Office 365 中的电话系统](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-143">For more information about hybrid voice requirements, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>

<span data-ttu-id="e98ed-144">在下面的部分，你将了解有关 Active Directory 配置的更多信息。</span><span class="sxs-lookup"><span data-stu-id="e98ed-144">You'll learn more about Active Directory configuration in the sections that follow.</span></span> <span data-ttu-id="e98ed-145">但首先是下图以及众多混合连接主题中使用的术语和缩略词概述：</span><span class="sxs-lookup"><span data-stu-id="e98ed-145">But first, an overview of the terminology and acronyms used in the diagrams below, and in many of the hybrid connectivity topics:</span></span>

- <span data-ttu-id="e98ed-146">PSTN - 公用电话交换网</span><span class="sxs-lookup"><span data-stu-id="e98ed-146">PSTN - Public Switched Telephone Network</span></span>

- <span data-ttu-id="e98ed-147">PBX - 专用交换机电话系统</span><span class="sxs-lookup"><span data-stu-id="e98ed-147">PBX - Private Branch Exchange phone system</span></span>

- <span data-ttu-id="e98ed-148">电话系统 - Microsoft 的云 PBX 电话系统产品</span><span class="sxs-lookup"><span data-stu-id="e98ed-148">Phone System - Microsoft's Cloud PBX phone system offering</span></span>

- <span data-ttu-id="e98ed-149">中继-Pbx 连接到 PSTN 的电话线路 — 中继可能使用会话初始协议 (SIP) — A Voice over Internet Protocol (VoIP) — 或较旧的-时分多路复用 (TDM) 技术</span><span class="sxs-lookup"><span data-stu-id="e98ed-149">Trunk - Telephony line that connects PBXs to the PSTN—A trunk might use Session Initiation Protocol (SIP)—A Voice over Internet Protocol (VoIP)—or the older Time-Division Multiplexing (TDM) technology</span></span>

- <span data-ttu-id="e98ed-150">SBC - 会话边界控制器 - 在电话网络中充当防火墙和路由器的设备。</span><span class="sxs-lookup"><span data-stu-id="e98ed-150">SBC - Session Border Controller - Device that serves as a firewall and router in telephony networks.</span></span> <span data-ttu-id="e98ed-151">例如，提供安全性、连接性、互操作性和服务质量。</span><span class="sxs-lookup"><span data-stu-id="e98ed-151">For example, provides security, connectivity, interoperability, and Quality of Services.</span></span>

- <span data-ttu-id="e98ed-152">PSTN 网关 - 在电话网络中充当路由器的设备，能够执行 SBC 可以执行的大部分操作，安全和 NAT 遍历除外。</span><span class="sxs-lookup"><span data-stu-id="e98ed-152">PSTN gateway - A device that serves as a router in telephony networks, capable of doing most of what an SBC can do except security and NAT traversal.</span></span>

<span data-ttu-id="e98ed-153">下图显示了业务"拆分域"混合配置 Skype。</span><span class="sxs-lookup"><span data-stu-id="e98ed-153">The following diagram shows a Skype for Business "split domain" hybrid configuration.</span></span> <span data-ttu-id="e98ed-154">用户 A 和 B 在线托管，但可以被本地用户发现；用户 C 和 D 在本地托管，但可以被在线用户发现。</span><span class="sxs-lookup"><span data-stu-id="e98ed-154">Users A and B are homed online but are discoverable by on-premises users; users C and D are homed on premises, but are discoverable by online users.</span></span>

![SfB 混合连接 - 拆分域](../media/c4fc9311-1930-4a58-877f-3c1524dfab5c.png)

<span data-ttu-id="e98ed-156">你可能也已对“混合语音”一词很熟悉—它是指向在云中托管的用户提供功能的本地语音主干。</span><span class="sxs-lookup"><span data-stu-id="e98ed-156">You might also be familiar with the term "hybrid voice"—which refers to on-premises voice trunks that provide functionality to users homed in the cloud.</span></span> <span data-ttu-id="e98ed-157">通过混合语音，可以在保留本地语音配置的同时迁移到云。</span><span class="sxs-lookup"><span data-stu-id="e98ed-157">Hybrid voice enables migration to the cloud while preserving on-premises voice configuration.</span></span> <span data-ttu-id="e98ed-158">如果你已具有 Skype for Business Server 部署，启用混合语音的第一步是配置拆分域环境。</span><span class="sxs-lookup"><span data-stu-id="e98ed-158">If you already have a Skype for Business Server deployment, the first step to enable hybrid voice is to configure a split domain environment.</span></span>

<span data-ttu-id="e98ed-159">例如，假定您的公司具有大型移动字段支持组织需要最少的 PBX 的语音，但广泛使用的智能手机。</span><span class="sxs-lookup"><span data-stu-id="e98ed-159">For example, assume your company has a large mobile field support organization that requires minimal PBX voice, but extensive smart phone use.</span></span> <span data-ttu-id="e98ed-160">你可以选择将这些用户迁移到云，以利用 Microsoft 的 Office 365 电话系统（云 PBX）。</span><span class="sxs-lookup"><span data-stu-id="e98ed-160">You might choose to move these users to the cloud to take advantage of Microsoft's Phone System in Office 365 (Cloud PBX).</span></span> <span data-ttu-id="e98ed-161">如果您的公司还具有内部部署 PBX 的一部分需要高级、 复杂联系中心软件大型本地呼叫中心，您可以选择在本地保留这些用户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-161">If your company also has a large on-premises call center that requires advanced, complex contact center software as part of your on-premises PBX, you might choose to leave these users on premises.</span></span> <span data-ttu-id="e98ed-162">在线托管和在本地托管的用户均具有通过本地部署的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="e98ed-162">Users homed online and on premises both have PSTN connectivity through your on-premises deployment.</span></span>

<span data-ttu-id="e98ed-163">下图显示了 Skype for Business 混合语音部署：</span><span class="sxs-lookup"><span data-stu-id="e98ed-163">The following diagram shows a Skype for Business hybrid voice deployment:</span></span>

![SfB 拆分域和云 PBX](../media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)

<span data-ttu-id="e98ed-165">有关设置与您 Skype Business Server 部署的混合语音解决方案的详细信息，请参阅[规划与业务服务器 Skype 中的内部部署 PSTN 连接的 Office 365 中的电话系统](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-165">For more information about setting up a hybrid voice solution with your Skype for Business Server deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>

<span data-ttu-id="e98ed-166">您还可以配置混合部署的与集成本地 Exchange 和 SharePoint，或与 Microsoft Office 365 应用程序，包括 Exchange Online 和 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="e98ed-166">You can also configure hybrid deployments for integration with on-premises Exchange and SharePoint, or with Microsoft Office 365 applications, including Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="e98ed-167">你还可以使用云连接器版本配置不需要完整 Skype for Business Server 部署的混合语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="e98ed-167">You can also configure a hybrid voice solution that does not require a full Skype for Business Server deployment by using Cloud Connector Edition.</span></span> <span data-ttu-id="e98ed-168">有关用于业务混合解决方案和规划迁移到云中的所有 Skype 的详细信息，请参阅[业务混合解决方案的 Skype](skype-for-business-hybrid-solutions.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-168">For more information about all Skype for Business hybrid solutions and planning your move to the cloud, see [Skype for Business hybrid solutions](skype-for-business-hybrid-solutions.md).</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="e98ed-169">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="e98ed-169">Infrastructure requirements</span></span>
<span data-ttu-id="e98ed-170"><a name="BKMK_Infrastructure"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-170"></span></span>

<span data-ttu-id="e98ed-171">要实施和部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接，必须在环境中进行以下配置：</span><span class="sxs-lookup"><span data-stu-id="e98ed-171">To implement and deploy hybrid connectivity between Skype for Business Server and Skype for Business Online, you must configure the following in your environment:</span></span>

- <span data-ttu-id="e98ed-172">一个本地部署的 Skype 业务服务器或受支持的拓扑中部署 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="e98ed-172">A single on-premises deployment of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="e98ed-173">请参阅本主题中的[拓扑要求](plan-hybrid-connectivity.md#BKMK_Topology)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-173">See [Topology requirements](plan-hybrid-connectivity.md#BKMK_Topology) in this topic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e98ed-174">存在内部部署环境中每个 SIP 域还必须存在于您的 Office 365 租户，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="e98ed-174">Every SIP domain that exists in your on-premises environment must also exist in your Office 365 tenant and vice-versa.</span></span> <span data-ttu-id="e98ed-175">您不能有一些 SIP 域联机仅某些域在本地和仅。</span><span class="sxs-lookup"><span data-stu-id="e98ed-175">You cannot have some SIP domains online only and some domains on-premises only.</span></span> <span data-ttu-id="e98ed-176">否则，状态、 IM 和其他功能将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="e98ed-176">Otherwise, presence, IM and other features will not work correctly.</span></span>

- <span data-ttu-id="e98ed-177">Skype 业务 Online 启用的 Microsoft Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-177">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e98ed-178">只能将混合配置的单个租户与你的本地部署结合使用。</span><span class="sxs-lookup"><span data-stu-id="e98ed-178">You can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

- <span data-ttu-id="e98ed-179">Skype 业务服务器 2015年管理工具。</span><span class="sxs-lookup"><span data-stu-id="e98ed-179">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="e98ed-180">（如果您使用 Lync Server 2013 或 Lync Server 2010，可以使用 Lync Server 2013 管理工具。</span><span class="sxs-lookup"><span data-stu-id="e98ed-180">(If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="e98ed-181">有关详细信息，请参阅[Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360)。）</span><span class="sxs-lookup"><span data-stu-id="e98ed-181">For more information, see [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)</span></span>

- <span data-ttu-id="e98ed-182">Azure Active Directory Connect 用于将你的本地目录与 Office 365 同步。</span><span class="sxs-lookup"><span data-stu-id="e98ed-182">Azure Active Directory Connect to synchronize your on-premises directory with Office 365.</span></span> <span data-ttu-id="e98ed-183">有关详细信息，请参阅[与 Azure Active Directory 连接 Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-183">For more information, see [Connect Active Directory with Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).</span></span>

    <span data-ttu-id="e98ed-184">若要支持 Office 365 的单一登录，使用户能使用在本地所用的同一登录凭据，可以使用 Azure Active Directory (AAD) Connect 的密码同步功能。</span><span class="sxs-lookup"><span data-stu-id="e98ed-184">To support Single Sign-on with Office 365 so that users can use the same login credentials as they do for on premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="e98ed-185">还可以使用 Active Directory 联合身份验证服务 (AD FS) 来进行 Office 365 单一登录。</span><span class="sxs-lookup"><span data-stu-id="e98ed-185">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>

- <span data-ttu-id="e98ed-186">已在你的本地 Skype for Business 部署与 Office 365 租户之间启用联盟。</span><span class="sxs-lookup"><span data-stu-id="e98ed-186">Enabled federation between your on-premises Skype for Business deployment and your Office 365 tenant.</span></span> <span data-ttu-id="e98ed-187">联合身份验证允许在本地部署与 Office 365 组织中的用户进行通信中的用户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-187">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="e98ed-188">有关详细信息，请参阅[与业务 online Skype 配置联盟](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-188">For more information, see [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).</span></span>

- <span data-ttu-id="e98ed-189">已启用共享会话初始协议 (SIP) 地址空间。</span><span class="sxs-lookup"><span data-stu-id="e98ed-189">Enabled shared Session Initiation Protocol (SIP) address space.</span></span> <span data-ttu-id="e98ed-190">SIP 地址是网络上每个用户的唯一标识符，类似于电话号码或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e98ed-190">A SIP address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="e98ed-191">您尝试移动用户从内部部署到 Skype 业务 online 之前，您需要配置 Office 365 租户共享您的本地部署的共享会话初始协议 (SIP) 地址空间。</span><span class="sxs-lookup"><span data-stu-id="e98ed-191">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="e98ed-192">有关详细信息，请参阅[与业务 online Skype 配置联盟](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-192">For more information, see [Configure federation with Skype for Business Online](deploy-hybrid-connectivity/configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="multi-forest-support"></a><span data-ttu-id="e98ed-193">多林支持</span><span class="sxs-lookup"><span data-stu-id="e98ed-193">Multi-forest support</span></span>
<span data-ttu-id="e98ed-194"><a name="BKMK_MultiForest"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-194"></span></span>

<span data-ttu-id="e98ed-195">如果满足下列要求，用户可以访问其他林中的 Skype for Business 功能：</span><span class="sxs-lookup"><span data-stu-id="e98ed-195">Users can access Skype for Business functionality in another forest if the following requirements are met:</span></span>

- <span data-ttu-id="e98ed-196">用户已正确同步到托管 Skype for Business 的林中：在混合配置中，这意味着用户必须作为已禁用的用户对象同步。</span><span class="sxs-lookup"><span data-stu-id="e98ed-196">Users are properly synchronized into the forest that hosts Skype for Business: In hybrid configurations, this means that users must be synchronized as disabled user objects.</span></span>

- <span data-ttu-id="e98ed-197">托管 Skype for Business 的林必须信任包含用户的林。</span><span class="sxs-lookup"><span data-stu-id="e98ed-197">The forest hosting Skype for Business must trust the forest containing the users.</span></span>

<span data-ttu-id="e98ed-198">有关多林混合方案的详细信息，请参阅[Configure hybrid for Business 的 Skype 的多林环境](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-198">For details on multi-forest hybrid scenarios, see [Configure a multi-forest environment for hybrid Skype for Business](deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).</span></span>

## <a name="exchange-co-existence"></a><span data-ttu-id="e98ed-199">Exchange 共存</span><span class="sxs-lookup"><span data-stu-id="e98ed-199">Exchange co-existence</span></span>
<span data-ttu-id="e98ed-200"><a name="BKMK_Exchange"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-200"></span></span>

<span data-ttu-id="e98ed-201">要支持与 Exchange 共存，请记住下列事项：</span><span class="sxs-lookup"><span data-stu-id="e98ed-201">To support co-existence with Exchange, keep the following in mind:</span></span>

- <span data-ttu-id="e98ed-202">最佳做法是移动主页的用户的 Skype for Business 之前将用户的邮箱移动到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e98ed-202">The best practice is to move the user's mailbox to Exchange Online before moving the user's Skype for Business home.</span></span>

- <span data-ttu-id="e98ed-203">支持具有本地 Exchange 邮箱的用户，但存在下列已知限制：</span><span class="sxs-lookup"><span data-stu-id="e98ed-203">Users with Exchange mailboxes on premises are supported with following known limitations:</span></span>

  - <span data-ttu-id="e98ed-204">客户端登录：在 SfB 客户端登录过程中，用户可能需要登录两次</span><span class="sxs-lookup"><span data-stu-id="e98ed-204">Client sign on: Users may need to sign on twice during SfB client sign on</span></span>

  - <span data-ttu-id="e98ed-205">服务器端对话历史记录，存档、 统一联系人存储库、 HighRes 照片要求具有 Exchange 2013 或更高版本，并且必须启用 OAuth 服务器到服务器通信。</span><span class="sxs-lookup"><span data-stu-id="e98ed-205">Server side conversation history, Archiving, Unified Contact Store, HighRes Photo requires Exchange 2013 or later, and you must enable OAuth Server to Server communication.</span></span> <span data-ttu-id="e98ed-206">有关详细信息，请参阅[管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序中的业务服务器 2015 Skype](https://technet.microsoft.com/en-us/library/jj204817.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-206">For more information, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).</span></span>

<span data-ttu-id="e98ed-207">有关与 Exchange Server 的共存的详细信息，包括支持条件和限制各种组合中的内部部署和联机状态，请参阅[计划集成 Skype 商业和 Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)中的[支持的功能](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-207">For details on co-existence with Exchange Server, including support criteria and limitations in various combinations of on-premises and online, see [Feature support](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).</span></span>

## <a name="administrator-credentials"></a><span data-ttu-id="e98ed-208">管理员凭据</span><span class="sxs-lookup"><span data-stu-id="e98ed-208">Administrator credentials</span></span>
<span data-ttu-id="e98ed-209"><a name="BKMK_Credentials"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-209"></span></span>

<span data-ttu-id="e98ed-210">当要求您提供您的管理员凭据时，使用的用户名和密码的管理员帐户为您的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-210">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="e98ed-211">Azure Active Directory 联合身份验证、 目录同步、 单一登录，和将用户迁移到 Skype 配置业务 online 时，您还将使用这些凭据。</span><span class="sxs-lookup"><span data-stu-id="e98ed-211">You will also use these credentials when you configure Azure Active Directory for federation, directory synchronization, single sign-on, and moving users to Skype for Business Online.</span></span>

## <a name="skype-for-business-online-powershell"></a><span data-ttu-id="e98ed-212">Skype for Business Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e98ed-212">Skype for Business Online PowerShell</span></span>
<span data-ttu-id="e98ed-213"><a name="BKMK_PowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-213"></span></span>

<span data-ttu-id="e98ed-214">管理员现在可以使用 Windows PowerShell 管理 Skype 业务联机和其 Skype 业务联机用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-214">Administrators now have the ability to use Windows PowerShell to manage Skype for Business Online and their Skype for Business Online user accounts.</span></span> <span data-ttu-id="e98ed-215">若要执行此操作，您必须首先下载和安装的业务 Online 连接器模块从 Microsoft 下载中心下载 Skype。</span><span class="sxs-lookup"><span data-stu-id="e98ed-215">To do this, you must first download and install the Skype for Business Online Connector Module from the Microsoft Download Center.</span></span> <span data-ttu-id="e98ed-216">有关下载，安装和使用 Skype 对业务联机连接器模块和 using Windows PowerShell to manage Skype 业务 online 的详细信息，请参阅[使用 Windows PowerShell 管理 for Business 的 Skype联机](https://technet.microsoft.com/library/dn362831.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-216">For more information on downloading, installing, and using the Skype for Business Online Connector Module, and for detailed information on using Windows PowerShell to manage Skype for Business Online, see [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/library/dn362831.aspx).</span></span>

## <a name="skype-for-business-client-support"></a><span data-ttu-id="e98ed-217">Skype for Business 客户端支持</span><span class="sxs-lookup"><span data-stu-id="e98ed-217">Skype for Business client support</span></span>
<span data-ttu-id="e98ed-218"><a name="BKMK_ClientSupport"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-218"></span></span>

<span data-ttu-id="e98ed-219">客户端中支持的功能与本地和联机环境中提供的功能一样，存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="e98ed-219">There are some differences in the features supported in clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="e98ed-220">以下客户端支持与 Skype 业务 Online 混合部署中：</span><span class="sxs-lookup"><span data-stu-id="e98ed-220">The following clients are supported with Skype for Business Online in a hybrid deployment:</span></span>

- <span data-ttu-id="e98ed-221">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e98ed-221">Skype for Business</span></span>

- <span data-ttu-id="e98ed-222">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e98ed-222">Lync 2013</span></span>

- <span data-ttu-id="e98ed-223">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e98ed-223">Lync 2010</span></span>

- <span data-ttu-id="e98ed-224">Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="e98ed-224">Lync Windows Store app</span></span>

- <span data-ttu-id="e98ed-225">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="e98ed-225">Lync Web App</span></span>

- <span data-ttu-id="e98ed-226">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="e98ed-226">Lync Mobile</span></span>

- <span data-ttu-id="e98ed-227">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="e98ed-227">Lync for Mac 2011</span></span>

- <span data-ttu-id="e98ed-228">Lync 会议室系统和 Skype 的业务会议室系统</span><span class="sxs-lookup"><span data-stu-id="e98ed-228">Lync Room System and Skype for Business Room System</span></span>

- <span data-ttu-id="e98ed-229">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="e98ed-229">Lync Basic 2013</span></span>

- <span data-ttu-id="e98ed-230">Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e98ed-230">Microsoft Surface Hub</span></span>

<span data-ttu-id="e98ed-231">在决定要在其中家庭用户在组织中之前，您应当查看[for Business 的 Skype 的桌面客户端功能比较](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)以确定 Business Server Skype 的各种配置客户端支持。</span><span class="sxs-lookup"><span data-stu-id="e98ed-231">Before you decide where you want to home users in your organization, you should review the [Desktop client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) to determine the client support for the various configurations of Skype for Business Server.</span></span> <span data-ttu-id="e98ed-232">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="e98ed-232">See also:</span></span>

- [<span data-ttu-id="e98ed-233">规划客户端和设备</span><span class="sxs-lookup"><span data-stu-id="e98ed-233">Plan for clients and devices</span></span>](../plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [<span data-ttu-id="e98ed-234">Skype for Business 的移动客户端功能比较</span><span class="sxs-lookup"><span data-stu-id="e98ed-234">Mobile client feature comparison for Skype for Business</span></span>](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a><span data-ttu-id="e98ed-235">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="e98ed-235">Topology requirements</span></span>
<span data-ttu-id="e98ed-236"><a name="BKMK_Topology"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-236"></span></span>

<span data-ttu-id="e98ed-237">业务 online 与 Skype 配置混合部署，您需要具备以下支持的拓扑结构之一：</span><span class="sxs-lookup"><span data-stu-id="e98ed-237">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

- <span data-ttu-id="e98ed-238">包含业务服务器 2015年运行 Skype 的所有服务器的业务服务器 2015年部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="e98ed-238">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

- <span data-ttu-id="e98ed-239">运行 Lync Server 2013 的所有服务器与 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="e98ed-239">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

    <span data-ttu-id="e98ed-240">对于混合语音连接，指定为联盟边缘的边缘服务器必须为 Skype for Business 2015，边缘也需要 Skype for Business Server 后端。</span><span class="sxs-lookup"><span data-stu-id="e98ed-240">For hybrid voice connectivity, the Edge Server that is designated as Federation Edge must be Skype for Business 2015, the Edge also requires a Skype for Business Server backend.</span></span> <span data-ttu-id="e98ed-241">你可能有一个池中没有任何用户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-241">You might have a pool with no users on it.</span></span>

- <span data-ttu-id="e98ed-242">运行 Lync Server 2010 通过最新累积更新的所有服务器与 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="e98ed-242">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>

  - <span data-ttu-id="e98ed-243">联合身份验证边缘服务器和从联合身份验证边缘服务器的下一个跃点服务器必须运行 Lync Server 2010 通过最新累积更新。</span><span class="sxs-lookup"><span data-stu-id="e98ed-243">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>

  - <span data-ttu-id="e98ed-244">必须至少一台服务器或管理工作站上安装 Skype 业务服务器 2015年或 Lync Server 2013 管理工具。</span><span class="sxs-lookup"><span data-stu-id="e98ed-244">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

- <span data-ttu-id="e98ed-245">混合的 Lync Server 2013 和 Skype 业务服务器 2015年部署与运行业务服务器 2015 Skype 的至少一个站点中的以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="e98ed-245">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>

  - <span data-ttu-id="e98ed-246">至少一个企业版池或 Standard Edition 服务器 </span><span class="sxs-lookup"><span data-stu-id="e98ed-246">At least one Enterprise Pool or Standard Edition server</span></span>

  - <span data-ttu-id="e98ed-247">与 SIP 联盟关联的控制器池（如果存在）</span><span class="sxs-lookup"><span data-stu-id="e98ed-247">The Director Pool associated with SIP federation, if it exists</span></span>

  - <span data-ttu-id="e98ed-248">与 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="e98ed-248">The Edge Pool associated with SIP federation</span></span>

- <span data-ttu-id="e98ed-249">混合的 Lync Server 2010 和 Skype 业务服务器 2015年部署与运行业务服务器 2015 Skype 的至少一个站点中的以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="e98ed-249">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>

  - <span data-ttu-id="e98ed-250">至少一个企业版池或 Standard Edition 服务器 </span><span class="sxs-lookup"><span data-stu-id="e98ed-250">At least one Enterprise Pool or Standard Edition server</span></span>

  - <span data-ttu-id="e98ed-251">与 SIP 联盟关联的控制器池（如果存在）</span><span class="sxs-lookup"><span data-stu-id="e98ed-251">The Director Pool associated with SIP federation, if it exists</span></span>

  - <span data-ttu-id="e98ed-252">与站点的 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="e98ed-252">The Edge Pool associated with SIP federation for the Site</span></span>

- <span data-ttu-id="e98ed-253">混合的 Lync Server 2010 和 Lync Server 2013 部署与至少一个站点运行 Lync Server 2013 中的以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="e98ed-253">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>

  - <span data-ttu-id="e98ed-254">站点中至少一个企业版池或 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="e98ed-254">At least one Enterprise Pool or Standard Edition server in the site</span></span>

  - <span data-ttu-id="e98ed-255">与 SIP 联盟关联的控制器池（如果站点中存在）</span><span class="sxs-lookup"><span data-stu-id="e98ed-255">The Director Pool associated with SIP federation, if it exists in the site</span></span>

  - <span data-ttu-id="e98ed-256">与站点的 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="e98ed-256">The Edge Pool associated with SIP federation for the site</span></span>

## <a name="federation-allowedblocked-lists-requirements"></a><span data-ttu-id="e98ed-257">联盟允许/阻止列表的要求</span><span class="sxs-lookup"><span data-stu-id="e98ed-257">Federation Allowed/Blocked Lists requirements</span></span>
<span data-ttu-id="e98ed-258"><a name="BKMK_Federation"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-258"></span></span>

<span data-ttu-id="e98ed-259">允许域列表包括已配置合作伙伴“边缘”完全限定域名 (FQDN) 的域。</span><span class="sxs-lookup"><span data-stu-id="e98ed-259">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="e98ed-260">这些有时称为允许的伙伴服务器 ordirect 联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="e98ed-260">These are sometimes referred to as allowed partner servers ordirect federation partners.</span></span> <span data-ttu-id="e98ed-261">您应熟悉开放联盟和关闭联盟伙伴发现 andallowed 伙伴域列表中，分别中称为本地部署之间的差异。</span><span class="sxs-lookup"><span data-stu-id="e98ed-261">You should be familiar with the difference between Open Federation and Closed Federation, referred to as partner discovery andallowed partner domain list, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="e98ed-262">必须满足以下要求才能成功配置混合部署：</span><span class="sxs-lookup"><span data-stu-id="e98ed-262">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

- <span data-ttu-id="e98ed-p126">为您的本地部署和您的 Office 365 租户配置的域匹配必须相同。如果在本地部署中启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。如果未启用合作伙伴发现，则必须为您的联机租户配置封闭联盟。</span><span class="sxs-lookup"><span data-stu-id="e98ed-p126">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

- <span data-ttu-id="e98ed-266">本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="e98ed-266">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

- <span data-ttu-id="e98ed-267">本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="e98ed-267">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

- <span data-ttu-id="e98ed-268">Online 租户，使用适用于业务 Online 控制面板 Skype 配置的外部通信，必须启用联盟。</span><span class="sxs-lookup"><span data-stu-id="e98ed-268">Federation must be enabled for the external communications for the online tenant, which is configured by using the Skype for Business Online Control Panel.</span></span>

## <a name="dns-settings"></a><span data-ttu-id="e98ed-269">DNS 设置</span><span class="sxs-lookup"><span data-stu-id="e98ed-269">DNS settings</span></span>
<span data-ttu-id="e98ed-270"><a name="BKMK_DNS"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-270"></span></span>

<span data-ttu-id="e98ed-271">创建混合部署的 DNS 记录时，所有业务外部 DNS 记录的 Skype 应都指向的内部部署基础结构。</span><span class="sxs-lookup"><span data-stu-id="e98ed-271">When creating DNS records for hybrid deployments, all Skype for Business external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="e98ed-272">有关所需的 DNS 记录的详细信息，请参阅[业务服务器 2015年的 Skype 的 DNS 要求](../plan-your-deployment/network-requirements/dns.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-272">For details on required DNS records, please refer to [DNS requirements for Skype for Business Server 2015](../plan-your-deployment/network-requirements/dns.md).</span></span>

<span data-ttu-id="e98ed-273">此外，您还需要确保下表中所述的 DNS 解析在您的本地部署中正常运行：</span><span class="sxs-lookup"><span data-stu-id="e98ed-273">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>

|<span data-ttu-id="e98ed-274">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="e98ed-274">DNS record</span></span>  <br/> |<span data-ttu-id="e98ed-275">解析者</span><span class="sxs-lookup"><span data-stu-id="e98ed-275">Resolvable by</span></span>  <br/> |<span data-ttu-id="e98ed-276">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="e98ed-276">DNS requirement</span></span>  <br/> |
|:-----|:-----|:-----|
|<span data-ttu-id="e98ed-277">_Sipfederationtls._tcp 的 DNS SRV 记录。\<sipdomain.com\>用于所有支持的 SIP 域解析为访问边缘外部 IP(s)</span><span class="sxs-lookup"><span data-stu-id="e98ed-277">DNS SRV record for _sipfederationtls._tcp.\<sipdomain.com\> for all supported SIP domains resolving to Access Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="e98ed-278">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="e98ed-278">Edge server(s)</span></span>  <br/> |<span data-ttu-id="e98ed-p128">在混合配置中启用联盟通信。边缘服务器需要知道在什么位置为 SIP 域路由分布在本地设备和在线设备上的联盟流量。</span><span class="sxs-lookup"><span data-stu-id="e98ed-p128">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span>  <br/> <span data-ttu-id="e98ed-281">必须使用用户名与 SRV 记录中的域之间的严格 DNS 名称匹配。</span><span class="sxs-lookup"><span data-stu-id="e98ed-281">Must use strict DNS name matching between the domain in the user name and the SRV record.</span></span>  <br/> |
|<span data-ttu-id="e98ed-282">边缘 Web 会议服务 FQDN 的 DNS A 记录，例如解析为 Web 会议边缘外部 IP 的 webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e98ed-282">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="e98ed-283">内部企业网络连接的用户的计算机</span><span class="sxs-lookup"><span data-stu-id="e98ed-283">Internal corporate network connected users' computers</span></span>  <br/> |<span data-ttu-id="e98ed-p129">让在线用户能够在本地托管会议中演示或查看内容。内容包括 PowerPoint 文件、白板、轮询和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="e98ed-p129">Enable online users to present or view content in on-premises hosted meetings. Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span>  <br/> |

<span data-ttu-id="e98ed-286">根据 DNS 在您的组织中如何配置，您可能需要将这些记录添加到内部托管 DNS 区域，以便相应的 SIP 域能够提供对这些记录的内部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="e98ed-286">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

[!NOTE] <span data-ttu-id="e98ed-287">_sipfederationtls._tcp。\<sipdomain.com\> ，则需要混合配置从边缘服务器的 SRV 记录解析。</span><span class="sxs-lookup"><span data-stu-id="e98ed-287">_sipfederationtls._tcp.\<sipdomain.com\> SRV record resolution from the Edge Server is required for hybrid configuration.</span></span> <span data-ttu-id="e98ed-288">如果边缘服务器不能解决这些记录，请在本地用户不能看到的状态或与在线用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="e98ed-288">If the Edge Server cannot resolve these records, the on-premises users will not be able to see the presence or communicate with online users.</span></span>

## <a name="firewall-considerations"></a><span data-ttu-id="e98ed-289">防火墙注意事项</span><span class="sxs-lookup"><span data-stu-id="e98ed-289">Firewall considerations</span></span>
<span data-ttu-id="e98ed-290"><a name="BKMK_Firewall"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-290"></span></span>

<span data-ttu-id="e98ed-p131">您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。</span><span class="sxs-lookup"><span data-stu-id="e98ed-p131">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="e98ed-293">根据您的 Microsoft Online Services 数据中心的位置，您还必须配置网络防火墙设备以接受连接基于通配符域名 (例如，来自所有通讯\*。 outlook.com)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-293">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="e98ed-294">如果贵组织的防火墙不支持通配符名称配置，您将需要手动确定您希望允许的 IP 地址范围和指定的端口。</span><span class="sxs-lookup"><span data-stu-id="e98ed-294">If your organization's firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="e98ed-295">有关详细信息，请参阅[Office 365 Url 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?LinkId=252942)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-295">For more information, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?LinkId=252942).</span></span>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="e98ed-296">端口和协议要求</span><span class="sxs-lookup"><span data-stu-id="e98ed-296">Port and protocol requirements</span></span>
<span data-ttu-id="e98ed-297"><a name="BKMK_Ports"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-297"></span></span>

<span data-ttu-id="e98ed-298">除了内部通信的端口要求，还必须配置以下端口以启用混合连接：</span><span class="sxs-lookup"><span data-stu-id="e98ed-298">In addition to the port requirements for internal communication, you must also configure the following ports to enable hybrid connectivity:</span></span>


|<span data-ttu-id="e98ed-299">**协议**</span><span class="sxs-lookup"><span data-stu-id="e98ed-299">**Protocol**</span></span>|<span data-ttu-id="e98ed-300">**TCP 或 UDP**</span><span class="sxs-lookup"><span data-stu-id="e98ed-300">**TCP or UDP**</span></span>|<span data-ttu-id="e98ed-301">**源 IP**</span><span class="sxs-lookup"><span data-stu-id="e98ed-301">**Source IP**</span></span>|<span data-ttu-id="e98ed-302">**目标 IP**</span><span class="sxs-lookup"><span data-stu-id="e98ed-302">**Destination IP**</span></span>|<span data-ttu-id="e98ed-303">**源端口**</span><span class="sxs-lookup"><span data-stu-id="e98ed-303">**Source Port**</span></span>|<span data-ttu-id="e98ed-304">**目标端口**</span><span class="sxs-lookup"><span data-stu-id="e98ed-304">**Destination Port**</span></span>|<span data-ttu-id="e98ed-305">**说明**</span><span class="sxs-lookup"><span data-stu-id="e98ed-305">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e98ed-306">SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e98ed-306">SIP (MTLS)</span></span>  <br/> |<span data-ttu-id="e98ed-307">TCP</span><span class="sxs-lookup"><span data-stu-id="e98ed-307">TCP</span></span>  <br/> |<span data-ttu-id="e98ed-308">访问边缘</span><span class="sxs-lookup"><span data-stu-id="e98ed-308">Access Edge</span></span>  <br/> |<span data-ttu-id="e98ed-309">Office 365</span><span class="sxs-lookup"><span data-stu-id="e98ed-309">Office 365</span></span>  <br/> |<span data-ttu-id="e98ed-310">任何</span><span class="sxs-lookup"><span data-stu-id="e98ed-310">Any</span></span>  <br/> |<span data-ttu-id="e98ed-311">5061</span><span class="sxs-lookup"><span data-stu-id="e98ed-311">5061</span></span>  <br/> |<span data-ttu-id="e98ed-312">信号</span><span class="sxs-lookup"><span data-stu-id="e98ed-312">Signaling</span></span>  <br/> |
|<span data-ttu-id="e98ed-313">SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e98ed-313">SIP (MTLS)</span></span>  <br/> |<span data-ttu-id="e98ed-314">TCP</span><span class="sxs-lookup"><span data-stu-id="e98ed-314">TCP</span></span>  <br/> |<span data-ttu-id="e98ed-315">Office 365</span><span class="sxs-lookup"><span data-stu-id="e98ed-315">Office 365</span></span>  <br/> |<span data-ttu-id="e98ed-316">访问边缘</span><span class="sxs-lookup"><span data-stu-id="e98ed-316">Access Edge</span></span>  <br/> |<span data-ttu-id="e98ed-317">任何</span><span class="sxs-lookup"><span data-stu-id="e98ed-317">Any</span></span>  <br/> |<span data-ttu-id="e98ed-318">5061</span><span class="sxs-lookup"><span data-stu-id="e98ed-318">5061</span></span>  <br/> |<span data-ttu-id="e98ed-319">信号</span><span class="sxs-lookup"><span data-stu-id="e98ed-319">Signaling</span></span>  <br/> |
|<span data-ttu-id="e98ed-320">STUN</span><span class="sxs-lookup"><span data-stu-id="e98ed-320">STUN</span></span>  <br/> |<span data-ttu-id="e98ed-321">TCP</span><span class="sxs-lookup"><span data-stu-id="e98ed-321">TCP</span></span>  <br/> |<span data-ttu-id="e98ed-322">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="e98ed-322">A/V Edge</span></span>  <br/> |<span data-ttu-id="e98ed-323">Office 365</span><span class="sxs-lookup"><span data-stu-id="e98ed-323">Office 365</span></span>  <br/> |<span data-ttu-id="e98ed-324">50000-59999</span><span class="sxs-lookup"><span data-stu-id="e98ed-324">50000-59999</span></span>  <br/> |<span data-ttu-id="e98ed-325">443</span><span class="sxs-lookup"><span data-stu-id="e98ed-325">443</span></span>  <br/> |<span data-ttu-id="e98ed-326">为音频、视频、应用程序共享会话打开</span><span class="sxs-lookup"><span data-stu-id="e98ed-326">Open for audio, video, application sharing sessions</span></span>  <br/> |
|<span data-ttu-id="e98ed-327">STUN</span><span class="sxs-lookup"><span data-stu-id="e98ed-327">STUN</span></span>  <br/> |<span data-ttu-id="e98ed-328">TCP</span><span class="sxs-lookup"><span data-stu-id="e98ed-328">TCP</span></span>  <br/> |<span data-ttu-id="e98ed-329">Office 365</span><span class="sxs-lookup"><span data-stu-id="e98ed-329">Office 365</span></span>  <br/> |<span data-ttu-id="e98ed-330">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="e98ed-330">A/V Edge</span></span>  <br/> |<span data-ttu-id="e98ed-331">50000-59999</span><span class="sxs-lookup"><span data-stu-id="e98ed-331">50000-59999</span></span>  <br/> |<span data-ttu-id="e98ed-332">443</span><span class="sxs-lookup"><span data-stu-id="e98ed-332">443</span></span>  <br/> |<span data-ttu-id="e98ed-333">为音频、视频、应用程序共享会话打开</span><span class="sxs-lookup"><span data-stu-id="e98ed-333">Open for audio, video, application sharing sessions</span></span>  <br/> |
|<span data-ttu-id="e98ed-334">STUN</span><span class="sxs-lookup"><span data-stu-id="e98ed-334">STUN</span></span>  <br/> |<span data-ttu-id="e98ed-335">UDP</span><span class="sxs-lookup"><span data-stu-id="e98ed-335">UDP</span></span>  <br/> |<span data-ttu-id="e98ed-336">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="e98ed-336">A/V Edge</span></span>  <br/> |<span data-ttu-id="e98ed-337">Office 365</span><span class="sxs-lookup"><span data-stu-id="e98ed-337">Office 365</span></span>  <br/> |<span data-ttu-id="e98ed-338">3478</span><span class="sxs-lookup"><span data-stu-id="e98ed-338">3478</span></span>  <br/> |<span data-ttu-id="e98ed-339">3478</span><span class="sxs-lookup"><span data-stu-id="e98ed-339">3478</span></span>  <br/> |<span data-ttu-id="e98ed-340">为音频、视频会话打开</span><span class="sxs-lookup"><span data-stu-id="e98ed-340">Open for audio, video sessions</span></span>  <br/> |
|<span data-ttu-id="e98ed-341">STUN</span><span class="sxs-lookup"><span data-stu-id="e98ed-341">STUN</span></span>  <br/> |<span data-ttu-id="e98ed-342">UDP</span><span class="sxs-lookup"><span data-stu-id="e98ed-342">UDP</span></span>  <br/> |<span data-ttu-id="e98ed-343">Office 365</span><span class="sxs-lookup"><span data-stu-id="e98ed-343">Office 365</span></span>  <br/> |<span data-ttu-id="e98ed-344">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="e98ed-344">A/V Edge</span></span>  <br/> |<span data-ttu-id="e98ed-345">3478</span><span class="sxs-lookup"><span data-stu-id="e98ed-345">3478</span></span>  <br/> |<span data-ttu-id="e98ed-346">3478</span><span class="sxs-lookup"><span data-stu-id="e98ed-346">3478</span></span>  <br/> |<span data-ttu-id="e98ed-347">为音频、视频会话打开</span><span class="sxs-lookup"><span data-stu-id="e98ed-347">Open for audio, video sessions</span></span>  <br/> |

<span data-ttu-id="e98ed-348">有关端口和防火墙的边缘服务器规划的详细信息，请参阅[中的业务服务器 2015 Skype 的边缘服务器环境要求](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-348">For more information about port and firewall planning for Edge Server, see [Edge Server environmental requirements in Skype for Business Server 2015](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md).</span></span> <span data-ttu-id="e98ed-349">请参阅[服务器的端口和协议要求](../plan-your-deployment/network-requirements/ports-and-protocols.md)和[协议工作负荷图表](https://go.microsoft.com/fwlink/p/?LinkId=550989)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-349">See also [Port and protocol requirements for servers](../plan-your-deployment/network-requirements/ports-and-protocols.md) and the [Protocol workloads diagram](https://go.microsoft.com/fwlink/p/?LinkId=550989).</span></span>

## <a name="user-accounts-and-data"></a><span data-ttu-id="e98ed-350">用户帐户和数据</span><span class="sxs-lookup"><span data-stu-id="e98ed-350">User accounts and data</span></span>
<span data-ttu-id="e98ed-351"><a name="BKMK_UserAccounts"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-351"></span></span>

<span data-ttu-id="e98ed-352">在混合部署中，您想要联机承载任何用户必须先创建在本地部署中，以便在 Active Directory 域服务中创建的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-352">In a hybrid deployment, any user that you want to home online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="e98ed-353">然后，您可以将用户移动到 Skype 业务 online，其中将移动用户的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="e98ed-353">You can then move the user to Skype for Business Online, which will move the user's contact list.</span></span>

<span data-ttu-id="e98ed-354">在同步您的本地部署和使用 AAD 连接的 online 租户之间的用户帐户时，您需要同步的 AD 帐户为在组织中的业务或 Lync 用户的所有 Skype 即使用户未联机移动到。</span><span class="sxs-lookup"><span data-stu-id="e98ed-354">When you synchronize user accounts between your on-premises deployment and online tenant using AAD Connect, you need to synchronize the AD accounts for all Skype for Business or Lync users in your organization, even if users are not moved to online.</span></span> <span data-ttu-id="e98ed-355">如果未同步所有用户，则组织中本地和联机用户之间的通信可能无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="e98ed-355">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e98ed-356">所有用户管理，包括用户的本地和 Skype 之间移动业务 online，都必须使用最新的安装管理工具版本。</span><span class="sxs-lookup"><span data-stu-id="e98ed-356">All user management, including user moves between on-premises and Skype for Business Online, must be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="e98ed-357">必须具有对现有的内部部署和 Internet 连接访问的单独服务器上安装管理工具。</span><span class="sxs-lookup"><span data-stu-id="e98ed-357">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="e98ed-358">此 cmdlet 将用户从您的本地部署迁移到 Skype 业务 online， [Move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps)，必须从管理工具连接到内部部署运行。</span><span class="sxs-lookup"><span data-stu-id="e98ed-358">The cmdlet to move users from your on-premises deployment to Skype for Business Online, [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps), must be run from the administrative tools connected to your on-premises deployment.</span></span> <span data-ttu-id="e98ed-359">有关移动用户的详细信息，请参阅[移动用户从本地到业务 online Skype](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-359">For more information about moving users, see [Move users from on premises to Skype for Business Online](deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e98ed-360">如果用户是使用 Office 365 的联机门户创建的，则该用户帐户将不会与本地 Active Directory 同步，并且该用户将不会存在于本地 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="e98ed-360">If the user was created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="e98ed-361">如果你已在联机租户中创建用户，并且希望配置与本地部署的混合，请参阅“将用户从联机移动到本地”。</span><span class="sxs-lookup"><span data-stu-id="e98ed-361">If you have already created users in your online tenant, and want to configure hybrid with an on-premises deployment, see Move users from online to on premises.</span></span>

> [!NOTE]
> <span data-ttu-id="e98ed-362">如果您当前拥有不在本地部署中已启用的用户启用 Skype 业务 online 业务联机客户的 Skype，请参阅[移动用户从 Skype 业务 online 到本地](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-362">If you are currently a Skype for Business Online customer who has users enabled for Skype for Business Online who have not been enabled in an on-premises deployment, see [Move users from Skype for Business Online to on premises](deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md).</span></span>

<span data-ttu-id="e98ed-363">规划混合部署时还应考虑以下用户相关的问题。</span><span class="sxs-lookup"><span data-stu-id="e98ed-363">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

- <span data-ttu-id="e98ed-364">**用户联系人**为 Lync Online 用户的联系人的限制为 250 个字符。</span><span class="sxs-lookup"><span data-stu-id="e98ed-364">**User contacts** The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="e98ed-365">当帐户移至 Lync Online，超出该号码的任何联系人将从用户的联系人列表中删除。</span><span class="sxs-lookup"><span data-stu-id="e98ed-365">Any contacts beyond that number will be removed from the user's contact list when the account is moved to Lync Online.</span></span>

- <span data-ttu-id="e98ed-366">**即时消息和状态**使用用户帐户都将迁移的用户联系人列表、 组和访问控制列表 (Acl)。</span><span class="sxs-lookup"><span data-stu-id="e98ed-366">**Instant Messaging and Presence** User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

- <span data-ttu-id="e98ed-367">**会议数据、 会议内容和计划的会议**此内容不会迁移用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e98ed-367">**Conferencing data, meeting content, and scheduled meetings** This content is not migrated with the user account.</span></span> <span data-ttu-id="e98ed-368">用户必须在其帐户迁移到 Lync Online 之后重新安排会议。</span><span class="sxs-lookup"><span data-stu-id="e98ed-368">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

## <a name="user-policies-and-features"></a><span data-ttu-id="e98ed-369">用户策略和功能</span><span class="sxs-lookup"><span data-stu-id="e98ed-369">User policies and features</span></span>
<span data-ttu-id="e98ed-370"><a name="BKMK_UserPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="e98ed-370"></span></span>

- <span data-ttu-id="e98ed-371">在混合环境中，可以为本地或联机用户（但不是同时）启用即时消息和会议。</span><span class="sxs-lookup"><span data-stu-id="e98ed-371">In a hybrid environment, users can be enabled for Instant Messaging and conferencing (meetings) either on premises or online, but not both simultaneously.</span></span>

- <span data-ttu-id="e98ed-372">**客户端支持**他们会移动到 Skype 业务 online 时，某些用户可能需要新的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="e98ed-372">**Client support** Some users may require a new client version when they are moved to Skype for Business Online.</span></span> <span data-ttu-id="e98ed-373">为 Office Communications Server 2007 R2，用户必须将移动到 Skype 之前迁移到 Skype 业务 online 业务服务器或 Lync Server 2013 的池。</span><span class="sxs-lookup"><span data-stu-id="e98ed-373">For Office Communications Server 2007 R2, users must be moved to a Skype for Business Server or Lync Server 2013 pool prior to migration to Skype for Business Online.</span></span>

- <span data-ttu-id="e98ed-374">**在本地策略和配置 （非用户）** 联机和本地策略要求单独的配置。</span><span class="sxs-lookup"><span data-stu-id="e98ed-374">**On-premises policies and configuration (non-user)** Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="e98ed-375">无法设置适用于二者的全局策略。</span><span class="sxs-lookup"><span data-stu-id="e98ed-375">You cannot set global policies that apply to both.</span></span>


