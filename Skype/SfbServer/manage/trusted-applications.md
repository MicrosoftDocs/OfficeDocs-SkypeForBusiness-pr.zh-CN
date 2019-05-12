---
title: 管理受信任应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 受信任的应用程序是基于受 Business Server Skype 的 Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 的应用程序。
ms.openlocfilehash: 0f483cc0a1a3a9e7dad881fc40819a9c27dacdec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911866"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="56e0c-103">管理业务服务器中 Skype 的受信任应用程序</span><span class="sxs-lookup"><span data-stu-id="56e0c-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="56e0c-104">*受信任应用程序*是基于受 Business Server Skype 的 Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="56e0c-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="56e0c-105">有关 UCMA 应用程序的详细信息，请参阅"统一通信托管 API 3.0 Core SDK 文档"在http://go.microsoft.com/fwlink/p/?linkId=210320。</span><span class="sxs-lookup"><span data-stu-id="56e0c-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="56e0c-106">若要成功发布、 启用或禁用拓扑时添加或删除服务器角色，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="56e0c-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="56e0c-107">使用本文以了解如何配置新的受信任应用程序服务器、 查看受信任的应用程序的列表和查看受信任应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="56e0c-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="56e0c-108">配置新的受信任应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="56e0c-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="56e0c-109">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="56e0c-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="56e0c-110">启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server 拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="56e0c-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="56e0c-111">选择**下载从现有部署的拓扑**，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="56e0c-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="56e0c-112">在**将拓扑另存为**对话框中，单击您想要使用，该拓扑生成器文件，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="56e0c-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="56e0c-113">在左窗格中，右键单击**受信任应用程序服务器**，然后单击**新建受信任应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="56e0c-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="56e0c-114">是它将包含单服务器还是多服务器，然后单击**下一步**，请输入的受信任应用程序池中，选择的**池 FQDN** 。</span><span class="sxs-lookup"><span data-stu-id="56e0c-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="56e0c-115">在**选择下一个跃点**页上，从列表中，选择 Business Server 前端池的 Skype。</span><span class="sxs-lookup"><span data-stu-id="56e0c-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="56e0c-116">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="56e0c-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="56e0c-117">选择顶层节点**Skype 业务服务器**，，然后单击从**操作**菜单的**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="56e0c-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="56e0c-118">**受信任应用程序池**应已成功创建且与正确的前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="56e0c-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="56e0c-119">查看受信任应用程序的列表</span><span class="sxs-lookup"><span data-stu-id="56e0c-119">View a list of trusted applications</span></span>

<span data-ttu-id="56e0c-120">您可以使用业务 Server Control Panel Skype 查看已在您 Skype 业务服务器环境中部署的受信任应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="56e0c-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="56e0c-121">受信任的应用程序是基于受 Business Server Skype 的 Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="56e0c-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="56e0c-122">以下列表概述了此信任关系：</span><span class="sxs-lookup"><span data-stu-id="56e0c-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="56e0c-123">受信任应用程序不会要求进行身份验证 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="56e0c-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="56e0c-124">受信任应用程序不会限制进行 Skype 业务服务器的 SIP 事务、 连接或传出语音 (Voip) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="56e0c-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="56e0c-125">受信任应用程序可模拟任何用户，并可以加入会议而不出现在名单中。</span><span class="sxs-lookup"><span data-stu-id="56e0c-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="56e0c-126">受信任应用程序是高可用性和恢复能力。</span><span class="sxs-lookup"><span data-stu-id="56e0c-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="56e0c-127">在业务 Server 控制面板的 Skype，您可以看到应用程序名称、 它们运行时所在的池以及它们使用的端口。</span><span class="sxs-lookup"><span data-stu-id="56e0c-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="56e0c-128">若要查看的受信任应用程序列表</span><span class="sxs-lookup"><span data-stu-id="56e0c-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="56e0c-129">使用分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="56e0c-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="56e0c-130">有关业务服务器 Skype 中提供的预定义管理角色的详细信息，请参阅[基于角色的访问控制 (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="56e0c-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="56e0c-131">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="56e0c-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="56e0c-132">在左侧的导航栏中，单击**拓扑**，，然后单击**受信任应用程序**。</span><span class="sxs-lookup"><span data-stu-id="56e0c-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="56e0c-133">在**受信任应用程序**页上，单击某个列标题进行排序的应用程序中，如果需要。</span><span class="sxs-lookup"><span data-stu-id="56e0c-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="56e0c-134">查看受信任应用程序信息</span><span class="sxs-lookup"><span data-stu-id="56e0c-134">View trusted application information</span></span>

<span data-ttu-id="56e0c-135">您可以使用 Windows PowerShell 和**Get-cstrustedapplication** cmdlet 查看有关受信任的应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="56e0c-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="56e0c-136">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="56e0c-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="56e0c-137">若要查看受信任应用程序</span><span class="sxs-lookup"><span data-stu-id="56e0c-137">To view trusted applications</span></span>

<span data-ttu-id="56e0c-138">若要查看所有受信任应用程序，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="56e0c-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="56e0c-139">此命令将返回类似于每个受信任的应用程序的以下信息：</span><span class="sxs-lookup"><span data-stu-id="56e0c-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="56e0c-140">有关详细信息，请参阅[Get-cstrustedapplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)。</span><span class="sxs-lookup"><span data-stu-id="56e0c-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
