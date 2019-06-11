---
title: Lync Server 2013：创建并验证 DNS SRV 记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a539b58abbad323aaf7c7343b40eabb49d04d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="83173-102">在 Lync Server 2013 中创建并验证 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="83173-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83173-103">_**主题上次修改时间:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="83173-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="83173-104">若要成功完成此过程, 你应至少作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="83173-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="83173-105">本主题介绍了如何配置您需要在 Lync Server 2013 部署中创建的域名系统 (DNS) 记录以及自动客户端登录所需的域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="83173-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="83173-106">创建前端池时, 安装程序将为池创建 Active Directory 对象和设置, 包括池完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="83173-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="83173-107">为标准版服务器创建类似的对象和设置。</span><span class="sxs-lookup"><span data-stu-id="83173-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="83173-108">对于能够连接到池或标准版服务器的客户端, 必须在 DNS 中注册池或标准版服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="83173-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="83173-109">必须在每个 SIP 域的内部 DNS 中创建 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="83173-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="83173-110">此过程假定你的内部 DNS 具有适用于你的 SIP 用户域的区域。</span><span class="sxs-lookup"><span data-stu-id="83173-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="83173-111">配置 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="83173-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="83173-112">在 DNS 服务器上, 单击 "**开始**", 单击 "**管理工具**", 然后单击 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="83173-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="83173-113">在 SIP 域的控制台树中, 展开 "**正向查找区域**", 然后右键单击将在其中安装 Lync Server 2013 的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="83173-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="83173-114">单击 "**其他新记录**"。</span><span class="sxs-lookup"><span data-stu-id="83173-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="83173-115">在 "**选择资源记录类型**" 中, 单击 "**服务位置 (SRV)**", 然后单击 "**创建记录**"。</span><span class="sxs-lookup"><span data-stu-id="83173-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="83173-116">单击 "**服务**", 然后\*\* \_\*\* 键入 "sipinternaltls"。</span><span class="sxs-lookup"><span data-stu-id="83173-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="83173-117">单击 "**协议**", 然后\*\* \_\*\* 键入 "tcp"。</span><span class="sxs-lookup"><span data-stu-id="83173-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="83173-118">单击 "**端口号**", 然后键入**5061**。</span><span class="sxs-lookup"><span data-stu-id="83173-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="83173-119">单击 "**主机提供此服务**", 然后键入池或标准版服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="83173-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="83173-120">单击 **"确定**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="83173-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="83173-121">验证 DNS SRV 记录的创建</span><span class="sxs-lookup"><span data-stu-id="83173-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="83173-122">使用已验证用户组的成员的帐户登录到域中的客户端计算机或具有同等权限。</span><span class="sxs-lookup"><span data-stu-id="83173-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="83173-123">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="83173-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="83173-124">在 "**打开**" 框中, 键入**cmd**, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="83173-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="83173-125">在命令提示符处, 键入**nslookup**, 然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="83173-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="83173-126">键入 " **set type = srv**", 然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="83173-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="83173-127">键入\*\* \_sipinternaltls。\_tcp.contoso.com\*\*, 然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="83173-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="83173-128">为传输层安全 (TLS) 记录显示的输出如下所示:</span><span class="sxs-lookup"><span data-stu-id="83173-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="83173-129">服务器: \<dns 服务器\>contoso.com</span><span class="sxs-lookup"><span data-stu-id="83173-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="83173-130">地址: \<DNS 服务器的 IP 地址\></span><span class="sxs-lookup"><span data-stu-id="83173-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="83173-131">非权威应答:</span><span class="sxs-lookup"><span data-stu-id="83173-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="83173-132">\_sipinternaltls.\_tcp.contoso.com SRV 服务位置:</span><span class="sxs-lookup"><span data-stu-id="83173-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="83173-133">优先级 = 0</span><span class="sxs-lookup"><span data-stu-id="83173-133">priority = 0</span></span>
    
    <span data-ttu-id="83173-134">权重 = 0</span><span class="sxs-lookup"><span data-stu-id="83173-134">weight = 0</span></span>
    
    <span data-ttu-id="83173-135">端口 = 5061</span><span class="sxs-lookup"><span data-stu-id="83173-135">port = 5061</span></span>
    
    <span data-ttu-id="83173-136">svr hostname = poolname.contoso.com (或标准版服务器 A 记录)</span><span class="sxs-lookup"><span data-stu-id="83173-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="83173-137">poolname.contoso.com internet 地址 = \<单个企业版服务器的负载平衡\>器\<或 ip 地址的虚拟 IP 地址, 其中仅有一个企业版服务器\>或\<标准的 ip 地址Edition 服务器\></span><span class="sxs-lookup"><span data-stu-id="83173-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="83173-138">完成后, 在命令提示符处键入 "**退出**", 然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="83173-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="83173-139">验证是否可以解析前端池或标准版服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="83173-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="83173-140">登录到域中的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="83173-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="83173-141">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="83173-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="83173-142">在 "**打开**" 框中, 键入**cmd**, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="83173-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="83173-143">在命令提示符处, 键入 " **nslookup** \<FQDN" (标准版\>服务器\<\>的前端池或 fqdn), 然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="83173-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="83173-144">验证您是否收到了解析为 FQDN 的相应 IP 地址的答复。</span><span class="sxs-lookup"><span data-stu-id="83173-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

