---
title: 'Lync Server 2013: 在 Microsoft Exchange 上配置统一消息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcbdbfbca5f532b1ca192cc0e9d89e93e3c8acb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="b18ab-102">在 Microsoft Exchange for Lync Server 2013 上配置统一消息</span><span class="sxs-lookup"><span data-stu-id="b18ab-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b18ab-103">_**主题上次修改时间:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="b18ab-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="b18ab-104">本主题介绍如何在 Microsoft Exchange Server 上配置 Exchange 统一消息 (UM), 以便与企业语音配合使用。</span><span class="sxs-lookup"><span data-stu-id="b18ab-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b18ab-105">本主题中的 cmdlet 示例提供 exchange 2007 版本的 Exchange 命令行管理程序的语法。</span><span class="sxs-lookup"><span data-stu-id="b18ab-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="b18ab-106">如果您运行的是 Exchange 2010 或 Exchange 2013, 请参阅参考的相应文档。</span><span class="sxs-lookup"><span data-stu-id="b18ab-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="b18ab-107">配置运行 Exchange Server UM 的服务器</span><span class="sxs-lookup"><span data-stu-id="b18ab-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="b18ab-108">为您的每个企业语音位置配置文件创建 UM 会话初始协议 (SIP) 统一资源标识符 (URI) 的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b18ab-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="b18ab-109">如果你选择使用 Exchange 管理控制台, 请使用安全设置 "安全设置" **(首选)** 创建新的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b18ab-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b18ab-110">如果将 "安全设置" 值设置为 " <STRONG>Sip 安全</STRONG>" 以仅对 sip 通信加密需要加密, 请注意, 如果将前端池配置为需要加密, 则拨号计划中的此安全设置不是足够的, 这意味着该池要求对 SIP 和 RTP 通信进行加密。</span><span class="sxs-lookup"><span data-stu-id="b18ab-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="b18ab-111">当拨号计划和池安全设置不兼容时, 从前端池中调用 Exchange UM 的所有呼叫都将失败, 从而导致错误, 表明您的 "安全设置不兼容"。</span><span class="sxs-lookup"><span data-stu-id="b18ab-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="b18ab-112">如果您使用的是 Exchange 命令行管理程序, 请键入:</span><span class="sxs-lookup"><span data-stu-id="b18ab-112">If you use the Exchange Management Shell, type:</span></span>
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    <span data-ttu-id="b18ab-113">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b18ab-113">For details, see:</span></span>
    
      - <span data-ttu-id="b18ab-114">有关 Office 通信服务器 2007, 请参阅 "如何创建统一消息 SIP URI 拨号计划" [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632)和 "新-UMDialplan: Exchange 2007 帮助"。 [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)</span><span class="sxs-lookup"><span data-stu-id="b18ab-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="b18ab-115">对于 Exchange 2010, 请参阅 "创建 UM 拨号计划" [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674)和 "新-UMDialplan: Exchange 2010 帮助"。 [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)</span><span class="sxs-lookup"><span data-stu-id="b18ab-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="b18ab-116">有关 Exchange 2013, 请参阅的[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"统一消息"。</span><span class="sxs-lookup"><span data-stu-id="b18ab-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b18ab-117">选择的安全级别是<STRONG>SIPSecured</STRONG>还是安全级别<STRONG></STRONG>取决于是否为媒体加密激活或停用安全实时传输协议 (SRTP)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="b18ab-118">对于 Lync Server 2010 与 Exchange UM 的集成, 这应对应于 Lync Server 媒体配置中的加密级别。</span><span class="sxs-lookup"><span data-stu-id="b18ab-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="b18ab-119">可通过运行<STRONG>CsMediaConfiguration</STRONG> Cmdlet 查看 Lync Server 媒体配置。</span><span class="sxs-lookup"><span data-stu-id="b18ab-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="b18ab-120">有关详细信息, 请参阅 Lync Server Management Shell 文档中的 CsMediaConfiguration。</span><span class="sxs-lookup"><span data-stu-id="b18ab-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="b18ab-121">有关选择相应的 VoIP 安全设置的详细信息, 请参阅<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">集成本地统一消息和 Lync Server 2013 的部署过程</A>。</span><span class="sxs-lookup"><span data-stu-id="b18ab-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="b18ab-122">运行以下 cmdlet 以获取每个 UM 拨号计划的完全限定的域名 (FQDN):</span><span class="sxs-lookup"><span data-stu-id="b18ab-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="b18ab-123">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b18ab-123">For details, see:</span></span>
    
      - <span data-ttu-id="b18ab-124">有关 Exchange 2007, 请参阅 "UMDialplan: Exchange 2007 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="b18ab-125">有关 Exchange 2010, 请参阅 "UMDialplan: Exchange 2010 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="b18ab-126">有关 Exchange 2013, 请参阅的[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"统一消息"。</span><span class="sxs-lookup"><span data-stu-id="b18ab-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="b18ab-127">记录每个 UM 拨号计划的拨号计划名称。</span><span class="sxs-lookup"><span data-stu-id="b18ab-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="b18ab-128">根据你的 Exchange Server 版本, 你可能需要先使用每个拨号计划名称的 FQDN 作为每个 UM 拨号计划的相应 Lync 服务器拨号计划的名称, 以便拨入计划名称匹配。</span><span class="sxs-lookup"><span data-stu-id="b18ab-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b18ab-129">只有当 UM 拨号计划在<EM>早</EM>于 EXCHANGE 2010 SP1 的 exchange 版本上运行时, Lync Server 拨号计划名称才必须匹配 um 拨号计划名称。</span><span class="sxs-lookup"><span data-stu-id="b18ab-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="b18ab-130">将拨号计划添加到运行 Exchange UM 的服务器, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="b18ab-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="b18ab-131">如果您选择使用 Exchange 管理控制台, 则可以从服务器的属性表中添加拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b18ab-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="b18ab-132">有关特定说明, 请参阅 Exchange Server 产品文档。</span><span class="sxs-lookup"><span data-stu-id="b18ab-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="b18ab-133">对于 Exchange 2007, 请参阅 "如何将统一消息服务器添加到拨号计划" [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="b18ab-134">对于 Exchange 2010, 请参阅 "查看或配置 UM 服务器的属性" [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="b18ab-135">有关 Exchange 2013, 请参阅的[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)"统一消息"。</span><span class="sxs-lookup"><span data-stu-id="b18ab-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="b18ab-136">如果您使用的是 Exchange 命令行管理程序, 请为您的每个 Exchange UM 服务器运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="b18ab-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umservice -instance $ums[0]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b18ab-137">在执行以下步骤之前, 请确保所有企业语音用户均已配置了 Exchange Server 邮箱。</span><span class="sxs-lookup"><span data-stu-id="b18ab-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="b18ab-138">有关 Exchange 2007, 请参阅中的 Exchange Server 2007 TechNet <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>库。</span><span class="sxs-lookup"><span data-stu-id="b18ab-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="b18ab-139">有关 Exchange 2010, 请参阅中的 Exchange Server 2010 TechNet <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>库。</span><span class="sxs-lookup"><span data-stu-id="b18ab-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="b18ab-140">为在步骤1中创建的每个拨号计划指定邮箱策略时, 请选择默认策略或已创建的策略。</span><span class="sxs-lookup"><span data-stu-id="b18ab-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="b18ab-141">导航到\<exchange 安装目录\>\\脚本, 然后如果在单个林中部署了 exchange, 请键入:</span><span class="sxs-lookup"><span data-stu-id="b18ab-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="b18ab-142">或者, 如果 Exchange 是在多个目录林中部署的, 请键入:</span><span class="sxs-lookup"><span data-stu-id="b18ab-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    <span data-ttu-id="b18ab-143">其中, 林 FQDN 指定了在其中部署 Lync 服务器的林。</span><span class="sxs-lookup"><span data-stu-id="b18ab-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="b18ab-144">如果您有一个或多个与多个 IP 网关相关联的 UM 拨号计划, 请继续执行步骤6。</span><span class="sxs-lookup"><span data-stu-id="b18ab-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="b18ab-145">如果您的拨号计划仅与单个 IP 网关相关联, 请跳过步骤6。</span><span class="sxs-lookup"><span data-stu-id="b18ab-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b18ab-146">请确保在运行 exchucutil<EM>后</EM>重新启动<STRONG>Lync Server 前端</STRONG>服务 (rtcsrv)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="b18ab-147">否则, Lync Server 将不会检测拓扑中的统一消息。</span><span class="sxs-lookup"><span data-stu-id="b18ab-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="b18ab-148">使用 Exchange 命令行管理程序或 Exchange 管理控制台, 禁用除了一个与每个拨号计划关联的 IP 网关之外的所有其他 IP 网关的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="b18ab-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b18ab-149">必须执行此步骤, 以确保由运行 Exchange Server 统一消息的服务器对外部用户的出站调用 (例如, 在使用手机方案的情况下) 可靠地遍历企业防火墙。</span><span class="sxs-lookup"><span data-stu-id="b18ab-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b18ab-150">选择允许传出呼叫的 UM IP 网关时, 选择可能处理最多流量的 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="b18ab-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="b18ab-151">不允许传出流量通过连接到 Lync Server 控制器池的 IP 网关。</span><span class="sxs-lookup"><span data-stu-id="b18ab-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="b18ab-152">还要避免在另一个中心站点或分支站点中使用池。</span><span class="sxs-lookup"><span data-stu-id="b18ab-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="b18ab-153">你可以使用以下任一方法阻止传出呼叫通过 IP 网关传递:</span><span class="sxs-lookup"><span data-stu-id="b18ab-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="b18ab-154">如果使用 Exchange 命令行管理程序, 请通过运行以下命令禁用每个 IP 网关:</span><span class="sxs-lookup"><span data-stu-id="b18ab-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        <span data-ttu-id="b18ab-155">对于 Exchange 2007, 请参阅 "Set-UMIPGateway: Exchange 2007 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="b18ab-156">对于 Exchange 2010, 请参阅 "Set-UMIPGateway: Exchange 2010 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="b18ab-157">如果您使用的是 Exchange 管理控制台, 请清除 "**允许通过此 IP 网关拨出呼叫**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="b18ab-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b18ab-158">如果你的 UM SIP URI 拨号计划仅与单个 IP 网关相关联, 请不要通过此网关禁止传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="b18ab-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="b18ab-159">为每个 Lync Server 拨号计划创建 UM 自动助理。</span><span class="sxs-lookup"><span data-stu-id="b18ab-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b18ab-160">不要在自动助理的名称中包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="b18ab-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
        New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    
    <span data-ttu-id="b18ab-161">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b18ab-161">For details, see:</span></span>
    
      - <span data-ttu-id="b18ab-162">有关 Exchange 2007, 请参阅 "New-UMAutoAttendant: Exchange 2007 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="b18ab-163">有关 Exchange 2010, 请参阅 "New-UMAutoAttendant: Exchange 2010 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="b18ab-164">在已启用 "适用于企业语音的 Lync Server 用户" 并了解其 SIP Uri 之后, 应为每个用户执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b18ab-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="b18ab-165">将 Exchange UM 用户 (每个用户都配置有 Exchange 邮箱的用户) 与 UM 拨号计划相关联, 并为每个用户创建 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="b18ab-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b18ab-166">以下示例中的<STRONG>SIPResourceIdentifier</STRONG>必须是 Lync 服务器用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="b18ab-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    <span data-ttu-id="b18ab-167">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b18ab-167">For details, see:</span></span>
    
      - <span data-ttu-id="b18ab-168">对于 Exchange 2007, 请参阅 "Enable-UMMailbox: Exchange 2007 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="b18ab-169">对于 Exchange 2010, 请参阅 "Enable-UMMailbox: Exchange 2010 帮助" [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)。</span><span class="sxs-lookup"><span data-stu-id="b18ab-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

