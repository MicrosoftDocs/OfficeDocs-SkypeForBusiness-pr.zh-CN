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
ms.openlocfilehash: 8c114766bffb665e2c7da2850fefc6113365e4c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="61ed1-102">在 Lync Server 2013 中配置网络适配器</span><span class="sxs-lookup"><span data-stu-id="61ed1-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61ed1-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="61ed1-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="61ed1-104">必须向外部网络适配器分配一个或多个 IP 地址，并向内部网络适配器分配至少一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="61ed1-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="61ed1-105">在下面的过程中，运行 Forefront 威胁管理网关（TMG）2010或 Internet Information Server 应用程序请求路由的服务器具有两个网络适配器：</span><span class="sxs-lookup"><span data-stu-id="61ed1-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="61ed1-106">一个公用或外部网络适配器，用于尝试连接到您的网站的客户端（通常在 Internet 上）。</span><span class="sxs-lookup"><span data-stu-id="61ed1-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="61ed1-107">一个专用的或内部的网络接口，用于运行承载 Web 服务的 Lync Server 的内部服务器。</span><span class="sxs-lookup"><span data-stu-id="61ed1-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="61ed1-108">与边缘服务器类似，您只需要在外部网络适配器上设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="61ed1-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="61ed1-109">默认网关将是将流量定向到 Internet 的路由器或面向外部的防火墙的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="61ed1-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="61ed1-110">对于从反向代理发送到面向内部的网络适配器的流量，必须对包含 web 发布规则所引用的服务器的所有子网使用永久静态路由（如 Windows Server 中的 route 命令）。</span><span class="sxs-lookup"><span data-stu-id="61ed1-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="61ed1-111">设置持久路由不会导致计算机成为路由器。</span><span class="sxs-lookup"><span data-stu-id="61ed1-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="61ed1-112">如果未启用 IP 转发，则计算机将仅作用为将其他网络的特定通信定向到适当的接口。</span><span class="sxs-lookup"><span data-stu-id="61ed1-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="61ed1-113">实际上，这是设置两个网关，一个是指向外部网络的默认网关，另一个用于发往内部接口和路由器或其他网络的通信。</span><span class="sxs-lookup"><span data-stu-id="61ed1-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="61ed1-114">但是，如果将网络路由器配置为汇总路由，则可能不需要为所有子网创建持久路由。</span><span class="sxs-lookup"><span data-stu-id="61ed1-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="61ed1-115">创建到定义了路由器的网络的持久路由，并将该路由器用作默认网关。</span><span class="sxs-lookup"><span data-stu-id="61ed1-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="61ed1-116">如果您不确定网络的配置方式，并需要有关需要创建的持久路由的指南，请咨询贵公司的网络工程师。</span><span class="sxs-lookup"><span data-stu-id="61ed1-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="61ed1-117">反向代理必须能够解析内部控制器或前端服务器的 DNS 主机（A）记录，以及 web 发布规则中使用的下一个跃点池 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="61ed1-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="61ed1-118">与边缘服务器一样，出于安全考虑，我们建议您不要将反向代理配置为使用位于内部网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="61ed1-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="61ed1-119">这意味着，您需要在外围中包含 DNS 服务器，或者需要反向代理上的主机文件条目，将这些 Fqdn 解析为服务器的内部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="61ed1-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="61ed1-120">在反向代理计算机上配置网络适配器卡</span><span class="sxs-lookup"><span data-stu-id="61ed1-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="61ed1-121">在 Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 服务器上运行作为反向代理，单击 "**开始**"，指向 **"控制面板**"，单击 "**网络和共享中心**"，然后单击 "**更改适配器设置**"，以打开 "**更改适配器设置**"。</span><span class="sxs-lookup"><span data-stu-id="61ed1-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="61ed1-122">右键单击要用于外部接口的外部网络连接，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="61ed1-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="61ed1-123">在 "**属性**" 页上，单击 "**网络**" 选项卡，单击 "**此连接使用下列项目**" 列表中的 " **Internet 协议版本4（TCP/IPv4）** "，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="61ed1-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="61ed1-124">在 " **Internet 协议（tcp/ip）属性**" 页上，配置与网络适配器连接到的网络子网对应的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="61ed1-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61ed1-125">如果反向代理已由其他使用 HTTPS/TCP/443 的应用程序使用，例如，对于发布 Outlook Web Access，您需要添加另一个 IP 地址，以便可以在 HTTPS/TCP/443 上发布 Lync Server 2013 Web 服务，而不会影响现有的规则和 Web 侦听器，或者需要将现有证书替换为将新的外部 FQDN 名称添加到使用者替代名称的现有证书。</span><span class="sxs-lookup"><span data-stu-id="61ed1-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="61ed1-126">单击 **"确定**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="61ed1-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="61ed1-127">在 "**网络连接**" 中，右键单击要用于内部接口的内部网络连接，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="61ed1-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="61ed1-128">重复步骤3到5以配置内部网络连接。</span><span class="sxs-lookup"><span data-stu-id="61ed1-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

