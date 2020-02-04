---
title: Lync Server 2013：配置网络适配器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="6150c-102">在 Lync Server 2013 中配置网络适配器</span><span class="sxs-lookup"><span data-stu-id="6150c-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6150c-103">_**主题上次修改时间：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6150c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6150c-104">必须将一个或多个 IP 地址分配给外部网络适配器，并将至少一个 IP 地址分配给内部网络适配器。</span><span class="sxs-lookup"><span data-stu-id="6150c-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="6150c-105">在以下过程中，运行 Forefront 威胁管理网关（TMG）2010或 Internet Information Server 应用程序请求路由的服务器具有两个网络适配器：</span><span class="sxs-lookup"><span data-stu-id="6150c-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="6150c-106">用于尝试连接到您的网站（通常通过 Internet）的客户端的公共网络适配器或外部网络适配器。</span><span class="sxs-lookup"><span data-stu-id="6150c-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="6150c-107">运行 Lync Server 托管 Web 服务的内部服务器的专用网络接口或内部网络接口。</span><span class="sxs-lookup"><span data-stu-id="6150c-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6150c-108">与边缘服务器类似，仅在外部网络适配器上设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="6150c-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="6150c-109">默认网关将是路由器的 IP 地址或将流量定向到 Internet 的面向外部的防火墙。</span><span class="sxs-lookup"><span data-stu-id="6150c-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="6150c-110">对于发往面向内部网络适配器的反向代理的流量，必须对包含 web 发布规则所引用的服务器的所有子网使用永久静态路由（如 Windows Server 中的 route 命令）。</span><span class="sxs-lookup"><span data-stu-id="6150c-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="6150c-111">设置持久路由不会导致计算机成为路由器。</span><span class="sxs-lookup"><span data-stu-id="6150c-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="6150c-112">如果未启用 IP 转发，则计算机仅适用于将其他网络的特定流量定向到相应的接口。</span><span class="sxs-lookup"><span data-stu-id="6150c-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="6150c-113">这基本上是设置两个网关-一个是指向外部网络的默认网关，另一个用于发送到内部接口和路由器或其他网络的通信。</span><span class="sxs-lookup"><span data-stu-id="6150c-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="6150c-114">但是，如果您的网络路由器配置为概括路由，则可能不需要为所有子网创建持久路由。</span><span class="sxs-lookup"><span data-stu-id="6150c-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="6150c-115">创建到定义路由器的网络的永久路由，并将该路由器用作默认网关。</span><span class="sxs-lookup"><span data-stu-id="6150c-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="6150c-116">如果不确定您的网络的配置方式，并且需要有关需要创建的持久路由的指南，请咨询贵公司的网络工程师。</span><span class="sxs-lookup"><span data-stu-id="6150c-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="6150c-117">反向代理服务器必须能够解析内部控制器或前端服务器的 DNS 主机（A）记录和 web 发布规则中使用的下一个跃点池 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="6150c-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="6150c-118">与边缘服务器一样，出于安全考虑，我们建议你不要将反向代理配置为使用位于内部网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="6150c-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="6150c-119">这意味着你需要在外围服务器中加入 DNS 服务器，或者你需要将这些 Fqdn 解析为服务器内部 IP 地址的反向代理上的主机文件条目。</span><span class="sxs-lookup"><span data-stu-id="6150c-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="6150c-120">在反向代理计算机上配置网络适配器卡</span><span class="sxs-lookup"><span data-stu-id="6150c-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="6150c-121">在 Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 或运行为反向代理的 Windows Server 2012 R2 服务器上，通过单击 "**开始**"，指向 **"控制面板**"，单击 "**网络和共享中心**"，然后单击 "**更改适配器设置**"，打开 "**更改适配器设置**"。</span><span class="sxs-lookup"><span data-stu-id="6150c-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="6150c-122">右键单击要用于外部接口的外部网络连接，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="6150c-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="6150c-123">在 "**属性**" 页上，单击 "**网络**" 选项卡，单击 "**此连接使用下列项目"** 列表中的 " **Internet 协议版本4（TCP/IPv4）** "，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="6150c-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="6150c-124">在 " **Internet 协议（tcp/ip）属性**" 页上，根据需要为连接网络适配器的网络子网配置 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6150c-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6150c-125">如果反向代理已由使用 HTTPS/TCP/443 的其他应用程序使用，例如，对于发布 Outlook Web Access，你需要添加另一个 IP 地址，以便你可以在不影响现有规则和 Web 侦听器的情况下在 HTTPS/TCP/443 上发布 Lync Server 2013 Web 服务，或者你需要将新的外部 FQDN 名称替换为使用者备用名称的现有证书。</span><span class="sxs-lookup"><span data-stu-id="6150c-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="6150c-126">单击 **"确定**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="6150c-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="6150c-127">在 "**网络连接**" 中，右键单击要用于内部接口的内部网络连接，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="6150c-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="6150c-128">重复步骤3到步骤5配置内部网络连接。</span><span class="sxs-lookup"><span data-stu-id="6150c-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

