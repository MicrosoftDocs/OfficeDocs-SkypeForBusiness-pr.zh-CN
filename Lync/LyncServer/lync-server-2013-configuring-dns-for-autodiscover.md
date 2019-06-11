---
title: 'Lync Server 2013: 配置用于自动发现的 DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c490cac475f3b9a9c8038636f4ac7f6670f22637
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="c96a1-102">在 Lync Server 2013 中配置自动发现的 DNS</span><span class="sxs-lookup"><span data-stu-id="c96a1-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c96a1-103">_**主题上次修改时间:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="c96a1-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="c96a1-104">若要支持 Lync 客户端的自动发现, 你需要创建以下域名系统 (DNS) 记录:</span><span class="sxs-lookup"><span data-stu-id="c96a1-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="c96a1-105">支持从组织的网络中连接的 Lync 客户端的内部 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c96a1-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="c96a1-106">支持从 Internet 连接的 Lync 客户端的外部 DNS 记录或公共 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c96a1-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="c96a1-107">必须为每个 SIP 域创建一个内部 DNS 记录和一个外部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="c96a1-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="c96a1-108">DNS 记录可以是 (主机) 记录或 CNAME 记录, 具体取决于使用其他主题备用名称 (SAN) 创建新证书的能力。</span><span class="sxs-lookup"><span data-stu-id="c96a1-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="c96a1-109">如果无法使用 lyncdiscover 请求和部署新的外部 (公共) 证书。\<域名\> SAN, 请使用 HTTP/TCP 端口80的过程。</span><span class="sxs-lookup"><span data-stu-id="c96a1-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\> SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="c96a1-110">以下过程介绍了如何创建内部和外部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="c96a1-110">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="c96a1-111">创建 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="c96a1-111">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="c96a1-112">按如下方式登录到 DNS 服务器:</span><span class="sxs-lookup"><span data-stu-id="c96a1-112">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="c96a1-113">若要创建内部 DNS 记录, 请以域管理员组的成员或 DnsAdmins 组的成员身份登录到您的网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="c96a1-113">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="c96a1-114">若要创建外部 DNS 记录, 请连接到您的公共 DNS 提供商。</span><span class="sxs-lookup"><span data-stu-id="c96a1-114">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="c96a1-115">打开 "DNS 管理" 管理单元: 单击 "**开始**", 单击 "**管理工具**", 然后单击 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="c96a1-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="c96a1-116">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c96a1-116">Do one of the following:</span></span>
    
      - <span data-ttu-id="c96a1-117">对于内部 DNS 记录, 请在 DNS 服务器的控制台树中, 展开您的 Active Directory 域的 "**正向查找区域**" (例如, "contoso")。</span><span class="sxs-lookup"><span data-stu-id="c96a1-117">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c96a1-118">此域是安装 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="c96a1-118">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="c96a1-119">对于外部 DNS 记录, 请在 DNS 服务器的控制台树中, 展开您的 SIP 域的 "**正向查找区域**" (例如, contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-119">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="c96a1-120">验证主机 A 是否存在针对你的控制器池的记录, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c96a1-120">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="c96a1-121">对于内部 DNS 记录, 你的控制器池的内部 Web 服务完全限定的域名 (FQDN) 应存在主机 A 记录 (例如, lyncwebdir01)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-121">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="c96a1-122">对于外部 DNS 记录, 你的控制器池的外部 web 服务 FQDN 应存在主机 A 记录 (例如, lyncwebextdir.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-122">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="c96a1-123">验证主机 A 是否存在用于你的前端池的记录, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c96a1-123">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="c96a1-124">对于内部 DNS 记录, 你的前端池的内部 Web 服务 FQDN 应存在主机 A 记录 (例如, lyncwebpool01)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-124">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="c96a1-125">对于外部 DNS 记录, 你的前端池的外部 Web 服务 FQDN 应存在主机 A 记录 (例如, lyncwebextpool01.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-125">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="c96a1-126">对于内部 DNS 记录, 请在 DNS 服务器的控制台树中, 展开您的 SIP 域的 "**正向查找区域**" (例如, contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-126">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c96a1-127">如果你要创建外部 DNS 记录, 则已为你的 SIP 域在步骤3中展开了 "<STRONG>正向查找区域</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="c96a1-127">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="c96a1-128">右键单击 SIP 域名称, 然后单击 "**新建别名 (CNAME)**"。</span><span class="sxs-lookup"><span data-stu-id="c96a1-128">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="c96a1-129">在 "**别名名称**" 中, 键入下列内容之一:</span><span class="sxs-lookup"><span data-stu-id="c96a1-129">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="c96a1-130">对于内部 DNS 记录, 请键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="c96a1-130">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="c96a1-131">对于外部 DNS 记录, 请键入 lyncdiscover 作为外部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="c96a1-131">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="c96a1-132">**对于目标主机的完全限定的域名 (FQDN)**, 请执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="c96a1-132">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="c96a1-133">对于内部 DNS 记录, 请键入或浏览到你的控制器池的内部 Web 服务 FQDN (例如, lyncwebdir01), 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c96a1-133">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="c96a1-134">对于外部 DNS 记录, 请键入或浏览到你的控制器池的外部 Web 服务 FQDN (例如, lyncwebextdir.contoso.com), 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c96a1-134">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c96a1-135">如果不使用 Director, 请对前端池使用内部和外部 Web 服务 FQDN, 或者对于单个服务器, 使用前端服务器或标准版服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c96a1-135">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c96a1-136">必须在 Lync Server 2013 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="c96a1-136">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="c96a1-137">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c96a1-137">To create DNS A records</span></span>

1.  <span data-ttu-id="c96a1-138">按如下方式登录到 DNS 服务器:</span><span class="sxs-lookup"><span data-stu-id="c96a1-138">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="c96a1-139">若要创建内部 DNS 记录, 请以域管理员组的成员或 DnsAdmins 组的成员身份登录到您的网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="c96a1-139">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="c96a1-140">若要创建外部 DNS 记录, 请连接到您的公共 DNS 提供商或外部 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="c96a1-140">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="c96a1-141">打开 "DNS 管理" 管理单元: 单击 "**开始**", 单击 "**管理工具**", 然后单击 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="c96a1-141">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="c96a1-142">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c96a1-142">Do one of the following:</span></span>
    
      - <span data-ttu-id="c96a1-143">对于内部 DNS 记录, 请在 DNS 服务器的控制台树中, 展开您的 Active Directory 域的 "**正向查找区域**" (例如, "contoso")。</span><span class="sxs-lookup"><span data-stu-id="c96a1-143">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c96a1-144">此域是安装 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="c96a1-144">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="c96a1-145">对于外部 DNS 记录, 请在 DNS 服务器的控制台树中, 展开您的 SIP 域的 "**正向查找区域**" (例如, contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-145">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="c96a1-146">验证控制器池的主机 A (for IPv6、AAAA) 记录是否存在, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c96a1-146">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="c96a1-147">对于内部 DNS 记录, 你的控制器池的内部 Web 服务 FQDN 应存在主机 A (for IPv6, AAAA) 记录 (例如, lyncwebdir01)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-147">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="c96a1-148">对于外部 DNS 记录, 你的控制器池的外部 Web 服务 FQDN 应存在主机 A (for IPv6, AAAA) 记录 (例如, lyncwebextdir.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-148">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="c96a1-149">验证你的前端池的主机 A (适用于 IPv6、AAAA) 记录是否存在, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c96a1-149">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="c96a1-150">对于内部 DNS 记录, 你的前端池 (例如, lyncwebpool01) 的内部 Web 服务 FQDN 应存在主机 A (for IPv6, AAAA) 记录。</span><span class="sxs-lookup"><span data-stu-id="c96a1-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="c96a1-151">对于外部 DNS 记录, 你的前端池的外部 Web 服务 FQDN 应存在主机 A (for IPv6, AAAA) 记录 (例如, lyncwebextpool01.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="c96a1-152">对于内部 DNS 记录, 请在 DNS 服务器的控制台树中, 展开您的 SIP 域的 "**正向查找区域**" (例如, contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="c96a1-152">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c96a1-153">如果你要创建外部 DNS 记录, 则已为你的 SIP 域在步骤3中展开了 "<STRONG>正向查找区域</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="c96a1-153">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="c96a1-154">右键单击 SIP 域名称, 然后单击 "**新建主机 (A 或 AAAA)**"。</span><span class="sxs-lookup"><span data-stu-id="c96a1-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="c96a1-155">在 "**名称**" 中, 键入主机名, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c96a1-155">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="c96a1-156">对于内部 DNS 记录, 请键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="c96a1-156">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="c96a1-157">对于外部 DNS 记录, 请键入 lyncdiscover 作为外部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="c96a1-157">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c96a1-158">从定义记录的区域中假定域名, 因此不需要将其作为 A 记录的一部分输入。</span><span class="sxs-lookup"><span data-stu-id="c96a1-158">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="c96a1-159">在 " **Ip 地址**" 中, 键入 IP 地址, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c96a1-159">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="c96a1-160">对于内部 DNS 记录, 请键入 Director 的内部 Web 服务 IP 地址 (或者, 如果使用负载平衡器, 请键入控制器负载平衡器的虚拟 IP (VIP))。</span><span class="sxs-lookup"><span data-stu-id="c96a1-160">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c96a1-161">如果不使用 Director, 请键入前端服务器或标准版服务器的 IP 地址, 或者, 如果使用负载平衡器, 请键入前端池负载平衡器的 VIP。</span><span class="sxs-lookup"><span data-stu-id="c96a1-161">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="c96a1-162">对于外部 DNS 记录, 请键入反向代理的外部或公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c96a1-162">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="c96a1-163">单击 "**添加主机**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c96a1-163">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="c96a1-164">若要创建另一条记录, 请重复步骤8到步骤10。</span><span class="sxs-lookup"><span data-stu-id="c96a1-164">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c96a1-165">必须在 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建新的 lyncdiscover 和 lyncdiscoverinternal 记录。</span><span class="sxs-lookup"><span data-stu-id="c96a1-165">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="c96a1-166">完成创建 (适用于 IPv6、AAAA) 记录后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="c96a1-166">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

