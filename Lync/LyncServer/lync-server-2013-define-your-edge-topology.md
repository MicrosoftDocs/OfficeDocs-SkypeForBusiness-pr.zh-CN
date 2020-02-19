---
title: Lync Server 2013：定义边缘拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55653e39086c311778335999d2e9fc2101b28d40
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="b8951-102">在 Lync Server 2013 中定义边缘拓扑</span><span class="sxs-lookup"><span data-stu-id="b8951-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8951-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b8951-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b8951-104">必须使用拓扑生成器生成拓扑，并且必须至少设置一个内部前端池或 Standard Edition server，然后才能部署边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b8951-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="b8951-105">使用以下过程可为单个边缘服务器定义边缘拓扑，然后使用在[Lync server 2013 中发布拓扑中](lync-server-2013-publish-your-topology.md)的过程并[导出 lync server 2013 拓扑，并将其复制到外部媒体以进行边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)，以发布拓扑并使其可用于边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b8951-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8951-p102">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="b8951-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="b8951-108">若要在添加或删除服务器角色后成功发布、启用或禁用拓扑，必须以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="b8951-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="b8951-109">您还可以授予向用户帐户添加服务器角色所需的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="b8951-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="b8951-110">有关详细信息，请参阅 Standard Edition server 或 Enterprise Edition server Deployment 文档中的 "[在 Lync Server 2013 中委派安装程序权限](lync-server-2013-delegate-setup-permissions.md)"。</span><span class="sxs-lookup"><span data-stu-id="b8951-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="b8951-111">对于其他配置更改，只需要 RTCUniversalServerAdmins 组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="b8951-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="b8951-112">如果在定义和发布内部拓扑时定义了边缘拓扑，且不需要对之前定义的边缘拓扑进行任何更改，则无需再次对其进行定义和发布。</span><span class="sxs-lookup"><span data-stu-id="b8951-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="b8951-113">仅当需要对边缘拓扑进行更改时才应使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="b8951-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="b8951-114">您必须将之前定义和发布的拓扑提供给您的边缘服务器，这是通过使用 "[导出 Lync Server 2013 拓扑" 中的过程并将其复制到 "边缘安装" 的外部媒体](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)来实现的。</span><span class="sxs-lookup"><span data-stu-id="b8951-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8951-115">无法从边缘服务器运行拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="b8951-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="b8951-116">必须在前端服务器或 Standard Edition 服务器上运行它。</span><span class="sxs-lookup"><span data-stu-id="b8951-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="b8951-117">定义边缘服务器拓扑的过程是在拓扑生成器中完成的。</span><span class="sxs-lookup"><span data-stu-id="b8951-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="b8951-118">下面列出了您需要规划和配置的三种主要类型的边缘服务器拓扑：</span><span class="sxs-lookup"><span data-stu-id="b8951-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="b8951-119">为单台边缘服务器定义拓扑</span><span class="sxs-lookup"><span data-stu-id="b8951-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="b8951-120">为负载平衡边缘服务器池定义拓扑</span><span class="sxs-lookup"><span data-stu-id="b8951-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="b8951-121">为硬件负载平衡边缘池定义拓扑</span><span class="sxs-lookup"><span data-stu-id="b8951-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="b8951-122">为单台边缘服务器定义拓扑</span><span class="sxs-lookup"><span data-stu-id="b8951-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="b8951-123">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="b8951-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b8951-124">在控制台树中，展开要在其中部署边缘服务器的站点。</span><span class="sxs-lookup"><span data-stu-id="b8951-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="b8951-125">右键单击 "**边缘池**"，然后单击 "**新建边缘池**"。</span><span class="sxs-lookup"><span data-stu-id="b8951-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="b8951-126">在 **“定义新的边缘池”** 中，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="b8951-127">在 **“定义边缘池 FQDN”** 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-128">在“池 FQDN”\*\*\*\* 中，键入边缘服务器内部接口的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="b8951-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="b8951-129">指定的名称必须与在服务器上配置的计算机名称相同。</span><span class="sxs-lookup"><span data-stu-id="b8951-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="b8951-130">默认情况下，未加入域的计算机的计算机名称是短名称，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8951-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="b8951-131">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="b8951-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="b8951-132">因此，如果要部署为边缘服务器的计算机未加入域，则必须为计算机名称配置 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="b8951-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="b8951-133">分配 Lync Server、边缘服务器和池的 FQDN 时只能使用标准字符（包括 A–Z、a–z、0–9 和连字符）。</span><span class="sxs-lookup"><span data-stu-id="b8951-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="b8951-134">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="b8951-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b8951-135">外部 DNS 和公共 CA 通常不支持在 FQDN 中使用非标准字符（当必须向证书中的 SN 分配 FQDN 时）。</span><span class="sxs-lookup"><span data-stu-id="b8951-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="b8951-136">有关向计算机名称添加 DNS 后缀的详细信息，请参阅<A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中为边缘支持配置 dns</A>。</span><span class="sxs-lookup"><span data-stu-id="b8951-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="b8951-137">单击“单计算机池”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="b8951-138">在“选择功能”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-139">如果您计划对 SIP 访问服务、Lync Server 2013 Web 会议服务和 A/V 边缘服务使用一个 FQDN 和 IP 地址，请选中 "**使用一个 fqdn 和 Ip 地址**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8951-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="b8951-140">如果您计划启用联盟，请选中“为此边缘池启用联盟(端口 5061)”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8951-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b8951-p108">您可以选择此选项，但只能为联盟对外发布组织中的一个边缘池或边缘服务器。联盟用户（包括公共即时消息 (IM) 用户）的所有访问都将通过相同的边缘池或单台边缘服务器。例如，如果部署中有一个边缘池或单台边缘服务器部署在纽约，另一个部署在伦敦，并对纽约的边缘池或单台边缘服务器启用联盟支持，则联盟用户的信号流量将通过纽约的边缘池或单台边缘服务器。这同样适用于伦敦用户的通信，尽管伦敦内部用户呼叫伦敦联盟用户时将使用伦敦的池或边缘服务器路由 A/V 流量。</span><span class="sxs-lookup"><span data-stu-id="b8951-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="b8951-145">如果您计划支持适用于部署的可扩展消息传递和状态协议 (XMPP)，请选中“启用 XMPP 联盟(端口 5269)”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8951-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="b8951-146">在“选择 IP 选项”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-147">**在内部接口上启用 ipv4**：如果要将 ipv4 地址应用到边缘服务器或边缘池内部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b8951-148">**在内部接口上启用 ipv6**：如果要将 ipv6 地址应用到边缘服务器或边缘池内部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b8951-149">**在外部接口上启用 ipv4**：如果要将 ipv4 地址应用到边缘服务器或边缘池外部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="b8951-150">**在外部接口上启用 ipv6**：如果要将 ipv6 地址应用到边缘服务器或边缘池外部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="b8951-151">您还可以将边缘服务器或边缘池配置为对外部 IP 地址使用网络地址转换地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="b8951-152">可通过选中“此边缘池的外部 IP 地址是由 NAT 转换的”\*\*\*\* 复选框来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b8951-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="b8951-153">在“外部 FQDN”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-154">如果在“选择功能”\*\*\*\* 中选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在“SIP 访问”\*\*\*\* 中键入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8951-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b8951-p110">如果选择此选项，则必须为每个边缘服务指定不同的端口号（推荐的端口设置为：访问边缘服务为 5061，Web 会议边缘服务为 444，A/V 边缘服务为 443）。选择此选项可帮助防止潜在的连接问题并简化配置，因为可以将同一端口号（例如，443）同时用于所有这三种服务。</span><span class="sxs-lookup"><span data-stu-id="b8951-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="b8951-157">如果在“选择功能”\*\*\*\* 中未选择使用单个 FQDN 和 IP 地址，请键入“SIP 访问”\*\*\*\*、“Web 会议”\*\*\*\* 和“音频视频”\*\*\*\* 的外部 FQDN，并保留默认端口。</span><span class="sxs-lookup"><span data-stu-id="b8951-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="b8951-158">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b8951-158">Click **Next**.</span></span>

10. <span data-ttu-id="b8951-p111">在“定义内部 IP 地址”\*\*\*\* 中，键入适合您需求的“内部 IPv4 地址”\*\*\*\* 和“内部 IPv6 地址”\*\*\*\* 中的边缘服务器的 IP 地址。单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="b8951-161">在“定义外部 IP 地址”\*\*\*\* 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-162">如果选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在“SIP 访问”\*\*\*\* 中键入边缘服务器的外部 IPv4 地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="b8951-163">如果选择使用 IPv6 地址，请在“SIP 访问”\*\*\*\* 中键入边缘服务器的外部 IPv6 地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="b8951-164">如果未选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在“SIP 访问”\*\*\*\*、“Web 会议”\*\*\*\* 和“A/V 会议”\*\*\*\* 中键入边缘服务器的外部 IPv4 地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="b8951-165">如果选择使用 IPv6 地址且不选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在“SIP 访问”\*\*\*\*、“Web 会议”\*\*\*\* 和“A/V 会议”\*\*\*\* 中键入边缘服务器的外部 IPv6 地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b8951-166">如果您未选择启用和分配 IPv6 寻址，则将不会显示此对话框。</span><span class="sxs-lookup"><span data-stu-id="b8951-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="b8951-p112">如果选择使用 NAT，则会显示一个对话框。在“适用于 A/V 边缘服务的公共 IPv4 地址”\*\*\*\* 中，键入要通过 NAT 转换的公共 IPv4 地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-169">该地址应为 A/V 边缘服务的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="b8951-p113">如果选择使用 NAT 和 IPv6 地址，则会显示一个对话框。在“适用于 A/V 边缘服务的公共 IPv6 地址”\*\*\*\* 中，键入要通过 NAT 转换的公共 IPv6 地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-172">该地址应为 A/V 边缘服务的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="b8951-p114">在“定义下一个跃点”\*\*\*\* 的“下一个跃点池”\*\*\*\* 中，选择内部池的名称，该池可以是前端池，也可以是 Standard Edition 池。或者，如果部署包括控制器，则选择该控制器。然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="b8951-176">在“关联前端池”\*\*\*\* 中，通过选择将该边缘服务器用于与支持的外部用户通信的内部池名称，来指定要与该边缘服务器关联的一个或多个内部池，其中可包括前端池和 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="b8951-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-p115">只能将一个负载平衡边缘池或单台边缘服务器与 A/V 流量的每个内部池关联。如果您已将内部池与边缘池或边缘服务器关联，则会显示警告，指出该内部池已与边缘池或边缘服务器关联。如果选择已与其他边缘服务器关联的池，则会更改关联。</span><span class="sxs-lookup"><span data-stu-id="b8951-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="b8951-180">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-180">Click **Finish**.</span></span>

17. <span data-ttu-id="b8951-181">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="b8951-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="b8951-182">为 DNS 负载平衡边缘服务器池定义拓扑</span><span class="sxs-lookup"><span data-stu-id="b8951-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="b8951-183">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="b8951-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b8951-184">在控制台树中，展开要在其中部署边缘服务器的站点。</span><span class="sxs-lookup"><span data-stu-id="b8951-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="b8951-185">右键单击“边缘池”\*\*\*\*，然后单击“新建边缘池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="b8951-186">在 **“定义新的边缘池”** 中，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="b8951-187">在 **“定义边缘池 FQDN”** 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-188">在“池 FQDN”\*\*\*\* 中，键入边缘池的内部连接的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="b8951-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="b8951-189">为池指定的名称必须是内部边缘池名称。</span><span class="sxs-lookup"><span data-stu-id="b8951-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="b8951-190">此名称必须定义为 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8951-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="b8951-191">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="b8951-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="b8951-192">在指定 Lync Server、边缘服务器和池的 FQDN 时，只应使用标准字符（包括 A-Z、a-z、0-9 和连字符）。</span><span class="sxs-lookup"><span data-stu-id="b8951-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="b8951-193">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="b8951-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b8951-194">外部 DNS 和公共 CA 通常不支持在 FQDN 中使用非标准字符（当必须向证书中的 SN 分配 FQDN 时）。</span><span class="sxs-lookup"><span data-stu-id="b8951-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="b8951-195">单击“多计算机池”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="b8951-196">在“选择功能”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-197">如果您计划将单个 FQDN 和 IP 地址用于 SIP 访问、Lync Server 2013 Web 会议服务和 A/V 边缘服务，请选中 "**使用一个 FQDN 和 Ip 地址**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8951-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="b8951-p117">如果您计划启用联盟，请选中“为此边缘池启用联盟(端口 5061)”\*\*\*\* 复选框。单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b8951-p118">您可以选择此选项，但只能为联盟对外发布组织中的一个边缘池或边缘服务器。联盟用户（包括公共即时消息 (IM) 用户）的所有访问都将通过相同的边缘池或单台边缘服务器。例如，如果部署中有一个边缘池或单个边缘服务器部署在纽约，另一个部署在伦敦，并对纽约的边缘池或单个边缘服务器启用联盟支持，则联盟用户的信号流量将通过纽约的边缘池或单个边缘服务器。这同样适用于伦敦用户的通信，尽管伦敦内部用户呼叫伦敦联盟用户时将使用伦敦的池或边缘服务器路由 A/V 流量。</span><span class="sxs-lookup"><span data-stu-id="b8951-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="b8951-204">如果您计划支持适用于部署的可扩展消息传递和状态协议 (XMPP)，请选中“启用 XMPP 联盟(端口 5269)”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8951-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="b8951-205">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b8951-205">Click **Next**.</span></span>

8.  <span data-ttu-id="b8951-206">在“选择 IP 选项”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-207">**在内部接口上启用 ipv4**：如果要将 ipv4 地址应用到边缘服务器或边缘池内部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b8951-208">**在内部接口上启用 ipv6**：如果要将 ipv6 地址应用到边缘服务器或边缘池内部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b8951-209">**在外部接口上启用 ipv4**：如果要将 ipv4 地址应用到边缘服务器或边缘池外部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="b8951-210">**在外部接口上启用 ipv6**：如果要将 ipv6 地址应用到边缘服务器或边缘池外部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="b8951-211">您还可以将边缘服务器或边缘池配置为对外部 IP 地址使用网络地址转换地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="b8951-212">可通过选中“此边缘池的外部 IP 地址是由 NAT 转换的”\*\*\*\* 复选框来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b8951-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="b8951-213">在“外部 FQDN”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-214">如果在“选择功能”\*\*\*\* 中选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在“SIP 访问”\*\*\*\* 中键入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8951-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b8951-p120">如果选择此选项，则必须为每个边缘服务指定不同的端口号（推荐的端口设置为：访问边缘服务为 5061，Web 会议边缘服务为 444，A/V 边缘服务为 443）。通过选择此选项，可帮助防止潜在的连接问题并简化配置，因为可以将同一端口号（例如，443）用于所有三种服务。</span><span class="sxs-lookup"><span data-stu-id="b8951-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="b8951-p121">如果在“选择功能”\*\*\*\* 中未选择使用单个 FQDN 和 IP 地址，则在“SIP 访问”\*\*\*\* 中键入为边缘池的公共端选择的 FQDN。在“Web 会议”\*\*\*\* 中，键入为边缘池的公共端选择的 FQDN。在“音频/视频”\*\*\*\* 中，键入为边缘池的公共端选择的 FQDN。使用默认端口。</span><span class="sxs-lookup"><span data-stu-id="b8951-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="b8951-221">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-221">Click **Next**.</span></span>

11. <span data-ttu-id="b8951-222">在 **“定义此池中的计算机”** 中，单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="b8951-223">在“内部 FQDN 和 IP 地址”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-224">在“内部 IPv4 地址”\*\*\*\* 中，为要在此池中创建的第一台边缘服务器键入适合您需求的 IPv4 地址和“内部 IPv6 地址”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="b8951-225">在“内部 FQDN”\*\*\*\* 中，键入要在此池中创建的第一台边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8951-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b8951-226">指定的名称必须与在服务器上配置的计算机名称相同。</span><span class="sxs-lookup"><span data-stu-id="b8951-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="b8951-227">默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8951-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="b8951-228">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="b8951-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="b8951-229">因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="b8951-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="b8951-230">在指定 Lync Server、边缘服务器、池和阵列的 FQDN 时，只应使用标准字符（包括 A-Z、a-z、0-9 和连字符）。</span><span class="sxs-lookup"><span data-stu-id="b8951-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="b8951-231">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="b8951-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b8951-232">外部 DNS 和公共 CA 通常不支持在 FQDN 中使用非标准字符（当必须向证书中的 SN 分配 FQDN 时）。</span><span class="sxs-lookup"><span data-stu-id="b8951-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="b8951-233">有关向计算机名称添加 DNS 后缀的详细信息，请参阅<A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中为边缘支持配置 dns</A>。</span><span class="sxs-lookup"><span data-stu-id="b8951-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="b8951-234">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-234">Click **Next**.</span></span>

14. <span data-ttu-id="b8951-235">在 **“定义外部 IP 地址”** 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-236">如果选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在 **“SIP 访问”** 中键入边缘服务器的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="b8951-p123">如果未选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 会议服务，则在 **“SIP 访问”** 中键入为该边缘池服务器的公共端选择的 IP 地址。在 **“Web 会议”** 中，键入为该边缘池服务器的公共端选择的 IP 地址。在 **“A/V 会议”** 中，键入为该边缘池服务器的公共端选择的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="b8951-240">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-240">Click **Next**.</span></span>

16. <span data-ttu-id="b8951-241">如果选择启用 IPv6 地址，请在“定义外部 IP 地址”\*\*\*\* 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-242">如果选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在“SIP 访问”\*\*\*\* 中键入边缘服务器的外部 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="b8951-p124">如果未选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 会议服务，则在“SIP 访问”\*\*\*\* 中键入为该边缘池服务器的公共端选择的 IPv6 地址。在“Web 会议”\*\*\*\* 中，键入为该边缘池服务器的公共端选择的 IPv6 地址。在“A/V 会议”\*\*\*\* 中，键入为该边缘池服务器的公共端选择的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-246">如果您未选择启用和分配 IPv6 寻址，则将不会显示此对话框。</span><span class="sxs-lookup"><span data-stu-id="b8951-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="b8951-247">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-248">此时可在<STRONG>“定义此池中的计算机”</STRONG>对话框中看到在池中创建的第一台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b8951-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="b8951-249">在“定义此池中的计算机”\*\*\*\* 中，单击“添加”\*\*\*\*，然后对要添加到边缘池的第二台边缘服务器重复步骤 11 至 14。</span><span class="sxs-lookup"><span data-stu-id="b8951-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="b8951-250">重复步骤 11 至 14 后，在 **“定义此池中的计算机”** 中单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-251">此时，可以在池中看到两台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b8951-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="b8951-p125">如果选择使用 NAT，则会显示一个对话框。在“公共 IP 地址”\*\*\*\* 中，键入要通过 NAT 转换的公共 IPv4 和 IPv6（根据需要）地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-254">该地址应为 A/V 边缘的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="b8951-p126">在 **“定义下一个跃点”** 的 **“下一个跃点池”** 列表中，选择内部池的名称，该池可以是前端池，也可以是 Standard Edition 池。或者，如果部署中包括控制器，则选择控制器的名称。然后单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="b8951-258">在 **“关联前端池”** 中，通过选择将该边缘服务器用于与支持的外部用户进行通信的内部池的名称，来指定要与该边缘服务器关联的一个或多个内部池，其中可包括前端池和 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="b8951-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-p127">只能将一个负载平衡边缘池或单台边缘服务器与 A/V 流量的每个内部池关联。如果您已将内部池与边缘池或边缘服务器关联，则会显示警告，指出该内部池已与边缘池或边缘服务器关联。如果选择已与其他边缘服务器关联的池，则会更改关联。</span><span class="sxs-lookup"><span data-stu-id="b8951-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="b8951-262">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-262">Click **Finish**.</span></span>

24. <span data-ttu-id="b8951-263">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="b8951-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="b8951-264">为硬件负载平衡边缘服务器池定义拓扑</span><span class="sxs-lookup"><span data-stu-id="b8951-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="b8951-265">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="b8951-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b8951-266">在控制台树中，展开要在其中部署边缘服务器的站点。</span><span class="sxs-lookup"><span data-stu-id="b8951-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="b8951-267">右键单击 "**边缘池**"，然后选择 "**新建边缘池**"。</span><span class="sxs-lookup"><span data-stu-id="b8951-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="b8951-268">在 **“定义新的边缘池”** 中，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="b8951-269">在 **“定义边缘池 FQDN”** 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-270">在“FQDN”\*\*\*\* 中，键入为边缘池的内端选择的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="b8951-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="b8951-271">为池指定的名称必须是内部边缘池名称。</span><span class="sxs-lookup"><span data-stu-id="b8951-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="b8951-272">此名称必须定义为 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8951-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="b8951-273">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="b8951-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="b8951-274">在指定 Lync Server、边缘服务器和池的 FQDN 时，只应使用标准字符（包括 A-Z、a-z、0-9 和连字符）。</span><span class="sxs-lookup"><span data-stu-id="b8951-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="b8951-275">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="b8951-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b8951-276">外部 DNS 和公共 CA 通常不支持在 FQDN 中使用非标准字符（当必须向证书中的 SN 分配 FQDN 时）。</span><span class="sxs-lookup"><span data-stu-id="b8951-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="b8951-277">单击 "**多个计算机池**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b8951-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="b8951-278">在 **“选择功能”** 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="b8951-279">如果您计划对 SIP 访问服务、Lync Server Web 会议服务和 A/V 边缘服务使用一个 FQDN 和 IP 地址，请选中 "**使用单个 FQDN & IP 地址**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8951-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="b8951-280">如果您计划启用联盟，请选中 **“为此边缘池启用联盟(端口 5061)”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8951-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b8951-p129">您可以选择此选项，但只能为联盟对外发布组织中的一个边缘池或边缘服务器。联盟用户（包括公共即时消息 (IM) 用户）的所有访问都将通过相同的边缘池或单台边缘服务器。例如，如果部署中有一个边缘池或单个边缘服务器部署在纽约，另一个部署在伦敦，并对纽约的边缘池或单个边缘服务器启用联盟支持，则联盟用户的信号流量将通过纽约的边缘池或单个边缘服务器。这同样适用于伦敦用户的通信，尽管伦敦内部用户呼叫伦敦联盟用户时将使用伦敦的池或边缘服务器路由 A/V 流量。</span><span class="sxs-lookup"><span data-stu-id="b8951-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="b8951-285">如果您计划支持适用于部署的可扩展消息传递和状态协议 (XMPP)，请选中“启用 XMPP 联盟(端口 5269)”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8951-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="b8951-286">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b8951-286">Click **Next**.</span></span>

8.  <span data-ttu-id="b8951-287">在“选择 IP 选项”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-288">**在内部接口上启用 ipv4**：如果要将 ipv4 地址应用到边缘服务器或边缘池内部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b8951-289">**在内部接口上启用 ipv6**：如果要将 ipv6 地址应用到边缘服务器或边缘池内部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b8951-290">**在外部接口上启用 ipv4**：如果要将 ipv4 地址应用到边缘服务器或边缘池外部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="b8951-291">**在外部接口上启用 ipv6**：如果要将 ipv6 地址应用到边缘服务器或边缘池外部接口，请选中此复选框</span><span class="sxs-lookup"><span data-stu-id="b8951-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b8951-p130"><STRONG></STRONG>请勿选中“边缘池的外部 IP 地址由 NAT 转换”<STRONG></STRONG>复选框。使用硬件负载平衡时，不支持网络地址转换 (NAT)。</span><span class="sxs-lookup"><span data-stu-id="b8951-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="b8951-294">在“外部 FQDN”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-295">如果在“选择功能”\*\*\*\* 中选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在“SIP 访问”\*\*\*\* 中键入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8951-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b8951-p131">如果选择此选项，则必须为每个边缘服务指定不同的端口号（推荐的端口设置为：访问边缘服务为 5061，Web 会议边缘服务为 444，A/V 边缘服务为 443）。通过选择此选项，可帮助防止潜在的连接问题并简化配置，因为可以将同一端口号（例如，443）用于所有三种服务。</span><span class="sxs-lookup"><span data-stu-id="b8951-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="b8951-p132">如果在“选择功能”\*\*\*\* 中未选择使用单个 FQDN 和 IP 地址，则在“SIP 访问”\*\*\*\* 中键入为边缘池的公共端选择的 FQDN。在“Web 会议”\*\*\*\* 中，键入为边缘池的公共端选择的 FQDN。在“音频/视频”\*\*\*\* 中，键入为边缘池的公共端选择的 FQDN。使用默认端口。</span><span class="sxs-lookup"><span data-stu-id="b8951-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b8951-302">这些 FQDN 将是池的公共虚拟 IP (VIP) FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8951-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="b8951-303">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b8951-303">Click **Next**.</span></span>

11. <span data-ttu-id="b8951-304">在“定义此池中的计算机”\*\*\*\* 中，单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="b8951-305">在“定义外部 IP 地址”\*\*\*\* 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-306">如果选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在“SIP 访问”\*\*\*\* 中键入边缘服务器的外部 IPv4 地址。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b8951-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="b8951-p133">如果未选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 会议服务，则在“SIP 访问”\*\*\*\* 中键入为该边缘池服务器的公共端选择的 IP 地址。在“Web 会议”\*\*\*\* 中，键入为该边缘池服务器的公共端选择的 IP 地址。在“A/V 会议”\*\*\*\* 中，键入为该边缘池服务器的公共端选择的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="b8951-310">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-310">Click **Next**.</span></span>

14. <span data-ttu-id="b8951-311">如果选择启用 IPv6 地址，请在“定义外部 IP 地址”\*\*\*\* 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8951-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="b8951-312">如果选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 边缘服务，请在“SIP 访问”\*\*\*\* 中键入边缘服务器的外部 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="b8951-p134">如果未选择将单个 FQDN 和 IP 地址用于 SIP 访问、Web 会议服务和 A/V 会议服务，则在“SIP 访问”\*\*\*\* 中键入为该边缘池服务器的公共端选择的 IPv6 地址。在“Web 会议”\*\*\*\* 中，键入为该边缘池服务器的公共端选择的 IPv6 地址。在“A/V 会议”\*\*\*\* 中，键入为该边缘池服务器的公共端选择的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="b8951-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-316">如果您未选择启用和分配 IPv6 寻址，则将不会显示此对话框。</span><span class="sxs-lookup"><span data-stu-id="b8951-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="b8951-317">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8951-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-318">此时可在<STRONG>“定义此池中的计算机”</STRONG>对话框中看到在池中创建的第一台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b8951-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="b8951-319">在“定义此池中的计算机”\*\*\*\* 中，单击“添加”\*\*\*\*，然后对要添加到边缘池的第二台边缘服务器重复步骤 11 至 14。</span><span class="sxs-lookup"><span data-stu-id="b8951-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="b8951-320">重复步骤 11 至 14 后，在 **“定义此池中的计算机”** 中单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-321">此时，可以在池中看到两台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="b8951-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="b8951-p135">在 **“定义下一个跃点”** 的 **“下一个跃点池”** 列表中，选择内部池的名称，该池可以是前端池，也可以是 Standard Edition 池。或者，如果部署中包括控制器，则选择控制器的名称。然后单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="b8951-325">在 **“关联前端池”** 中，通过选择将该边缘服务器用于与支持的外部用户进行通信的内部池的名称，来指定要与该边缘服务器关联的一个或多个内部池，其中可包括前端池和 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="b8951-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8951-p136">只能将一个负载平衡边缘池或单台边缘服务器与 A/V 流量的每个内部池关联。如果您已将内部池与边缘池或边缘服务器关联，则会显示警告，指出该内部池已与边缘池或边缘服务器关联。如果选择已与其他边缘服务器关联的池，则会更改关联。</span><span class="sxs-lookup"><span data-stu-id="b8951-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="b8951-329">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="b8951-329">Click **Finish**.</span></span>

21. <span data-ttu-id="b8951-330">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="b8951-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

