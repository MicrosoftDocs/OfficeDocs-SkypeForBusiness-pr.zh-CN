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
ms.openlocfilehash: 34df2639ed57376549b2a8bde2e4b0e071d08957
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295271"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a><span data-ttu-id="26aea-103">规划业务服务器 Skype 和 Office 365 之间的混合连接性</span><span class="sxs-lookup"><span data-stu-id="26aea-103">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="26aea-104">概述</span><span class="sxs-lookup"><span data-stu-id="26aea-104">Overview</span></span>

<span data-ttu-id="26aea-105">阅读本主题可了解如何规划业务联机或团队的 Skype 业务服务器和 Skype 之间的混合连接性。</span><span class="sxs-lookup"><span data-stu-id="26aea-105">Read this topic to learn how to plan hybrid connectivity between Skype for Business Server and Skype for Business Online or Teams.</span></span> <span data-ttu-id="26aea-106">设置混合连接是部署多种 Skype for Business 混合解决方案的第一步。</span><span class="sxs-lookup"><span data-stu-id="26aea-106">Setting up hybrid connectivity is the first step in deploying many Skype for Business hybrid solutions.</span></span>

<span data-ttu-id="26aea-107">混合解决方案，使您能够同时还利用 Microsoft 云中提供的在线服务保留某些本地控件。</span><span class="sxs-lookup"><span data-stu-id="26aea-107">Hybrid solutions enable you to retain some on-premises control while also taking advantage of online services provided in the Microsoft cloud.</span></span> <span data-ttu-id="26aea-108">使用混合连接性设置和各种云服务供您在线和本地用户，您可以选择将用户移动到云根据日程安排和业务需求。</span><span class="sxs-lookup"><span data-stu-id="26aea-108">With hybrid connectivity set up, and a variety of cloud services available to your online and on-premises users, you can choose to move your users to the cloud based on your schedule and business need.</span></span>

<span data-ttu-id="26aea-109">例如，您可能选择呼叫控制通过获得 Microsoft 电话系统在云中同时保留您的本地 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="26aea-109">For example, you might choose to get call control through Microsoft Phone System in the cloud while retaining your on-premises PSTN connectivity.</span></span> <span data-ttu-id="26aea-110">您还可以选择充分利用其他云服务，例如云语音邮件和呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="26aea-110">You might also choose to take advantage of other cloud services, such as Cloud Voicemail and Call Data Connector.</span></span>

<span data-ttu-id="26aea-111">本主题介绍您需要配置混合部署的 Business Server-与在您的内部部署 Active Directory-中创建的用户您现有的本地 Skype 和 Skype 之间的连接的基础结构和系统要求适用于在线商务或团队。</span><span class="sxs-lookup"><span data-stu-id="26aea-111">This topic describes the infrastructure and system requirements you'll need to configure hybrid connectivity between your existing on-premises Skype for Business Server deployment--with users who were created in your on-premises Active Directory--and Skype for Business Online or Teams.</span></span>

<span data-ttu-id="26aea-112">您已阅读本主题，并准备好配置混合连接后，请参阅[Business Server 和 Office 365 的 Skype 之间配置混合连接性](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="26aea-112">After you have read this topic and are ready to configure hybrid connectivity, see [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span> <span data-ttu-id="26aea-113">配置主题提供业务 online 设置您的本地部署和 Skype 之间的混合连接性的分步指导。</span><span class="sxs-lookup"><span data-stu-id="26aea-113">The configuration topics provide step-by-step guidance for setting up hybrid connectivity between your on-premises deployment and Skype for Business Online.</span></span>

<span data-ttu-id="26aea-114">（有关配置 Lync Server 2013 或 Lync Server 2010 混合部署的信息，请参阅[Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360)。）</span><span class="sxs-lookup"><span data-stu-id="26aea-114">(For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)</span></span>

## <a name="split-domain-functionality"></a><span data-ttu-id="26aea-115">拆分域功能</span><span class="sxs-lookup"><span data-stu-id="26aea-115">Split domain functionality</span></span>
<span data-ttu-id="26aea-116"><a name="BKMK_Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-116"></span></span>

 <span data-ttu-id="26aea-117">Skype 业务服务器的内部部署和 Skype 之间设置业务联机或团队的混合连接，您可以将一些用户驻留在本地和联机驻留的一些用户。</span><span class="sxs-lookup"><span data-stu-id="26aea-117">With hybrid connectivity set up between an on-premises deployment of Skype for Business Server and Skype for Business Online or Teams, you can have some users homed on-premises and some users homed online.</span></span>

<span data-ttu-id="26aea-118">此类型的配置有时称为"拆分域"— 这意味着用户的域名，例如，contoso.com，分别驻留在本地的企业服务器和 Skype 业务联机或团队使用 Skype，如下图中所示：</span><span class="sxs-lookup"><span data-stu-id="26aea-118">This type of configuration is sometimes referred to as "split domain"--meaning users of a domain, such as contoso.com, are split between using Skype for Business Server on premises and Skype for Business Online or Teams, as shown in the following diagram:</span></span>

![SfB 混合连接 - 拆分域](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

<span data-ttu-id="26aea-120">使用拆分域环境中：</span><span class="sxs-lookup"><span data-stu-id="26aea-120">With a split domain environment:</span></span>

- <span data-ttu-id="26aea-121">用户驻留在本地与业务服务器的内部部署 Skype 进行交互。</span><span class="sxs-lookup"><span data-stu-id="26aea-121">Users who are homed on premises interact with on-premises Skype for Business servers.</span></span> <span data-ttu-id="26aea-122">他们还可能有权访问在线服务，例如云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="26aea-122">They might also have access to online services, such as Cloud Voicemail.</span></span>

- <span data-ttu-id="26aea-123">联机驻留用户可能交互 Skype 业务或团队的联机服务。</span><span class="sxs-lookup"><span data-stu-id="26aea-123">Users who are homed online may interact with Skype for Business or Teams online services.</span></span>

- <span data-ttu-id="26aea-124">这两种环境中的用户可以使用即时消息、 参加会议呼叫或 VoIP 呼叫、 进行相互协作，依此类推。</span><span class="sxs-lookup"><span data-stu-id="26aea-124">Users from both environments can collaborate with each other by using Instant Messaging, participating in conference calls or VoIP calls, and so on.</span></span>

- <span data-ttu-id="26aea-125">Azure Active Directory 连接用于与 Office 365 同步您的本地目录。</span><span class="sxs-lookup"><span data-stu-id="26aea-125">Azure Active Directory Connect is used to synchronize your on-premises directory with Office 365.</span></span>

<span data-ttu-id="26aea-126">本地 Active Directory 是权威性的，即你必须执行下列操作以确保本地和在线用户可以相互发现：</span><span class="sxs-lookup"><span data-stu-id="26aea-126">The on-premises Active Directory is authoritative, which means that you must do the following to ensure that on-premises and online users are discoverable to one another:</span></span>

- <span data-ttu-id="26aea-127">所有用户应首先，在内部部署 Active Directory 中创建，然后同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="26aea-127">All users should be created in the on-premises Active Directory first, and then synchronized to Azure AD.</span></span>

- <span data-ttu-id="26aea-128">迁移到云中的用户必须具有业务计划 2 或团队许可证的任一 Skype。</span><span class="sxs-lookup"><span data-stu-id="26aea-128">Users who are moving to the cloud must have either a Skype for Business Plan 2 or Teams license.</span></span>

- <span data-ttu-id="26aea-129">如果您的用户想要充分利用附加的联机功能，如 Skype 会议广播或云语音邮件，您需要将其分配 Office 365 中的适当许可。</span><span class="sxs-lookup"><span data-stu-id="26aea-129">If your users want to take advantage of additional online features, such as Skype Meeting Broadcast or Cloud Voicemail, you need to assign them the appropriate license in Office 365.</span></span>

- <span data-ttu-id="26aea-130">为 Skype for Business Online 用户分配许可证后，你需要为 Skype for Business 或本地 Enterprise Voice 启用这些用户。</span><span class="sxs-lookup"><span data-stu-id="26aea-130">After Skype for Business Online users are assigned a license, you need to enable them for Skype for Business or for Enterprise Voice on premises.</span></span> <span data-ttu-id="26aea-131">有关详细信息，请参阅[启用本地的企业语音的用户](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="26aea-131">For more information, see [Enable the users for Enterprise Voice on premises](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md).</span></span> <span data-ttu-id="26aea-132">有关混合语音要求的详细信息，请参阅[Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="26aea-132">For more information about hybrid voice requirements, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>


## <a name="infrastructure-requirements"></a><span data-ttu-id="26aea-133">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="26aea-133">Infrastructure requirements</span></span>
<span data-ttu-id="26aea-134"><a name="BKMK_Infrastructure"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-134"></span></span>

<span data-ttu-id="26aea-135">若要实现您的内部部署环境与 Office 365 通信服务之间的混合连接，您需要满足以下基础结构要求。</span><span class="sxs-lookup"><span data-stu-id="26aea-135">To implement hybrid connectivity between your on-premises environment and Office 365 communication services, you need to meet the following infrastructure requirements.</span></span>

- <span data-ttu-id="26aea-136">一个本地部署的 Skype 业务服务器或受支持的拓扑中部署 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="26aea-136">A single on-premises deployment of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="26aea-137">请参阅本主题中的[拓扑要求](plan-hybrid-connectivity.md#BKMK_Topology)。</span><span class="sxs-lookup"><span data-stu-id="26aea-137">See [Topology requirements](plan-hybrid-connectivity.md#BKMK_Topology) in this topic.</span></span>

- <span data-ttu-id="26aea-138">Skype 业务 Online 启用的 Microsoft Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="26aea-138">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26aea-139">只能将混合配置的单个租户与你的本地部署结合使用。</span><span class="sxs-lookup"><span data-stu-id="26aea-139">You can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

- <span data-ttu-id="26aea-140">Skype Business Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="26aea-140">Skype for Business Server administrative tools.</span></span> <span data-ttu-id="26aea-141">（如果您使用 Lync Server 2013 或 Lync Server 2010，可以使用 Lync Server 2013 管理工具。</span><span class="sxs-lookup"><span data-stu-id="26aea-141">(If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="26aea-142">有关详细信息，请参阅[Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360)。）</span><span class="sxs-lookup"><span data-stu-id="26aea-142">For more information, see [Lync Server 2013 hybrid](https://go.microsoft.com/fwlink/p/?LinkId=617360).)</span></span>

- <span data-ttu-id="26aea-143">Azure Active Directory Connect 用于将你的本地目录与 Office 365 同步。</span><span class="sxs-lookup"><span data-stu-id="26aea-143">Azure Active Directory Connect to synchronize your on-premises directory with Office 365.</span></span> <span data-ttu-id="26aea-144">有关详细信息，请参阅[Azure AD 连接： 帐户和权限](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。</span><span class="sxs-lookup"><span data-stu-id="26aea-144">For more information, see [Azure AD Connect: Accounts and permissions](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).</span></span>

    <span data-ttu-id="26aea-p110">若要支持 Office 365 的单一登录，使用户能使用在本地所用的同一登录凭据，可以使用 Azure Active Directory (AAD) Connect 的密码同步功能。 还可以使用 Active Directory 联合身份验证服务 (AD FS) 来进行 Office 365 单一登录。 </span><span class="sxs-lookup"><span data-stu-id="26aea-p110">To support Single Sign-on with Office 365 so that users can use the same login credentials as they do for on premises, you can use the password sync features of Azure Active Directory (AAD) Connect. You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>

<span data-ttu-id="26aea-147">若要配置混合连接，还需要设置您的本地和联机环境之间的联盟和配置您的业务 Online 租户中为共享的会话初始协议 (SIP) 地址空间 Skype 上。</span><span class="sxs-lookup"><span data-stu-id="26aea-147">To configure hybrid connectivity, you will also need to set up federation between your on-premises and online environments, and configure your Skype for Business Online tenant for a shared Session Initiation Protocol (SIP) address space.</span></span> <span data-ttu-id="26aea-148">有关配置混合连接所需的步骤的详细信息，请参阅[配置混合连接性](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="26aea-148">For more information about the steps required to configure hybrid connectivity, see [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

<span data-ttu-id="26aea-149">配置混合连接后，可以业务联机或团队中将用户移动到 Skype。</span><span class="sxs-lookup"><span data-stu-id="26aea-149">After you configure hybrid connectivity, you can move users to Skype for Business Online or Teams.</span></span> <span data-ttu-id="26aea-150">有关详细信息，请参阅[移动到业务 online Skype 本地用户](move-users-from-on-premises-to-skype-for-business-online.md)和[移动用户从内部部署到团队](move-users-from-on-premises-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="26aea-150">For more information, see [Move users from on premises to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md) and [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md).</span></span>

## <a name="multi-forest-support"></a><span data-ttu-id="26aea-151">多林支持</span><span class="sxs-lookup"><span data-stu-id="26aea-151">Multi-forest support</span></span>
<span data-ttu-id="26aea-152"><a name="BKMK_MultiForest"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-152"></span></span>

<span data-ttu-id="26aea-153">如果满足下列要求，用户可以访问其他林中的 Skype for Business 功能：</span><span class="sxs-lookup"><span data-stu-id="26aea-153">Users can access Skype for Business functionality in another forest if the following requirements are met:</span></span>

- <span data-ttu-id="26aea-154">用户已正确同步到托管 Skype for Business 的林中：在混合配置中，这意味着用户必须作为已禁用的用户对象同步。</span><span class="sxs-lookup"><span data-stu-id="26aea-154">Users are properly synchronized into the forest that hosts Skype for Business: In hybrid configurations, this means that users must be synchronized as disabled user objects.</span></span>

- <span data-ttu-id="26aea-155">托管 Skype for Business 的林必须信任包含用户的林。</span><span class="sxs-lookup"><span data-stu-id="26aea-155">The forest hosting Skype for Business must trust the forest containing the users.</span></span>

<span data-ttu-id="26aea-156">有关多林混合方案的详细信息，请参阅[Configure hybrid for Business 的 Skype 的多林环境](configure-a-multi-forest-environment-for-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="26aea-156">For details on multi-forest hybrid scenarios, see [Configure a multi-forest environment for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).</span></span>

## <a name="administrator-credentials"></a><span data-ttu-id="26aea-157">管理员凭据</span><span class="sxs-lookup"><span data-stu-id="26aea-157">Administrator credentials</span></span>
<span data-ttu-id="26aea-158"><a name="BKMK_Credentials"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-158"></span></span>

<span data-ttu-id="26aea-159">当要求您提供您的管理员凭据时，使用的用户名和密码的管理员帐户为您的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="26aea-159">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="26aea-160">Azure Active Directory 联合身份验证、 目录同步、 单一登录，和将用户迁移到 Skype 配置业务 online 时，您还将使用这些凭据。</span><span class="sxs-lookup"><span data-stu-id="26aea-160">You will also use these credentials when you configure Azure Active Directory for federation, directory synchronization, single sign-on, and moving users to Skype for Business Online.</span></span>

## <a name="skype-for-business-online-powershell"></a><span data-ttu-id="26aea-161">Skype for Business Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="26aea-161">Skype for Business Online PowerShell</span></span>
<span data-ttu-id="26aea-162"><a name="BKMK_PowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-162"></span></span>

<span data-ttu-id="26aea-163">管理员现在可以使用 Windows PowerShell 管理 Skype 业务联机和其 Skype 业务联机用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26aea-163">Administrators now have the ability to use Windows PowerShell to manage Skype for Business Online and their Skype for Business Online user accounts.</span></span> <span data-ttu-id="26aea-164">若要执行此操作，您必须首先下载和安装的业务 Online 连接器模块从 Microsoft 下载中心下载 Skype。</span><span class="sxs-lookup"><span data-stu-id="26aea-164">To do this, you must first download and install the Skype for Business Online Connector Module from the Microsoft Download Center.</span></span> <span data-ttu-id="26aea-165">下载、 安装和使用 Skype 对业务联机连接器模块和 using Windows PowerShell to manage Skype 业务 online 的详细信息的详细信息，请参阅[Windows PowerShell 将计算机设置](https://technet.microsoft.com/library/dn362831.aspx)。</span><span class="sxs-lookup"><span data-stu-id="26aea-165">For more information on downloading, installing, and using the Skype for Business Online Connector Module, and for detailed information on using Windows PowerShell to manage Skype for Business Online, see [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span></span>

## <a name="skype-for-business-client-support"></a><span data-ttu-id="26aea-166">Skype for Business 客户端支持</span><span class="sxs-lookup"><span data-stu-id="26aea-166">Skype for Business client support</span></span>
<span data-ttu-id="26aea-167"><a name="BKMK_ClientSupport"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-167"></span></span>

<span data-ttu-id="26aea-168">客户端中支持的功能与本地和联机环境中提供的功能一样，存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="26aea-168">There are some differences in the features supported in clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="26aea-169">以下客户端支持与 Skype 业务 Online 混合部署中：</span><span class="sxs-lookup"><span data-stu-id="26aea-169">The following clients are supported with Skype for Business Online in a hybrid deployment:</span></span>

- <span data-ttu-id="26aea-170">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="26aea-170">Skype for Business</span></span>

- <span data-ttu-id="26aea-171">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="26aea-171">Lync 2013</span></span>

- <span data-ttu-id="26aea-172">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="26aea-172">Lync 2010</span></span>

- <span data-ttu-id="26aea-173">Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="26aea-173">Lync Windows Store app</span></span>

- <span data-ttu-id="26aea-174">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="26aea-174">Lync Web App</span></span>

- <span data-ttu-id="26aea-175">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="26aea-175">Lync Mobile</span></span>

- <span data-ttu-id="26aea-176">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="26aea-176">Lync for Mac 2011</span></span>

- <span data-ttu-id="26aea-177">Lync 会议室系统和 Skype 的业务会议室系统</span><span class="sxs-lookup"><span data-stu-id="26aea-177">Lync Room System and Skype for Business Room System</span></span>

- <span data-ttu-id="26aea-178">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="26aea-178">Lync Basic 2013</span></span>

- <span data-ttu-id="26aea-179">Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="26aea-179">Microsoft Surface Hub</span></span>

<span data-ttu-id="26aea-180">在决定要在其中家庭用户在组织中之前，您应当查看[for Business 的 Skype 的桌面客户端功能比较](../../sfbserver/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)以确定 Business Server Skype 的各种配置客户端支持。</span><span class="sxs-lookup"><span data-stu-id="26aea-180">Before you decide where you want to home users in your organization, you should review the [Desktop client feature comparison for Skype for Business](../../sfbserver/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) to determine the client support for the various configurations of Skype for Business Server.</span></span> <span data-ttu-id="26aea-181">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="26aea-181">See also:</span></span>

- [<span data-ttu-id="26aea-182">规划客户端和设备</span><span class="sxs-lookup"><span data-stu-id="26aea-182">Plan for clients and devices</span></span>](../../sfbserver/plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [<span data-ttu-id="26aea-183">Skype for Business 的移动客户端功能比较</span><span class="sxs-lookup"><span data-stu-id="26aea-183">Mobile client feature comparison for Skype for Business</span></span>](../../sfbserver/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a><span data-ttu-id="26aea-184">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="26aea-184">Topology requirements</span></span>
<span data-ttu-id="26aea-185"><a name="BKMK_Topology"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-185"></span></span>

<span data-ttu-id="26aea-186">业务 online 与 Skype 配置混合部署，您需要具备以下支持的拓扑结构之一：</span><span class="sxs-lookup"><span data-stu-id="26aea-186">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

- <span data-ttu-id="26aea-187">包含业务服务器 2015年运行 Skype 的所有服务器的业务服务器 2015年部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="26aea-187">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

- <span data-ttu-id="26aea-188">运行 Lync Server 2013 的所有服务器与 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="26aea-188">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

    <span data-ttu-id="26aea-189">混合语音连接，必须业务 2015; 的 Skype 被指定为联合身份验证边缘边缘服务器。边缘还需要 Skype 针对 Business Server 后端。</span><span class="sxs-lookup"><span data-stu-id="26aea-189">For hybrid voice connectivity, the Edge Server that is designated as Federation Edge must be Skype for Business 2015; the Edge also requires a Skype for Business Server backend.</span></span> <span data-ttu-id="26aea-190">你可能有一个池中没有任何用户。</span><span class="sxs-lookup"><span data-stu-id="26aea-190">You might have a pool with no users on it.</span></span>

- <span data-ttu-id="26aea-191">运行 Lync Server 2010 通过最新累积更新的所有服务器与 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="26aea-191">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>

  - <span data-ttu-id="26aea-192">联合身份验证边缘服务器和从联合身份验证边缘服务器的下一个跃点服务器必须运行 Lync Server 2010 通过最新累积更新。</span><span class="sxs-lookup"><span data-stu-id="26aea-192">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>

  - <span data-ttu-id="26aea-193">必须至少一台服务器或管理工作站上安装 Skype 业务服务器 2015年或 Lync Server 2013 管理工具。</span><span class="sxs-lookup"><span data-stu-id="26aea-193">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

- <span data-ttu-id="26aea-194">混合的 Lync Server 2013 和 Skype 业务服务器 2015年部署与运行业务服务器 2015 Skype 的至少一个站点中的以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="26aea-194">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>

  - <span data-ttu-id="26aea-195">至少一个企业版池或 Standard Edition 服务器 </span><span class="sxs-lookup"><span data-stu-id="26aea-195">At least one Enterprise Pool or Standard Edition server</span></span>

  - <span data-ttu-id="26aea-196">与 SIP 联盟关联的控制器池（如果存在）</span><span class="sxs-lookup"><span data-stu-id="26aea-196">The Director Pool associated with SIP federation, if it exists</span></span>

  - <span data-ttu-id="26aea-197">与 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="26aea-197">The Edge Pool associated with SIP federation</span></span>

- <span data-ttu-id="26aea-198">混合的 Lync Server 2010 和 Skype 业务服务器 2015年部署与运行业务服务器 2015 Skype 的至少一个站点中的以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="26aea-198">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>

  - <span data-ttu-id="26aea-199">至少一个企业版池或 Standard Edition 服务器 </span><span class="sxs-lookup"><span data-stu-id="26aea-199">At least one Enterprise Pool or Standard Edition server</span></span>

  - <span data-ttu-id="26aea-200">与 SIP 联盟关联的控制器池（如果存在）</span><span class="sxs-lookup"><span data-stu-id="26aea-200">The Director Pool associated with SIP federation, if it exists</span></span>

  - <span data-ttu-id="26aea-201">与站点的 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="26aea-201">The Edge Pool associated with SIP federation for the Site</span></span>

- <span data-ttu-id="26aea-202">混合的 Lync Server 2010 和 Lync Server 2013 部署与至少一个站点运行 Lync Server 2013 中的以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="26aea-202">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>

  - <span data-ttu-id="26aea-203">站点中至少一个企业版池或 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="26aea-203">At least one Enterprise Pool or Standard Edition server in the site</span></span>

  - <span data-ttu-id="26aea-204">与 SIP 联盟关联的控制器池（如果站点中存在）</span><span class="sxs-lookup"><span data-stu-id="26aea-204">The Director Pool associated with SIP federation, if it exists in the site</span></span>

  - <span data-ttu-id="26aea-205">与站点的 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="26aea-205">The Edge Pool associated with SIP federation for the site</span></span>

## <a name="federation-allowedblocked-lists-requirements"></a><span data-ttu-id="26aea-206">联盟允许/阻止列表的要求</span><span class="sxs-lookup"><span data-stu-id="26aea-206">Federation Allowed/Blocked Lists requirements</span></span>
<span data-ttu-id="26aea-207"><a name="BKMK_Federation"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-207"></span></span>

<span data-ttu-id="26aea-208">允许域列表包括已配置合作伙伴“边缘”完全限定域名 (FQDN) 的域。</span><span class="sxs-lookup"><span data-stu-id="26aea-208">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="26aea-209">这些域有时也称允许的合作伙伴服务器 或直接联盟合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="26aea-209">These are sometimes referred to as allowed partner servers or direct federation partners.</span></span> <span data-ttu-id="26aea-210">您应熟悉开放联盟和封闭联盟（在本地部署中分别称为合作伙伴发现 和允许的合作伙伴域列表）之间的差异。</span><span class="sxs-lookup"><span data-stu-id="26aea-210">You should be familiar with the difference between Open Federation and Closed Federation, referred to as partner discovery and allowed partner domain list, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="26aea-211">必须满足以下要求才能成功配置混合部署：</span><span class="sxs-lookup"><span data-stu-id="26aea-211">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

- <span data-ttu-id="26aea-p119">为您的本地部署和您的 Office 365 租户配置的域匹配必须相同。如果在本地部署中启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。如果未启用合作伙伴发现，则必须为您的联机租户配置封闭联盟。</span><span class="sxs-lookup"><span data-stu-id="26aea-p119">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

- <span data-ttu-id="26aea-215">本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="26aea-215">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

- <span data-ttu-id="26aea-216">本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="26aea-216">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

- <span data-ttu-id="26aea-217">Online 租户，使用适用于业务 Online 控制面板 Skype 配置的外部通信，必须启用联盟。</span><span class="sxs-lookup"><span data-stu-id="26aea-217">Federation must be enabled for the external communications for the online tenant, which is configured by using the Skype for Business Online Control Panel.</span></span>

## <a name="dns-settings"></a><span data-ttu-id="26aea-218">DNS 设置</span><span class="sxs-lookup"><span data-stu-id="26aea-218">DNS settings</span></span>
<span data-ttu-id="26aea-219"><a name="BKMK_DNS"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-219"></span></span>

<span data-ttu-id="26aea-220">创建混合部署的 DNS 记录时，所有业务外部 DNS 记录的 Skype 应都指向的内部部署基础结构。</span><span class="sxs-lookup"><span data-stu-id="26aea-220">When creating DNS records for hybrid deployments, all Skype for Business external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="26aea-221">有关所需的 DNS 记录的详细信息，请参阅[Skype 业务服务器的 DNS 要求](../../sfbserver/plan-your-deployment/network-requirements/dns.md)。</span><span class="sxs-lookup"><span data-stu-id="26aea-221">For details on required DNS records, please refer to [DNS requirements for Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).</span></span>

<span data-ttu-id="26aea-222">此外，您需要以确保 DNS 解析下表中所述的本地部署中：</span><span class="sxs-lookup"><span data-stu-id="26aea-222">Additionally, you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>

|<span data-ttu-id="26aea-223">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="26aea-223">DNS record</span></span>  <br/> |<span data-ttu-id="26aea-224">解析者</span><span class="sxs-lookup"><span data-stu-id="26aea-224">Resolvable by</span></span>  <br/> |<span data-ttu-id="26aea-225">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="26aea-225">DNS requirement</span></span>  <br/> |
|:-----|:-----|:-----|
|<span data-ttu-id="26aea-226">_Sipfederationtls._tcp 的 DNS SRV 记录。\<sipdomain.com\>用于所有支持的 SIP 域解析为访问边缘外部 IP(s)</span><span class="sxs-lookup"><span data-stu-id="26aea-226">DNS SRV record for _sipfederationtls._tcp.\<sipdomain.com\> for all supported SIP domains resolving to Access Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="26aea-227">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="26aea-227">Edge server(s)</span></span>  <br/> |<span data-ttu-id="26aea-p121">在混合配置中启用联盟通信。边缘服务器需要知道在什么位置为 SIP 域路由分布在本地设备和在线设备上的联盟流量。</span><span class="sxs-lookup"><span data-stu-id="26aea-p121">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span>  <br/> <span data-ttu-id="26aea-230">必须使用用户名与 SRV 记录中的域之间的严格 DNS 名称匹配。</span><span class="sxs-lookup"><span data-stu-id="26aea-230">Must use strict DNS name matching between the domain in the user name and the SRV record.</span></span>  <br/> |
|<span data-ttu-id="26aea-231">边缘 Web 会议服务 FQDN 的 DNS A 记录，例如解析为 Web 会议边缘外部 IP 的 webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="26aea-231">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="26aea-232">内部企业网络连接的用户的计算机</span><span class="sxs-lookup"><span data-stu-id="26aea-232">Internal corporate network connected users' computers</span></span>  <br/> |<span data-ttu-id="26aea-p122">让在线用户能够在本地托管会议中演示或查看内容。内容包括 PowerPoint 文件、白板、轮询和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="26aea-p122">Enable online users to present or view content in on-premises hosted meetings. Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span>  <br/> |

<span data-ttu-id="26aea-235">根据 DNS 在您的组织中如何配置，您可能需要将这些记录添加到内部托管 DNS 区域，以便相应的 SIP 域能够提供对这些记录的内部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="26aea-235">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

## <a name="firewall-considerations"></a><span data-ttu-id="26aea-236">防火墙注意事项</span><span class="sxs-lookup"><span data-stu-id="26aea-236">Firewall considerations</span></span>
<span data-ttu-id="26aea-237"><a name="BKMK_Firewall"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-237"></span></span>

<span data-ttu-id="26aea-p123">您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。</span><span class="sxs-lookup"><span data-stu-id="26aea-p123">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="26aea-240">根据您的 Microsoft Online Services 数据中心的位置，您还必须配置网络防火墙设备以接受连接基于通配符域名 (例如，来自所有通讯\*。 outlook.com)。</span><span class="sxs-lookup"><span data-stu-id="26aea-240">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="26aea-241">如果贵组织的防火墙不支持通配符名称配置，您将需要手动确定您希望允许的 IP 地址范围和指定的端口。</span><span class="sxs-lookup"><span data-stu-id="26aea-241">If your organization's firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="26aea-242">有关详细信息，请参阅 [Office 365 URL 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?LinkId=252942)。</span><span class="sxs-lookup"><span data-stu-id="26aea-242">For more information, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?LinkId=252942).</span></span>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="26aea-243">端口和协议要求</span><span class="sxs-lookup"><span data-stu-id="26aea-243">Port and protocol requirements</span></span>
<span data-ttu-id="26aea-244"><a name="BKMK_Ports"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-244"></span></span>

<span data-ttu-id="26aea-245">除了内部通信的端口要求，还必须配置以下端口以启用混合连接：</span><span class="sxs-lookup"><span data-stu-id="26aea-245">In addition to the port requirements for internal communication, you must also configure the following ports to enable hybrid connectivity:</span></span>


|<span data-ttu-id="26aea-246">**协议**</span><span class="sxs-lookup"><span data-stu-id="26aea-246">**Protocol**</span></span>|<span data-ttu-id="26aea-247">**TCP 或 UDP**</span><span class="sxs-lookup"><span data-stu-id="26aea-247">**TCP or UDP**</span></span>|<span data-ttu-id="26aea-248">**源 IP**</span><span class="sxs-lookup"><span data-stu-id="26aea-248">**Source IP**</span></span>|<span data-ttu-id="26aea-249">**目标 IP**</span><span class="sxs-lookup"><span data-stu-id="26aea-249">**Destination IP**</span></span>|<span data-ttu-id="26aea-250">**源端口**</span><span class="sxs-lookup"><span data-stu-id="26aea-250">**Source port**</span></span>|<span data-ttu-id="26aea-251">**目标端口**</span><span class="sxs-lookup"><span data-stu-id="26aea-251">**Destination port**</span></span>|<span data-ttu-id="26aea-252">**说明**</span><span class="sxs-lookup"><span data-stu-id="26aea-252">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="26aea-253">SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="26aea-253">SIP (MTLS)</span></span>  <br/> |<span data-ttu-id="26aea-254">TCP</span><span class="sxs-lookup"><span data-stu-id="26aea-254">TCP</span></span>  <br/> |<span data-ttu-id="26aea-255">访问边缘</span><span class="sxs-lookup"><span data-stu-id="26aea-255">Access Edge</span></span>  <br/> |<span data-ttu-id="26aea-256">Office 365</span><span class="sxs-lookup"><span data-stu-id="26aea-256">Office 365</span></span>  <br/> |<span data-ttu-id="26aea-257">任何</span><span class="sxs-lookup"><span data-stu-id="26aea-257">Any</span></span>  <br/> |<span data-ttu-id="26aea-258">5061</span><span class="sxs-lookup"><span data-stu-id="26aea-258">5061</span></span>  <br/> |<span data-ttu-id="26aea-259">信号</span><span class="sxs-lookup"><span data-stu-id="26aea-259">Signaling</span></span>  <br/> |
|<span data-ttu-id="26aea-260">SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="26aea-260">SIP (MTLS)</span></span>  <br/> |<span data-ttu-id="26aea-261">TCP</span><span class="sxs-lookup"><span data-stu-id="26aea-261">TCP</span></span>  <br/> |<span data-ttu-id="26aea-262">Office 365</span><span class="sxs-lookup"><span data-stu-id="26aea-262">Office 365</span></span>  <br/> |<span data-ttu-id="26aea-263">访问边缘</span><span class="sxs-lookup"><span data-stu-id="26aea-263">Access Edge</span></span>  <br/> |<span data-ttu-id="26aea-264">任何</span><span class="sxs-lookup"><span data-stu-id="26aea-264">Any</span></span>  <br/> |<span data-ttu-id="26aea-265">5061</span><span class="sxs-lookup"><span data-stu-id="26aea-265">5061</span></span>  <br/> |<span data-ttu-id="26aea-266">信号</span><span class="sxs-lookup"><span data-stu-id="26aea-266">Signaling</span></span>  <br/> |
|<span data-ttu-id="26aea-267">STUN</span><span class="sxs-lookup"><span data-stu-id="26aea-267">STUN</span></span>  <br/> |<span data-ttu-id="26aea-268">TCP</span><span class="sxs-lookup"><span data-stu-id="26aea-268">TCP</span></span>  <br/> |<span data-ttu-id="26aea-269">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="26aea-269">A/V Edge</span></span>  <br/> |<span data-ttu-id="26aea-270">Office 365</span><span class="sxs-lookup"><span data-stu-id="26aea-270">Office 365</span></span>  <br/> |<span data-ttu-id="26aea-271">50000-59999</span><span class="sxs-lookup"><span data-stu-id="26aea-271">50000-59999</span></span>  <br/> |<span data-ttu-id="26aea-272">443，50000-59999</span><span class="sxs-lookup"><span data-stu-id="26aea-272">443, 50000-59999</span></span>  <br/> |<span data-ttu-id="26aea-273">为音频、视频、应用程序共享会话打开</span><span class="sxs-lookup"><span data-stu-id="26aea-273">Open for audio, video, application sharing sessions</span></span>  <br/> |
|<span data-ttu-id="26aea-274">STUN</span><span class="sxs-lookup"><span data-stu-id="26aea-274">STUN</span></span>  <br/> |<span data-ttu-id="26aea-275">TCP</span><span class="sxs-lookup"><span data-stu-id="26aea-275">TCP</span></span>  <br/> |<span data-ttu-id="26aea-276">Office 365</span><span class="sxs-lookup"><span data-stu-id="26aea-276">Office 365</span></span>  <br/> |<span data-ttu-id="26aea-277">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="26aea-277">A/V Edge</span></span>  <br/> |<span data-ttu-id="26aea-278">443</span><span class="sxs-lookup"><span data-stu-id="26aea-278">443</span></span>  <br/> |<span data-ttu-id="26aea-279">50000-59999</span><span class="sxs-lookup"><span data-stu-id="26aea-279">50000-59999</span></span>  <br/> |<span data-ttu-id="26aea-280">为音频、视频、应用程序共享会话打开</span><span class="sxs-lookup"><span data-stu-id="26aea-280">Open for audio, video, application sharing sessions</span></span>  <br/> |
|<span data-ttu-id="26aea-281">STUN</span><span class="sxs-lookup"><span data-stu-id="26aea-281">STUN</span></span>  <br/> |<span data-ttu-id="26aea-282">UDP</span><span class="sxs-lookup"><span data-stu-id="26aea-282">UDP</span></span>  <br/> |<span data-ttu-id="26aea-283">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="26aea-283">A/V Edge</span></span>  <br/> |<span data-ttu-id="26aea-284">Office 365</span><span class="sxs-lookup"><span data-stu-id="26aea-284">Office 365</span></span>  <br/> |<span data-ttu-id="26aea-285">3478</span><span class="sxs-lookup"><span data-stu-id="26aea-285">3478</span></span>  <br/> |<span data-ttu-id="26aea-286">3478</span><span class="sxs-lookup"><span data-stu-id="26aea-286">3478</span></span>  <br/> |<span data-ttu-id="26aea-287">为音频、视频会话打开</span><span class="sxs-lookup"><span data-stu-id="26aea-287">Open for audio, video sessions</span></span>  <br/> |
|<span data-ttu-id="26aea-288">STUN</span><span class="sxs-lookup"><span data-stu-id="26aea-288">STUN</span></span>  <br/> |<span data-ttu-id="26aea-289">UDP</span><span class="sxs-lookup"><span data-stu-id="26aea-289">UDP</span></span>  <br/> |<span data-ttu-id="26aea-290">Office 365</span><span class="sxs-lookup"><span data-stu-id="26aea-290">Office 365</span></span>  <br/> |<span data-ttu-id="26aea-291">A/V 边缘</span><span class="sxs-lookup"><span data-stu-id="26aea-291">A/V Edge</span></span>  <br/> |<span data-ttu-id="26aea-292">3478</span><span class="sxs-lookup"><span data-stu-id="26aea-292">3478</span></span>  <br/> |<span data-ttu-id="26aea-293">3478</span><span class="sxs-lookup"><span data-stu-id="26aea-293">3478</span></span>  <br/> |<span data-ttu-id="26aea-294">为音频、视频会话打开</span><span class="sxs-lookup"><span data-stu-id="26aea-294">Open for audio, video sessions</span></span>  <br/> |

<span data-ttu-id="26aea-295">有关端口和防火墙的边缘服务器规划的详细信息，请参阅[Skype 业务服务器中的边缘服务器环境要求](../../sfbserver/plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26aea-295">For more information about port and firewall planning for Edge Server, see [Edge Server environmental requirements in Skype for Business Server](../../sfbserver/plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md).</span></span> <span data-ttu-id="26aea-296">另请参阅[Port and protocol requirements for servers](../../sfbserver/plan-your-deployment/network-requirements/ports-and-protocols.md)和[协议工作负荷图](https://go.microsoft.com/fwlink/p/?LinkId=550989)。</span><span class="sxs-lookup"><span data-stu-id="26aea-296">See also [Port and protocol requirements for servers](../../sfbserver/plan-your-deployment/network-requirements/ports-and-protocols.md) and the [Protocol workloads diagram](https://go.microsoft.com/fwlink/p/?LinkId=550989).</span></span>

## <a name="user-accounts-and-data"></a><span data-ttu-id="26aea-297">用户帐户和数据</span><span class="sxs-lookup"><span data-stu-id="26aea-297">User accounts and data</span></span>
<span data-ttu-id="26aea-298"><a name="BKMK_UserAccounts"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-298"></span></span>

<span data-ttu-id="26aea-299">在混合部署中，您想要联机承载任何用户必须先创建在本地部署中，以便在 Active Directory 域服务中创建的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26aea-299">In a hybrid deployment, any user who you want to home online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="26aea-300">然后，您可以将用户移动到 Skype 业务 online，其中将移动用户的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="26aea-300">You can then move the user to Skype for Business Online, which will move the user's contact list.</span></span>

<span data-ttu-id="26aea-301">在同步您的本地部署和使用 AAD 连接的 online 租户之间的用户帐户时，您需要同步的 AD 帐户为在组织中的业务或 Lync 用户的所有 Skype 即使用户未联机移动到。</span><span class="sxs-lookup"><span data-stu-id="26aea-301">When you synchronize user accounts between your on-premises deployment and online tenant using AAD Connect, you need to synchronize the AD accounts for all Skype for Business or Lync users in your organization, even if users are not moved to online.</span></span> <span data-ttu-id="26aea-302">如果未同步所有用户，则组织中本地和联机用户之间的通信可能无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="26aea-302">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26aea-303">所有用户管理，包括用户的本地和 Skype 之间移动业务 online，都必须使用最新的安装管理工具版本。</span><span class="sxs-lookup"><span data-stu-id="26aea-303">All user management, including user moves between on-premises and Skype for Business Online, must be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="26aea-304">必须具有对现有的内部部署和 Internet 连接访问的单独服务器上安装管理工具。</span><span class="sxs-lookup"><span data-stu-id="26aea-304">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="26aea-305">此 cmdlet 将用户从您的本地部署迁移到 Skype 业务 online， [Move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps)，必须从管理工具连接到内部部署运行。</span><span class="sxs-lookup"><span data-stu-id="26aea-305">The cmdlet to move users from your on-premises deployment to Skype for Business Online, [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser?view=skype-ps), must be run from the administrative tools connected to your on-premises deployment.</span></span> <span data-ttu-id="26aea-306">有关移动用户的详细信息，请参阅[移动用户从本地到业务 online Skype](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="26aea-306">For more information about moving users, see [Move users from on premises to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>

<span data-ttu-id="26aea-307">规划混合部署时，您还应考虑与用户相关的以下问题：</span><span class="sxs-lookup"><span data-stu-id="26aea-307">You should also consider the following user-related issues when planning for a hybrid deployment:</span></span>

- <span data-ttu-id="26aea-308">**用户联系人**为 Lync Online 用户的联系人的限制为 250 个字符。</span><span class="sxs-lookup"><span data-stu-id="26aea-308">**User contacts** The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="26aea-309">当帐户移至 Lync Online，超出该号码的任何联系人将从用户的联系人列表中删除。</span><span class="sxs-lookup"><span data-stu-id="26aea-309">Any contacts beyond that number will be removed from the user's contact list when the account is moved to Lync Online.</span></span>

- <span data-ttu-id="26aea-310">**即时消息和状态**使用用户帐户都将迁移的用户联系人列表、 组和访问控制列表 (Acl)。</span><span class="sxs-lookup"><span data-stu-id="26aea-310">**Instant Messaging and Presence** User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

- <span data-ttu-id="26aea-311">**会议数据、 会议内容和计划的会议**此内容不会迁移用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26aea-311">**Conferencing data, meeting content, and scheduled meetings** This content is not migrated with the user account.</span></span> <span data-ttu-id="26aea-312">用户必须在其帐户迁移到 Lync Online 之后重新安排会议。</span><span class="sxs-lookup"><span data-stu-id="26aea-312">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

## <a name="user-policies-and-features"></a><span data-ttu-id="26aea-313">用户策略和功能</span><span class="sxs-lookup"><span data-stu-id="26aea-313">User policies and features</span></span>
<span data-ttu-id="26aea-314"><a name="BKMK_UserPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="26aea-314"></span></span>

- <span data-ttu-id="26aea-315">在混合环境中，可以为本地或联机用户（但不是同时）启用即时消息和会议。</span><span class="sxs-lookup"><span data-stu-id="26aea-315">In a hybrid environment, users can be enabled for Instant Messaging and conferencing (meetings) either on premises or online, but not both simultaneously.</span></span>

- <span data-ttu-id="26aea-316">**客户端支持**他们会移动到 Skype 业务 online 时，某些用户可能需要新的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="26aea-316">**Client support** Some users may require a new client version when they are moved to Skype for Business Online.</span></span> <span data-ttu-id="26aea-317">为 Office Communications Server 2007 R2，用户必须将移动到 Skype 之前迁移到 Skype 业务 online 业务服务器或 Lync Server 2013 的池。</span><span class="sxs-lookup"><span data-stu-id="26aea-317">For Office Communications Server 2007 R2, users must be moved to a Skype for Business Server or Lync Server 2013 pool prior to migration to Skype for Business Online.</span></span>

- <span data-ttu-id="26aea-318">**在本地策略和配置 （非用户）** 联机和本地策略要求单独的配置。</span><span class="sxs-lookup"><span data-stu-id="26aea-318">**On-premises policies and configuration (non-user)** Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="26aea-319">无法设置适用于二者的全局策略。</span><span class="sxs-lookup"><span data-stu-id="26aea-319">You cannot set global policies that apply to both.</span></span>
