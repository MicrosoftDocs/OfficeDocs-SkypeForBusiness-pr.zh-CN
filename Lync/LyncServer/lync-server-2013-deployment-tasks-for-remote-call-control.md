---
title: Lync Server 2013：远程呼叫控制的部署任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd2ac45e0f589ac155d2e0f51b0115036a97809e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499049"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="bd281-102">Lync Server 2013 中的远程呼叫控制的部署任务</span><span class="sxs-lookup"><span data-stu-id="bd281-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd281-103">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="bd281-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="bd281-104">本主题介绍为 Lync Server 环境中的用户启用远程呼叫控制而必须执行的部署任务。</span><span class="sxs-lookup"><span data-stu-id="bd281-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd281-105">如果要在 Microsoft Office Communicator 2007 R2 中迁移以前为远程呼叫控制启用的用户，则在开始执行本主题中所述的远程呼叫控制部署任务之前，必须执行额外的部署任务。</span><span class="sxs-lookup"><span data-stu-id="bd281-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="bd281-106">在将迁移过程迁移到 Lync Server 时， (之前称为 "已 <EM>授权主机条目</EM> " 的受信任的应用程序条目) 必须使用 Office 通信服务器 2007 R2 管理工具（如适用）删除。</span><span class="sxs-lookup"><span data-stu-id="bd281-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="bd281-107">有关删除已授权主机的详细信息，请参阅 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中删除旧版授权主机 (可选) </A>。</span><span class="sxs-lookup"><span data-stu-id="bd281-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="bd281-108">步骤 1：安装和配置 SIP/CSTA 网关，以与 PBX 进行通信</span><span class="sxs-lookup"><span data-stu-id="bd281-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="bd281-109">您需要安装至少一个 SIP/CSTA 网关，以便在您的环境中连接到 Lync Server 和现有的专用分支 exchange (PBX) ，以便为用户提供远程呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="bd281-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="bd281-110">SIP/CSTA 网关是 SIP 和计算机支持的电信应用程序 (CSTA) 之间的网关。</span><span class="sxs-lookup"><span data-stu-id="bd281-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="bd281-111">不管是安装多个网关，还是只安装一个网关，都只能为每个用户配置一个网关或 PBX。</span><span class="sxs-lookup"><span data-stu-id="bd281-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="bd281-112">如果现有 PBX 没有 SIP/CSTA 接口，请确保部署可支持 PBX（包括支持专用于 PBX 的供应商特定的信号协议）的 SIP/CSTA 网关。</span><span class="sxs-lookup"><span data-stu-id="bd281-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="bd281-113">有关功能的详细信息，请直接咨询各个供应商。</span><span class="sxs-lookup"><span data-stu-id="bd281-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="bd281-114">当您准备好部署可与 Lync Server 集成以进行远程呼叫控制的 SIP/CSTA 网关时，请咨询您的网关供应商或供应商的网关文档，以了解有关网关所需的以下信息的语法：</span><span class="sxs-lookup"><span data-stu-id="bd281-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="bd281-115">网关的线路服务器 URI</span><span class="sxs-lookup"><span data-stu-id="bd281-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="bd281-116">要分配给网关的用户的线路 URI</span><span class="sxs-lookup"><span data-stu-id="bd281-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="bd281-117">用户配置期间需要上述设置，且网关必须按预期指定这些设置，以正确路由并连接到 PBX。</span><span class="sxs-lookup"><span data-stu-id="bd281-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="bd281-118">你可以在上的 Microsoft 统一通信开放式互操作性计划网站上参阅供应商 [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) 。</span><span class="sxs-lookup"><span data-stu-id="bd281-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="bd281-119">步骤2：将 Lync Server 配置为将 CSTA 请求路由到 SIP/CSTA 网关</span><span class="sxs-lookup"><span data-stu-id="bd281-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="bd281-120">您必须在您打算路由远程呼叫控制请求的部署中的所有 SIP/CSTA 网关 (Server URI) 的目标地址，在 Lync Server 池上创建静态路由。</span><span class="sxs-lookup"><span data-stu-id="bd281-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="bd281-121">还必须创建与每个目标地址相对应的受信任应用程序项。</span><span class="sxs-lookup"><span data-stu-id="bd281-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="bd281-122">将网关指定为受信任的应用程序时，它被授予作为 Lync Server 环境的一部分运行的受信任状态，即使它是由第三 (方开发的，也会运行作为 *外部服务* 的服务，因为它不是产品) 的内置部件。</span><span class="sxs-lookup"><span data-stu-id="bd281-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="bd281-123">最后，如果 Lync Server 将使用传输控制协议 (TCP) 连接而不是传输层安全性 (TLS) 连接连接到 SIP/CSTA 网关，则还必须使用拓扑生成器定义网关 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="bd281-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="bd281-124">有关配置静态路由的详细信息，请参阅 [Lync Server 2013 中的为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。</span><span class="sxs-lookup"><span data-stu-id="bd281-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="bd281-125">有关配置受信任的应用程序项的详细信息，请参阅 [Lync Server 2013 中的为远程呼叫控制配置受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。</span><span class="sxs-lookup"><span data-stu-id="bd281-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="bd281-126">有关在拓扑生成器中定义 SIP/CSTA 网关 IP 地址的详细信息，请参阅 [在 Lync Server 2013 中定义 sip/CSTA 网关 ip 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。</span><span class="sxs-lookup"><span data-stu-id="bd281-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="bd281-127">步骤3：配置 Lync 用户的远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="bd281-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="bd281-128">为用户启用 Lync Server 后，可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序来启用远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="bd281-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="bd281-129">在此部署步骤期间，为每个用户分配线路服务器 URI 和线路 URI。</span><span class="sxs-lookup"><span data-stu-id="bd281-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="bd281-130">线路服务器 URI 是计划分配给用户的 SIP/CSTA 网关的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="bd281-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="bd281-131">线路 URI 是分配给用户的唯一电话号码。</span><span class="sxs-lookup"><span data-stu-id="bd281-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="bd281-132">有关为用户配置远程呼叫控制的详细信息，请参阅 [在 Lync Server 2013 中为远程呼叫控制启用 lync 用户](lync-server-2013-enable-lync-users-for-remote-call-control.md)。</span><span class="sxs-lookup"><span data-stu-id="bd281-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="bd281-133">步骤 4：定义 Lync Server 电话号码规范化规则</span><span class="sxs-lookup"><span data-stu-id="bd281-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="bd281-134">在远程呼叫控制方案中，Lync Server 使用电话号码规范化规则将其收到的电话号码从 SIP/CSTA 网关转换为 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="bd281-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="bd281-135">电话号码必须使用此标准化格式，远程呼叫控制的某些功能才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="bd281-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="bd281-136">远程呼叫控制使用的电话号码规范化规则与为通讯簿服务电话号码规范化配置的规则相同，但不同于企业语音使用的电话号码规范化规则。</span><span class="sxs-lookup"><span data-stu-id="bd281-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="bd281-137">有关远程呼叫控制如何使用电话号码规范化规则的详细信息，请参阅 [Lync Server 2013 中的远程呼叫控制和电话号码规范化](lync-server-2013-remote-call-control-and-phone-number-normalization.md)。</span><span class="sxs-lookup"><span data-stu-id="bd281-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="bd281-138">有关通讯簿服务的电话号码规范化规则的详细信息，请参阅操作文档中的在 [Lync Server 2013 主题中管理通讯簿服务](lync-server-2013-administering-the-address-book-service.md) 。</span><span class="sxs-lookup"><span data-stu-id="bd281-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

