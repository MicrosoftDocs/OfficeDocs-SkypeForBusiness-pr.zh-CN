---
title: 管理受信任的应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 受信任的应用程序是基于 Microsoft 统一通信托管 API (UCMA) 3.0 Core SDK 受 Skype for Business Server 信任的应用程序。
ms.openlocfilehash: 272785cd1dcfe0bf21f7ac2b5ab64f36646237eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275064"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="4d6d6-103">在 Skype for Business 服务器中管理受信任的应用程序</span><span class="sxs-lookup"><span data-stu-id="4d6d6-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="4d6d6-104">*受信任的应用程序*是基于 Microsoft 统一通信托管 API (UCMA) 3.0 Core SDK 受 Skype For business Server 信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="4d6d6-105">有关 UCMA 应用程序的详细信息, 请参阅 "统一通信托管 API 3.0 核心 SDK http://go.microsoft.com/fwlink/p/?linkId=210320文档"。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="4d6d6-106">若要在添加或删除服务器角色时成功发布、启用或禁用拓扑, 您应以 RTCUniversalServerAdmins 和域管理员组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="4d6d6-107">使用本文了解如何配置新的受信任的应用程序服务器、查看受信任的应用程序列表以及查看受信任的应用程序信息。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="4d6d6-108">配置新的受信任的应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="4d6d6-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="4d6d6-109">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="4d6d6-110">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 "skype for business**服务器**", 然后单击 " **skype for business 服务器拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="4d6d6-111">选择 "**从现有部署下载拓扑**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="4d6d6-112">在 "**将拓扑另存为**" 对话框中, 单击要使用的拓扑生成器文件, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="4d6d6-113">在左窗格中, 右键单击 "**受信任的应用程序服务器**", 然后单击 "**新建受信任的应用程序池**"。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="4d6d6-114">输入受信任的应用程序池的**池 FQDN** , 选择它是单服务器还是多服务器, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="4d6d6-115">在 "**选择下一个跃点**" 页面上, 从列表中选择 "Skype For Business 服务器前端池"。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="4d6d6-116">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="4d6d6-117">选择顶部节点**Skype for Business 服务器**, 然后从 "**操作**" 菜单中单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="4d6d6-118">**受信任的应用程序池**应已成功创建并与正确的前端池关联。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="4d6d6-119">查看受信任的应用程序列表</span><span class="sxs-lookup"><span data-stu-id="4d6d6-119">View a list of trusted applications</span></span>

<span data-ttu-id="4d6d6-120">您可以使用 Skype for Business 服务器控制面板查看您在 Skype for business 服务器环境中部署的受信任的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="4d6d6-121">受信任的应用程序是基于 Microsoft 统一通信托管 API (UCMA) 3.0 Core SDK 受 Skype for Business Server 信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="4d6d6-122">下表总结了此信任关系:</span><span class="sxs-lookup"><span data-stu-id="4d6d6-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="4d6d6-123">受信任的应用程序不会受到 Skype for Business 服务器的身份验证的挑战。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="4d6d6-124">Skype for Business Server 不会阻止受信任的应用程序进行 SIP 交易、连接或通过 Internet 协议 (VoIP) 呼叫发出语音。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="4d6d6-125">受信任的应用程序可以模拟任何用户, 并且可以加入会议, 而无需出现在海报中。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="4d6d6-126">受信任的应用程序高度可用且具有弹性。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="4d6d6-127">在 Skype for Business 服务器控制面板中, 你可以看到应用程序的名称、运行的池以及它们使用的端口。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="4d6d6-128">查看受信任的应用程序列表</span><span class="sxs-lookup"><span data-stu-id="4d6d6-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="4d6d6-129">使用分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="4d6d6-130">有关 Skype for Business Server 中可用的预定义管理角色的详细信息, 请参阅[基于角色的访问控制 (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="4d6d6-131">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="4d6d6-132">在左侧导航栏中, 单击 "**拓扑**", 然后单击 "**受信任的应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="4d6d6-133">如果需要, 请在 "**受信任的应用程序**" 页面上, 单击列标题以对应用程序进行排序。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="4d6d6-134">查看受信任的应用程序信息</span><span class="sxs-lookup"><span data-stu-id="4d6d6-134">View trusted application information</span></span>

<span data-ttu-id="4d6d6-135">你可以使用 Windows PowerShell 和**CsTrustedApplication** cmdlet 查看有关你的受信任的应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="4d6d6-136">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="4d6d6-137">查看受信任的应用程序</span><span class="sxs-lookup"><span data-stu-id="4d6d6-137">To view trusted applications</span></span>

<span data-ttu-id="4d6d6-138">若要查看所有受信任的应用程序, 请在 Skype for Business Server 命令行管理程序中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="4d6d6-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="4d6d6-139">此命令针对每个受信任的应用程序返回类似于以下内容的信息:</span><span class="sxs-lookup"><span data-stu-id="4d6d6-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="4d6d6-140">有关详细信息, 请参阅[CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)。</span><span class="sxs-lookup"><span data-stu-id="4d6d6-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
