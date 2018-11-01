---
title: 规划混合连接性
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 规划业务联机或团队实现业务服务器 Skype 和 Skype 之间的混合连接性注意事项。
ms.openlocfilehash: 55a6fd1d59e8e5af578b9a1c35c61204f925d866
ms.sourcegitcommit: 6d30cfdd8c8b8908d4e4f278c39fd22062f4a888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890569"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a><span data-ttu-id="5646a-103">规划业务服务器 Skype 和 Office 365 之间的混合连接性</span><span class="sxs-lookup"><span data-stu-id="5646a-103">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="5646a-104">概述</span><span class="sxs-lookup"><span data-stu-id="5646a-104">Overview</span></span>

<span data-ttu-id="5646a-105">阅读本主题可了解如何规划 Skype Business Server 和团队或 Skype 业务 online 之间的混合连接性。</span><span class="sxs-lookup"><span data-stu-id="5646a-105">Read this topic to learn how to plan hybrid connectivity between Skype for Business Server and Teams or Skype for Business Online.</span></span> <span data-ttu-id="5646a-106">设置混合连接性是在内部部署环境迁移到云的第一步。</span><span class="sxs-lookup"><span data-stu-id="5646a-106">Setting up hybrid connectivity is the first step in in moving your on-premises environment to the cloud.</span></span>

<span data-ttu-id="5646a-107">如果您有还使用团队 （并行） 的业务用户的内部部署 Skype，这些用户没有与 Skype 互操作的业务用户从其团队客户端，也不能与联盟组织中的用户通信的功能及其团队客户端。</span><span class="sxs-lookup"><span data-stu-id="5646a-107">If you have on-premises Skype for Business users that are also using Teams (side by side), those users do not have the ability to interoperate with Skype for Business users from their Teams client, nor communicate with users in federated organizations, from their Teams client.</span></span> <span data-ttu-id="5646a-108">若要获得此团队中的功能，这些用户必须从移 Skype 业务本地到云，这需要配置的业务混合模式的 Skype。</span><span class="sxs-lookup"><span data-stu-id="5646a-108">To gain this functionality in Teams, these users must be moved from Skype for Business on-premises to the cloud, which requires configuring Skype for Business hybrid mode.</span></span> <span data-ttu-id="5646a-109">此外，获得最佳体验，这些用户应仅团队模式，它可确保所有传入呼叫并从用户的工作组客户端中的任何用户园地聊天。</span><span class="sxs-lookup"><span data-stu-id="5646a-109">In addition, for the best experience, these users should be in Teams Only mode, which ensures all incoming calls and chats from any user land in the user’s Teams client.</span></span>

<span data-ttu-id="5646a-110">设置混合连接性和所有用户都迁移到云也是需要先停用业务部署您的本地 Skype。</span><span class="sxs-lookup"><span data-stu-id="5646a-110">Setting up hybrid connectivity and moving all users to the cloud is also required before you decommission your on-premises Skype for Business deployment.</span></span>  <span data-ttu-id="5646a-111">混合连接设置，您可以选择将用户移动到云根据日程安排和业务需求。</span><span class="sxs-lookup"><span data-stu-id="5646a-111">With hybrid connectivity set up, you can choose to move your users to the cloud based on your schedule and business need.</span></span> <span data-ttu-id="5646a-112">使用直接路由时，您可以利用本地语音基础结构，移动到云中和完成迁移后时。</span><span class="sxs-lookup"><span data-stu-id="5646a-112">With Direct Routing, you can leverage your on-premises voice infrastructure while you move to the cloud and after your migration is complete.</span></span>

<span data-ttu-id="5646a-113">本主题介绍您需要配置您现有的内部部署 Skype 业务服务器部署-与在您的本地 Active Directory-中创建的用户之间的混合连接的基础结构和系统要求和团队或 Skype for Business 联机。</span><span class="sxs-lookup"><span data-stu-id="5646a-113">This topic describes the infrastructure and system requirements you'll need to configure hybrid connectivity between your existing on-premises Skype for Business Server deployment--with users who were created in your on-premises Active Directory--and Teams or Skype for Business Online.</span></span> 

<span data-ttu-id="5646a-114">本主题介绍基础结构和系统要求您需要配置混合连接之间您现有的内部部署 Skype 业务服务器部署和团队或 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="5646a-114">This topic describes the infrastructure and system requirements you'll need to configure hybrid connectivity between your existing on-premises Skype for Business Server deployment and Teams or Skype for Business Online.</span></span>

<span data-ttu-id="5646a-115">您已阅读本主题，并准备好配置混合连接后，请参阅[Business Server 和 Office 365 的 Skype 之间配置混合连接性](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="5646a-115">After you have read this topic and are ready to configure hybrid connectivity, see [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span> <span data-ttu-id="5646a-116">配置主题提供业务 online 设置您的本地部署和团队或 Skype 之间的混合连接性的分步指导。</span><span class="sxs-lookup"><span data-stu-id="5646a-116">The configuration topics provide step-by-step guidance for setting up hybrid connectivity between your on-premises deployment and Teams or Skype for Business Online.</span></span>


## <a name="about-split-domain-functionality"></a><span data-ttu-id="5646a-117">有关拆分域功能</span><span class="sxs-lookup"><span data-stu-id="5646a-117">About Split domain functionality</span></span>
<span data-ttu-id="5646a-118"><a name="BKMK_Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="5646a-118"></span></span>

 <span data-ttu-id="5646a-119">在本地部署的 Business Server 和团队的 Skype 或 Skype 业务 online 之间设置混合连接，您可以将一些用户驻留在本地和联机驻留的一些用户。</span><span class="sxs-lookup"><span data-stu-id="5646a-119">With hybrid connectivity set up between an on-premises deployment of Skype for Business Server and Teams or Skype for Business Online, you can have some users homed on-premises and some users homed online.</span></span>

<span data-ttu-id="5646a-120">这种配置依赖于共享 SIP 地址空间功能，并有时称为"拆分域"— 这意味着用户的域名，例如，contoso.com，分别使用 Skype 业务服务器上部署和团队或 for Business 的 Skype 之间联机，如下图中所示：</span><span class="sxs-lookup"><span data-stu-id="5646a-120">This type of configuration relies on shared SIP address space functionality, and is sometimes referred to as "split domain"--meaning users of a domain, such as contoso.com, are split between using Skype for Business Server on premises and Teams or Skype for Business Online, as shown in the following diagram:</span></span> 

![SfB 混合连接 - 拆分域](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

<span data-ttu-id="5646a-122">当配置共享的 SIP 地址空间：</span><span class="sxs-lookup"><span data-stu-id="5646a-122">When shared SIP address space is configured:</span></span>

- <span data-ttu-id="5646a-123">Azure Active Directory 连接用于与 Office 365 同步您的本地目录。</span><span class="sxs-lookup"><span data-stu-id="5646a-123">Azure Active Directory Connect is used to synchronize your on-premises directory with Office 365.</span></span>

- <span data-ttu-id="5646a-124">用户驻留在本地与业务服务器的内部部署 Skype 进行交互。</span><span class="sxs-lookup"><span data-stu-id="5646a-124">Users who are homed on premises interact with on-premises Skype for Business servers.</span></span> 

- <span data-ttu-id="5646a-125">联机驻留用户可能交互 Skype 业务联机或团队服务。</span><span class="sxs-lookup"><span data-stu-id="5646a-125">Users who are homed online may interact with Skype for Business Online or Teams services.</span></span>

- <span data-ttu-id="5646a-126">这两种环境中的用户可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="5646a-126">Users from both environments can communicate with each other.</span></span> 

- <span data-ttu-id="5646a-127">内部部署 Active Directory 是权威。</span><span class="sxs-lookup"><span data-stu-id="5646a-127">The on-premises Active Directory is authoritative.</span></span> <span data-ttu-id="5646a-128">所有用户应首先，在内部部署 Active Directory 中创建，然后同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="5646a-128">All users should be created in the on-premises Active Directory first, and then synchronized to Azure AD.</span></span> <span data-ttu-id="5646a-129">即使您打算联机驻留用户，必须首先在内部部署环境中，创建用户，然后将用户移动到 online 以确保用户是内部部署用户可供搜索。</span><span class="sxs-lookup"><span data-stu-id="5646a-129">Even if you intend for the user to be homed online, you must first create the user in the on-premises environment, and then move the user to online to ensure the user is discoverable by on-premises users.</span></span> 

<span data-ttu-id="5646a-130">用户可以联机移动之前，必须为用户分配业务 Online (计划 2) 许可证 Skype。</span><span class="sxs-lookup"><span data-stu-id="5646a-130">Before a user can be moved online, the user must be assigned a Skype for Business Online (Plan 2) license.</span></span> <span data-ttu-id="5646a-131">如果用户将使用团队，还必须为用户分配的工作组许可证 （和业务许可证 Skype 必须保持启用状态）。</span><span class="sxs-lookup"><span data-stu-id="5646a-131">If the user will be using Teams, the user must also be assigned a Teams license (and the Skype for Business license must remain enabled).</span></span> <span data-ttu-id="5646a-132">如果您的用户想要充分利用附加的联机功能，如要进行音频会议或电话系统，您需要将其分配 Office 365 中的适当许可。</span><span class="sxs-lookup"><span data-stu-id="5646a-132">If your users want to take advantage of additional online features, such as Audio Conferencing or Phone System, you need to assign them the appropriate license in Office 365.</span></span>


## <a name="infrastructure-requirements"></a><span data-ttu-id="5646a-133">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="5646a-133">Infrastructure requirements</span></span>
<span data-ttu-id="5646a-134"><a name="BKMK_Infrastructure"> </a></span><span class="sxs-lookup"><span data-stu-id="5646a-134"></span></span>

<span data-ttu-id="5646a-135">若要实现您的内部部署环境与 Office 365 通信服务之间的混合连接，您需要满足以下基础结构要求：</span><span class="sxs-lookup"><span data-stu-id="5646a-135">To implement hybrid connectivity between your on-premises environment and Office 365 communication services, you need to meet the following infrastructure requirements:</span></span>

- <span data-ttu-id="5646a-136">一个本地部署的 Skype 业务服务器或受支持的拓扑中部署 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="5646a-136">A single on-premises deployment of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="5646a-137">请参阅本主题中的[拓扑要求](plan-hybrid-connectivity.md#BKMK_Topology)。</span><span class="sxs-lookup"><span data-stu-id="5646a-137">See [Topology requirements](plan-hybrid-connectivity.md#BKMK_Topology) in this topic.</span></span>

- <span data-ttu-id="5646a-138">Skype 业务 Online 启用的 Microsoft Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="5646a-138">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5646a-139">只能将混合配置的单个租户与你的本地部署结合使用。</span><span class="sxs-lookup"><span data-stu-id="5646a-139">You can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

- <span data-ttu-id="5646a-140">Azure Active Directory Connect 用于将你的本地目录与 Office 365 同步。</span><span class="sxs-lookup"><span data-stu-id="5646a-140">Azure Active Directory Connect to synchronize your on-premises directory with Office 365.</span></span> <span data-ttu-id="5646a-141">有关详细信息，请参阅[Azure AD 连接： 帐户和权限](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。</span><span class="sxs-lookup"><span data-stu-id="5646a-141">For more information, see [Azure AD Connect: Accounts and permissions](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).</span></span>

- <span data-ttu-id="5646a-142">Skype Business Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="5646a-142">Skype for Business Server administrative tools.</span></span>  <span data-ttu-id="5646a-143">需要将用户从内部部署移动到云。</span><span class="sxs-lookup"><span data-stu-id="5646a-143">These are required to move users from on-premises to the cloud.</span></span> <span data-ttu-id="5646a-144">必须有权在本地部署和 internet 服务器上安装这些工具。</span><span class="sxs-lookup"><span data-stu-id="5646a-144">These tools must be installed on a server with access to both on-premises deployment and the internet.</span></span> 

- <span data-ttu-id="5646a-145">Online 管理工具。</span><span class="sxs-lookup"><span data-stu-id="5646a-145">Online administrative tools.</span></span>  <span data-ttu-id="5646a-146">可以使用的团队和 Skype 业务管理中心或 Windows PowerShell 来管理工作组和 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="5646a-146">You can use either the Teams and Skype for Business Admin Center or Windows PowerShell to manage Teams and Skype for Business Online.</span></span> <span data-ttu-id="5646a-147">若要使用 PowerShell 管理团队或 Skype 业务 online，下载并安装 Business Online Connector Skype。</span><span class="sxs-lookup"><span data-stu-id="5646a-147">To use PowerShell to manage either Teams or Skype for Business Online, download and install the Skype for Business Online Connector.</span></span> 

- <span data-ttu-id="5646a-148">必须启用共享的 SIP 地址空间，并且必须配置内部部署 Office 365 用作宿主提供商。</span><span class="sxs-lookup"><span data-stu-id="5646a-148">Shared SIP address space must be enabled, and your on-premise deployment must be configured to use Office 365 as a hosting provider.</span></span> <span data-ttu-id="5646a-149">有关配置混合连接所需的步骤的详细信息，请参阅[配置混合连接性](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="5646a-149">For more information about the steps required to configure hybrid connectivity, see [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

<span data-ttu-id="5646a-150">配置混合连接后，您可以将用户移至团队或 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="5646a-150">After you configure hybrid connectivity, you can move users to Teams or Skype for Business Online.</span></span> <span data-ttu-id="5646a-151">有关详细信息，请参阅[移动用户从内部部署到团队](move-users-from-on-premises-to-teams.md)和[移动用户从本地到业务 online Skype](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="5646a-151">For more information, see [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md) and [Move users from on premises to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>


## <a name="topology-requirements"></a><span data-ttu-id="5646a-152">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="5646a-152">Topology requirements</span></span>
<span data-ttu-id="5646a-153"><a name="BKMK_Topology"> </a></span><span class="sxs-lookup"><span data-stu-id="5646a-153"></span></span>

<span data-ttu-id="5646a-154">**工作组**或业务 online Skype 配置混合部署，您需要具备以下支持的拓扑结构之一：</span><span class="sxs-lookup"><span data-stu-id="5646a-154">To configure your deployment for hybrid with **Teams or Skype for Business Online**, you need to have one of the following supported topologies:</span></span>

- <span data-ttu-id="5646a-155">包含业务服务器 2019年运行 Skype 的所有服务器的业务服务器 2019年部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="5646a-155">A Skype for Business Server 2019 deployment with all servers running Skype for Business Server 2019.</span></span> 
- <span data-ttu-id="5646a-156">包含业务服务器 2015年运行 Skype 的所有服务器的业务服务器 2015年部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="5646a-156">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>
- <span data-ttu-id="5646a-157">运行 Lync Server 2013 的所有服务器与 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="5646a-157">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>  <span data-ttu-id="5646a-158">但是，如果不需要混合语音连接，您必须使用混合的版本拓扑如下所述。</span><span class="sxs-lookup"><span data-stu-id="5646a-158">However, if hybrid voice connectivity is required, you must use a mixed version topology as noted below.</span></span>
- <span data-ttu-id="5646a-159">具有两个不同的服务器版本，如下所示的最大部署：</span><span class="sxs-lookup"><span data-stu-id="5646a-159">A deployment with maximum of 2 different server versions as listed below:</span></span>
  - <span data-ttu-id="5646a-160">Skype 业务服务器 2015年和 Skype 业务服务器 2019</span><span class="sxs-lookup"><span data-stu-id="5646a-160">Skype for Business Server 2015 and Skype for Business Server 2019</span></span>
  - <span data-ttu-id="5646a-161">Lync Server 2013 和 Skype 业务服务器 2019</span><span class="sxs-lookup"><span data-stu-id="5646a-161">Lync Server 2013 and Skype for Business Server 2019</span></span>
  - <span data-ttu-id="5646a-162">Lync Server 2013 和 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="5646a-162">Lync Server 2013 and Skype for Business Server 2015</span></span>

<span data-ttu-id="5646a-163">*如果在任何拓扑中需要混合语音*，这两个被指定为联合身份验证边缘，以及与 SIP 联盟关联的池的边缘服务器必须运行 Skype 的业务 2015年或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5646a-163">*If hybrid voice is desired in any topology*, both the edge server that is designated as the Federation Edge as well as the pool associated with SIP federation must be running Skype for Business 2015 or later.</span></span> <span data-ttu-id="5646a-164">如果存在，则用户可以在 Lync 2013 池上保留。</span><span class="sxs-lookup"><span data-stu-id="5646a-164">Users can remain on a Lync 2013 Pool if one exists.</span></span> <span data-ttu-id="5646a-165">有关详细信息，请参阅[规划中的业务服务器 Skype 的 PSTN 连接电话系统](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="5646a-165">For more details, see [Plan Phone System with PSTN Connectivity in Skype for Business Server](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).</span></span>

<span data-ttu-id="5646a-166">以下拓扑，包括即时消息和会议的**Lync Server 2010 支持与业务 online Skype** 。</span><span class="sxs-lookup"><span data-stu-id="5646a-166">The following topologies that include **Lync Server 2010 are supported with Skype for Business Online** for instant messaging and meetings.</span></span>  <span data-ttu-id="5646a-167">包含**混合语音也团队不支持 Lync Server 2010**的拓扑。</span><span class="sxs-lookup"><span data-stu-id="5646a-167">Topologies that include **Lync Server 2010 are not supported for hybrid voice nor Teams**.</span></span>

- <span data-ttu-id="5646a-168">混合的 Lync Server 2010 和 Skype 业务服务器 2015年部署</span><span class="sxs-lookup"><span data-stu-id="5646a-168">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment</span></span>
- <span data-ttu-id="5646a-169">Lync Server 2010 和 Lync Server 2013 混合的部署</span><span class="sxs-lookup"><span data-stu-id="5646a-169">A mixed Lync Server 2010 and Lync Server 2013 deployment</span></span>
-   <span data-ttu-id="5646a-170">运行 Lync Server 2010 通过最新累积更新的所有服务器与 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="5646a-170">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
<span data-ttu-id="5646a-171">联合身份验证边缘服务器和从联合身份验证边缘服务器的下一个跃点服务器必须运行 Lync Server 2010 通过最新累积更新。</span><span class="sxs-lookup"><span data-stu-id="5646a-171">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span> <span data-ttu-id="5646a-172">必须至少一台服务器或管理工作站上安装 Skype 业务服务器 2015年或 Lync Server 2013 管理工具。</span><span class="sxs-lookup"><span data-stu-id="5646a-172">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>



 ## <a name="multi-forest-support"></a><span data-ttu-id="5646a-173">多林支持</span><span class="sxs-lookup"><span data-stu-id="5646a-173">Multi-forest support</span></span>
<span data-ttu-id="5646a-174"><a name="BKMK_MultiForest"> </a></span><span class="sxs-lookup"><span data-stu-id="5646a-174"></span></span>

<span data-ttu-id="5646a-175">如果满足下列要求，用户可以访问其他林中的 Skype for Business 功能：</span><span class="sxs-lookup"><span data-stu-id="5646a-175">Users can access Skype for Business functionality in another forest if the following requirements are met:</span></span>

- <span data-ttu-id="5646a-176">用户已正确同步到托管 Skype for Business 的林中：在混合配置中，这意味着用户必须作为已禁用的用户对象同步。</span><span class="sxs-lookup"><span data-stu-id="5646a-176">Users are properly synchronized into the forest that hosts Skype for Business: In hybrid configurations, this means that users must be synchronized as disabled user objects.</span></span>

- <span data-ttu-id="5646a-177">托管 Skype for Business 的林必须信任包含用户的林。</span><span class="sxs-lookup"><span data-stu-id="5646a-177">The forest hosting Skype for Business must trust the forest containing the users.</span></span>

<span data-ttu-id="5646a-178">有关多林混合方案的详细信息，请参阅[Configure hybrid for Business 的 Skype 的多林环境](configure-a-multi-forest-environment-for-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="5646a-178">For details on multi-forest hybrid scenarios, see [Configure a multi-forest environment for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).</span></span>


## <a name="federation-requirements"></a><span data-ttu-id="5646a-179">联合身份验证要求</span><span class="sxs-lookup"><span data-stu-id="5646a-179">Federation requirements</span></span>
<span data-ttu-id="5646a-180"><a name="BKMK_Federation"> </a></span><span class="sxs-lookup"><span data-stu-id="5646a-180"></span></span>

<span data-ttu-id="5646a-181">在配置混合时，必须确保您在本地和联机环境可以与每个其他联盟。</span><span class="sxs-lookup"><span data-stu-id="5646a-181">When configuring hybrid, you must ensure that your on-premises and online environments can federate with each other.</span></span>  <span data-ttu-id="5646a-182">Online 环境具有开放联盟默认设置。通常，在本地环境具有默认情况下关闭联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="5646a-182">The online environment has open federation by default; the on-premises environment often has closed federation by default.</span></span>  

<span data-ttu-id="5646a-183">必须满足以下要求才能成功配置混合部署：</span><span class="sxs-lookup"><span data-stu-id="5646a-183">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

- <span data-ttu-id="5646a-p118">为您的本地部署和您的 Office 365 租户配置的域匹配必须相同。如果在本地部署中启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。如果未启用合作伙伴发现，则必须为您的联机租户配置封闭联盟。</span><span class="sxs-lookup"><span data-stu-id="5646a-p118">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

- <span data-ttu-id="5646a-187">本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="5646a-187">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

- <span data-ttu-id="5646a-188">本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="5646a-188">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

- <span data-ttu-id="5646a-189">Online 租户的外部通信，必须启用联盟。</span><span class="sxs-lookup"><span data-stu-id="5646a-189">Federation must be enabled for the external communications for the online tenant.</span></span>


## <a name="network-considerations"></a><span data-ttu-id="5646a-190">网络注意事项</span><span class="sxs-lookup"><span data-stu-id="5646a-190">Network considerations</span></span>

<span data-ttu-id="5646a-191">以下各节介绍的注意事项：</span><span class="sxs-lookup"><span data-stu-id="5646a-191">The following sections describe considerations for:</span></span> 

- <span data-ttu-id="5646a-192">DNS 设置</span><span class="sxs-lookup"><span data-stu-id="5646a-192">DNS settings</span></span> 
- <span data-ttu-id="5646a-193">防火墙注意事项</span><span class="sxs-lookup"><span data-stu-id="5646a-193">Firewall considerations</span></span> 


### <a name="dns-settings"></a><span data-ttu-id="5646a-194">DNS 设置</span><span class="sxs-lookup"><span data-stu-id="5646a-194">DNS settings</span></span>
<span data-ttu-id="5646a-195"><a name="BKMK_DNS"> </a></span><span class="sxs-lookup"><span data-stu-id="5646a-195"></span></span>

<span data-ttu-id="5646a-196">创建混合部署的 DNS 记录时，所有业务外部 DNS 记录的 Skype 应都指向的内部部署基础结构。</span><span class="sxs-lookup"><span data-stu-id="5646a-196">When creating DNS records for hybrid deployments, all Skype for Business external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="5646a-197">有关所需的 DNS 记录的详细信息，请参阅[Skype 业务服务器的 DNS 要求](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。</span><span class="sxs-lookup"><span data-stu-id="5646a-197">For details on required DNS records, please refer to [DNS requirements for Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).</span></span>

<span data-ttu-id="5646a-198">此外，您需要确保 DNS 解析下表中所述的本地部署中。</span><span class="sxs-lookup"><span data-stu-id="5646a-198">Additionally, you need to ensure that the DNS resolution described in the following table works in your on-premises deployment.</span></span> <span data-ttu-id="5646a-199">（如果已配置为在本地联盟，然后您很可能已具有这些。）</span><span class="sxs-lookup"><span data-stu-id="5646a-199">(If you already configured federation for on-premises, then you most likely already have these.)</span></span>

|<span data-ttu-id="5646a-200">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="5646a-200">DNS record</span></span>  <br/> |<span data-ttu-id="5646a-201">解析者</span><span class="sxs-lookup"><span data-stu-id="5646a-201">Resolvable by</span></span>  <br/> |<span data-ttu-id="5646a-202">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="5646a-202">DNS requirement</span></span>  <br/> |
|:-----|:-----|:-----|
|<span data-ttu-id="5646a-203">_Sipfederationtls._tcp 的 DNS SRV 记录。\<sipdomain.com\>用于所有支持的 SIP 域解析为访问边缘外部 IP(s)</span><span class="sxs-lookup"><span data-stu-id="5646a-203">DNS SRV record for _sipfederationtls._tcp.\<sipdomain.com\> for all supported SIP domains resolving to Access Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="5646a-204">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="5646a-204">Edge server(s)</span></span>  <br/> |<span data-ttu-id="5646a-p121">在混合配置中启用联盟通信。边缘服务器需要知道在什么位置为 SIP 域路由分布在本地设备和在线设备上的联盟流量。</span><span class="sxs-lookup"><span data-stu-id="5646a-p121">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span>  <br/> <span data-ttu-id="5646a-207">必须使用用户名与 SRV 记录中的域之间的严格 DNS 名称匹配。</span><span class="sxs-lookup"><span data-stu-id="5646a-207">Must use strict DNS name matching between the domain in the user name and the SRV record.</span></span>  <br/> |
|<span data-ttu-id="5646a-208">边缘 Web 会议服务 FQDN 的 DNS A 记录，例如解析为 Web 会议边缘外部 IP 的 webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5646a-208">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="5646a-209">内部企业网络连接的用户的计算机</span><span class="sxs-lookup"><span data-stu-id="5646a-209">Internal corporate network connected users' computers</span></span>  <br/> |<span data-ttu-id="5646a-p122">让在线用户能够在本地托管会议中演示或查看内容。内容包括 PowerPoint 文件、白板、轮询和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="5646a-p122">Enable online users to present or view content in on-premises hosted meetings. Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span>  <br/> |

<span data-ttu-id="5646a-212">根据 DNS 在您的组织中如何配置，您可能需要将这些记录添加到内部托管 DNS 区域，以便相应的 SIP 域能够提供对这些记录的内部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="5646a-212">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span> 

### <a name="firewall-considerations"></a><span data-ttu-id="5646a-213">防火墙注意事项</span><span class="sxs-lookup"><span data-stu-id="5646a-213">Firewall considerations</span></span>
<span data-ttu-id="5646a-214"><a name="BKMK_Firewall"> </a></span><span class="sxs-lookup"><span data-stu-id="5646a-214"></span></span>

<span data-ttu-id="5646a-p123">您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。</span><span class="sxs-lookup"><span data-stu-id="5646a-p123">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="5646a-217">根据您的 Microsoft Online Services 数据中心的位置，您还必须配置网络防火墙设备以接受连接基于通配符域名 (例如，来自所有通讯\*。 outlook.com)。</span><span class="sxs-lookup"><span data-stu-id="5646a-217">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="5646a-218">如果贵组织的防火墙不支持通配符名称配置，您将需要手动确定您希望允许的 IP 地址范围和指定的端口。</span><span class="sxs-lookup"><span data-stu-id="5646a-218">If your organization's firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="5646a-219">有关详细信息，包括有关端口和协议要求的详细信息，请参阅[Office 365 Url 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?LinkId=252942)。</span><span class="sxs-lookup"><span data-stu-id="5646a-219">For more information, including details about ports and protocol requirements, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?LinkId=252942).</span></span>
