---
title: Lync Server 2013：在 Microsoft Exchange 上配置统一消息
description: Lync Server 2013：在 Microsoft Exchange 上配置统一消息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577518"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="3b431-103">在 Microsoft Exchange 上为 Lync Server 2013 配置统一消息</span><span class="sxs-lookup"><span data-stu-id="3b431-103">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b431-104">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="3b431-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="3b431-105">本主题介绍如何在 Microsoft Exchange Server 上配置 Exchange 统一消息 (UM) ，以便与企业语音配合使用。</span><span class="sxs-lookup"><span data-stu-id="3b431-105">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b431-106">本主题中的 cmdlet 示例提供了 Exchange 2007 版本的 Exchange 命令行管理程序的语法。</span><span class="sxs-lookup"><span data-stu-id="3b431-106">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="3b431-107">如果您运行的是 Exchange 2010 或 Exchange 2013，请参阅参考的相应文档。</span><span class="sxs-lookup"><span data-stu-id="3b431-107">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="3b431-108">配置运行 Exchange Server UM 的服务器</span><span class="sxs-lookup"><span data-stu-id="3b431-108">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="3b431-p102">为每个企业语音位置配置文件创建 UM 会话初始协议 (SIP) 统一资源标识符 (URI) 拨号计划。如果选择使用 Exchange 管理控制台，则创建一个具有安全设置 **Secured（首选）** 的新拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3b431-p102">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles. If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3b431-111">如果将安全设置值设置为 <STRONG>SIP Secured</STRONG> 来要求仅加密 SIP 流量（如之前所建议），请注意，如果前端池配置为要求加密（表明该池要求对 SIP 和 RTP 流量都进行加密），则拨号计划上的该安全设置是不够的。</span><span class="sxs-lookup"><span data-stu-id="3b431-111">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="3b431-112">当拨号计划和池安全设置不兼容时，来自前端池的对 Exchange UM 的所有呼叫都将失败，从而导致出现错误，指示您具有 "不兼容的安全设置"。</span><span class="sxs-lookup"><span data-stu-id="3b431-112">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="3b431-113">如果使用 Exchange 命令行管理程序，则键入：</span><span class="sxs-lookup"><span data-stu-id="3b431-113">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="3b431-114">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="3b431-114">For details, see:</span></span>
    
      - <span data-ttu-id="3b431-115">有关 Office 通信服务器2007，请参阅 at 和 "UMDialplan： Exchange 2007 帮助" 中的 "如何创建统一消息 SIP URI 拨号计划" [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) 和 "新-： Exchange 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-115">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="3b431-116">有关 Exchange 2010，请参阅 at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) 和 "UMDialplan： exchange 2010 帮助" 处的 "创建 UM 拨号计划" 和 "新-： Exchange 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-116">For Exchange 2010, see "Create a UM Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="3b431-117">对于 Exchange 2013，请参阅中的 "统一消息" [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-117">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b431-118">选择 <STRONG>SIPSecured</STRONG> 还是 <STRONG>Secured</STRONG> 安全级别，取决于对媒体加密是激活还是停用了安全实时传输协议 (SRTP)。</span><span class="sxs-lookup"><span data-stu-id="3b431-118">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="3b431-119">对于与 Exchange UM 的 Lync Server 2010 集成，这应与 Lync Server 媒体配置中的加密级别相对应。</span><span class="sxs-lookup"><span data-stu-id="3b431-119">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="3b431-120">可以通过运行 <STRONG>set-csmediaconfiguration</STRONG> cmdlet 来查看 Lync Server 媒体配置。</span><span class="sxs-lookup"><span data-stu-id="3b431-120">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="3b431-121">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 Get-CsMediaConfiguration。</span><span class="sxs-lookup"><span data-stu-id="3b431-121">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="3b431-122">有关选择适当的 VoIP 安全设置的详细信息，请参阅 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">集成本地统一消息和 Lync Server 2013 的部署过程</A>。</span><span class="sxs-lookup"><span data-stu-id="3b431-122">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="3b431-123">运行以下 cmdlet 获取每个 UM 拨号计划的完全限定的域名 (FQDN)：</span><span class="sxs-lookup"><span data-stu-id="3b431-123">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="3b431-124">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="3b431-124">For details, see:</span></span>
    
      - <span data-ttu-id="3b431-125">有关 Exchange 2007，请参阅位于处的 "UMDialplan： Exchange 2007 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-125">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="3b431-126">有关 Exchange 2010，请参阅位于处的 "UMDialplan： Exchange 2010 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-126">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="3b431-127">对于 Exchange 2013，请参阅中的 "统一消息" [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-127">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="3b431-128">记录每个 UM 拨号计划的拨号计划名称。</span><span class="sxs-lookup"><span data-stu-id="3b431-128">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="3b431-129">根据您的 Exchange Server 版本，您可能需要在以后将每个拨号计划名称的 FQDN 用作每个 UM 拨号计划对应的 Lync Server 拨号计划的名称，以便与拨号计划名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="3b431-129">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b431-130">只有在 UM 拨号计划运行在 exchange 2010 SP1 <EM>之前</EM> 的 exchange 版本上时，Lync Server 拨号计划名称才必须与 um 拨号计划名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="3b431-130">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="3b431-131">将拨号计划添加到运行 Exchange UM 的服务器上，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3b431-131">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="3b431-p106">如果选择使用 Exchange 管理控制台，则可以通过服务器的属性页添加拨号计划。有关具体说明，请参阅 Exchange Server 产品文档。</span><span class="sxs-lookup"><span data-stu-id="3b431-p106">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server. For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="3b431-134">有关 Exchange 2007，请参阅中的 "如何将统一消息服务器添加到拨号计划中" [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-134">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="3b431-135">有关 Exchange 2010，请参阅在上的 "查看或配置 UM 服务器的属性" [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-135">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="3b431-136">对于 Exchange 2013，请参阅中的 "统一消息" [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-136">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="3b431-137">如果使用 Exchange 命令行管理程序，请为每台 Exchange UM 服务器运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="3b431-137">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b431-138">执行以下步骤之前，请确保已为所有企业语音用户配置了 Exchange Server 邮箱。</span><span class="sxs-lookup"><span data-stu-id="3b431-138">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="3b431-139">对于 Exchange 2007，请参阅上的 Exchange Server 2007 TechNet 库 <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> 。</span><span class="sxs-lookup"><span data-stu-id="3b431-139">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="3b431-140">对于 Exchange 2010，请参阅上的 Exchange Server 2010 TechNet 库 <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> 。</span><span class="sxs-lookup"><span data-stu-id="3b431-140">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="3b431-141">为在步骤 1 中创建的每个拨号计划指定邮箱策略时，既可以选择默认策略，也可以选择已创建的策略。</span><span class="sxs-lookup"><span data-stu-id="3b431-141">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="3b431-142">导航到 \<Exchange installation directory\> \\ "脚本"，然后如果在一个林中部署了 Exchange，请键入：</span><span class="sxs-lookup"><span data-stu-id="3b431-142">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="3b431-143">否则，如果 Exchange 部署在多个林中，则键入：</span><span class="sxs-lookup"><span data-stu-id="3b431-143">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="3b431-144">其中，林 FQDN 指定要在其中部署 Lync Server 的林。</span><span class="sxs-lookup"><span data-stu-id="3b431-144">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="3b431-p107">如果具有与多个 IP 网关关联的一个或多个 UM 拨号计划，则继续步骤 6。如果每个拨号计划仅与单个 IP 网关关联，则跳过步骤 6。</span><span class="sxs-lookup"><span data-stu-id="3b431-p107">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6. If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b431-147">运行 exchucutil.ps1 后<EM></EM>，请确保重新启动“Lync Server 前端”<STRONG></STRONG>服务 (rtcsrv.exe)。</span><span class="sxs-lookup"><span data-stu-id="3b431-147">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="3b431-148">否则，Lync Server 将不会在拓扑中检测到统一消息。</span><span class="sxs-lookup"><span data-stu-id="3b431-148">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="3b431-149">通过使用 Exchange 命令行管理程序或 Exchange 管理控制台，禁用所有 IP 网关的出站呼叫（与每个拨号计划关联的 IP 网关除外）。</span><span class="sxs-lookup"><span data-stu-id="3b431-149">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b431-150">需要执行此步骤，以确保运行 Exchange Server 统一消息的服务器对外部用户进行的出站呼叫 (例如，在电话上播放的方案) 可靠地遍历公司防火墙。</span><span class="sxs-lookup"><span data-stu-id="3b431-150">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b431-151">当选择允许传出呼叫通过的 UM IP 网关时，请选择有希望处理最多流量的 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="3b431-151">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="3b431-152">不允许传出流量通过连接到 Lync Server 控制器池的 IP 网关。</span><span class="sxs-lookup"><span data-stu-id="3b431-152">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="3b431-153">此外，避免池位于其他中央站点或分支站点中。</span><span class="sxs-lookup"><span data-stu-id="3b431-153">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="3b431-154">可以使用以下任意一种方法阻止传出呼叫通过 IP 网关传递：</span><span class="sxs-lookup"><span data-stu-id="3b431-154">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="3b431-155">如果使用的是 Exchange 命令行管理程序，则可通过运行以下命令来禁用每个 IP 网关：</span><span class="sxs-lookup"><span data-stu-id="3b431-155">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="3b431-156">有关 Exchange 2007，请参阅位于处的 "UMIPGateway： Exchange 2007 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-156">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="3b431-157">有关 Exchange 2010，请参阅位于处的 "UMIPGateway： Exchange 2010 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-157">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="3b431-158">如果使用 Exchange 管理控制台，请清除 **“允许通过此 IP 网关的传出呼叫”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="3b431-158">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b431-159">如果您的 UM SIP URI 拨号计划仅与单个 IP 网关关联，则不禁止传出呼叫通过此网关。</span><span class="sxs-lookup"><span data-stu-id="3b431-159">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="3b431-160">为每个 Lync Server 拨号计划创建一个 UM 自动助理。</span><span class="sxs-lookup"><span data-stu-id="3b431-160">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b431-161">请勿在自动助理的名称中包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="3b431-161">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="3b431-162">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="3b431-162">For details, see:</span></span>
    
      - <span data-ttu-id="3b431-163">有关 Exchange 2007，请参阅位于处的 "Get-umautoattendant： Exchange 2007 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-163">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="3b431-164">有关 Exchange 2010，请参阅位于处的 "Get-umautoattendant： Exchange 2010 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-164">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="3b431-165">为每个用户启用了适用于企业语音的 Lync Server 用户并了解其 SIP Uri 后，应执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="3b431-165">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="3b431-166">将 Exchange UM 用户（他们中的每一个应该都配置了 Exchange 邮箱）与 UM 拨号计划关联，并为每个用户创建一个 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="3b431-166">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b431-167">以下示例中的 <STRONG>SIPResourceIdentifier</STRONG> 必须是 Lync Server 用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="3b431-167">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="3b431-168">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="3b431-168">For details, see:</span></span>
    
      - <span data-ttu-id="3b431-169">有关 Exchange 2007，请参阅位于上的 "Enable-Get-ummailbox： Exchange 2007 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-169">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="3b431-170">有关 Exchange 2010，请参阅位于上的 "Enable-Get-ummailbox： Exchange 2010 帮助" [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) 。</span><span class="sxs-lookup"><span data-stu-id="3b431-170">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

