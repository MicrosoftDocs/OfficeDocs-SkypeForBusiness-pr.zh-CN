---
title: Lync Server 2013：配置 DNS 以实现负载平衡
description: Lync Server 2013：配置 DNS 以实现负载平衡。
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
ms.openlocfilehash: 4b13db22d65ee67723ebc0a31544137d467d5c6b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553448"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="e73ff-103">在 Lync Server 2013 中为负载平衡配置 DNS</span><span class="sxs-lookup"><span data-stu-id="e73ff-103">Configure DNS for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e73ff-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e73ff-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e73ff-105">若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="e73ff-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="e73ff-106">域名系统 (DNS) 负载平衡将对 Lync Server 2013 所特有的网络流量（如 SIP 流量和媒体流量）进行平衡。</span><span class="sxs-lookup"><span data-stu-id="e73ff-106">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="e73ff-107">前端池、边缘池、控制器池和独立的中介池都支持 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="e73ff-107">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="e73ff-108">配置为使用 DNS 负载平衡的池必须有两个完全限定的域名 (Fqdn) 定义： DNS 负载平衡使用的常规池 FQDN (例如，pool1.contoso.com) 并解析为池中服务器的物理 Ip 以及池的 Web 服务的另一个 FQDN (例如，web1.contoso.net) ，它将解析为池的虚拟 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e73ff-108">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="e73ff-109">有关 DNS 负载平衡的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md) 。</span><span class="sxs-lookup"><span data-stu-id="e73ff-109">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e73ff-110">要使客户端能够提供 HTTPS 流量，仍然需要硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="e73ff-110">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="e73ff-111">使用 DNS 负载平衡之前，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e73ff-111">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="e73ff-112">替代内部 Web 服务池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e73ff-112">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e73ff-113">如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e73ff-113">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="e73ff-114">创建 DNS A 主机记录以将池 FQDN 解析为池中所有服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e73ff-114">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="e73ff-115">启用 IP 地址随机选择，或启用循环（对于 Windows Server DNS）。</span><span class="sxs-lookup"><span data-stu-id="e73ff-115">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e73ff-116">默认情况下应启用循环。</span><span class="sxs-lookup"><span data-stu-id="e73ff-116">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="e73ff-117">覆盖内部 Web 服务 FQDN</span><span class="sxs-lookup"><span data-stu-id="e73ff-117">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="e73ff-118">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="e73ff-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e73ff-119">在控制台树中，展开 Enterprise Edition 前端池节点。</span><span class="sxs-lookup"><span data-stu-id="e73ff-119">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="e73ff-120">右键单击该池，单击“编辑属性”\*\*\*\*，然后单击“Web 服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e73ff-120">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="e73ff-121">在“内部 Web 服务”\*\*\*\* 下面，选中“覆盖 FQDN”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="e73ff-121">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="e73ff-122">键入解析为池中服务器的物理 IP 地址的池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e73ff-122">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="e73ff-123">在“外部 Web 服务”\*\*\*\* 下面，键入解析为池的虚拟 IP 地址的外部池 FQDN，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e73ff-123">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="e73ff-124">在控制台树中，单击 " **Lync Server 2013**"，然后在 " **操作** " 窗格中，单击 " **发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="e73ff-124">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="e73ff-125">为所有内部池服务器创建 DNS 主机 (A) 记录</span><span class="sxs-lookup"><span data-stu-id="e73ff-125">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="e73ff-126">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e73ff-126">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="e73ff-127">在“DNS 管理器”\*\*\*\* 中，单击管理记录的 DNS 服务器以将其展开。</span><span class="sxs-lookup"><span data-stu-id="e73ff-127">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="e73ff-128">单击“正向查找区域”\*\*\*\* 以将其展开。</span><span class="sxs-lookup"><span data-stu-id="e73ff-128">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="e73ff-129">右键单击要向其中添加记录的 DNS 域，然后单击“新主机 (A 或 AAAA)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e73ff-129">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="e73ff-130">在 " **名称** " 框中，键入主机记录的名称 (域名将自动追加) 。</span><span class="sxs-lookup"><span data-stu-id="e73ff-130">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="e73ff-131">在 IP 地址框中，键入单个前端服务器的 IP 地址，然后选择“创建关联的指针 (PTR) 记录”\*\*\*\* 或“允许所有经过身份验证的用户使用同一所有者名称更新 DNS 记录”\*\*\*\*（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="e73ff-131">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="e73ff-132">继续为将参与 DNS 负载平衡的所有成员前端服务器创建记录。</span><span class="sxs-lookup"><span data-stu-id="e73ff-132">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="e73ff-133">例如，如果已有一个名为 pool1.contoso.com 的池和三个前端服务器，则需创建以下 DNS 条目：</span><span class="sxs-lookup"><span data-stu-id="e73ff-133">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="e73ff-134">FQDN</span><span class="sxs-lookup"><span data-stu-id="e73ff-134">FQDN</span></span></th>
    <th><span data-ttu-id="e73ff-135">类型</span><span class="sxs-lookup"><span data-stu-id="e73ff-135">Type</span></span></th>
    <th><span data-ttu-id="e73ff-136">Data</span><span class="sxs-lookup"><span data-stu-id="e73ff-136">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="e73ff-137">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e73ff-137">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="e73ff-138">主机 (A)</span><span class="sxs-lookup"><span data-stu-id="e73ff-138">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="e73ff-139">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="e73ff-139">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e73ff-140">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e73ff-140">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="e73ff-141">主机 (A)</span><span class="sxs-lookup"><span data-stu-id="e73ff-141">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="e73ff-142">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="e73ff-142">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e73ff-143">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e73ff-143">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="e73ff-144">主机 (A)</span><span class="sxs-lookup"><span data-stu-id="e73ff-144">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="e73ff-145">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="e73ff-145">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="e73ff-146">有关创建) 记录 (DNS 主机的详细信息，请参阅 [CONFIGURE DNS host 记录 For Lync Server 2013](lync-server-2013-configure-dns-host-records.md)。</span><span class="sxs-lookup"><span data-stu-id="e73ff-146">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="e73ff-147">为 Windows Server 启用循环</span><span class="sxs-lookup"><span data-stu-id="e73ff-147">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="e73ff-148">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e73ff-148">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="e73ff-149">展开“DNS”\*\*\*\*，右键单击要配置的 DNS 服务器，然后单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e73ff-149">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="e73ff-150">单击“高级”\*\*\*\* 选项卡，选择“启用循环”\*\*\*\* 和“启用网络掩码排序”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e73ff-150">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="e73ff-151">!["DNS 轮循机制" 对话框](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg ""DNS 轮循机制" 对话框")</span><span class="sxs-lookup"><span data-stu-id="e73ff-151">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e73ff-152">默认情况下应启用此功能。</span><span class="sxs-lookup"><span data-stu-id="e73ff-152">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e73ff-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e73ff-153">See Also</span></span>


[<span data-ttu-id="e73ff-154">Lync Server 2013 中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="e73ff-154">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

