---
title: Lync Server 2013：定义边缘拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8364d2167b719e020ecebc3808c2ca850d14bc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="a19c3-102">在 Lync Server 2013 中定义边缘拓扑</span><span class="sxs-lookup"><span data-stu-id="a19c3-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a19c3-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a19c3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a19c3-104">必须使用拓扑生成器构建拓扑, 并且必须至少设置一个内部前端池或标准版服务器, 然后才能部署 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="a19c3-105">使用以下过程定义单个边缘服务器的边缘拓扑, 然后使用在[Lync server 2013 中发布拓扑](lync-server-2013-publish-your-topology.md)中的过程和[导出 lync server 2013 拓扑并将其复制到外部媒体进行边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)发布拓扑并使其可供边缘服务器使用。</span><span class="sxs-lookup"><span data-stu-id="a19c3-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a19c3-106">内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="a19c3-106">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="a19c3-107">您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="a19c3-107">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="a19c3-108">若要在添加或删除服务器角色时成功发布、启用或禁用拓扑, 您必须以 RTCUniversalServerAdmins 和域管理员组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="a19c3-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="a19c3-109">你还可以授予将服务器角色添加到用户帐户所需的管理员权限和权限。</span><span class="sxs-lookup"><span data-stu-id="a19c3-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="a19c3-110">有关详细信息, 请参阅在标准版服务器或企业版服务器部署文档中[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="a19c3-111">对于其他配置更改, 仅需要 RTCUniversalServerAdmins 组中的成员身份。</span><span class="sxs-lookup"><span data-stu-id="a19c3-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="a19c3-112">如果你在定义和发布内部拓扑时定义了 edge 拓扑, 并且你以前定义的边缘拓扑不需要进行任何更改, 则无需定义它并再次发布它。</span><span class="sxs-lookup"><span data-stu-id="a19c3-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="a19c3-113">仅当需要对 edge 拓扑进行更改时, 请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="a19c3-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="a19c3-114">你必须将以前定义和发布的拓扑提供给你的边缘服务器, 你可以通过使用[导出 Lync Server 2013 拓扑中的过程并将其复制到外部媒体进行边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a19c3-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a19c3-115">不能从边缘服务器运行拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="a19c3-116">必须从前端服务器或标准版服务器运行它。</span><span class="sxs-lookup"><span data-stu-id="a19c3-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="a19c3-117">定义边缘服务器拓扑的过程在拓扑生成器中完成。</span><span class="sxs-lookup"><span data-stu-id="a19c3-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="a19c3-118">下面列出了你计划和配置的三种主要类型的边缘服务器拓扑:</span><span class="sxs-lookup"><span data-stu-id="a19c3-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="a19c3-119">定义单个边缘服务器的拓扑</span><span class="sxs-lookup"><span data-stu-id="a19c3-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="a19c3-120">定义负载平衡的边缘服务器池的拓扑</span><span class="sxs-lookup"><span data-stu-id="a19c3-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="a19c3-121">定义硬件负载平衡的边缘池的拓扑</span><span class="sxs-lookup"><span data-stu-id="a19c3-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="a19c3-122">定义单个边缘服务器的拓扑</span><span class="sxs-lookup"><span data-stu-id="a19c3-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="a19c3-123">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a19c3-124">在控制台树中, 展开要在其中部署边缘服务器的网站。</span><span class="sxs-lookup"><span data-stu-id="a19c3-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="a19c3-125">右键单击 "**边缘池**", 然后单击 "**新建边缘池**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="a19c3-126">在 "**定义新的边缘池**" 中, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="a19c3-127">在 "**定义边缘池 FQDN**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-128">在 "**池 FQDN**" 中, 键入边缘服务器的内部接口的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a19c3-129">您指定的名称必须与服务器上配置的计算机名相同。</span><span class="sxs-lookup"><span data-stu-id="a19c3-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="a19c3-130">默认情况下, 未加入域的计算机的计算机名是一个短名称, 而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a19c3-131">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="a19c3-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a19c3-132">因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="a19c3-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a19c3-133">分配您的 Lync Server、边缘服务器和池的 FQDN 时，只使用标准字符（包括 A–Z、a–z、0–9 和连字符）。</span><span class="sxs-lookup"><span data-stu-id="a19c3-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="a19c3-134">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="a19c3-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a19c3-135">外部 DNS 和公共 Ca 通常不支持 FQDN 中的非标准字符 (当 FQDN 必须分配给证书中的 SN 时)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="a19c3-136">有关向计算机名添加 DNS 后缀的详细信息, 请参阅<A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中为 edge 支持配置 DNS</A>。</span><span class="sxs-lookup"><span data-stu-id="a19c3-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="a19c3-137">单击 "**单计算机池**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="a19c3-138">在 "**选择功能**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-139">如果你计划为 SIP Access 服务使用单个 FQDN 和 IP 地址, Lync Server 2013 Web 会议服务和 A/V 边缘服务, 请选中 "**使用单个 FQDN 和 Ip 地址**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="a19c3-140">如果你计划启用联盟, 请选中 "**为此 Edge 池启用联盟 (端口 5061)** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a19c3-141">你可以选择此选项, 但你的组织中只能为联盟发布一个 Edge 池或边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-141">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="a19c3-142">联盟用户 (包括公共即时消息 (IM) 用户) 的所有访问权限, 请访问同一 Edge 池或单个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-142">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="a19c3-143">例如, 如果你的部署包括在纽约部署的 Edge 池或单层服务器, 并且在伦敦部署了一个, 并且你在纽约的 Edge 池或单边服务器上启用了联合身份验证支持, 则联盟用户的信号流量将通过纽约边缘池或单边服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-143">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="a19c3-144">这同样适用于 London 用户的通信，尽管 London 内部用户呼叫 London 联盟用户时将使用 London 池或边缘服务器路由 A/V 流量。</span><span class="sxs-lookup"><span data-stu-id="a19c3-144">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="a19c3-145">如果你计划支持你的部署的可扩展消息和状态协议 (XMPP), 请选中 "**启用 XMPP 联合身份验证 (端口 5269)** " 复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="a19c3-146">在 "**选择 IP 选项**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-147">**在内部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a19c3-148">**在内部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a19c3-149">**在外部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="a19c3-150">**在外部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="a19c3-151">你还可以将 Edge 服务器或边缘池配置为使用外部 IP 地址的网络地址转换地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a19c3-152">要执行此操作, 请选中该复选框**此边缘池的外部 IP 地址由 NAT 转换**。</span><span class="sxs-lookup"><span data-stu-id="a19c3-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="a19c3-153">在**外部 fqdn**中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-154">如果在 "**选择" 功能中选择**使用单个 FQDN 和 IP 地址进行 sip 访问、Web 会议服务和 a/V 边缘服务, 请在 " **sip 访问**" 中键入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a19c3-155">如果选择此选项, 则必须为每个 edge 服务指定不同的端口号 (推荐的端口设置: 5061 用于访问边缘服务, 444 用于 Web 会议 Edge 服务, 443 用于 A/V 边缘服务)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-155">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="a19c3-156">选择此选项可帮助防止潜在的连接问题, 并简化配置, 因为你可以对所有三个服务使用相同的端口号 (例如, 443)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-156">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="a19c3-157">如果在 **"选择" 功能**中未选择使用单个 FQDN 和 IP 地址, 请键入**SIP 访问**、 **Web 会议**和**音频视频**的外部 fqdn, 并保留默认端口。</span><span class="sxs-lookup"><span data-stu-id="a19c3-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="a19c3-158">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-158">Click **Next**.</span></span>

10. <span data-ttu-id="a19c3-159">在 "**定义内部 IP 地址**" 中, 在 "**内部 IPv4 地址**" 和 "**内部 IPv6 地址**" 中键入边缘服务器的 IP 地址, 这适合你的要求。</span><span class="sxs-lookup"><span data-stu-id="a19c3-159">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements.</span></span> <span data-ttu-id="a19c3-160">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-160">Click **Next**.</span></span>

11. <span data-ttu-id="a19c3-161">在 "**定义外部 IP 地址**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-162">如果你选择对 SIP 访问、Web 会议服务和 A/V 边缘服务使用单个 FQDN 和 IP 地址, 请在**SIP access**中键入 Edge 服务器的外部 IPv4 地址, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="a19c3-163">如果您选择使用 IPv6 地址, 请在 " **SIP 访问**" 中键入边缘服务器的外部 IPv6 地址, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="a19c3-164">如果未选择使用单个 FQDN 和 IP 地址进行 SIP 访问、Web 会议服务和 A/V 边缘服务, 请在**SIP 访问**、 **Web 会议**和**a/v 会议**中键入边缘服务器的外部 IPv4 地址, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a19c3-165">如果你选择使用 IPv6 地址, 但未选择对 SIP 访问、Web 会议服务和 A/V 边缘服务使用单个 FQDN 和 IP 地址, 请在 " **Sip 访问**"、" **web 会议**" 和 "/" 中键入边缘服务器的外部 IPv6 地址。 **V 形会议**", 然后单击"**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a19c3-166">如果你没有选择启用和分配 IPv6 寻址, 则不会看到此对话框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="a19c3-167">如果您选择使用 NAT, 则会显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-167">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="a19c3-168">在**A/V 边缘服务的公共 ipv4 地址**中, 键入要由 NAT 转换的公共 ipv4 地址, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-168">In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-169">这应该是 A/V 边缘服务的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="a19c3-170">如果您选择使用 NAT 和 IPv6 地址, 则会出现一个对话框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-170">If you chose to use NAT and IPv6 addresses, a dialog box appears.</span></span> <span data-ttu-id="a19c3-171">在**A/V 边缘服务的公共 ipv6 地址**中, 键入要由 NAT 转换的公共 ipv6 地址, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-171">In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-172">这应该是 A/V 边缘服务的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="a19c3-173">在 "**定义下一跃点**" 的 "**下一跃点" 池中**, 选择内部池的名称, 该名称可以是前端池, 也可以是标准版池。</span><span class="sxs-lookup"><span data-stu-id="a19c3-173">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="a19c3-174">或者, 如果你的部署包含 Director, 请选择 Director。</span><span class="sxs-lookup"><span data-stu-id="a19c3-174">Or, if your deployment includes a Director, select the Director.</span></span> <span data-ttu-id="a19c3-175">然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-175">Then, click **Next**.</span></span>

15. <span data-ttu-id="a19c3-176">在**关联前端池**中, 指定一个或多个内部池 (其中包括要与此边缘服务器关联的前端池和标准版服务器), 方法是选择要使用此 edge 服务器的内部池的名称与受支持的外部用户的通信。</span><span class="sxs-lookup"><span data-stu-id="a19c3-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-177">对于 A/V 流量, 只能将一个负载平衡的边缘池或单个边缘服务器与每个内部池相关联。</span><span class="sxs-lookup"><span data-stu-id="a19c3-177">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="a19c3-178">如果你已有与边缘池或边缘服务器关联的内部池, 则会显示一条警告, 指示内部池已关联到边缘池或边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-178">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="a19c3-179">如果你选择的池已与另一 Edge 服务器关联, 则它将更改关联。</span><span class="sxs-lookup"><span data-stu-id="a19c3-179">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="a19c3-180">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a19c3-180">Click **Finish**.</span></span>

17. <span data-ttu-id="a19c3-181">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="a19c3-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="a19c3-182">定义 DNS 负载平衡的边缘服务器池的拓扑</span><span class="sxs-lookup"><span data-stu-id="a19c3-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="a19c3-183">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a19c3-184">在控制台树中, 展开要在其中部署边缘服务器的网站。</span><span class="sxs-lookup"><span data-stu-id="a19c3-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="a19c3-185">右键单击 "**边缘池**", 然后单击 "**新建边缘池**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="a19c3-186">在 "**定义新的边缘池**" 中, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="a19c3-187">在 "**定义边缘池 FQDN**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-188">在 "**池 FQDN**" 中, 键入边缘池的内部连接的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a19c3-189">为池指定的名称必须是内部边缘池名称。</span><span class="sxs-lookup"><span data-stu-id="a19c3-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="a19c3-190">必须将其定义为 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="a19c3-191">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="a19c3-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a19c3-192">分配您的 Lync Server、边缘服务器和池的 FQDN 时，只使用标准字符（包括 A–Z、a–z、0–9 和连字符）。</span><span class="sxs-lookup"><span data-stu-id="a19c3-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="a19c3-193">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="a19c3-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a19c3-194">外部 DNS 和公共 Ca 通常不支持 FQDN 中的非标准字符 (当 FQDN 必须分配给证书中的 SN 时)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="a19c3-195">单击 "**多台计算机池**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="a19c3-196">在 "**选择功能**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-197">如果你计划将单个 FQDN 和 IP 地址用于 SIP 访问, 请使用 Lync Server 2013 Web 会议服务和 A/V 边缘服务, 选中 "**使用单个 FQDN 和 Ip 地址**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="a19c3-198">如果你计划启用联盟, 请选中 "**为此 Edge 池启用联盟 (端口 5061)** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-198">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span> <span data-ttu-id="a19c3-199">单击 "**下一步**"</span><span class="sxs-lookup"><span data-stu-id="a19c3-199">Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a19c3-200">你可以选择此选项, 但你的组织中只能为联盟发布一个 Edge 池或边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-200">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="a19c3-201">联盟用户 (包括公共即时消息 (IM) 用户) 的所有访问权限, 请访问同一 Edge 池或单个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-201">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="a19c3-202">例如，如果部署中有一个边缘池或单个边缘服务器部署在纽约，另一个部署在伦敦，并对纽约的边缘池或单个边缘服务器启用联盟支持，则联盟用户的信号流量将通过纽约的边缘池或单个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-202">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="a19c3-203">这同样适用于 London 用户的通信，尽管 London 内部用户呼叫 London 联盟用户时将使用 London 池或边缘服务器路由 A/V 流量。</span><span class="sxs-lookup"><span data-stu-id="a19c3-203">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="a19c3-204">如果你计划支持你的部署的可扩展消息和状态协议 (XMPP), 请选中 "**启用 XMPP 联合身份验证 (端口 5269)** " 复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="a19c3-205">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-205">Click **Next**.</span></span>

8.  <span data-ttu-id="a19c3-206">在 "**选择 IP 选项**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-207">**在内部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a19c3-208">**在内部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a19c3-209">**在外部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="a19c3-210">**在外部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="a19c3-211">你还可以将 Edge 服务器或边缘池配置为使用外部 IP 地址的网络地址转换地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a19c3-212">要执行此操作, 请选中该复选框**此边缘池的外部 IP 地址由 NAT 转换**。</span><span class="sxs-lookup"><span data-stu-id="a19c3-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="a19c3-213">在**外部 fqdn**中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-214">如果在 "**选择" 功能中选择**使用单个 FQDN 和 IP 地址进行 sip 访问、Web 会议服务和 a/V 边缘服务, 请在 " **sip 访问**" 中键入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a19c3-215">如果选择此选项, 则必须为每个 Edge 服务指定不同的端口号 (推荐的端口设置: 5061 用于访问边缘服务, 444 用于 Web 会议 Edge 服务, 443 用于 A/V 边缘服务)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-215">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="a19c3-216">通过选择此选项, 你可以帮助防止潜在的连接问题, 并简化配置, 因为你可以对所有三个服务使用相同的端口号 (例如, 443)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-216">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="a19c3-217">如果在 "**选择" 功能**中未选择使用单个 FQDN 和 IP 地址, 请在 " **SIP 访问**" 中键入您为 edge 池的公共对开面选择的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-217">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="a19c3-218">在 " **Web 会议**" 中, 键入为边缘池的公共面向面选择的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-218">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="a19c3-219">在 "**音频/视频**" 中, 键入为边缘池的公共面向面选择的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-219">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="a19c3-220">使用默认端口。</span><span class="sxs-lookup"><span data-stu-id="a19c3-220">Use the default ports.</span></span>

10. <span data-ttu-id="a19c3-221">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-221">Click **Next**.</span></span>

11. <span data-ttu-id="a19c3-222">在 "**定义此池中的计算机**" 中, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="a19c3-223">在 "**内部 FQDN 和 IP 地址**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-224">在 "**内部 IPv4 地址**" 中, 键入 IPv4 地址和**内部 IPv6 地址**, 以适合你希望在此池中创建的第一个边缘服务器的要求。</span><span class="sxs-lookup"><span data-stu-id="a19c3-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="a19c3-225">在 "**内部 FQDN**" 中, 键入要在此池中创建的第一个边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a19c3-226">指定的名称必须与在服务器上配置的计算机名称相同。</span><span class="sxs-lookup"><span data-stu-id="a19c3-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="a19c3-227">默认情况下，未加入域的计算机的计算机名称为短名称，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a19c3-228">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="a19c3-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a19c3-229">因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="a19c3-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a19c3-230">分配 Lync 服务器、边缘服务器、池和数组的 Fqdn 时, 只使用标准字符 (包括 A-Z、a-z、0-9 和连字符)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="a19c3-231">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="a19c3-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a19c3-232">外部 DNS 和公共 Ca 通常不支持 FQDN 中的非标准字符 (当 FQDN 必须分配给证书中的 SN 时)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="a19c3-233">有关向计算机名添加 DNS 后缀的详细信息, 请参阅<A href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中为 edge 支持配置 DNS</A>。</span><span class="sxs-lookup"><span data-stu-id="a19c3-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="a19c3-234">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-234">Click **Next**.</span></span>

14. <span data-ttu-id="a19c3-235">在 "**定义外部 IP 地址**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-236">如果你选择对 SIP 访问、Web 会议服务和 A/V 边缘服务使用单个 FQDN 和 IP 地址, 请在**SIP access**中键入边缘服务器的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a19c3-237">如果你未选择使用单个 FQDN 和 IP 地址进行 SIP 访问、Web 会议服务和 A/V 会议服务, 请键入为此 Edge 池服务器的公共对开面选择的 IP 地址以进行**Sip 访问**。</span><span class="sxs-lookup"><span data-stu-id="a19c3-237">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="a19c3-238">在 " **Web 会议**" 中, 键入您为此 Edge 池服务器的公共对开面选择的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-238">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="a19c3-239">在**A/V 会议**中, 键入为此 Edge 池服务器的公共对开面选择的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-239">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="a19c3-240">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-240">Click **Next**.</span></span>

16. <span data-ttu-id="a19c3-241">如果您选择启用 IPv6 地址, 请在 "**定义外部 IP 地址**" 中执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-242">如果你选择对 SIP 访问、Web 会议服务和 A/V 边缘服务使用单个 FQDN 和 IP 地址, 请在**SIP access**中键入边缘服务器的外部 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a19c3-243">如果您没有选择使用单个 FQDN 和 IP 地址进行 SIP 访问、Web 会议服务和 A/V 会议服务, 请键入为该 Edge 池服务器的公共对开面选择的 IPv6 地址以进行**Sip 访问**。</span><span class="sxs-lookup"><span data-stu-id="a19c3-243">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="a19c3-244">在**Web 会议**中, 键入你为此 Edge 池服务器的公共对开面选择的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-244">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="a19c3-245">在**A/V 会议**中, 键入你为此 Edge 池服务器的公共对开面选择的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-245">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-246">如果你没有选择启用和分配 IPv6 寻址, 则不会看到此对话框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="a19c3-247">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a19c3-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-248">现在, 你将在 "<STRONG>定义此池中的计算机</STRONG>" 对话框中的池中看到你创建的第一个 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="a19c3-249">在 "**定义此池中的计算机**" 中, 单击 "**添加**", 然后为要添加到 Edge 池的第二边缘服务器重复步骤11到步骤14。</span><span class="sxs-lookup"><span data-stu-id="a19c3-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="a19c3-250">重复步骤11至14后, 在 "**定义此池中的计算机"** 中单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-251">此时, 你可以看到池中的两个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="a19c3-252">如果您选择使用 NAT, 则会显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-252">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="a19c3-253">在 "**公共 IP 地址**" 中, 键入要由 NAT 转换的公共 IPv4 和 IPv6 (根据需要) 地址, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-253">In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-254">这应该是 A/V 边缘的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="a19c3-255">在 "**定义下一跃点**" 下的 "**下一跃点池**" 列表中, 选择内部池的名称, 该名称可以是前端池, 也可以是标准版池。</span><span class="sxs-lookup"><span data-stu-id="a19c3-255">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="a19c3-256">或者, 如果你的部署包含 Director, 请选择 Director 的名称。</span><span class="sxs-lookup"><span data-stu-id="a19c3-256">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="a19c3-257">然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-257">Then, click **Next**.</span></span>

22. <span data-ttu-id="a19c3-258">在**关联前端池**中, 指定一个或多个内部池 (其中包括要与此边缘服务器关联的前端池和标准版服务器), 方法是选择要使用此 edge 服务器的内部池的名称与受支持的外部用户的通信。</span><span class="sxs-lookup"><span data-stu-id="a19c3-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-259">对于 A/V 流量, 只能将一个负载平衡的边缘池或单个边缘服务器与每个内部池相关联。</span><span class="sxs-lookup"><span data-stu-id="a19c3-259">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="a19c3-260">如果你已有与边缘池或边缘服务器关联的内部池, 则会显示一条警告, 指示内部池已关联到边缘池或边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-260">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="a19c3-261">如果你选择的池已与另一 Edge 服务器关联, 则它将更改关联。</span><span class="sxs-lookup"><span data-stu-id="a19c3-261">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="a19c3-262">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a19c3-262">Click **Finish**.</span></span>

24. <span data-ttu-id="a19c3-263">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="a19c3-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="a19c3-264">定义硬件负载平衡的边缘服务器池的拓扑</span><span class="sxs-lookup"><span data-stu-id="a19c3-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="a19c3-265">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a19c3-266">在控制台树中, 展开要在其中部署边缘服务器的网站。</span><span class="sxs-lookup"><span data-stu-id="a19c3-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="a19c3-267">右键单击 "**边缘池**", 然后选择 "**新建边缘池**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="a19c3-268">在 "**定义新的边缘池**" 中, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="a19c3-269">在 "**定义边缘池 FQDN**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-270">在 " **FQDN**" 中, 键入为边缘池的内部端选择的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a19c3-271">为池指定的名称必须是内部边缘池名称。</span><span class="sxs-lookup"><span data-stu-id="a19c3-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="a19c3-272">必须将其定义为 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="a19c3-273">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="a19c3-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a19c3-274">分配您的 Lync Server、边缘服务器和池的 FQDN 时，只使用标准字符（包括 A–Z、a–z、0–9 和连字符）。</span><span class="sxs-lookup"><span data-stu-id="a19c3-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="a19c3-275">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="a19c3-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a19c3-276">外部 DNS 和公共 Ca 通常不支持 FQDN 中的非标准字符 (当 FQDN 必须分配给证书中的 SN 时)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="a19c3-277">单击 "**多台计算机池**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="a19c3-278">在 "**选择功能**" 中, 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="a19c3-279">如果你计划为 SIP access 服务、Lync Server Web 会议服务和 A/V 边缘服务使用单个 FQDN 和 IP 地址, 请选中 "**使用单个 FQDN & IP 地址**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="a19c3-280">如果你计划启用联盟, 请选中 "**为此 Edge 池启用联盟 (端口 5061)** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a19c3-281">你可以选择此选项, 但你的组织中只能有一个 Edge 池或边缘服务器可在外部针对联盟进行发布。</span><span class="sxs-lookup"><span data-stu-id="a19c3-281">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="a19c3-282">联盟用户 (包括公共即时消息 (IM) 用户) 的所有访问权限, 请访问同一 Edge 池或单个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-282">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="a19c3-283">例如，如果部署中有一个边缘池或单个边缘服务器部署在纽约，另一个部署在伦敦，并对纽约的边缘池或单个边缘服务器启用联盟支持，则联盟用户的信号流量将通过纽约的边缘池或单个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-283">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="a19c3-284">这同样适用于 London 用户的通信，尽管 London 内部用户呼叫 London 联盟用户时将使用 London 池或边缘服务器路由 A/V 流量。</span><span class="sxs-lookup"><span data-stu-id="a19c3-284">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="a19c3-285">如果你计划支持你的部署的可扩展消息和状态协议 (XMPP), 请选中 "**启用 XMPP 联合身份验证 (端口 5269)** " 复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="a19c3-286">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-286">Click **Next**.</span></span>

8.  <span data-ttu-id="a19c3-287">在 "**选择 IP 选项**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-288">**在内部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a19c3-289">**在内部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池内部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a19c3-290">**在外部接口上启用 ipv4**: 如果要将 ipv4 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="a19c3-291">**在外部接口上启用 ipv6**: 如果要将 ipv6 地址应用到边缘服务器或边缘池外部接口, 请选中该复选框</span><span class="sxs-lookup"><span data-stu-id="a19c3-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a19c3-292"><STRONG>不要</STRONG>选择 "<STRONG>通过 NAT 转换边缘池的外部 IP 地址</STRONG>" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-292"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box.</span></span> <span data-ttu-id="a19c3-293">使用硬件负载平衡时, 不支持网络地址转换 (NAT)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-293">Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="a19c3-294">在**外部 fqdn**中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-295">如果在 "**选择" 功能中选择**使用单个 FQDN 和 IP 地址进行 sip 访问、Web 会议服务和 a/V 边缘服务, 请在 " **sip 访问**" 中键入外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a19c3-296">如果选择此选项, 则必须为每个 Edge 服务指定不同的端口号 (推荐的端口设置: 5061 用于访问边缘服务, 444 用于 Web 会议 Edge 服务, 443 适用于 A/V 边缘服务)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-296">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="a19c3-297">通过选择此选项, 你可以帮助防止潜在的连接问题, 并简化配置, 因为你可以对所有三个服务使用相同的端口号 (例如, 443)。</span><span class="sxs-lookup"><span data-stu-id="a19c3-297">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="a19c3-298">如果在 "**选择" 功能**中未选择使用单个 FQDN 和 IP 地址, 请在 " **SIP 访问**" 中键入您为 edge 池的公共对开面选择的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-298">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="a19c3-299">在 " **Web 会议**" 中, 键入为边缘池的公共面向面选择的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-299">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="a19c3-300">在 "**音频/视频**" 中, 键入为边缘池的公共面向面选择的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a19c3-300">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="a19c3-301">使用默认端口。</span><span class="sxs-lookup"><span data-stu-id="a19c3-301">Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a19c3-302">这些将是池的面向公众的虚拟 IP (VIP) Fqdn。</span><span class="sxs-lookup"><span data-stu-id="a19c3-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="a19c3-303">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-303">Click **Next**.</span></span>

11. <span data-ttu-id="a19c3-304">在 "**定义此池中的计算机**" 中, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="a19c3-305">在 "**定义外部 IP 地址**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-306">如果你选择对 SIP 访问、Web 会议服务和 A/V 边缘服务使用单个 FQDN 和 IP 地址, 请在**Sip 访问**中键入 edge 服务器的外部 IPv4 地址。 **sip 访问**中的边缘服务器的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a19c3-307">如果你未选择使用单个 FQDN 和 IP 地址进行 SIP 访问、Web 会议服务和 A/V 会议服务, 请键入为此 Edge 池服务器的公共对开面选择的 IP 地址以进行**Sip 访问**。</span><span class="sxs-lookup"><span data-stu-id="a19c3-307">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="a19c3-308">在 " **Web 会议**" 中, 键入您为此 Edge 池服务器的公共对开面选择的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-308">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="a19c3-309">在**A/V 会议**中, 键入为此 Edge 池服务器的公共对开面选择的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-309">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="a19c3-310">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-310">Click **Next**.</span></span>

14. <span data-ttu-id="a19c3-311">如果您选择启用 IPv6 地址, 请在 "**定义外部 IP 地址**" 中执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a19c3-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a19c3-312">如果你选择对 SIP 访问、Web 会议服务和 A/V 边缘服务使用单个 FQDN 和 IP 地址, 请在**SIP access**中键入边缘服务器的外部 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a19c3-313">如果您没有选择使用单个 FQDN 和 IP 地址进行 SIP 访问、Web 会议服务和 A/V 会议服务, 请键入为该 Edge 池服务器的公共对开面选择的 IPv6 地址以进行**Sip 访问**。</span><span class="sxs-lookup"><span data-stu-id="a19c3-313">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="a19c3-314">在**Web 会议**中, 键入你为此 Edge 池服务器的公共对开面选择的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-314">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="a19c3-315">在**A/V 会议**中, 键入你为此 Edge 池服务器的公共对开面选择的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="a19c3-315">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-316">如果你没有选择启用和分配 IPv6 寻址, 则不会看到此对话框。</span><span class="sxs-lookup"><span data-stu-id="a19c3-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="a19c3-317">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a19c3-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-318">现在, 你将在 "<STRONG>定义此池中的计算机</STRONG>" 对话框中的池中看到你创建的第一个 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="a19c3-319">在 "**定义此池中的计算机**" 中, 单击 "**添加**", 然后为要添加到 Edge 池的第二边缘服务器重复步骤11到步骤14。</span><span class="sxs-lookup"><span data-stu-id="a19c3-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="a19c3-320">重复步骤11至14后, 在 "**定义此池中的计算机"** 中单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-321">此时, 你可以看到池中的两个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="a19c3-322">在 "**定义下一跃点**" 下的 "**下一跃点池**" 列表中, 选择内部池的名称, 该名称可以是前端池, 也可以是标准版池。</span><span class="sxs-lookup"><span data-stu-id="a19c3-322">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="a19c3-323">或者, 如果你的部署包含 Director, 请选择 Director 的名称。</span><span class="sxs-lookup"><span data-stu-id="a19c3-323">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="a19c3-324">然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a19c3-324">Then, click **Next**.</span></span>

19. <span data-ttu-id="a19c3-325">在**关联前端池**中, 指定一个或多个内部池 (其中包括要与此边缘服务器关联的前端池和标准版服务器), 方法是选择要使用此 edge 服务器的内部池的名称与受支持的外部用户的通信。</span><span class="sxs-lookup"><span data-stu-id="a19c3-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a19c3-326">对于 A/V 流量, 只能将一个负载平衡的边缘池或单个边缘服务器与每个内部池相关联。</span><span class="sxs-lookup"><span data-stu-id="a19c3-326">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="a19c3-327">如果你已有与边缘池或边缘服务器关联的内部池, 则会显示一条警告, 指示内部池已关联到边缘池或边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a19c3-327">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="a19c3-328">如果你选择的池已与另一 Edge 服务器关联, 则它将更改关联。</span><span class="sxs-lookup"><span data-stu-id="a19c3-328">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="a19c3-329">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a19c3-329">Click **Finish**.</span></span>

21. <span data-ttu-id="a19c3-330">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="a19c3-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

