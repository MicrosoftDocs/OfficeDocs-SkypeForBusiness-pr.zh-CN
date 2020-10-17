---
title: Lync Server 2013：配置 DNS 以实现负载平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831968516ef155d6ad018f33bfa27226f58292dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537139"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="696b2-102">在 Lync Server 2013 中为负载平衡配置 DNS</span><span class="sxs-lookup"><span data-stu-id="696b2-102">Configure DNS for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="696b2-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="696b2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="696b2-104">若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="696b2-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="696b2-105">域名系统 (DNS) 负载平衡将对 Lync Server 2013 所特有的网络流量（如 SIP 流量和媒体流量）进行平衡。</span><span class="sxs-lookup"><span data-stu-id="696b2-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="696b2-106">前端池、边缘池、控制器池和独立的中介池都支持 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="696b2-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="696b2-107">配置为使用 DNS 负载平衡的池必须有两个完全限定的域名 (Fqdn) 定义： DNS 负载平衡使用的常规池 FQDN (例如，pool1.contoso.com) 并解析为池中服务器的物理 Ip 以及池的 Web 服务的另一个 FQDN (例如，web1.contoso.net) ，它将解析为池的虚拟 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="696b2-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="696b2-108">有关 DNS 负载平衡的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md) 。</span><span class="sxs-lookup"><span data-stu-id="696b2-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="696b2-109">要使客户端能够提供 HTTPS 流量，仍然需要硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="696b2-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="696b2-110">使用 DNS 负载平衡之前，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="696b2-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="696b2-111">替代内部 Web 服务池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="696b2-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="696b2-112">如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="696b2-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="696b2-113">创建 DNS A 主机记录以将池 FQDN 解析为池中所有服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="696b2-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="696b2-114">启用 IP 地址随机选择，或启用循环（对于 Windows Server DNS）。</span><span class="sxs-lookup"><span data-stu-id="696b2-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="696b2-115">默认情况下应启用循环。</span><span class="sxs-lookup"><span data-stu-id="696b2-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="696b2-116">覆盖内部 Web 服务 FQDN</span><span class="sxs-lookup"><span data-stu-id="696b2-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="696b2-117">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="696b2-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="696b2-118">在控制台树中，展开 Enterprise Edition 前端池节点。</span><span class="sxs-lookup"><span data-stu-id="696b2-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="696b2-119">右键单击该池，单击“编辑属性”\*\*\*\*，然后单击“Web 服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="696b2-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="696b2-120">在“内部 Web 服务”\*\*\*\* 下面，选中“覆盖 FQDN”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="696b2-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="696b2-121">键入解析为池中服务器的物理 IP 地址的池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="696b2-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="696b2-122">在“外部 Web 服务”\*\*\*\* 下面，键入解析为池的虚拟 IP 地址的外部池 FQDN，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="696b2-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="696b2-123">在控制台树中，单击 " **Lync Server 2013**"，然后在 " **操作** " 窗格中，单击 " **发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="696b2-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="696b2-124">为所有内部池服务器创建 DNS 主机 (A) 记录</span><span class="sxs-lookup"><span data-stu-id="696b2-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="696b2-125">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="696b2-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="696b2-126">在“DNS 管理器”\*\*\*\* 中，单击管理记录的 DNS 服务器以将其展开。</span><span class="sxs-lookup"><span data-stu-id="696b2-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="696b2-127">单击“正向查找区域”\*\*\*\* 以将其展开。</span><span class="sxs-lookup"><span data-stu-id="696b2-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="696b2-128">右键单击要向其中添加记录的 DNS 域，然后单击“新主机 (A 或 AAAA)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="696b2-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="696b2-129">在 " **名称** " 框中，键入主机记录的名称 (域名将自动追加) 。</span><span class="sxs-lookup"><span data-stu-id="696b2-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="696b2-130">在 IP 地址框中，键入单个前端服务器的 IP 地址，然后选择“创建关联的指针 (PTR) 记录”\*\*\*\* 或“允许所有经过身份验证的用户使用同一所有者名称更新 DNS 记录”\*\*\*\*（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="696b2-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="696b2-131">继续为将参与 DNS 负载平衡的所有成员前端服务器创建记录。</span><span class="sxs-lookup"><span data-stu-id="696b2-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="696b2-132">例如，如果已有一个名为 pool1.contoso.com 的池和三个前端服务器，则需创建以下 DNS 条目：</span><span class="sxs-lookup"><span data-stu-id="696b2-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="696b2-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="696b2-133">FQDN</span></span></th>
    <th><span data-ttu-id="696b2-134">类型</span><span class="sxs-lookup"><span data-stu-id="696b2-134">Type</span></span></th>
    <th><span data-ttu-id="696b2-135">Data</span><span class="sxs-lookup"><span data-stu-id="696b2-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="696b2-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="696b2-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="696b2-137">主机 (A)</span><span class="sxs-lookup"><span data-stu-id="696b2-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="696b2-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="696b2-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="696b2-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="696b2-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="696b2-140">主机 (A)</span><span class="sxs-lookup"><span data-stu-id="696b2-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="696b2-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="696b2-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="696b2-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="696b2-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="696b2-143">主机 (A)</span><span class="sxs-lookup"><span data-stu-id="696b2-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="696b2-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="696b2-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="696b2-145">有关创建) 记录 (DNS 主机的详细信息，请参阅 [CONFIGURE DNS host 记录 For Lync Server 2013](lync-server-2013-configure-dns-host-records.md)。</span><span class="sxs-lookup"><span data-stu-id="696b2-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="696b2-146">为 Windows Server 启用循环</span><span class="sxs-lookup"><span data-stu-id="696b2-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="696b2-147">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="696b2-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="696b2-148">展开“DNS”\*\*\*\*，右键单击要配置的 DNS 服务器，然后单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="696b2-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="696b2-149">单击“高级”\*\*\*\* 选项卡，选择“启用循环”\*\*\*\* 和“启用网络掩码排序”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="696b2-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="696b2-150">!["DNS 轮循机制" 对话框](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg ""DNS 轮循机制" 对话框")</span><span class="sxs-lookup"><span data-stu-id="696b2-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="696b2-151">默认情况下应启用此功能。</span><span class="sxs-lookup"><span data-stu-id="696b2-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="696b2-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="696b2-152">See Also</span></span>


[<span data-ttu-id="696b2-153">Lync Server 2013 中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="696b2-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

