---
title: Lync Server 2013：创建并验证 DNS SRV 记录
description: Lync Server 2013：创建并验证 DNS SRV 记录。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a71c876d0b26b9305feed7146fa6321a3983588d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562378"
---
# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="f5999-103">在 Lync Server 2013 中创建和验证 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="f5999-103">Create and verify DNS SRV records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5999-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f5999-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f5999-105">若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="f5999-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="f5999-106">本主题介绍如何在 Lync Server 2013 部署中配置域名系统 (DNS) 记录，以及自动客户端登录所需的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="f5999-106">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="f5999-107">创建前端池时，安装程序将为池创建 Active Directory 对象和设置，包括池完全限定的域名 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="f5999-107">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="f5999-108">将为 Standard Edition server 创建类似的对象和设置。</span><span class="sxs-lookup"><span data-stu-id="f5999-108">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="f5999-109">若要使客户端能够连接到池或 Standard Edition 服务器，则必须在 DNS 中注册池或 Standard Edition 服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f5999-109">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="f5999-110">必须在内部 DNS 中为每个 SIP 域创建 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="f5999-110">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="f5999-111">此过程假定内部 DNS 具有 SIP 用户域的区域。</span><span class="sxs-lookup"><span data-stu-id="f5999-111">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="f5999-112">配置 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="f5999-112">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="f5999-113">在 DNS 服务器上，单击“开始”\*\*\*\*，再单击“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-113">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f5999-114">在您的 SIP 域的控制台树中，展开 " **正向查找区域**"，然后右键单击将在其中安装 Lync Server 2013 的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="f5999-114">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="f5999-115">单击“其他新记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-115">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="f5999-116">在“选择资源记录类型”\*\*\*\* 中，单击“服务位置(SRV)”\*\*\*\*，然后单击“创建记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-116">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="f5999-117">单击 "**服务**"，然后键入\*\* \_ sipinternaltls\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-117">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="f5999-118">单击 "**协议**"，然后键入\*\* \_ tcp\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-118">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="f5999-119">单击“端口号”\*\*\*\*，再键入“5061”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-119">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="f5999-120">单击 " **主机提供此服务**"，然后键入 Pool 或 Standard Edition SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f5999-120">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="f5999-121">单击“确定”\*\*\*\*，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="f5999-122">验证 DNS SRV 记录的创建</span><span class="sxs-lookup"><span data-stu-id="f5999-122">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="f5999-123">使用属于 Authenticated Users 组成员的帐户或具有等效权限的帐户登录到域中的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="f5999-123">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="f5999-124">单击“开始”\*\*\*\*，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="f5999-125">在“打开”\*\*\*\* 框中，键入 **cmd**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-125">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="f5999-126">在命令提示符处键入 **nslookup**，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="f5999-126">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="f5999-127">键入 **set type=srv**，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="f5999-127">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="f5999-128">键入\*\* \_ sipinternaltls。 \_tcp.contoso.com\*\*，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="f5999-128">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="f5999-129">输出的传输层安全性 (TLS) 记录如下所示：</span><span class="sxs-lookup"><span data-stu-id="f5999-129">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="f5999-130">服务器： \<dns server\> contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5999-130">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="f5999-131">处理 \<IP address of DNS server\></span><span class="sxs-lookup"><span data-stu-id="f5999-131">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="f5999-132">Non-authoritative answer:</span><span class="sxs-lookup"><span data-stu-id="f5999-132">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="f5999-133">\_sipinternaltls。 \_tcp.contoso.com SRV 服务位置：</span><span class="sxs-lookup"><span data-stu-id="f5999-133">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="f5999-134">优先级 = 0</span><span class="sxs-lookup"><span data-stu-id="f5999-134">priority = 0</span></span>
    
    <span data-ttu-id="f5999-135">权重 = 0</span><span class="sxs-lookup"><span data-stu-id="f5999-135">weight = 0</span></span>
    
    <span data-ttu-id="f5999-136">端口 = 5061</span><span class="sxs-lookup"><span data-stu-id="f5999-136">port = 5061</span></span>
    
    <span data-ttu-id="f5999-137">svr hostname = poolname.contoso.com (或 Standard Edition server A record) </span><span class="sxs-lookup"><span data-stu-id="f5999-137">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="f5999-138">poolname.contoso.com internet 地址 = \<virtual IP Address of the load balancer\> 或 \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> 或 \<IP address of the Standard Edition server\></span><span class="sxs-lookup"><span data-stu-id="f5999-138">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="f5999-139">完成后，在命令提示符处键入 **exit**，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="f5999-139">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="f5999-140">验证是否可以解析前端池或 Standard Edition Server 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="f5999-140">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="f5999-141">登录到域中的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="f5999-141">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="f5999-142">单击“开始”\*\*\*\*，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-142">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="f5999-143">在“打开”\*\*\*\* 框中，键入 **cmd**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5999-143">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="f5999-144">在命令提示符处，键入 **nslookup** \<FQDN of the Front End pool\> 或 \<FQDN of the Standard Edition server\> ，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="f5999-144">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="f5999-145">验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。</span><span class="sxs-lookup"><span data-stu-id="f5999-145">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

