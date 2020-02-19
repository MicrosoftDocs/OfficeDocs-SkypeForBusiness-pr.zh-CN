---
title: Lync Server 2013：为边缘支持配置 DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a76edebaf0b7ed1592ca398a802f4c638374f41f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="e142f-102">在 Lync Server 2013 中为边缘支持配置 DNS</span><span class="sxs-lookup"><span data-stu-id="e142f-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e142f-103">_**上次修改的主题：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="e142f-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="e142f-104">您必须为内部边缘接口和外部边缘接口配置域名系统 (DNS) 记录，同时包括边缘服务器和反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="e142f-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="e142f-105">默认情况下，边缘服务器未加入域，并且不具有完全限定的域名（完全限定的域名称）。</span><span class="sxs-lookup"><span data-stu-id="e142f-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="e142f-106">边缘服务器仅由短（计算机）名称引用，而不是由完全限定的域名引用。</span><span class="sxs-lookup"><span data-stu-id="e142f-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="e142f-107">但是，拓扑生成器使用 Fqdn 而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="e142f-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="e142f-108">边缘服务器的名称必须与拓扑生成器使用的 FQDN 相匹配。</span><span class="sxs-lookup"><span data-stu-id="e142f-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="e142f-109">为此，请定义一个 DNS 后缀，如果与计算机名称结合使用，则会生成预期的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e142f-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="e142f-110">使用下面的 "将 DNS 后缀添加到计算机名称和未加入域的边缘服务器" 中的过程将 DNS 后缀添加到计算机名称中。</span><span class="sxs-lookup"><span data-stu-id="e142f-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e142f-111">默认情况下，DNS 使用循环法算法来旋转查询应答中返回的资源记录数据的顺序，其中，对于所查询的 DNS 域名而言，存在多个相同类型的资源记录。</span><span class="sxs-lookup"><span data-stu-id="e142f-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="e142f-112">Lync Server 2013 DNS 负载平衡因 dns 负载平衡机制的一部分而被视为 dns 循环。</span><span class="sxs-lookup"><span data-stu-id="e142f-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="e142f-113">验证是否未禁用循环设置。</span><span class="sxs-lookup"><span data-stu-id="e142f-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="e142f-114">如果使用的是未运行 Windows 操作系统的 DNS 服务器，请验证是否已启用循环资源记录排序。</span><span class="sxs-lookup"><span data-stu-id="e142f-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="e142f-115">使用 "**创建 DNS srv 记录**" 中的以下过程创建并验证每个 DNS srv 记录。</span><span class="sxs-lookup"><span data-stu-id="e142f-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="e142f-116">使用 "**创建 DNS a 记录**" 中的过程定义外部用户访问所需的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="e142f-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="e142f-117">若要确认记录已配置并正常运行，请参阅本主题中的 "**验证 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="e142f-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="e142f-118">有关支持外部用户访问所需的每条记录的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e142f-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="e142f-119">向未加入域的边缘服务器上的计算机名称添加 DNS 后缀</span><span class="sxs-lookup"><span data-stu-id="e142f-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="e142f-120">在计算机上，单击 **“开始”**，右键单击 **“计算机”**，然后单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="e142f-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="e142f-121">在 **“计算机名称、域和工作组设置”** 下，单击 **“更改设置”**。</span><span class="sxs-lookup"><span data-stu-id="e142f-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="e142f-122">在 **“计算机名称”** 选项卡上，单击 **“更改”**。</span><span class="sxs-lookup"><span data-stu-id="e142f-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="e142f-123">在 **“计算机名称/域更改”** 中，单击 **“更多”**。</span><span class="sxs-lookup"><span data-stu-id="e142f-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="e142f-124">在 **“DNS 后缀和 NetBIOS 计算机名称”** 的 **“此计算机的主 DNS 后缀”** 中，键入内部域的名称（例如，corp.contoso.com），然后单击 **“确定”** 三次。</span><span class="sxs-lookup"><span data-stu-id="e142f-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="e142f-125">重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="e142f-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="e142f-126">创建 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="e142f-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="e142f-127">在相应的 DNS 服务器上，依次单击 **“开始”**、**“控制面板”**、**“管理工具”**，然后单击 **“DNS”**。</span><span class="sxs-lookup"><span data-stu-id="e142f-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e142f-128">您需要为远程用户和联盟伙伴配置 DNS，以便有：1）外部 DNS 查找的外部 DNS 条目;2）外围网络（也称为 DMZ、隔离区域和屏蔽子网）中的边缘服务器使用的用于 DNS 查找的条目，包括运行 Lync Server 2013 的内部服务器的记录;和3）内部 DNS 条目，用于由运行 Lync Server 2013 的内部客户端和服务器进行查找。</span><span class="sxs-lookup"><span data-stu-id="e142f-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="e142f-129">在您的 SIP 域的控制台树中，展开 "**正向查找区域**"，然后右键单击安装了 Lync Server 2013 的域。</span><span class="sxs-lookup"><span data-stu-id="e142f-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="e142f-130">单击 **“其他新记录”**。</span><span class="sxs-lookup"><span data-stu-id="e142f-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="e142f-131">在 **“选择资源记录类型”** 中，键入 **“服务位置 (SRV)”**，然后单击 **“创建记录”**。</span><span class="sxs-lookup"><span data-stu-id="e142f-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="e142f-132">提供所有所需的 DNS SRV 记录的信息。</span><span class="sxs-lookup"><span data-stu-id="e142f-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="e142f-133">创建 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="e142f-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="e142f-134">在 DNS 服务器上，依次单击 **“开始”**、**“控制面板”**、**“管理工具”**，然后单击 **“DNS”**。</span><span class="sxs-lookup"><span data-stu-id="e142f-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="e142f-135">在您的 SIP 域的控制台树中，展开 "**正向查找区域**"，然后右键单击安装了 Lync Server 2013 的域。</span><span class="sxs-lookup"><span data-stu-id="e142f-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="e142f-136">单击 **“新建主机 (A)”**。</span><span class="sxs-lookup"><span data-stu-id="e142f-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="e142f-137">提供所有所需的 DNS SRV 记录的信息。</span><span class="sxs-lookup"><span data-stu-id="e142f-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="e142f-138">验证 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="e142f-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="e142f-139">登录到域中的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="e142f-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="e142f-140">单击“开始”\*\*\*\*，再单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e142f-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="e142f-141">在命令提示符下，运行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e142f-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="e142f-142">验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。</span><span class="sxs-lookup"><span data-stu-id="e142f-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e142f-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e142f-143">See Also</span></span>


[<span data-ttu-id="e142f-144">创建 DNS SRV 记录以与托管 Exchange UM 集成</span><span class="sxs-lookup"><span data-stu-id="e142f-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="e142f-145">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="e142f-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

